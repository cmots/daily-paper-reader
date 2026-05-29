---
title: Knowledge Retention in Continual Model-Based Reinforcement Learning
title_zh: 持续模型强化学习中的知识保留
authors: "Haotian Fu, Yixiang Sun, Michael Littman, George Konidaris"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=DiqeZY27XK"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 持续模型强化学习中的世界模型知识保留
tldr: 该论文针对模型强化学习中世界模型在连续任务场景下知识遗忘的问题，提出DRAGO方法，包含合成经验回放和通过探索重获记忆两个组件。在不存储旧数据的情况下，利用生成式模型构建合成经验强化已学动态，并通过内在奖励引导智能体回访相关状态，从而维护持续发展的世界模型。实验证明该方法有效保留了先验知识，促进了长期规划能力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1379, \"height\": 612, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1350, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 777, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1516, \"height\": 922, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1611, \"height\": 910, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1719, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1529, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1734, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1645, \"height\": 307, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 389, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1778, \"height\": 1018, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1782, \"height\": 1348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1779, \"height\": 580, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1782, \"height\": 478, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1096, \"height\": 1145, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1075, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1457, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1322, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 963, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 839, \"height\": 203, \"label\": \"Table\"}]"
motivation: 模型强化学习中世界模型在连续任务下容易遗忘先前学到的动态知识，限制了长期规划。
method: 提出DRAGO方法，包含合成经验回放（用生成模型生成旧任务经验）和通过探索重获记忆（内在奖励引导回访相关状态）。
result: 在连续任务设置下，DRAGO相比基准方法显著提升了世界模型对旧任务动态的保持和新任务的适应能力。
conclusion: 合成经验与内在探索相结合能有效缓解世界模型的知识遗忘，适用于持续学习和规划。
---

## Abstract
We propose DRAGO, a novel approach for continual model-based reinforcement learning aimed at improving the incremental development of world models across a sequence of tasks that differ in their reward functions but not the state space or dynamics. DRAGO comprises two key components: *Synthetic Experience Rehearsal*, which leverages generative models to create synthetic experiences from past tasks, allowing the agent to reinforce previously learned dynamics without storing data, and *Regaining Memories Through Exploration*, which introduces an intrinsic reward mechanism to guide the agent toward revisiting relevant states from prior tasks. Together, these components enable the agent to maintain a comprehensive and continually developing world model, facilitating more effective learning and adaptation across diverse environments. Empirical evaluations demonstrate that DRAGO is able to preserve knowledge across tasks, achieving superior performance in various continual learning scenarios.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：在模型强化学习（MBRL）中，智能体需要学习一个世界模型来预测环境动态。然而，当面对一系列连续任务（各任务共享状态空间与转移动态，但奖励函数不同）时，世界模型容易发生**灾难性遗忘**——学习新任务时，旧任务的关键动态知识会被覆盖或丢失。
- **现实挑战**：由于存储限制、隐私法规或设备部署约束，智能体无法保留旧任务的原始交互数据，使得多任务学习或简单回放方法不可行。
- **整体目标**：设计一种无需存储旧数据即可持续积累世界知识的方法，使智能体在连续任务中逐步构建更完整的世界模型，提升知识保留与迁移能力。

## 2. 方法论

### 核心思想
DRAGO 由两个互补组件构成：
1. **合成经验回放**：利用持续学习的生成模型（VAE）合成旧任务的状态-动作对，再通过冻结的旧世界模型预测下一状态，生成合成经验，用于训练当前世界模型，从而在不存储数据的情况下强化已学动态。
2. **通过探索重获记忆**：设计一种内在奖励机制，鼓励智能体主动探索“旧模型预测准确、但当前模型预测不准”的状态，从而在真实交互中重新连接旧任务的知识区域，弥补生成模型可能遗漏的细节。

### 关键技术细节
- **合成经验生成流程**：
  - 从生成模型 \( p_G(\hat{s}, \hat{a}; \theta) \) 中采样合成的状态-动作对 \((\hat{s}, \hat{a})\)。
  - 用旧世界模型 \( T_{\text{old}} \) 预测下一状态 \(\hat{s}' = T_{\text{old}}(\hat{s}, \hat{a})\)。
  - 将合成的 \((\hat{s}, \hat{a}, \hat{s}')\) 加入训练集，按加权 MSE 损失训练当前世界模型。
- **生成模型的持续学习**：使用 VAE，同时用当前任务真实数据和前一个生成模型合成的数据联合训练，防止生成模型自身遗忘。
- **内在奖励设计**：
  \[
  r_{\text{cont}}(s_t, a_t, s_{t+1}) = \sigma(-\log|T_{i-1}(s_t, a_t) - s_{t+1}|) - \alpha \cdot \sigma(-\log|T_i(s_t, a_t) - s_{t+1}|)
  \]
  第一项奖励旧模型预测准确（即熟悉状态），第二项惩罚当前模型已学好的状态，鼓励探索。
- **整体算法**：基于 TD-MPC 框架，额外引入一个“评审者”模型（reviewer）最大化内在奖励，与“学习者”（learner）共享世界模型但各自有独立策略和价值函数。训练时，世界模型同时对学习者、评审者以及合成数据进行优化。

## 3. 实验设计

### 数据集与场景
- **MiniGrid**：一个 \(27\times27\) 网格世界，包含四个房间，每个任务限制在单个房间内移动至目标点，房间间通过门连接。持续学习顺序：房间1→房间2→房间3→房间4。测试任务需要跨房间转移（如从房间1到房间2）。
- **DeepMind Control Suite**：包含 **Cheetah** 和 **Walker** 两个实体，共8个连续任务（如奔跑、跳跃、后退等）。持续学习顺序：Cheetah（run → jump → backward），Walker（run → walk → backward → stand）。测试任务为组合/切换运动模式（如 jump2run、walker walk2run）。

### Benchmark 与对比方法
- **Scratch**：每个任务从头训练 TD-MPC。
- **Continual TD-MPC**：持续训练，仅初始化世界模型为前一个任务。
- **EWC**（弹性权重巩固）：一种正则化方法。
- **Curiosity + Continual TD-MPC**（消融实验）：使用好奇心内在奖励。
- **Replay-based MBRL**：存储有限大小的旧数据回放。
- **Pseudo-rehearsal MBRL**：使用预训练 VAE 生成旧数据（无持续训练）。
- **DRAGO 的各种变体**：去除合成经验回放、去除内在奖励等。

## 4. 资源与算力

- 论文中**未明确说明**所使用的 GPU 型号、数量、具体训练时长等算力信息。
- 仅在致谢中提到计算资源来自布朗大学计算与可视化中心（CCV），但未提供详细硬件规格。
- 训练最大步数：MiniGrid 100步/episode，Cheetah/Walker 1000步/episode；总步数未明确给出。

## 5. 实验数量与充分性

- **实验数量**：覆盖3个领域（MiniGrid、Cheetah、Walker），总共设计了**12个测试任务**（每个领域4个）。每个实验均报告平均奖励与标准差（通常3-5个随机种子）。
- **消融实验**：包括去除合成回放、去除内在奖励、不同VAE更新频率、规划地平线影响、是否使用Q值规划等。
- **额外对比**：与好奇心基线、PETS 结合版本（附录）、少样本迁移性能（表1）等。
- **充分性分析**：
  - **优点**：实验场景多样（离散网格、连续控制），对比方法全面（从 scratch、naive continual、EWC 到 replay-based 等），消融实验细致，验证了两个组件的必要性。
  - **不足**：所有环境均假设任务切换已知，且任务数量有限（4个），未验证更多任务或更复杂高维环境（如像素级输入）下的可扩展性。此外，未在真实机器人平台进行验证。

## 6. 主要结论与发现

- DRAGO 在**所有测试任务上均优于** naive continual MBRL 和 EWC，显著缓解了灾难性遗忘。
- **合成经验回放**和**内在奖励探索**两者结合效果最佳，单独使用任一组件也能提升性能，但全版本最优。
- 在少样本迁移场景（仅20个episode）中，DRAGO 在8个测试任务中6个取得最好结果，另外2个也保持竞争力。
- 可视化热图表明，DRAGO 能保留先前任务的知识区域，而 naive 方法几乎完全遗忘旧任务。
- 在持续训练任务本身，DRAGO 没有明显损害当前任务的学习效率（与 Continual TD-MPC 性能相近）。

## 7. 优点

- **无需存储旧数据**：解决了存储、隐私、在线部署等现实约束，具有强实用性。
- **两个组件设计巧妙**：生成式回放模拟“梦境”巩固记忆，内在奖励引导主动探索连接不同任务区域，相辅相成。
- **基于 TD-MPC** 的集成方案简洁有效，评审者-学习者结构解耦了探索与利用目标。
- **实验全面**：覆盖离散和连续控制，多组消融、对比、可视化分析，验证了方法的鲁棒性。
- **消融实验公平**：对比了多种基线，包括 EWC、好奇心、有限回放等。

## 8. 不足与局限

- **生成模型的长期遗忘风险**：只维护一个 VAE，随着任务数增长可能发生模式坍塌，导致合成数据质量下降。论文承认这一点，但未在更多任务上测试。
- **任务数量有限**：仅验证了4个任务的序列，现实场景可能面临数十甚至数百个任务，遗忘累积效应可能更严重。
- **任务切换假设已知**：实际中可能无法准确检测任务切换点。
- **未探索像素级输入**：所有实验使用低维状态（如位置、速度），高维视觉情况下生成模型质量与探索效率待验证。
- **计算开销**：需要同时训练学习者和评审者两个策略及价值网络，并额外训练 VAE，相比 naive 方法增加了计算资源需求，但论文未详细分析。
- **未提及代码复现细节**：虽然提供了 GitHub 链接，但超参数表仅在附录中给出，部分关键参数（如合成数据更新频率）的影响分析不够深入。

（完）
