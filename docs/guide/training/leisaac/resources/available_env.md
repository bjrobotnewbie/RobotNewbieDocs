# 可用环境

下表列出了 LeIsaac 中所有可用的任务和环境。您还可以通过运行以下命令获取最新的环境列表：

```bash
python scripts/environments/list_envs.py
```

| 任务 | 环境 ID | 任务描述 | 相关机器人 |
| :--- | :-------------- | :--------------- | :------------ |
| <video src="https://github.com/user-attachments/assets/466eddff-f720-4f99-94d5-5e123e4c302c" autoPlay loop muted playsInline style="max-width: 300px;"></video> | [LeIsaac-SO101-PickOrange-v0](https://github.com/LightwheelAI/leisaac/blob/main/source/leisaac/leisaac/tasks/pick_orange/pick_orange_env_cfg.py)<br /><br />[LeIsaac-SO101-PickOrange-Direct-v0](https://github.com/LightwheelAI/leisaac/blob/main/source/leisaac/leisaac/tasks/pick_orange/direct/pick_orange_env.py) | 拾取三个橙子并将它们放入盘子中，然后将机械臂重置为休息状态。 | 单臂 SO101 Follower |
| <video src="https://github.com/user-attachments/assets/1e4eb83a-0b38-40fb-a0b2-ddb0fe201e6d" autoPlay loop muted playsInline style="max-width: 300px;"></video> | [LeIsaac-SO101-LiftCube-v0](https://github.com/LightwheelAI/leisaac/blob/main/source/leisaac/leisaac/tasks/lift_cube/lift_cube_env_cfg.py)<br /><br />[LeIsaac-SO101-LiftCube-Direct-v0](https://github.com/LightwheelAI/leisaac/blob/main/source/leisaac/leisaac/tasks/lift_cube/direct/lift_cube_env.py) | 将红色立方体抬起。 | 单臂 SO101 Follower |
| <video src="https://github.com/user-attachments/assets/e49d8f1c-dcc9-412b-a88f-100680d8a45b" autoPlay loop muted playsInline style="max-width: 300px;"></video> | [LeIsaac-SO101-CleanToyTable-v0](https://github.com/LightwheelAI/leisaac/blob/main/source/leisaac/leisaac/tasks/clean_toy_table/clean_toy_table_env_cfg.py)<br /><br />[LeIsaac-SO101-CleanToyTable-BiArm-v0](https://github.com/LightwheelAI/leisaac/blob/main/source/leisaac/leisaac/tasks/clean_toy_table/clean_toy_table_bi_arm_env_cfg.py)<br /><br />[LeIsaac-SO101-CleanToyTable-BiArm-Direct-v0](https://github.com/LightwheelAI/leisaac/blob/main/source/leisaac/leisaac/tasks/clean_toy_table/direct/clean_toy_table_bi_arm_env.py) | 将两个字母 e 物体拾取到盒子中，然后将机械臂重置为休息状态。 | 单臂 SO101 Follower<br /><br />双臂 SO101 Follower |
| <video src="https://github.com/user-attachments/assets/e29a0f8a-9286-4ce6-b45d-342c3d3ba754" autoPlay loop muted playsInline style="max-width: 300px;"></video> | [LeIsaac-SO101-FoldCloth-BiArm-v0](https://github.com/LightwheelAI/leisaac/blob/main/source/leisaac/leisaac/tasks/fold_cloth/fold_cloth_bi_arm_env_cfg.py)<br /><br />[LeIsaac-SO101-FoldCloth-BiArm-Direct-v0](https://github.com/LightwheelAI/leisaac/blob/main/source/leisaac/leisaac/tasks/fold_cloth/direct/fold_cloth_bi_arm_env.py) | 折叠布料，然后将机械臂重置为休息状态。<br /><br />*注意：此任务中只有 DirectEnv 支持 check_success。* | 双臂 SO101 Follower |
| <video src="https://github.com/user-attachments/assets/b95baf5c-861d-4698-ab55-f929b271dab9" autoPlay loop muted playsInline style="max-width: 300px;"></video> | [LeIsaac-LeKiwi-CleanupTrash-v0](https://github.com/LightwheelAI/leisaac/blob/main/source/leisaac/leisaac/tasks/cleanup_trash/cleanup_trash_env_cfg.py) | 从地板上拾取纸巾垃圾并将其扔进垃圾桶。 | LeKiwi |
