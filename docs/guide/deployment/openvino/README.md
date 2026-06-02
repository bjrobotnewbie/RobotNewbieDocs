# OpenVINO
Intel 开源的边缘 AI 推理优化工具包，专为工业机器人和边缘计算场景设计。

## 简介
OpenVINO（Open Visual Inference and Neural Network Optimization）是 Intel 推出的**端到端深度学习推理加速工具套件**，主打**模型部署、推理优化、跨硬件统一调度**，覆盖从终端边缘设备、工业终端到云端服务器全场景，尤其适用于机器视觉、工业自动化、机器人感知、智能安防等落地场景。

它核心解决深度学习模型**部署难、推理慢、硬件适配杂**三大问题，无需大幅修改原有模型代码，即可完成模型转换、压缩、加速与部署，是Intel生态下边缘AI落地的主流方案。

**官方资源：**
- [GitHub 仓库](https://github.com/openvinotoolkit/openvino)
- [官方文档](https://docs.openvino.ai/)
- [预训练模型库 Open Model Zoo](https://github.com/openvinotoolkit/open_model_zoo)
- [OpenVINO 社区示例](https://github.com/openvinotoolkit/openvino_samples)

## 核心特性
### 🖥️ 广泛硬件支持
统一推理API，一套代码无缝运行在Intel全系硬件，同时兼容部分第三方硬件：
- **Intel CPU**：Atom、Celeron、Pentium、酷睿系列、Xeon 服务器CPU，支持多核并行、指令集深度优化
- **集成 GPU**：UHD Graphics、Iris Xe、Arc 独立显卡，支持GPU硬件并行推理
- **VPU（视觉处理单元）**：Myriad X、Keem Bay 边缘加速棒/模组，低功耗高算力，适合嵌入式机器人
- **FPGA**：Arria 10、Stratix 10，面向高可靠、低延迟工业场景
- 扩展支持：部分第三方GPU、NPU（通过插件拓展）

### 🔧 全链路优化工具链
覆盖**模型转换 → 压缩优化 → 部署推理 → 性能测评**全流程：
- **模型优化器 (Model Optimizer)**：主流框架模型一键转换为OpenVINO专属IR中间格式（`.xml` + `.bin`），支持 TensorFlow、PyTorch、ONNX、PaddlePaddle、Caffe、MXNet
- **训练后优化**：INT8/FP16 量化、层融合、常量折叠、算子剪枝，大幅降低算力与内存占用
- **NNCF**：Intel 神经网络压缩框架，支持量化、稀疏化、模型蒸馏、混合精度，兼顾精度与推理速度
- **基准测试工具 (Benchmark App)**：自动化吞吐量、延迟、帧率、资源占用测试，快速评估硬件性能
- **前后处理流水线 (PrePostProcessor)**：原生集成图像缩放、归一化、色域转换、维度变换，替代OpenCV等手动预处理，进一步提速

### 🧩 生态与场景适配
- 原生支持 **ROS/ROS2**，深度适配机器人开发生态
- 兼容 RealSense 深度相机、工业相机等视觉硬件，机器人视觉开发一站式打通
- 支持动态输入尺寸、异步推理、多流推理，适配工业高并发场景
- 跨操作系统：Windows、Linux、Ubuntu、嵌入式Linux（Yocto）全平台兼容

## 核心概念补充
1. **IR 模型格式**
OpenVINO 标准部署格式，由两个文件组成：
- `.xml`：网络拓扑、算子、层结构描述
- `.bin`：模型权重、偏置等二进制参数
由模型优化器转换生成，是推理阶段的标准输入。

2. **同步 / 异步推理**
- 同步推理：调用后阻塞等待结果，简单易用，适合低并发场景
- 异步推理：非阻塞调用，后台执行推理，主线程可并行处理业务逻辑，**工业机器人、高帧率视觉场景首选**

## 快速开始（基础版）
### 1. 环境安装
```bash
# pip 安装（推荐 Python 开发）
pip install openvino
```

### 2. 基础推理代码（同步）
```python
from openvino.runtime import Core

# 1. 初始化推理核心
ie = Core()

# 2. 读取 IR 模型 (.xml + .bin)
model = ie.read_model("model.xml")

# 3. 编译模型（指定硬件：CPU/GPU/VPU）
compiled_model = ie.compile_model(model, "CPU")

# 4. 创建推理请求并执行推理
infer_request = compiled_model.create_infer_request()
# inputs 为预处理完成的图像/张量数据
result = infer_request.infer(inputs)
```

### 3. 异步推理（机器人高并发推荐）
```python
from openvino.runtime import Core

ie = Core()
model = ie.read_model("model.xml")
compiled_model = ie.compile_model(model, "CPU")
infer_request = compiled_model.create_infer_request()

# 设置推理完成回调函数
def callback(request, user_data):
    res = request.results
    print("推理完成", res)

infer_request.set_callback(callback)
# 异步提交推理，主线程不阻塞
infer_request.start_async(inputs)
# 等待所有推理结束（可选）
infer_request.wait()
```

## 工业机器人部署（进阶）
针对**机器人视觉、关节控制、感知推理**场景，搭配预处理、精度、性能策略优化：
```python
from openvino.runtime import Core
from openvino.preprocess import PrePostProcessor, ResizeAlgorithm

ie = Core()
model = ie.read_model("robot_perception.xml")

# 1. 配置前后处理流水线（硬件级加速预处理）
ppp = PrePostProcessor(model)
# 设置输入数据布局、缩放、数据类型
ppp.input().tensor().set_layout("NCHW")
ppp.input().preprocess().resize(ResizeAlgorithm.RESIZE_LINEAR)
# 构建优化后模型
model = ppp.build()

# 2. 编译模型 + 硬件策略配置
compiled_model = ie.compile_model(
    model,
    device_name="GPU",  # 指定推理硬件
    config={
        "PERFORMANCE_HINT": "LATENCY",       # 优先低延迟（机器人实时控制必备）
        "INFERENCE_PRECISION_HINT": "f16",   # 使用FP16混合精度，提速减显存
        "NUM_THREADS": "8"                   # 绑定CPU线程数
    }
)

# 执行推理
infer_req = compiled_model.create_infer_request()
output = infer_req.infer(inputs)
```

### 工业场景常用配置说明
- `PERFORMANCE_HINT=LATENCY`：优先单帧低延迟，适用于机器人实时感知、运动控制
- `PERFORMANCE_HINT=THROUGHPUT`：优先吞吐率，适用于多相机、多任务并发检测
- `INFERENCE_PRECISION_HINT=INT8`：极致压缩提速，配合NNCF量化使用

## 性能对比（Intel i7-13700H）
测试环境：OpenVINO 最新版本，默认硬件优化，输入尺寸标准模型尺寸

| 模型 | 精度 | 延迟 (ms) | FPS | 适用场景 |
|------|------|-----------|-----|----------|
| YOLOv8n | FP16 | 5.2 | 192 | 嵌入式机器人、移动端实时检测 |
| YOLOv8s | FP16 | 12.1 | 83 | 工业视觉、常规目标检测 |
| PointPillars | FP16 | 18.5 | 54 | 激光雷达3D感知、自动驾驶机器人 |

## 模型转换示例（Model Optimizer）
将 PyTorch/ONNX 模型转为 OpenVINO IR 格式，命令行示例：
```bash
# ONNX 模型转 IR
mo --input_model model.onnx --output_dir ./ir_model

# PyTorch 导出 ONNX 后再转换，或直接转换
mo --input_model model.pt --input_shape [1,3,640,640]
```

## 参考资料 & 拓展链接
### 官方文档与工具
- [OpenVINO 主站文档](https://docs.openvino.ai/)
- [Open Model Zoo 预训练模型与Demo](https://github.com/openvinotoolkit/open_model_zoo)
- [NNCF 模型量化压缩框架](https://github.com/openvinotoolkit/nncf)
- [Benchmark 性能测试工具使用指南](https://docs.openvino.ai/2026/get-started/learn-openvino/openvino-samples/benchmark-tool.html)

### 机器人 & 视觉集成
- [ROS 2 + OpenVINO 集成方案](https://intel.github.io/robot_devkit_doc/pages/vino.html)
- [Intel RealSense + ROS2 视觉驱动](https://github.com/IntelRealSense/realsense-ros)
- 机器人 + 视觉obot 机械臂obot 机械臂 + Anomalib 缺陷检测，官方教程）：
  [https://www.intel.com/content/www/us/en/developer/articles/training/defect-detection-with-anomalib.html)
- [机器人视觉预处理最佳实践](https://docs.openvino.ai/2026/openvino-workflow/running-inference/optimize-inference/optimize-preprocessing.html)

### 实战案例 & 教程
- [OpenVINO 官方示例工程](https://docs.openvino.ai/2026/get-started/learn-openvino/openvino-samples/get-started-demos.html)
- [机器人 AI 套件（含部署教程、ROS2、YOLOv8）](https://docs.openedgeplatform.intel.com/dev/edge-ai-suites/robotics-ai-suite/embodied/developer_tools_tutorials/openvino.html)
- [ROS2 + OpenVINO 实战（YOLOv8 机器人视觉）](https://docs.openedgeplatform.intel.com/edge-ai-suites/robotics-ai-suite/main/robotics/dev_guide/tutorials_amr/perception/openvino/yolov8_openvino_tutorial.html)
- [后训练量化（含 Accuracy-Aware 实战）](https://docs.openvino.ai/2026/openvino-workflow/model-optimization-guide/quantizing-models-post-training.html)


## 适用场景总结
1. **工业机器人**：视觉检测、3D感知、运动预判、人机交互
2. **边缘视觉设备**：工业相机、智能摄像头、嵌入式终端
3. **车载/移动终端**：低功耗实时AI推理
4. **Intel 硬件集群**：服务器端批量AI推理、数据分析