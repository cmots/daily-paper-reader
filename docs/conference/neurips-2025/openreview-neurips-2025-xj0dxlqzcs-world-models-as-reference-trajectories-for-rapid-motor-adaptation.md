---
title: World Models as Reference Trajectories for Rapid Motor Adaptation
title_zh: 世界模型作为快速运动适应的参考轨迹
authors: "Carlos Stein Brito, Daniel C McNamee"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=xj0DXLQZCS"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 世界模型用于强化学习中的快速运动适应
tldr: 学习型控制策略在动态变化环境中性能下降，重新训练成本高。本文提出反思世界模型（RWM），将世界模型预测作为隐式参考轨迹，分离长期强化学习奖励最大化与快速运动执行，在保持近优性能的同时，实现比基于模型的RL基线更快的在线适应和低计算开销。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-xj0dxlqzcs/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xj0dxlqzcs/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1419, \"height\": 719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xj0dxlqzcs/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1286, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xj0dxlqzcs/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1421, \"height\": 717, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xj0dxlqzcs/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1424, \"height\": 334, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-xj0dxlqzcs/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 926, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xj0dxlqzcs/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1516, \"height\": 401, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xj0dxlqzcs/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1087, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xj0dxlqzcs/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1519, \"height\": 807, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xj0dxlqzcs/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 763, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xj0dxlqzcs/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1385, \"height\": 382, \"label\": \"Table\"}]"
motivation: 环境动态变化导致学习策略失效，现有方法适应慢或计算成本高。
method: 提出RWM双控制框架，使用世界模型预测作为隐式参考轨迹，将长期RL与快速潜空间控制分离。
result: 在多个仿真和真实场景中，RWM适应速度显著提升，在线计算量低，性能接近最优。
conclusion: 世界模型可作为参考轨迹实现快速适应，兼顾长期优化与短期鲁棒性。
---

## Abstract
Learned control policies often fail when deployed in real-world environments with changing dynamics. When system dynamics shift unexpectedly, performance degrades until models are retrained on new data. We introduce Reflexive World Models (RWM), a dual control framework that uses world model predictions as implicit reference trajectories for rapid adaptation. Our method separates the control problem into long-term reward maximization through reinforcement learning and robust motor execution through reward-free rapid control in latent space. This dual architecture achieves significantly faster adaptation with low online computational cost compared to model-based RL baselines, while maintaining near-optimal performance. The approach combines the benefits of flexible policy learning through reinforcement learning with rapid error correction capabilities, providing a theoretically grounded method for maintaining performance in high-dimensional continuous control tasks under varying dynamics.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义
- **研究动机**：在现实世界中，学习型控制策略（基于强化学习）常因环境动态变化（如物理磨损、环境扰动等）而性能急剧下降。标准方法需要重新训练模型，适应速度慢、计算成本高。
- **关键挑战**：现有基于模型的强化学习方法在动态改变时，其规划（planning）和值估计（value computation）会退化；而经典自适应控制虽能快速适应，但依赖明确的参考轨迹和人工设计的代价函数，难以应用于高维、复杂的任务。
- **核心目标**：提出一种能快速、奖励无关地适应动态变化，同时保持长期性能的持续控制框架。

## 2. 方法论
- **核心思想**：提出“反思世界模型”（Reflexive World Models, RWM）。框架将控制问题分解为两个并行的功能模块：
    - **慢速学习模块**：通过强化学习（RL）学习基础策略（base policy, π₀），旨在实现长期奖励最大化。
    - **快速适应模块**：通过一个无奖励的自适应控制器（controller policy, πc），在潜空间中执行快速误差校正，以维持执行准确性。
- **关键技术细节**：
    1.  **潜空间世界模型**：利用编码器（encoder）将观测映射到连续潜空间（z）。学习一个前向动力学模型（forward model, F）来预测给定当前状态和基础策略动作下的下一个潜状态（ẑ_{t+1}=F(z_t, a_0)）。
    2.  **参考轨迹生成**：将世界模型的单步预测（ẑ_{t+1}）作为自适应控制器的“隐含参考轨迹”。框架的核心是**反转**了标准模型学习中的关系：不再让模型去适应现实，而是让控制器采取行动使现实去匹配模型的预测。
    3.  **控制误差与更新**：定义控制误差为预测潜状态与实际潜状态的均方误差（MSE: L = ||ẑ_{t+1} - z_{t+1}||²）。自适应控制器通过梯度下降法进行更新，梯度方向为**使损失函数相对于基础策略动作的导数取反**（即 θ_c ← θ_c - η_c * (-∂L/∂a0) * (∂ac/∂θ_c)），从而在不需要奖励信号的情况下进行快速适应。
    4.  **阈值化动作成本**：为解决基础策略的动作饱和或衰减问题，在π₀的预训练中引入了一个特殊的阈值化二次动作惩罚（λ * max(0, |a_i| - c)²），确保基础策略工作在平滑、非饱和区域，为控制器留出调整空间。
    5.  **整体流程（算法1）**：每个时间步，系统根据当前编码状态执行基础策略动作 a₀ 和自适应动作 a_c，组合后作用于环境。控制器通过最小化世界模型预测的潜状态误差来在线更新 π_c。

## 3. 实验设计
- **环境与场景**：使用 DeepMind Control Suite 中的多类连续控制任务：
    - 2D点质量系统（简单）
    - 标准运动：Walker-Run, Cheetah-Run, Hopper-Hop（中等复杂度）
    - 操作任务：Ball-in-Cup
    - 高维协调：Humanoid-Walk（17个执行器）
- **扰动类型**：
    - **阶跃扰动**：模拟执行器突然校准错误，瞬间改变动作增益。
    - **非平稳扰动**：通过滤波噪声模拟执行器随时间的渐时漂移（如磨损、温度影响）。
- **对比基准（Baseline）**：
    - 冻结策略（Frozen Policy）：不进行任何适应。
    - 奖励微调（Fine-tuning）：在扰动出现后继续基于奖励信号微调策略。
    - TD-MPC2（有无规划器）：作为基于模型强化学习的代表性基线。在人形任务中使用带规划器的版本，在标准运动任务中使用无规划器的版本，以减少实验混淆。
    - 域随机化（Domain Randomization）基线：让基线策略在预训练时暴露于同样的扰动，以测试 RWM 的在线适应是否仍有优势。
- **评估指标**：主要比较奖励下降（Reward Drop）和潜空间控制误差（Control Error）。

## 4. 资源与算力
- **GPU型号与数量**：实验在**单张** NVIDIA Tesla T4 GPU（16 GB GDDR6）上运行。
- **训练时长**：
    - 预训练阶段（通用）：约 16–17 小时。
    - **RWM 在线适应阶段（1百万步）**：约 **1.8 小时**，远低于需要完整重训练的基线（16.5小时）。
    - 无适应推理阶段（No Adaptation）：约 1.4 小时。
- **总结**：RWM 的在线计算开销极低，其轻量级的控制器更新是其主要优势。

## 5. 实验数量与充分性
- **实验数量**：论文在 **5 种以上不同难度的任务**上进行了实验，覆盖了从简单点质量到17自由度人形机器人。针对每种任务，都进行了阶跃扰动和非平稳扰动测试（如Walker2D）。此外，还进行了**域随机化对比实验**（附录D）以及**与无规划器/有规划器TD-MPC2的对比实验**（附录E）。整体实验数量充足，覆盖了多种复杂度场景。
- **充分性与客观性**：
    - 实验设计比较规范，结果显示 **RWM 在几乎所有任务上均优于或与微调方法持平**，且在无奖励信号的情况下仍能保持性能。
    - 针对人形等高维任务，RWM 特别能保持核心的协调运动模式，而微调方法反而破坏了原有程序。
    - 实验结果附有区间统计（如 95% 置信区间），并说明了执行过程。
    - 存在一定的**评估偏差风险**：主要聚焦于特定的**执行器扰动**（增益变化），对于其他类型的环境变化（如形态改变、传感器噪声）的测试较为有限。

## 6. 主要结论与发现
1.  **世界模型可作为有效的参考轨迹**：RWM 成功证明了将世界模型的单步预测作为隐含参考轨迹，能在无奖励信息的情况下实现快速、高效的运动适应。
2.  **分离学习与控制是关键**：将长期的RL奖励最大化与快速、奖励无关的误差校正模块分离，在适应速度和维持原有策略执行完整性方面均优于传统微调方法。
3.  **理论保障**：论文提供了形式化的理论分析，证明了当控制误差有界时，任务的性能（值函数）也能被界定量化，建立了控制误差与性能之间的数学联系。
4.  **实际优势**：RWM 的在线更新计算成本极低（轻量级梯度更新），适合部署于对实时性要求高的物理系统。其在面对非平稳动态变化时，表现出比域随机化更强的适应能力。

## 7. 优点（亮点）
- **方法创新性强**：创造性地将模型预测与经典自适应控制（如 MRAC）思想结合，反转了模型与控制的传统关系，提供了一个理论扎实的持续适应框架。
- **无需奖励信号**：RWM 的关键优势在于，其适应过程不需要奖励信号，这在奖励稀疏或无法获取的离线/真实部署场景下具有重要价值。
- **理论严谨**：给出了控制误差界和性能界的数学推导，使方法具有一定的形式化保证，增加了框架的可信度。
- **实验设计合理**：实验覆盖多个任务和扰动类型，并对**运行效率**做了明确比较，凸显了 RWM 在计算效率上的显著优势。同时，实验实现了**域随机化对比**，说明在线适应机制不是简单鲁棒训练能做到的。
- **问题焦点明确**：研究集中于在线快速适应问题，不做额外工程优化，便于学术分析与复现。

## 8. 不足与局限
- **扰动类型有限**：论文主要测试了**执行器增益变化**这一种扰动。对于形态变化、环境物理参数变化、传感器噪声等其他类型的动态变化，RWM 的表现尚未验证。
- **依赖预训练**：RWM 强烈依赖一个预训练好的、提供编码器和世界模型的基础RL代理（如TD-MPC2）。这个预训练过程昂贵（16-17小时），且模型质量直接影响在线适应效果。
- **对基础策略有特殊要求**：为了确保自适应控制器的正常运作，需要对基础策略施加“阈值化动作成本”这种特定惩罚，这可能限制了它直接应用到任意、未经特殊设计的预训练策略上。
- **理论假设较强**：论文的理论保证依赖于如控制权威性、模型准确性等假设。在高度复杂或欠驱动的系统中，这些假设可能不完全成立，理论界可能放宽或失效。
- **实验范围仍有限**：尽管覆盖了仿真环境，但**没有在真实机器人上进行实验**，其向物理世界迁移的鲁棒性有待验证。

（完）
