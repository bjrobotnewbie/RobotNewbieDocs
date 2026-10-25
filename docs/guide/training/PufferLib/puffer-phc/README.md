# puffer-phc

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/training/PufferLib/puffer-phc/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

基于 Pufferlib 和 CARBS 的简化永久型人形机器人控制

## 项目链接

- GitHub: <https://github.com/kywch/puffer-phc>

## 项目介绍
puffer-phc是基于Pufferlib简化版的人形机器人持续控制（Perpetual Humanoid Control, PHC）项目，由Puffer AI赞助开发，核心是实现单基元模型，可复现AMASS数据集99.0%的11313种动作，基于Isaac Gym、gymtorch等工具完成策略训练，支持通过Aim工具记录训练过程。

## 主要特性
1. 对原PHC项目进行简化，大幅减少类继承与依赖，使用PufferLib完成策略训练
2. 支持复现AMASS数据集绝大多数动作，提供对应检查点文件
3. 基于pixi实现虚拟环境管理，支持Isaac Gym、gymtorch的安装配置，可通过VSCode调试Isaac Gym环境
4. 提供Aim工具支持训练日志本地记录、多设备运行合并等功能
