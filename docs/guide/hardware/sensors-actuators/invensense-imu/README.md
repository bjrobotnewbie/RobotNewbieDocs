# invensense-imu

Arduino 与 CMake 库：用于与 InvenSense MPU-6500、MPU-9250 和 MPU-9255 九轴 IMU 进行通信。

## 项目链接

- GitHub: <https://github.com/bolderflight/invensense-imu>

## 项目介绍
本项目是针对InvenSense MPU-6500、MPU-9250和MPU-9255九轴惯性测量单元(IMU)的Arduino与CMake库，支持通过I2C、SPI协议与传感器通信，可用于读取陀螺仪、加速度计、磁力计（MPU-9250系列）的数据，同时支持配置传感器量程、数字滤波器等参数，内置温度传感器读取功能。项目兼容Arduino和CMake两种构建系统。

## 主要特性
1.  支持MPU-6500（六轴IMU）、MPU-9250/9255（九轴IMU）两款传感器
2.  支持I2C（最高400kHz）、SPI（寄存器配置最高1MHz，数据读取最高20MHz）通信方式
3.  可选择多档陀螺仪、加速度计、磁力计量程
4.  内置可编程数字滤波器、高精度时钟与温度传感器
5.  提供Arduino库管理器安装方式与CMake编译构建方案，附带多种示例代码
