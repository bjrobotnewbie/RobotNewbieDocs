# Mooncake

Mooncake 是 Kimi 的服务部署平台，Kimi 是由 Moonshot AI 提供的主流大语言模型服务。

## 项目链接

- GitHub: <https://github.com/kvcache-ai/Mooncake>
- 项目主页: <https://kvcache-ai.github.io/Mooncake/>

## 项目介绍
Mooncake是由月之暗面（Moonshot AI）推出的大语言模型Kimi的服务部署平台，其核心是面向KVCache的分离式架构。在真实业务负载下，该架构可以让Kimi在满足服务等级目标（SLO）的前提下，多处理75%的请求。项目附带官方论文、演示幻灯片、测试数据集、文档、博客和社区交流渠道，同时提供多环境的PyPI安装包与Docker镜像。

## 主要特性
1.  采用KVCache-centric的分离式架构优化LLM服务部署
2.  支持多硬件环境，提供适配不同CUDA版本、NPU以及无CUDA环境的安装包
3.  经过真实生产环境验证，可显著提升LLM服务的请求处理上限
