# phyai

PhyAI 是一个高性能框架，用于运行物理 AI 模型（包括 VLA、WAM 及更先进的模型），同时支持云端推理与端侧部署。

## 项目链接

- GitHub: <https://github.com/mingti-org/phyai>
- 项目主页: <https://phyai.mintlify.app/>

## 项目介绍
PhyAI（发音为"phi"）是一款面向Physical AI的低延迟推理引擎，专为交互式系统中的策略、动作模型等延迟敏感型工作负载设计，支持云端部署和边缘设备运行。项目支持VLA、WAM等多种物理AI模型，已适配MiniCPM-Robotic、Pi0、Pi0.5、GR00T N1.7等多款模型，提供官方博客与完整文档支持。

## 主要特性
1.  支持NVIDIA Jetson边缘设备部署，同时可通过DP、TP、CFG并行扩展至GPU集群
2.  集成FlashInfer与Humming的高性能内核，保障推理速度
3.  支持W4A8（NVFP4、MXFP4、INT4）、W8A8、W8A16多种量化格式（部分量化方案待审核）
