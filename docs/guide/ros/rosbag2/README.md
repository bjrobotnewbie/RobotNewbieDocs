# rosbag2

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/ros/rosbag2/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

## 项目链接

- GitHub: <https://github.com/ros2/rosbag2>

## 项目介绍
rosbag2是ROS 2生态下的数据包录制、回放与信息查看工具，是官方设计文档中定义的新一代rosbag实现，可用于记录ROS 2系统中的话题数据，也支持读取ROS1 bag文件，适配ROS 2 Crystal及以上版本。

## 主要特性
1.  支持通过命令行进行数据录制、回放和话题信息查看
2.  支持自动发现新增话题录制，也可手动指定需要录制的话题
3.  提供Debian包一键安装和源码编译两种部署方式，兼容ROS 2官方工作区叠加构建
4.  内置ROS1 bag文件读取插件，可通过ros1_bridge实现跨版本数据兼容
5.  自带完整测试套件，可通过colcon工具执行验证
