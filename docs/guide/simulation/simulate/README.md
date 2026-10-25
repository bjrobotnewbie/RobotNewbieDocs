# simulate

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/simulation/simulate/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

🎢 构建与共享具身与合成数据的仿真环境

## 项目链接

- GitHub: <https://github.com/huggingface/simulate>
- 项目主页: <https://huggingface.co/docs/simulate>

## 项目介绍
Simulate是一个用于快速创建、共享智能体（如强化学习场景）或合成数据生成的仿真环境库。它支持通过Python API创建场景并添加物体、相机、光源等资产，可将场景保存为跨引擎的GIFT标准格式文件，支持使用Unity、Blender、Godot或pyvista作为后端进行渲染与仿真。当前项目处于非活跃维护状态，可通过提交Issue参与贡献。

## 主要特性
1.  极简安装方式，可通过`pip install simulate`快速部署（Apple Silicon需使用Python3.9+）
2.  借鉴Kubric的API设计，通过创建`Scene`并添加`Assets`快速搭建仿真场景
3.  支持将场景保存为跨引擎的行业标准GIFT格式文件，便于共享
4.  多后端支持：默认pyvista后端可快速预览场景，Unity/Blender/Godot后端可支持物理仿真
5.  自动下载适配的Unity后端运行环境，也可手动使用指定版本Unity编辑器运行
