# NavDP

[ICRA 2026] NavDP: 利用特权信息引导的模拟到现实导航扩散策略学习

## 项目链接

- GitHub: <https://github.com/InternRobotics/NavDP>

## 项目介绍
NavDP是一篇ICRA 2026论文项目，全称是Learning Sim-to-Real Navigation Diffusion Policy with Privileged Information Guidance，专注于基于扩散策略的机器人导航仿真到实境迁移研究。项目团队来自上海人工智能实验室、清华大学、浙江大学、香港大学等机构，同时还开源了相关的基准部署流程、LoGoPlanner端到端导航框架、InternVLA-N1双系统以及InternNav一体化机器人导航开源工具箱。其衍生版本X-NavDP已被CoRL 2026收录，是面向异构机器人平台的导航扩散策略强化学习后训练框架。

## 主要特性
1.  基于特权信息引导的扩散策略，实现机器人导航从仿真到真实环境的可靠迁移
2.  提供完整的硬件到算法的部署流程，适配LeKiwi机器人平台
3.  配套开源了导航相关的基准测试、数据集与全栈工具链，降低机器人导航研究与落地门槛
4.  支持异构机器人 embodiment 的导航策略适配与迁移
