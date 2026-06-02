# ONNX Runtime

跨平台机器学习推理加速器，支持多种硬件后端，是机器人部署的通用选择。

## 简介

ONNX Runtime 是微软开发的开源推理引擎，支持 ONNX 标准格式，提供跨 CPU、GPU、边缘设备的统一推理接口。

**官方资源：**

- [GitHub 仓库](https://github.com/microsoft/onnxruntime)
- [官方文档](https://onnxruntime.ai/docs/)
- [模型库](https://github.com/onnx/models)

## 核心特性

### 🔄 多后端支持

- **CPU** - Intel MKL, ARM Compute Library
- **GPU** - CUDA, TensorRT, DirectML
- **边缘** - NNAPI, CoreML, Vitis AI
- **Web** - WebGPU, WebAssembly

### ⚡ 优化技术

- **算子融合** - 减少内核启动开销
- **常量折叠** - 预计算常量
- **内存优化** - 张量共享，内存规划
- **量化** - INT8, UINT8, FP16

## 快速开始

```python
import onnxruntime as ort

# 创建会话
session = ort.InferenceSession(
    "model.onnx",
    providers=['CUDAExecutionProvider', 'CPUExecutionProvider']
)

# 推理
outputs = session.run(
    None,
    {"input": input_data}
)
```

## ROS 2 集成

```cpp
#include <onnxruntime_cxx_api.h>

class ONNXInferenceNode : public rclcpp::Node {
public:
  ONNXInferenceNode() : Node("onnx_inference") {
    Ort::SessionOptions session_options;
    session_ = std::make_unique<Ort::Session>(
        env_, "model.onnx", session_options);
  }
private:
  Ort::Env env_{ORT_LOGGING_LEVEL_WARNING, "robot"};
  std::unique_ptr<Ort::Session> session_;
};
```

## 参考资料

- [Python API](https://onnxruntime.ai/docs/api/python/)
- [C++ API](https://onnxruntime.ai/docs/api/c/)
- [量化工具](https://onnxruntime.ai/docs/performance/quantization.html)

