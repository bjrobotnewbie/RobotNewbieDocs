# groki-bot

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/robot-forms/groki-bot/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

Groki Bot 桌面机器人（M5Stack CoreS3）：固件、语音及 MCP 网关，用于您的电脑，并作为与 Grok Bot 代理的交接点。

## 项目链接

- GitHub: <https://github.com/JosssphZhou/groki-bot>
- 项目主页: <https://josssphzhou.github.io/groki-bot/>

## 项目介绍
groki-bot是一款基于M5Stack CoreS3与Stack-chan底座的开源桌面机器人，整合了固件、电脑端网关及Grok Bot代理链接功能，可通过Grok Bot应用实现语音交互，适配macOS系统。

## 主要特性
1. 原生语音支持（macOS）：无需额外xAI语音API密钥，直接使用Mac端已登录的Grok Bot应用与代理对话；
2. 免唤醒词：通过桌面网关的轻量本地语音检测，随时说“Hi Grok”唤醒机器人；
3. 动态人脸追踪：借助Mac摄像头实现人脸检测，驱动双轴舵机实时调整机器人朝向；
4. 丰富表情动画：设备端表情引擎支持15种表情及眨眼效果；
5. 便捷部署：支持Chrome/Edge一键网页烧录固件，也可通过设备端OTA实现Wi-Fi更新，无需搭建本地工具链。
