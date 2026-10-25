# ComfyUI_Sonic

Sonic 是一种关于“将焦点转向全身动作捕捉中的全局音频感知”的方法，可在 ComfyUI 中使用。

## 项目链接

- GitHub: <https://github.com/smthemex/ComfyUI_Sonic>

## 项目介绍
ComfyUI_Sonic是基于Sonic方法的ComfyUI自定义节点，核心功能是在人像动画中聚焦全局音频感知，可在ComfyUI环境中实现音频驱动的人像动画生成。本项目为smthemex/ComfyUI_Sonic的下游分支，修复了torch 2.11+cu130版本下的torchcodec ABI不兼容问题，将torchaudio.save替换为soundfile.write。

## 主要特性
1. 修复多项运行错误：解决部分设备必须使用cuda:0的报错、bf16精度错误、12G显存首次加载OOM问题，新增对MAC的MPS设备支持；
2. 优化参数控制：用duration（时长）替代frame number，可控制输出音频的秒数；
3. 兼容非25帧率场景，修复帧率不匹配导致的批次错误；
4. 支持非正方形图像输出，通过image_size参数控制输出图像最小尺寸，OOM时可调小该值；
5. 依赖模型需手动下载，包括Sonic核心模型、whisper-tiny、yoloface_v5m.pt、RIFE光流模型及Stable Video Diffusion（SVD）检查点。
