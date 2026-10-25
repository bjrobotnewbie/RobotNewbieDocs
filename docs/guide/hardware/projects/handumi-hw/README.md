# handumi-hw

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/hardware/projects/handumi-hw/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

开源的 UMI 手拟变体，用于在无机器人闭环采集双手操作数据：模块化设计，适用于任意并联爪型 gripper。

## 项目链接

- GitHub: <https://github.com/murobotics-ai/handumi-hw>

## 项目介绍
handumi-hw是一款开源可穿戴硬件，为Universal Manipulation Interface (UMI)的手持变体，用于在无机器人参与的情况下采集双手操作数据，适配平行夹爪机械臂。其成本仅为传统方案的1/8，可穿戴于操作者拇指与食指/中指，通过自然捏合动作实现开合，搭配可互换夹爪头适配不同平行夹爪机器人，需搭配VR头显（如PICO 4 Ultra或Meta Quest 3）使用。

## 主要特性
1. 无需机器人参与即可采集双手操作数据，解决传统遥操作成本高、受实验室环境限制的问题
2. 模块化设计，适配各类平行夹爪机械臂
3. 数据采集后可通过配套的handumi-sw软件跨不同双手机械臂重定向使用
4. 硬件成本低廉，单套零件成本约104美元，大幅降低数据采集门槛
