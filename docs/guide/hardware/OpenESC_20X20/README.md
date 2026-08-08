# OpenESC 20X20
- GitHub仓库: https://github.com/incutec-hw/OpenESC_20X20

## 项目概述
OpenESC 20X20是一款开源的四通道4合1无刷电调，专为FPV无人机设计。其采用20×20mm的安装尺寸，每通道支持30A电流，兼容3-6节电池。该电调基于AT32F421主控芯片和AM32固件，支持DShot通信协议，采用KiCad设计，适合JLCPCB批量生产。该产品是incutec OpenDrone产品线的一部分，还提供30.5×30.5mm的更大尺寸版本OpenESC-30x30，共享相同的设计架构。每个通道都有独立的MCU和栅极驱动器，采用分布式MCU设计而非单MCU方案，具备高精度的电流检测和稳定的电机控制能力。