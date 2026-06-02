# 数字孪生环境
> 数字孪生环境：让 Sim2Real 更简单

受 [SIMPLER](https://simpler-env.github.io/) 和 [ManiSkill](https://github.com/haosulab/ManiSkill) 绿幕功能的启发，我们实现了数字孪生环境（DigitalTwin Env）。此功能允许您用真实背景图像替换仿真环境中的背景，同时保留机械臂和交互对象等前景元素。这种方法显著减少了仿真与现实之间的差距，实现了更好的 sim2real 迁移。

要使用此功能，只需创建一个继承自 `ManagerBasedRLDigitalTwinEnvCfg` 的任务配置类，并通过相应的环境启动它。在配置类中，您可以指定相关参数，包括叠加模式（overlay_mode）、背景图像路径以及要保留的前景环境组件。

:::info
使用示例请参考示例任务：[LiftCubeDigitalTwinEnvCfg](https://github.com/LightwheelAI/leisaac/blob/main/source/leisaac/leisaac/tasks/lift_cube/lift_cube_env_cfg.py)。
:::
