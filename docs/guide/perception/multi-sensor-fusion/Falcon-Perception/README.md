# Falcon-Perception

Falcon-Perception和Falcon-OCR模型的推理仓库，是原生多模态、稠密自回归Transformer的早融合模型。

## 项目链接

- GitHub: <https://github.com/tiiuae/Falcon-Perception>

## 项目概述

## 项目介绍
Falcon-Perception是一个轻量、易读且高性能的PyTorch推理仓库，实现了原生多模态、密集型自回归Transformer模型，可基于自然语言查询完成目标检测、实例分割以及OCR任务。项目提供了官方的推理引擎实现，附带Hugging Face模型与数据集资源，同时开放了在线演示 playground。

## 主要特性
1.  支持多模态感知与OCR任务，可通过自然语言指令完成图像内目标框提取、像素级分割、文本/公式/表格提取
2.  提供多种推理引擎：PyTorch分页推理、批量推理，以及适配Apple Silicon的MLX批量推理引擎
3.  附带推理服务部署方案，支持vLLM Docker部署Falcon-OCR服务，同时提供Streamlit交互式演示应用
4.  配套官方预训练模型、测试数据集与在线试用工具，可快速上手体验功能。
