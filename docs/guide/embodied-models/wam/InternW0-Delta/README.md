# InternW0-Delta

<div class="zh-readme-entry"><a class="zh-readme-entry__link" href="/guide/embodied-models/wam/InternW0-Delta/README_zh"><span class="zh-readme-entry__badge" aria-hidden="true">中</span><span class="zh-readme-entry__text"><span class="zh-readme-entry__title">阅读中文 README</span><span class="zh-readme-entry__subtitle">本项目介绍的中文完整版</span></span><span class="zh-readme-entry__arrow" aria-hidden="true">→</span></a></div>

InternW0-Δ：一个融合预测动力学与动作的开放数据世界行动模型，涵盖 20K+ 小时数据

## 项目链接

- GitHub: <https://github.com/InternRobotics/InternW0-Delta>
- 项目主页: <https://internrobotics.github.io/InternW0-Delta/>

## 项目介绍
InternW0-Delta（InternW0-Δ）是一款统一的世界-动作模型，通过机器人与人类演示学习，结合预训练视频动力学模型、冻结的视觉语言模型（VLM）及仅训练阶段使用的4D监督，生成机器人动作。项目覆盖数据准备、预训练、4D蒸馏、后训练、评估及真实机器人部署全流程，依托超2万小时公开数据构建，核心是打通预测动力学与动作生成的关联。

## 主要特性
1. 世界-动作MoT：预训练视频专家与动作专家通过掩码自注意力交互，结合视觉记忆与任务条件场景语义；
2. 因果印记：紧凑查询从未来监督中学习动作相关场景变化，将预测特征传递给动作专家；
3. 4D蒸馏：训练阶段通过冻结的Track4World教师模型传递几何与运动知识，推理阶段无需教师与蒸馏分支，保证效率。
