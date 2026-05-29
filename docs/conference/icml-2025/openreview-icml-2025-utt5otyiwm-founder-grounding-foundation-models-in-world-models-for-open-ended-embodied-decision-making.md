---
title: "FOUNDER: Grounding Foundation Models in World Models for Open-Ended Embodied Decision Making"
title_zh: FOUNDER：将基础模型锚定到世界模型实现开放式具身决策
authors: "Yucen Wang, Rui Yu, Shenghua Wan, Le Gan, De-Chuan Zhan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=UTT5OTyIWm"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 将基础模型锚定到世界模型用于具身决策与规划
tldr: 针对具身智能中基础模型与环境动态建模分离的问题，提出FOUNDER框架，将基础模型的通用知识映射到世界模型状态空间，通过想象进行目标条件策略学习，从而在无需奖励的情况下实现开放式任务求解。实验表明该方法能有效利用世界模型动力学进行规划。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-utt5otyiwm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1758, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-utt5otyiwm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1774, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-utt5otyiwm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 858, \"height\": 457, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-utt5otyiwm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1771, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-utt5otyiwm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1774, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-utt5otyiwm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1382, \"height\": 545, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-utt5otyiwm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1753, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-utt5otyiwm/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1753, \"height\": 419, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-utt5otyiwm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1583, \"height\": 915, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-utt5otyiwm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 915, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-utt5otyiwm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1783, \"height\": 1231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-utt5otyiwm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1193, \"height\": 1074, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-utt5otyiwm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1247, \"height\": 453, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-utt5otyiwm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1786, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-utt5otyiwm/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1603, \"height\": 364, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-utt5otyiwm/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 922, \"height\": 1858, \"label\": \"Table\"}]"
motivation: 基础模型与世界模型优势互补，但缺乏有效集成来应对开放式具身任务。
method: 学习映射函数将基础模型表示转换到世界模型状态空间，并在行为学习阶段通过想象训练目标条件策略。
result: 在具身环境中的开放式任务求解中展现了良好的泛化能力和零样本迁移效果。
conclusion: 提出了一种无奖励的集成框架，有效结合了基础模型的通用知识与世界模型的动态建模能力。
---

## Abstract
Foundation Models (FMs) and World Models (WMs) offer complementary strengths in task generalization at different levels. In this work, we propose FOUNDER, a framework that integrates the generalizable knowledge embedded in FMs with the dynamic modeling capabilities of WMs to enable open-ended task solving in embodied environments in a reward-free manner. We learn a mapping function that grounds FM representations in the WM state space, effectively inferring the agent's physical states in the world simulator from external observations. This mapping enables the learning of a goal-conditioned policy through imagination during behavior learning, with the mapped task serving as the goal state. Our method leverages the predicted temporal distance to the goal state as an informative reward signal. FOUNDER demonstrates superior performance on various multi-task offline visual control benchmarks, excelling in capturing the deep-level semantics of tasks specified by text or videos, particularly in scenarios involving complex observations or domain gaps where prior methods struggle. The consistency of our learned reward function with the ground-truth reward is also empirically validated. Our project website is https://sites.google.com/view/founder-rl.

---

## 论文详细总结（自动生成）

# 论文总结：FOUNDER: Grounding Foundation Models in World Models for Open-Ended Embodied Decision Making

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：如何将基础模型（FMs，如视频-语言模型）的通用知识与世界模型（WMs，如Dreamer系列）的环境动态建模能力有效整合，以解决无奖励信号（reward-free）的开放式具身决策任务？现有方法（如GenRL）仅使用视觉特征进行逐帧对齐，缺乏时间感知和对任务深度语义的理解，在复杂观察或跨域场景中容易失败。
- **背景**：FMs提供了高层语义理解，WMs擅长低层动力学建模和样本高效的想象规划，但WMs缺少先验知识，无法直接解释人类提示（文本/视频）指定的任务。本文旨在桥接两者，使智能体无需真实奖励即可从离线数据中学习，并泛化到多模态任务。

## 2. 论文提出的方法论

- **核心思想**：通过学习一个映射函数，将FM生成的表示（如视频/文本嵌入）转换为WM状态空间中的目标状态，然后在WM的想象轨迹中利用预测的**时间距离**作为奖励信号，进行目标条件强化学习（GCRL）。
- **关键技术细节**：
  - **阶段一：世界模型学习**  
    使用DreamerV3架构（RSSM骨干），仅基于离线数据中的状态-动作对训练WM（不含奖励模型），最大化证据下界（ELBO）。
  - **阶段二：映射函数学习**  
    利用离线轨迹：用FM处理短观察序列得到嵌入\( e_t \)，用WM编码得到对应隐状态\( z_t \)，学习映射\( Q_\psi: e_t \to \hat{z}_t \)，最小化\( \hat{z}_t \)与\( z_t \)的KL散度，并添加自编码重构损失\( -\ln P_\psi(e_t|\hat{z}_t) \)以避免序列建模。最终可将任意任务提示嵌入映射为目标状态\( z_g \)。
  - **阶段三：时间距离预测器**  
    训练一个模型\( D_\theta \)预测两个WM状态之间的时间步数（归一化），采用MSE损失，包括同一轨迹正样本对和不同轨迹负样本对。
  - **阶段四：行为学习（GCRL）**  
    在WM中想象展开轨迹，使用\( r_D(z_t, z_g) = -D_\theta(z_t, z_g) \)作为奖励，采用Dreamer风格的Actor-Critic学习目标条件策略。
- **算法流程**：离线数据 → WM预训练 → 映射函数+距离预测器预训练 → 对给定任务提示，用映射函数得到目标状态 → 在WM中想象并优化策略。

## 3. 实验设计

- **数据集/场景**：
  - **DeepMind Control Suite (DMC)**：Cheetah, Walker, Quadruped, Stickman（4种形态），任务包括Stand, Walk, Run, Flip。
  - **Franka Kitchen**：5种操作任务（Light, Slide, Microwave, Burner, Kettle）。
  - **Minecraft**（Minedojo基准）：5个任务（Hunt Cow, Shear Sheep, Chop Trees, Milk Cow, Hunt Sheep）。
- **Benchmark**：多任务离线视觉控制，无奖励信号，仅给离线状态-动作数据集和VLM（InternVideo2）。
- **对比方法**：
  - 主要基线：GenRL（逐帧序列匹配）、WM-CLIP（逆向映射+FM空间相似度奖励）、GenRL-TempD（在GenRL中加入时间距离）、FOUNDER w/o TempD（FOUNDER去掉时间距离，用余弦相似度）。
  - 额外对比：模型无关方法（IQL, TD3+BC, HILP, TD3）和MineCLIP-IQL（Minecraft中的oracle）。
- **实验设置**：500K梯度步预训练，50K（DMC/Kitchen）或100K（Minecraft）行为学习步。跨越语言、跨领域视频（跨形态、跨视角）和真实世界视频任务。

## 4. 资源与算力

- **文中说明**：所有实验在单张RTX 3090 GPU上进行。FOUNDER预训练约需3天（Dreamer-style WM+映射函数+距离预测器），而GenRL预训练约需5天（MFWM序列建模）。下游任务微调50K步约需5小时。
- **未明确内容**：未提及使用的GPU数量（可能是1张），也未提及推断时具体算力需求。

## 5. 实验数量与充分性

- **实验数量**：
  - 语言任务：DMC上16个任务 + Kitchen上5个任务，共19个任务，6种子（除了Kitchen是4种子？）→ 约114次运行。
  - 跨形态视频：Run和Flip各12个域组合（共12任务），4种子 → 48次运行。
  - 跨视角视频：DMC + Kitchen共6个任务，4种子 → 24次运行。
  - 真实世界视频：5个任务，每方法单次或多次（未说明种子数）。
  - Minecraft：5个任务，3种子，对比GenRL和MineCLIP-IQL。
  - 奖励函数评估：7个DMC任务，计算多种指标。
  - 消融分析：FOUNDER w/o TempD（主表），以及案例研究。
- **充分性**：实验覆盖多个领域（运动控制、操作、Minecraft）、多种任务（静态/动态）、多种提示模态（文本/视频）、多种域偏移（跨形态、跨视角、真实→仿真）。统计数据较充分（多种子，标准差报告），对比基线全面，还包括模型无关方法和oracle。结论可信度高。

## 6. 主要结论与发现

- FOUNDER在19个语言任务中总体归一化得分0.81，显著优于GenRL（0.60）、WM-CLIP（0.57）等基线。
- 在跨形态和跨视角视频任务中，FOUNDER在11/12个跨形态任务和多数跨视角任务上取得最佳，是唯一在Cheetah形态上完全成功的方案。
- 奖励评估表明FOUNDER的伪奖励与真实奖励的相关性最高（Corr=0.54），精度完美（Precision=1.0），有效避免奖励劫持。
- 在Minecraft中，FOUNDER在5个任务中有3个显著优于GenRL，并接近或超过oracle方法MineCLIP-IQL。
- 时间距离奖励信号对于动态任务至关重要，防止了仅模仿视觉特征的奖励劫持；而整体的FOUNDER架构（目标映射 + GCRL + 时间距离）是性能提升的根本原因。

## 7. 优点

- **方法创新**：提出将FM表示映射到WM状态空间的全新范式，实现高层语义与低层动力学的无缝桥接，无需手工设计奖励。
- **高效性**：映射函数学习无需复杂的序列生成（如GenRL的seq2seq），预训练时间更短（3天对5天）。
- **强泛化**：在跨形态、跨视角、真实-仿真等多种域偏移下均表现优越，表明其能够捕获任务深层语义而非表面视觉特征。
- **奖励质量**：时间距离作为奖励信号鲁棒且可解释，与真实奖励高度一致，避免奖励劫持。
- **全面实验**：涵盖多种环境、任务、模态和域偏移，并进行奖励一致性评估和消融，说服力强。

## 8. 不足与局限

- **数据依赖**：方法性能上限受限于离线数据集的质量和覆盖范围；如果提示元素未在数据中出现，可能无法正确接地。
- **任务范围**：当前实验主要集中在短视距任务（short-horizon），未充分验证长视距任务和任务分解能力。
- **世界模型限制**：使用DreamerV3作为WM，可能不适合更复杂的环境或需要长期记忆的任务。文中提到未来可结合更强的序列建模和大语言模型来改进。
- **跨域泛化的边界**：虽然跨形态有效，但文中未探索更大形态差异（例如从人类视频到机器人），也未在真实机器人上验证。
- **计算可重复性**：虽报告了种子和置信区间，但未提供所有超参数列表（例如DreamerV3的具体配置），可能影响精确复现。
- **潜在偏差风险**：VLM（InternVideo2）是预训练模型，其语义理解可能存在偏差，影响映射准确性；文中未深入分析VLM错误输入的影响。

（完）
