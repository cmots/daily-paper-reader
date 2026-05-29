---
title: "WALL-E: World Alignment by NeuroSymbolic Learning improves World Model-based LLM Agents"
title_zh: "WALL-E: 通过神经符号学习实现世界对齐以改进基于世界模型的LLM智能体"
authors: "Siyu Zhou, Tianyi Zhou, Yijun Yang, Guodong Long, Deheng Ye, Jing Jiang, Chengqi Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=DorAT49sxj"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 基于神经符号学习的世界对齐方法用于LLM智能体
tldr: 针对LLM作为世界模型时环境动态知识不足的问题，提出无需训练的世界对齐方法，通过从探索轨迹中提取符号知识（动作规则、知识图谱、场景图）并编码为可执行代码来调节LLM智能体的策略。进一步基于模型预测控制（MPC）构建无强化学习的智能体WALL-E，避免了传统MPC的高昂优化成本。实验表明该方法有效提升了LLM智能体在多种环境中的表现。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-dorat49sxj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 683, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dorat49sxj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 658, \"height\": 972, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dorat49sxj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 795, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dorat49sxj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 540, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dorat49sxj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 736, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-dorat49sxj/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 738, \"height\": 364, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-dorat49sxj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1438, \"height\": 563, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dorat49sxj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 882, \"height\": 318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dorat49sxj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 697, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dorat49sxj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 697, \"height\": 201, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dorat49sxj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 711, \"height\": 154, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dorat49sxj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1390, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-dorat49sxj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1442, \"height\": 210, \"label\": \"Table\"}]"
motivation: 缩小LLM先验知识与指定环境动态之间的差距，构建准确的世界模型。
method: 利用LLM从探索轨迹中提取符号知识并编码为可执行代码，通过MPC框架实现无需训练的世界对齐。
result: 在多种环境中验证了所提方法能有效提升LLM智能体的性能。
conclusion: 提出了一种无需训练的符号世界对齐方法，为基于世界模型的LLM智能体提供了新范式。
---

## Abstract
Can we build accurate world models out of large language models (LLMs)? How can world models benefit LLM agents? The gap between the prior knowledge of LLMs and the specified environment's dynamics usually bottlenecks LLMs' performance as world models. To bridge the gap, we propose a training-free "world alignment" that learns an environment's symbolic knowledge complementary to LLMs. The symbolic knowledge covers action rules, knowledge graphs, and scene graphs, which are extracted by LLMs from exploration trajectories and encoded into executable codes to regulate LLM agents' policies. We further propose an RL-free, model-based agent "WALL-E" through the model-predictive control (MPC) framework. Unlike classical MPC requiring costly optimization on the fly, we adopt an LLM agent as an efficient look-ahead optimizer of future steps' actions by interacting with the neurosymbolic world model. While the LLM agent's strong heuristics make it an efficient planner in MPC, the quality of its planned actions is also secured by the accurate predictions of the aligned world model. They together considerably improve learning efficiency in a new environment. On open-world challenges in Mars (Minecraft like) and ALFWorld (embodied indoor environments), WALL-E significantly outperforms existing methods, e.g., surpassing baselines in Mars by 16.1%–51.6% of success rate and by at least 61.7% in score. In ALFWorld, it achieves a new record 98% success rate after only 4 iterations.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：大语言模型（LLM）作为世界模型时，其先验知识与特定环境动态之间存在巨大差距，导致预测不准、规划失败。现有方法要么依赖昂贵微调/RL，要么依赖手工提示工程，缺乏高效、可扩展的“世界对齐”手段。
- **整体含义**：提出一种**无需训练**的“世界对齐”方法——通过神经符号学习从探索轨迹中提取符号知识（动作规则、知识图谱、场景图）并将其编译为可执行代码，以纠正和补充LLM的先验知识，从而构建更准确的神经符号世界模型，并基于该模型设计高效的模型预测控制（MPC）智能体WALL-E，显著提升LLM智能体在开放世界任务中的适应性和成功率。

### 2. 论文提出的方法论
- **核心思想**：将LLM本身作为世界模型，通过自动提取符号知识并转化为可执行代码规则来对齐环境动态；采用MPC框架，让LLM智能体作为高效的前瞻优化器，与对齐后的世界模型交互进行规划，避免传统MPC的在线优化成本。
- **关键技术细节**：
  - **神经符号学习（NeuroSymbolic Learning）**：
    - **Stage 1**：收集真实轨迹和模型预测轨迹，对比找出错误预测的转换（D_inc）。
    - **Stage 2**：利用LLM的归纳推理能力从真实轨迹中提取三类符号知识：
      - **动作规则（Action Rules）**：确定性约束，如“若工具不合适则动作失败”。
      - **知识图谱（Knowledge Graph）**：实体间的可行性约束和前提条件（如“制作需消耗材料”）。
      - **场景图（Scene Graph）**：全局空间关系，弥补部分可观测性。
    - **Stage 3**：将符号知识翻译为可执行的Python代码规则（Code Rules），每条规则返回反馈、成功标志和建议。
    - **Stage 4**：通过验证（过滤错误规则）和最大覆盖优化（选择能纠正最多错误预测的规则）进行规则集剪枝，得到紧凑有效的规则集R_code。
  - **模型预测控制（MPC）框架**：
    - 在每个时间步，LLM智能体基于当前观察和反馈提出动作，世界模型（经代码规则对齐）预测结果；若预测失败则提供反馈和建议，智能体继续改进动作直至通过验证或达到重规划上限。
    - 对齐方式（ALIGN）：比较LLM世界模型输出与代码规则输出，若冲突则重新调用LLM世界模型并注入规则反馈，确保预测与规则一致。
  - **算法流程**：
    - 初始化空规则集，主循环中：执行MPC得到动作并执行，记录真实/预测轨迹，执行神经符号学习更新规则集。详见Algorithm 1和Algorithm 2。

### 3. 实验设计
- **数据集/场景**：
  - **Mars**：基于Crafter的开放世界环境，包含默认世界和七种反常识世界（修改地形、生存、任务依赖等）。用于评估LLM智能体在非标准动态下的适应能力。
  - **ALFWorld**：文本化的室内家庭环境，包含134个测试任务（共6种任务类型：拾取、清洁、加热、冷却、检查、拾两个等）。
- **基准对比方法**：
  - Mars：RL方法（PPO、DreamerV3）和LLM方法（ReAct、Reflexion、Skill Library、IfR）。其中DreamerV3作为参考（使用100万环境步训练）。
  - ALFWorld：BUTLER、GPT-BUTLER、DEPS、AutoGen、ReAct、AdaPlanner、Reflexion、RAFA等，以及人类表现。
- **评估指标**：
  - Mars：奖励（累积稀疏奖励）和得分（不同成就成功率的加权几何平均）。
  - ALFWorld：任务成功率。

### 4. 资源与算力
- **文中有明确说明**：
  - 硬件：本地Ubuntu 20.04.6工作站，Intel i5-13600KF CPU，64GB RAM，单张NVIDIA RTX 4060 Ti 16GB GPU。
  - 每次评估试验（一次trial）约5-10分钟；全部评估总耗时<24小时。
  - 注意：未提及完整训练/探索的总耗时，但明确指出算法无需训练，仅有推理和符号学习开销。

### 5. 实验数量与充分性
- **实验数量**：
  - Mars：9种世界类型（默认+7种反常识+平均），每个方法做9次独立试验（LLM方法）或20次（RL方法）。
  - ALFWorld：固定134个测试任务，对比8+种基线方法。
  - 消融实验：符号知识类型消融（动作规则、KG/SG的有无）、组件消融（有无世界模型、有无符号知识）、代码规则剪枝消融（不同规则数限制）、与技能库方法对比。
- **充分性**：
  - 覆盖了多种环境变化（反常识、组合变化），对比了当前SOTA基线。
  - 消融实验设计合理，验证了每类符号知识与MPC框架的必要性。
  - 实验标准偏差已报告，统计上可靠。
  - 整体上实验充分、客观，公平对比（代码已开源）。

### 6. 论文的主要结论与发现
- **主要结论**：LLM世界上模型通过神经符号学习的对齐（提取并编译动作规则、知识图谱、场景图）可以显著提升预测准确性和LLM智能体的规划能力。WALL-E在Mars上比最佳基线IfR在奖励上提升约17.9%，在得分上提升51.6%；在ALFWorld上仅用4次迭代即达到98%成功率，刷新纪录。
- **关键发现**：
  - 多种符号知识（规则+图谱+场景图）联合使用效果最佳。
  - 符号知识应用于世界模型比直接应用于代理效果更好（提升46.3% vs 30.9%）。
  - 代码规则剪枝（最大覆盖）是必要的，能有效过滤噪声规则。
  - 在反常识环境中，WALL-E表现出色（奖励提升至少31%），但当多种变化同时发生时提升减弱，说明当前规则尚难完全捕捉复杂交互。

### 7. 优点
- **无需训练或微调**：完全依赖LLM的推理能力，避免了昂贵的强化学习或监督微调，易于迁移到新环境。
- **神经符号结合**：充分融合LLM的先验知识和符号系统的确定性约束，既保证了灵活性又提升了准确性。
- **高效MPC**：利用LLM作为前瞻优化器，突破传统MPC的计算瓶颈，实现快速迭代规划。
- **自动规则提取与剪枝**：无需人工设计提示或规则，通过归纳推理和最大覆盖优化自动获得高质量规则集。
- **强有力的实验验证**：在两种截然不同的开放世界（2D网格、文本室内）上均达到SOTA，消融实验充分揭示了各组件贡献。

### 8. 不足与局限
- **限于确定性动态**：当前方法假设环境转换是确定性的，无法处理随机性（如动作有一定概率失败）。作者在附录G中承认此局限，并计划扩展至概率模型。
- **仅学习转换级别规则**：不具备捕捉长期规划约束或时间依赖的抽象知识，例如任务间的顺序依赖或高层策略。
- **对多因素组合变化适应性有限**：当多个环境变量同时改变时（如地形+生存+任务依赖），性能提升减弱，表明当前规则可能无法完全覆盖复杂交互。
- **计算资源消耗未完整报告**：尽管每次试验时间短，但完整探索/学习过程（5 episodes）的总体LLM查询成本未详细给出（如token消耗）。
- **实验环境有限**：仅在Mars和ALFWorld上评估，缺乏更复杂或真实3D环境的验证（如Minecraft、机器人仿真）。

（完）
