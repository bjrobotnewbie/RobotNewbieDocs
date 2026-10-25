# youtu-parsing

Youtu-Parsing: 通过高并行解码实现感知、结构化与识别 && Youtu-Parsing-Omni: 一个编码器、一个 Schema、所有模态

## 项目链接

- GitHub: <https://github.com/TencentCloudADP/youtu-parsing>

## 项目介绍
Youtu-Parsing是基于开源Youtu-LLM 2B构建的专用文档解析模型，通过提示引导框架与NaViT风格动态视觉编码器扩展基础模型能力，具备文本、表格、公式、图表等多种文档元素的解析能力，采用高效并行解码机制加速推理，可应用于实际文档分析场景，同时项目还推出了多模态版本Youtu-Parsing-Omni，支持文档、图像、图表、几何、音频、视频等全模态解析。

## 主要特性
1. **文档结构保留**：实现像素级精准的文本区域定位，智能恢复文档内容的逻辑阅读顺序，适配多栏、多章节、多页面的复杂布局。
2. **高级内容识别**：支持多场景文本识别、数学表达式转LaTeX格式、表格转HTML格式、图表转Markdown表格及Mermaid格式的思维导图/流程图。
3. **高性能推理**：采用Token并行推理机制，实现5-11倍的推理速度提升。
