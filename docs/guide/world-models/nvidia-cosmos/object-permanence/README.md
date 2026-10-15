# object-permanence

世界模型中的对象持久性训练代码库

## 项目链接

- GitHub: <https://github.com/hokindeng/object-permanence>
- 项目主页: <https://object-permanence.world>

## 项目介绍
object-permanence是论文《Training Object Permanence in World Models》的代码库，核心是训练具备物体恒存性的世界模型，提供了数据生成与模型训练的完整技术栈。项目包含两大部分：一是基于Blender的150个任务生成器，可生成带遮挡场景的视频样本；二是基于PyTorch的训练栈，用于在AWS Trainium2上训练NVIDIA Cosmos3-Nano模型。

## 主要特性
1. 数据工厂：提供150个自包含任务生成器，涵盖6类认知场景，可生成带遮挡物体的视频样本，支持并行生成、预览、分片生成等多种操作，输出包含输入视频、目标视频、指令文本、轨迹数据等5类文件的标准化样本集。
2. 训练栈：原生PyTorch实现，基于Neuron运行，无需XLA图追踪，支持64个NeuronCore的张量并行与FSDP2，可在trn2.48xlarge实例上完成模型训练与采样。
3. 配套资源：提供150万训练数据集、基准测试集、预训练模型及排行榜，遵循CC BY-NC 4.0与NVIDIA Cosmos OpenMDW-1.1许可协议。
