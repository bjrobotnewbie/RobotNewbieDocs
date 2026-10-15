# RoboRSI

带有命令行界面和本地 Web 控制台的机器人代理框架，用于 LIBERO 项目的短期评估

## 项目链接

- GitHub: <https://github.com/nssmd/RoboRSI>
- 项目主页: <https://lab.noematrix.ai/blog/2-roborsi-research-preview/>

## 项目介绍
RoboRSI是一款面向机器人自主进化的多智能体框架，支持CLI与本地Web控制台，用于LIBERO短周期评估，适用于复杂真实环境下的机器人任务执行与自主优化。

## 主要特性
1. 采用Manager、Planner、Engineer、Reviewer分工架构，通过自顶向下技能细化（TSR）构建任务-技能树；
2. 支持在线探索生成解决方案、稳定工作流固化为代码，执行数据可用于训练学习策略，失败可回溯至最早责任节点；
3. 在LIBERO、LIBERO-PRO等任务集上表现优异，LIBERO累计任务通过率达95/120，具备自适应迭代优化能力，可降低代码、VLM调用及时间成本。
