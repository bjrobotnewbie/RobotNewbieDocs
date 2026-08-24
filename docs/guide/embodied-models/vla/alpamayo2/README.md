# alpamayo2

NVIDIA Alpamayo 2 Super 是一款开源的 34B 参数多任务基础模型，旨在为自动驾驶开发提供强劲动力。

## 项目链接

- GitHub: <https://github.com/NVlabs/alpamayo2>

## 项目概述

## 项目介绍
Alpamayo 2 Super是NVIDIA推出的开源34B参数多任务自动驾驶基础大模型，旨在加速自动驾驶车辆开发。它由32B VLM主干网络和2B扩散专家模块组成，推理流程为先通过VLM主干生成因果链文本，再通过动作专家采样未来行驶轨迹。本仓库提供CLI工具、Notebook和可导入API来运行该模型。

## 主要特性
1.  专为自动驾驶开发设计的多任务基础模型，参数量达34B
2.  结合视觉语言模型与扩散专家模块，支持轨迹预测等自动驾驶核心任务
3.  提供完整的部署、推理工具链，支持CLI、Notebook调用以及API导入
4.  基于Apache 2.0开源协议，可商用修改
5.  依赖Linux系统、NVIDIA GPU与CUDA环境，需提前申请Hugging Face模型与数据集访问权限
