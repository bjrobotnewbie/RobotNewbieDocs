# agent-sandbox

agent-sandbox 支持对隔离、有状态的单一实例工作负载进行便捷管理，适用于如 AI 代理运行时和强化学习（RL）等用例。

## 项目链接

- GitHub: <https://github.com/kubernetes-sigs/agent-sandbox>
- 项目主页: <https://agent-sandbox.sigs.k8s.io>

## 项目介绍
agent-sandbox 是 Kubernetes SIG Apps 旗下的开源项目，用于为 Kubernetes 提供声明式的标准化 API，管理具备稳定标识、有状态的单实例工作负载。它通过依托 Kubernetes 原生能力，打造轻量级单容器虚拟机式的运行环境，特别适合 AI 代理运行时、强化学习（RL）等场景。
该项目核心是`Sandbox`自定义资源定义（CRD）与控制器，会将底层容器隔离工作委托给 gVisor、Kata Containers 等安全沙箱运行时。

## 主要特性
1.  **核心能力**：提供具备稳定网络标识、持久化存储的单实例有状态 Pod 管理能力，可完成创建、定时删除、暂停恢复等生命周期管理，适配 Deployment 和 StatefulSet 不适用的工作负载场景。
2.  **扩展功能**：提供`SandboxTemplate`、`SandboxClaim`、`SandboxWarmPool`等扩展 CRD，支持复用沙箱配置、快速分配预启动沙箱实例，降低大规模沙箱管理成本。
