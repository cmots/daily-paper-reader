---
title: Dynamics-Aligned Latent Imagination in Contextual World Models for Zero-Shot Generalization
title_zh: 面向上下文世界模型的对齐动态潜在想象用于零样本泛化
authors: "Frank Röder, Jan Benad, Manfred Eppe, Pradeep Kr. Banerjee"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=41bIzD5sit"
tags: ["query:wm-vla-sa"]
score: 10.0
evidence: 用于强化学习与规划的世界模型
tldr: 针对真实世界强化学习在未知环境泛化困难的问题，本文提出了Dynamics-Aligned Latent Imagination (DALI)，将自监督上下文编码器集成到Dreamer架构中，从智能体与环境交互中推断潜在上下文表示，从而无需显式变量即可实现零样本泛化。理论证明可证明其有效性，实验表明在多种环境下的泛化性能显著提升。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-41bizd5sit/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 1430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-41bizd5sit/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1423, \"height\": 901, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-41bizd5sit/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1344, \"height\": 1098, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-41bizd5sit/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1449, \"height\": 1087, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-41bizd5sit/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 728, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-41bizd5sit/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1425, \"height\": 918, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-41bizd5sit/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1433, \"height\": 2154, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-41bizd5sit/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1390, \"height\": 355, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-41bizd5sit/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1126, \"height\": 567, \"label\": \"Table\"}]"
motivation: 现有方法需要显式上下文变量，限制了在潜在或难以测量环境中的使用。
method: 提出DALI框架，在Dreamer中训练自监督编码器预测前向动态，生成可操作的上下文表示以调节世界模型和策略。
result: 在多个基准任务中实现了零样本泛化，性能优于基线方法。
conclusion: DALI通过隐式上下文推断有效提升了世界模型在未知环境中的适应能力。
---

## Abstract
Real-world reinforcement learning demands adaptation to unseen environmental conditions without costly retraining. Contextual Markov Decision Processes (cMDP) model this challenge, but existing methods often require explicit context variables (e.g., friction, gravity), limiting their use when contexts are latent or hard to measure. We introduce Dynamics-Aligned Latent Imagination (DALI), a framework integrated within the Dreamer architecture that infers latent context representations from agent-environment interactions. By training a self-supervised encoder to predict forward dynamics, DALI generates actionable representations conditioning the world model and policy, bridging perception and control. We theoretically prove this encoder is essential for efficient context inference and robust generalization. DALI’s latent space enables counterfactual consistency: Perturbing a gravity-encoding dimension alters imagined rollouts in physically plausible ways. On challenging cMDP benchmarks, DALI achieves significant gains over context-unaware baselines, often surpassing context-aware baselines in extrapolation tasks, enabling zero-shot generalization to unseen contextual variations.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：真实世界的强化学习（RL）要求智能体能够适应未见过的环境条件，而无需昂贵的重新训练。上下文马尔可夫决策过程（cMDP）形式化了这一挑战，但现有方法通常需要显式的上下文变量（如摩擦系数、重力加速度），当上下文是潜在的或难以测量时，这些方法便失效。例如，机器人需要根据表面摩擦调整步态，但无法直接获得摩擦系数。
- **整体含义**：本文旨在开发一种自监督的方式，让RL智能体从交互历史中推断潜在上下文，从而实现零样本泛化（zero-shot generalization），即在不经过微调的情况下应对未见过的环境变化。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：提出 Dynamics-Aligned Latent Imagination (DALI) 框架，集成在 DreamerV3 架构中。通过一个自监督的上下文编码器，从智能体与环境交互的短窗口中推断潜在上下文表示，并用该表示来调节世界模型和策略，从而实现零样本泛化。
- **关键技术细节**：
  - **上下文编码器**：使用 Transformer 编码器，将长度为 K 的观测-动作历史映射为一个潜在上下文向量 z_t ∈ R⁸。
  - **前向动力学对齐损失**：`L_FD = E[∥o_{t+1} - f_wφ(o_t, a_t, z_t)∥²]`，使得 z_t 能够预测下一观测，从而捕获对动力学至关重要的上下文因素。
  - **跨模态正则化损失**：`L_cross = E[∥z_t - W_z z_t∥²] + E[∥z_t - W_{zt} z_t∥²]`，对齐上下文编码器输出 z_t 与 DreamerV3 的后验随机状态 z_t，增强鲁棒性。
  - **集成到 DreamerV3**：提供浅层集成（Shallow Integration，z_t 仅加入编码器）和深层集成（Deep Integration，z_t 加入序列模型、奖励预测、策略和价值函数）。
  - **训练策略**：冻结世界模型参数，仅更新编码器参数 φ 和线性映射矩阵；通过停止梯度传播以避免上下文学习干扰世界模型。

## 3. 实验设计：数据集/场景、benchmark、对比方法

- **数据集/场景**：基于 CARL 基准的上下文化 DMC（DeepMind Control Suite）任务：
  - **Ball-in-Cup**（球与杯）：上下文参数为重力（gravity）和绳长（string length）。
  - **Walker Walk**（步行机器人）：上下文参数为重力和执行器强度（actuator strength）。
- **Benchmark**：上下文范围分为训练/插值和外推（OOD）区间，评估三种泛化模式：插值（Interpolation）、外推（Extrapolation）、混合（Mixed，一个维度外推，一个维度插值）。
- **对比方法**：
  - **上下文无关基线**：Dreamer-DR (DreamerV3 + 领域随机化)。
  - **上下文感知基线**：cRSSM-S 和 cRSSM-D（使用真实上下文 c 的 DreamerV3 变体）。
  - **DALI 变体**：DALI-S（浅层集成）、DALI-S-χ（浅层 + 跨模态正则化）、DALI-D、DALI-D-χ。
- **观测模态**：Featurized（结构化状态输入）和 Pixel（原始图像输入）。

## 4. 资源与算力

- 论文明确说明了计算资源：**NVIDIA A100 GPU (80GB VRAM)**，CPU 为 Intel Xeon Platinum 8352V。
- **训练时间**：每个 trial 约 1-2 天，取决于观测模态。
- **实验总量**：共 600 个独立训练 runs（10 种子 × 5 算法变体 × 2 环境 × 2 模态 × 3 上下文设置）。
- **总 GPU 小时**：若串行执行约 24,000 GPU 小时。通过并行化（最多 4 块 GPU），实际墙钟时间约 1,051 小时（最优）至 2,101 小时（典型）。
- **说明**：算力消耗较大，但文章中给出了详细分解，可复现。

## 5. 实验数量与充分性

- **实验数量**：覆盖 2 种环境、2 种观测模态、5 种算法变体、10 个随机种子、3 种泛化模式，总计 600 次运行。还额外在 DMC Quadruped Walk 上进行了扩展实验。
- **充分性**：实验设计全面，包含了插值、外推、混合三种泛化场景；对比了有无上下文、真实上下文与推断上下文；使用了 IQM（四分位均值）和 PoI（改进概率）等稳健指标，并报告了 95% 置信区间。消融实验（跨模态正则化）也做了分析。因此实验充分、客观、公平。

## 6. 论文的主要结论与发现

- **性能提升**：在外推场景下，DALI-S-χ 相比 Dreamer-DR 在 Ball-in-Cup 上提升高达 +96.4%（Pixel），在 Walker Walk 上 DALI-S 提升 +4.0%~+11.3%，且多数情况下优于使用真实上下文的 cRSSM 基线（最高 +63.9%），表明推断的上下文表征比真实上下文更具泛化性。
- **理论支撑**：证明了上下文编码器对于高效上下文推断和鲁棒泛化是必要的，且其采样复杂度低于 DreamerV3 的循环状态。
- **物理一致性**：通过扰动潜在空间维度（如重力编码维度），可以生成符合牛顿力学的反事实轨迹（如球更快下落、绳长变短），验证了表征的因果结构。

## 7. 优点：方法或实验设计上的亮点

- **方法创新**：将自监督上下文编码器无缝集成到 DreamerV3 中，无需任何真实上下文标签，实现了零样本泛化。理论证明与经验结果一致。
- **实验设计规范**：遵循 CARL 基准和 rliable 框架，使用 IQM、PoI、95% 置信区间，评估了多种泛化模式，消融了不同集成策略和正则化项。
- **可解释性**：通过反事实实验验证了潜在表征的物理意义，增强了方法的可信度。
- **效率**：DALI 仅增加约 4% 的参数（DreamerV3-small 的 15.73M → 16.45M），参数开销小。

## 8. 不足与局限

- **理论局限**：理论分析（定理 1）假设了 β-mixing 和 Lipschitz 动力学，但未直接建模上下文表示对策略性能的下游影响。在稀疏奖励、高维状态空间或慢混合环境中，可能失效。
- **实验局限**：仅测试了两个 DMC 环境（Ball-in-Cup 和 Walker Walk），虽然增加了 Quadruped Walk，但整体环境多样性有限。需要更多复杂环境验证（如视觉丰富场景、机器人操控）。
- **集成策略选择**：浅层集成效果最佳，但作者未深入分析其正则化效应；深层集成在某些场景（Pixel 混合）反而不如上下文感知基线，说明集成策略需任务依赖。
- **计算成本**：训练时间较长（每种子 1-2 天），可能限制实际应用。
- **未探讨迁移到真实世界**：所有实验均在模拟器中完成，真实世界的观测噪声、延迟和部分可观测性可能带来额外挑战。

（完）
