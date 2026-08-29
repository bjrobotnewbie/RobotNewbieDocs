# LatentSpatialMemory

视频世界模型的潜在空间记忆

## 项目链接

- GitHub: <https://github.com/microsoft/LatentSpatialMemory>
- 项目主页: <https://aka.ms/latent-spatial-memory>

## 项目介绍
本项目是针对视频世界模型的**Latent Spatial Memory（潜在空间记忆）**方法，旨在为视频世界模型实现高效的空间一致性。它直接将持久化的3D场景内容存储为隐空间token，避免了从显式3D缓存中重复进行RGB渲染和重编码的流程，属于World-R1系列相关研究。

## 主要特性
1.  **隐式空间记忆**：将3D场景上下文直接存储在隐空间中，实现持久化场景记忆
2.  **无RGB冗余流程**：跳过重复的渲染-重编码缓存更新步骤
3.  **完整记忆生命周期**：支持在生成片段间完成记忆初始化、读取、去噪和更新
4.  **高效生成**：降低3D缓存内存占用，提升视频世界模型生成效率
