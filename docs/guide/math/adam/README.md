# adam

- 项目链接：https://github.com/gbionics/adam
- 项目主页：https://adam-docs.readthedocs.io/en/latest/

## 项目概述

adam是**浮动基机器人刚体动力学自动微分算法集合**，支持在多个后端计算刚体动力学。主要特点：

1. **多后端支持**：
   - JAX：支持XLA编译、向量化和微分
   - CasADi：支持优化和控制的符号计算
   - PyTorch：GPU加速和批量操作
   - NumPy：简单数值评估
2. **统一接口**：所有后端共享相同接口，产生数值一致的结果，可以根据需求选择合适工具
3. **支持多种扩展**：支持MuJoCo、OpenUSD，提供可视化支持
4. **基于Featherstone算法**：构建在Featherstone算法基础上

adam为刚体动力学计算提供了统一多后端接口，方便在不同计算场景下使用，适合机器人控制、优化等研究。