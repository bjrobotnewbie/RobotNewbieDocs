# RLark

跨集群具身智能云原生平台。使用 Kubernetes 原生 CRD 管理跨集群具身 AI 工作负载，提供统一的任务调度、跨集群 Pod 网络通信以及多运行时支持。

## 项目链接

- GitHub: <https://github.com/RLinf/RLark>
- 项目主页: <https://rlark.readthedocs.io/en/latest/>
- 中文文档: https://rlark.readthedocs.io/zh-cn/latest/

## 项目介绍
RLark是一款跨集群具身智能云原生平台，基于Kubernetes生态构建，用于管理跨集群具身智能工作负载，支持从云端GPU训练（含RL、LLM场景）到边缘设备部署的全流程，可适配GPU集群、机械臂、传感器、摄像头等异构资源，实现跨集群协同与边缘部署的统一管理。

## 主要特性
1. 具身智能工作负载编排：提供统一的声明式Job/Task抽象，覆盖从云端GPU训练到边缘部署的全流程；
2. 多运行时数据平面：基于Kubernetes统一管理云端GPU集群与边缘设备，后续将扩展Docker、Raw运行时以适配轻量边缘场景；
3. 跨集群资源抽象：通过Domain（虚拟网络域）、Node（计算节点）CRD统一多站点GPU集群与边缘设备，控制平面基于kcp运行；
4. 声明式训练作业：支持声明式分布式训练与Ray集群定义；
5. 跨集群Pod网络：基于TUN设备、gVisor netstack、SSH隧道实现Pod间无NAT穿越的直接通信，支持云端GPU与边缘机器人直连；
6. 双证书体系：采用X.509+SSH双证书，支持Agent访问、域级跨集群转发认证及用户SSH认证。
