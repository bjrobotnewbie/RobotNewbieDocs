# three-pathfinding

基于 PatrolJS 的 three.js 导航网格工具集

## 项目链接

- GitHub: <https://github.com/donmccurdy/three-pathfinding>
- 项目主页: <https://three-pathfinding.donmccurdy.com/>

## 项目介绍
这是一个基于PatrolJS的Three.js导航网格工具库，可在3D导航网格上计算两点间路径，支持多区域，还可用于约束FPS游戏的移动向量。用户可通过Blender、Recast等工具创建导航网格，导出为OBJ、glTF等3D格式后，借助three.js加载器将`THREE.BufferGeometry`实例传入该库使用。

## 主要特性
1.  基于PatrolJS构建，专为Three.js设计
2.  支持在3D导航网格上计算路径，可处理多区域场景
3.  可约束移动向量，适配FPS类游戏控制
4.  支持适配AI代理的尺寸，比传统路点导航更精准高效
5.  遵循three.js的+Y向上坐标系规范
