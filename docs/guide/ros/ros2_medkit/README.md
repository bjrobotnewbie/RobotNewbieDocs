# ros2_medkit

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/ros/ros2_medkit/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

ros2_medkit - 用于ROS 2机器人的诊断网关。通过REST API实现故障获取、实时数据、操作、脚本、锁定、触发器和OTA更新。无需SSH，无需自定义工具。

## 项目链接

- GitHub: <https://github.com/selfpatch/ros2_medkit>
- 项目主页: https://selfpatch.github.io/ros2_medkit/

## 项目介绍
ros2_medkit是一款ROS 2机器人的诊断网关工具，无需SSH或自定义工具，可通过REST API实现机器人故障监控、实时数据获取、运维操作、脚本执行、资源锁定、触发控制以及OTA升级等功能。

## 主要特性
1.  提供完整的ROS 2机器人运维远程访问能力
2.  支持故障管理、实时数据采集与上报
3.  内置脚本执行、资源锁定与事件触发功能
4.  支持远程OTA升级
5.  无需额外自定义工具或SSH连接，通过标准REST API即可完成所有操作
6.  包含多个配套功能包，覆盖诊断桥接、参数/话题信标、Linux系统 introspection等细分功能
