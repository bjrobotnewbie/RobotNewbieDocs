# GMR

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/robot-forms/gmr-motionlab/GMR/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

[ICRA 2026] GMR: 通用运动重定向。将人类动作实时重定向至多样化的人形机器人，并在 CPU 上运行。TWIST 重定向器。

## 项目链接

- GitHub: <https://github.com/YanjieZe/GMR>

## 项目介绍
GMR是ICRA 2026收录的通用运动重定向工具，可在CPU上实时将人类动作重定向至各类人形机器人，是TWIST项目的配套重定向器。

## 主要特性
1. 支持实时高质量动作重定向，可解锁全身实时遥操作（如TWIST）的应用潜力，适配RL跟踪策略的性能优化；
2. 兼容多个人形机器人（含Fourier GR3、PAL Robotics Talos等）及多种人类动作数据格式（如Xsens、Nokov BVH数据）；
3. 支持扩展新机器人或新动作数据格式，可通过提交需求或提供合规文件实现适配；
4. 采用MIT开源协议，当前版本为0.2.0。
