# 安装

## 1. 环境设置

### 作为包安装

您可以将 LeIsaac 作为依赖项安装。以下脚本会配置 IsaacLab、IsaacSim 和所有必需的组件。

```bash
conda create -n leisaac python=3.11
conda activate leisaac

# 安装 cuda-toolkit
conda install -c "nvidia/label/cuda-12.8.1" cuda-toolkit

# 安装 PyTorch（CUDA 12.8 版本）
pip install -U torch==2.7.0 torchvision==0.22.0 --index-url https://download.pytorch.org/whl/cu128

# 安装 LeIsaac 和 IsaacLab/IsaacSim 额外组件
pip install 'leisaac[isaaclab] @ git+https://github.com/LightwheelAI/leisaac.git#subdirectory=source/leisaac' --extra-index-url https://pypi.nvidia.com
```

::::tip
以包方式安装可能会暴露一些边缘情况。如果遇到问题，请在 GitHub 上提交 issue，并考虑切换到下面描述的“从源码安装”工作流。
::::

### 从源码安装

您也可以直接从源码安装以进行本地开发。首先，克隆我们的仓库和相关子模块。

```bash
git clone https://github.com/LightwheelAI/leisaac.git --recursive
```

然后按照 [IsaacLab 官方安装指南](https://isaac-sim.github.io/IsaacLab/main/source/setup/installation/index.html) 安装 IsaacLab。我们建议使用 Conda 以便更轻松地进行环境管理。总之，您只需运行以下命令。

```bash
# 创建并激活环境
conda create -n leisaac python=3.11
conda activate leisaac

# 安装 cuda-toolkit
conda install -c "nvidia/label/cuda-12.8.1" cuda-toolkit

# 安装 PyTorch
pip install -U torch==2.7.0 torchvision==0.22.0 --index-url https://download.pytorch.org/whl/cu128

# 安装 IsaacSim
pip install --upgrade pip
pip install "isaacsim[all,extscache]==5.1.0" --extra-index-url https://pypi.nvidia.com

# 安装 IsaacLab
sudo apt install cmake build-essential

cd leisaac/dependencies/IsaacLab
./isaaclab.sh --install
```

最后，将 leisaac 作为依赖项安装。
```bash
cd ../..
pip install -e source/leisaac
```

::::tip
上述步骤与官方 IsaacLab 文档基本相同；请根据您使用的版本进行调整。以下是 LeIsaac 与 IsaacLab 的兼容性以及相关版本依赖关系。

如果您使用的是 50 系列 GPU，我们建议使用 IsaacSim 5.0+ 和 IsaacLab `v2.2.1+`。我们已在 IsaacSim 5.0 上测试过，可以正常工作。

| 依赖项 | IsaacSim4.5 | IsaaSim5.0 | IsaacSim5.1 |
| ---------- | ----------- | ---------- | ----------- |
| Python     | 3.10        | 3.11       | 3.11        |
| IsaacLab   | v2.1.1      | v2.2.1     | v2.3.0      |
| CUDA       | 11.8        | 12.8       | 12.8        |
| PyTorch    | 2.5.1       | 2.7.0      | 2.7.0       |
::::

### [可选] 安装 Lerobot

我们还提供与 LeRobot 的集成。在某些情况下，您可能需要 lerobot 依赖项，例如用于数据转换、lerobot 数据集录制器、lerobot 模型推理和 envhub 支持。这是可选的；当您需要这些功能时，可以与 leisaac 一起安装 lerobot。

```bash
# 安装带 lerobot 的版本
pip install -e "source/leisaac[lerobot]"

# 固定 numpy 版本
pip install numpy==1.26.0
```

## 2. 资源准备

我们提供了一个示例 USD 资源——厨房场景。请在[此处](https://github.com/LightwheelAI/leisaac/releases/tag/v0.1.0)下载相关场景并将其解压到 `assets` 目录中。目录结构应如下所示：

```
<assets>
├── robots/
│   └── so101_follower.usd
└── scenes/
    └── kitchen_with_orange/
        ├── scene.usd
        ├── assets
        └── objects/
            ├── Orange001
            ├── Orange002
            ├── Orange003
            └── Plate
```

::::info
以下是我们提供的场景下载链接。如需更多高质量场景资源，请访问我们的[官方网站](https://lightwheel.ai/)或 [Releases 页面](https://github.com/LightwheelAI/leisaac/releases)。

| 场景名称 | 描述 | 下载链接 |
|----------------------|------------------------------------|------------------------------------------------------------------------------------------|
| Kitchen with Orange  | 带橙子的示例厨房场景 | [下载](https://github.com/LightwheelAI/leisaac/releases/tag/v0.1.0)                  |
| Lightwheel Toyroom   | 现代房间，有很多玩具 | [下载](https://github.com/LightwheelAI/leisaac/releases/tag/v0.1.1)                  |
| Table with Cube      | 简单桌子，有一个立方体 | [下载](https://github.com/LightwheelAI/leisaac/releases/tag/v0.1.2)                  |
| Lightwheel Bedroom   | 逼真的卧室场景，有布料 | [下载](https://github.com/LightwheelAI/leisaac/releases/tag/v0.2.0)                  |
| Lightwheel Loft      | 大型两层阁楼 | [下载](https://github.com/LightwheelAI/leisaac/releases/tag/v0.3.0)                  |

您还可以从 [huggingface](https://huggingface.co/LightwheelAI/leisaac_env/tree/main) 下载场景；它们应该放在 `assets` 目录中。机器人资源也可以在此仓库中找到并下载。
::::

## 3. 设备设置

我们使用 SO101Leader 作为遥操作设备。请按照[官方文档](https://huggingface.co/docs/lerobot/so101)进行连接和配置。

::::tip
请注意，您不需要使用 LeRobot 仓库进行校准；我们的代码库提供了校准过程的指导步骤。
::::
