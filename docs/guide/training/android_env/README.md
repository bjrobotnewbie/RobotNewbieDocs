# android_env

基于Android设备的RL研究。

## 项目链接

- GitHub: <https://github.com/google-deepmind/android_env>

## 项目介绍
AndroidEnv是DeepMind推出的Python库，可将Android设备作为强化学习（RL）环境。它将真实/模拟的Android系统封装为RL训练平台，支持在任意Android应用上自定义训练任务。智能体通过触摸屏发送精准触摸、抬起事件与设备交互，库会返回像素观测结果与自定义配置的奖励信号，可用于滚动页面、发送邮件、游戏得分等各类研究场景。

## 主要特性
1.  支持与真实量产级Android系统交互，拥有真实设备的全部功能与使用逻辑，可落地到现实场景的RL研究
2.  提供通用触控交互接口，可针对任意原生或自研Android应用设计训练任务，任务场景几乎无限丰富
3.  支持实体设备与虚拟模拟器两种部署方式，配套完整的任务定义、运行部署指南与示例任务库
