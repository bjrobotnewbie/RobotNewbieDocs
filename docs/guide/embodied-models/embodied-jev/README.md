# embodied-jev

EmbodiedJev：配备 MiniCPM5-2B 的 MuJoCo 机器人决策工作区，支持 Jev 及兼容的模型 API

## 项目链接

- GitHub: <https://github.com/FBddcz/embodied-jev>

## 项目介绍
embodied-jev（行知）是基于MuJoCo的具身AI决策工作台，支持在浏览器中运行，无需复杂安装，可体验「观察→决策→执行→反馈」的具身AI闭环流程，适配桌面与移动端，支持本地小模型及云端模型API接入，提供开箱即用的仿真任务，方便用户快速上手具身AI实验。

## 主要特性
1. 开箱体验：内置规则基线，无需API Key、GPU或模型权重，可运行搬运入盘、方块堆叠、越障搬运三个仿真任务；
2. 物理交互：基于MuJoCo与Franka Panda实现真实物理反馈，支持夹爪接触、抓取等操作；
3. 模型兼容：可接入TypeSafe Jev、Claude、OpenAI兼容API及本地MiniCPM5-2B模型；
4. 决策可视化：可查看决策过程、动作说明、调用次数与延迟，支持多模型对比实验；
5. 灵活配置：支持多相机组合、逐步规划、动作预演、实验控制，提供JSON导入导出与二次开发接口；
6. 本地运行：数据由本机服务处理，调用云端模型时仅发送任务状态，保障本地数据安全。
