# LocationSimulator

这是一款用于欺骗/伪造/模拟你的iOS、iPadOS或iPhoneSimulator设备位置的MacOS应用，部分支持WatchOS和TvOS。

## 项目链接

- GitHub: <https://github.com/Schlaubischlump/LocationSimulator>
- 项目主页: <https://schlaubischlump.github.io/LocationSimulator/>

## 项目介绍
LocationSimulator是一款macOS应用，可伪造iOS、iPadOS、iPhone模拟器的设备位置，对watchOS和tvOS有部分支持，当前暂不支持iOS 17及以上版本和测试版系统。其面向开发者，用于测试基于位置服务的应用，官方不鼓励将其用于iOS游戏作弊。该项目基于libimobiledevice开发，运行时无需安装Xcode，但需要对应iOS版本的`DeveloperDiskImage.dmg`及签名文件。

## 主要特性
1.  无需越狱或在设备端安装应用即可伪造iOS设备位置，同时支持模拟器位置修改
2.  可自动匹配下载对应iOS版本的DeveloperDiskImage文件
3.  通过地图长按快速设置位置，支持搜索地点
4.  支持自定义和预设的步行/骑行/驾车移动速度，可通过方向键控制移动
5.  支持从当前位置导航到目标地点
6.  支持网络设备连接，适配深色模式
