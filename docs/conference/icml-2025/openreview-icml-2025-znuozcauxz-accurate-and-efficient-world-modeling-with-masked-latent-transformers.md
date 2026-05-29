---
title: Accurate and Efficient World Modeling with Masked Latent Transformers
title_zh: 基于掩码潜在变换器的精确高效世界建模
authors: "Maxime Burchi, Radu Timofte"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=zNUOZcAUxz"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 使用掩码潜在变换器的精确高效世界建模
tldr: 本文提出EMERALD方法，通过掩码潜在变换器构建既精确又高效的世界模型，解决了Dreamer等算法中潜在空间信息丢失的问题。EMERALD在保持训练效率的同时提升了模型准确性，使智能体能从世界模型的内在表征中受益，在多样环境域中取得更好性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-znuozcauxz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 856, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-znuozcauxz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1773, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-znuozcauxz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1731, \"height\": 933, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-znuozcauxz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1778, \"height\": 824, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-znuozcauxz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 841, \"height\": 587, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-znuozcauxz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1547, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-znuozcauxz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1762, \"height\": 566, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-znuozcauxz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 823, \"height\": 578, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-znuozcauxz/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1344, \"height\": 683, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-znuozcauxz/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1167, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-znuozcauxz/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1594, \"height\": 1950, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-znuozcauxz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1754, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-znuozcauxz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 869, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-znuozcauxz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1766, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-znuozcauxz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 804, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-znuozcauxz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1579, \"height\": 1119, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-znuozcauxz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 800, \"height\": 624, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-znuozcauxz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1094, \"height\": 490, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-znuozcauxz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 770, \"height\": 791, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-znuozcauxz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1124, \"height\": 576, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-znuozcauxz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 718, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-znuozcauxz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 880, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-znuozcauxz/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 964, \"height\": 1780, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-znuozcauxz/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1614, \"height\": 940, \"label\": \"Table\"}]"
motivation: 现有世界模型在潜在空间压缩时丢失信息，影响智能体性能。
method: 使用掩码潜在变换器改进世界建模，平衡精度与效率。
result: EMERALD在多个环境域中获得比Dreamer等更强性能，且训练高效。
conclusion: 所提方法为强化学习世界模型提供了准确且高效的替代方案。
---

## Abstract
The Dreamer algorithm has recently obtained remarkable performance across diverse environment domains by training powerful agents with simulated trajectories. However, the compressed nature of its world model's latent space can result in the loss of crucial information, negatively affecting the agent's performance. Recent approaches, such as $\Delta$-IRIS and DIAMOND, address this limitation by training more accurate world models. However, these methods require training agents directly from pixels, which reduces training efficiency and prevents the agent from benefiting from the inner representations learned by the world model. In this work, we propose an alternative approach to world modeling that is both accurate and efficient. We introduce EMERALD (Efficient MaskEd latent tRAnsformer worLD model), a world model using a spatial latent state with MaskGIT predictions to generate accurate trajectories in latent space and improve the agent performance. On the Crafter benchmark, EMERALD achieves new state-of-the-art performance, becoming the first method to surpass human experts performance within 10M environment steps. Our method also succeeds to unlock all 22 Crafter achievements at least once during evaluation.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题背景**：基于模型的强化学习中，Dreamer 算法通过训练世界模型在潜在空间生成模拟轨迹来训练智能体，取得了显著性能。然而，其潜在空间的压缩特性（使用向量潜在空间）会导致关键细节信息的丢失，例如在 Crafter 环境中无法准确感知钻石、骷髅弓箭等关键物体，从而限制了智能体的性能。
- **现有方法的局限**：近期提出的 Δ-IRIS 和 DIAMOND 等更准确的世界模型，通过像素空间重建或扩散模型提高了轨迹质量，但它们要求智能体直接从重建图像中学习策略，降低了训练效率，且无法利用世界模型内部学到的隐藏表征（如长期记忆）。
- **本文目标**：提出一种既准确又高效的世界建模替代方案——EMERALD（Efficient MaskEd latent tRAnsformer worLD model），通过空间潜在状态和 MaskGIT 预测，在潜在空间生成精确轨迹，同时保持训练效率，让智能体能受益于世界模型的内部表征。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：使用**空间潜在状态（spatial latent state）** 替代传统的向量潜在状态，以保留更多空间信息；采用**MaskGIT 预测器**进行非自回归的并行解码，在不损失准确性的前提下提升效率；智能体在潜在空间中进行想象学习，避免从像素重建中学习。
- **关键技术细节**：
  - **世界模型组件**：
    - **编码器**：将输入图像编码为空间潜在状态 \( z_t \in \mathbb{R}^{H \times W \times G \times (D/G)} \)，其中 \( H \times W = 4 \times 4 \)，\( G=32 \) 个特征组，每组 32 个类别。采用分组软最大化采样，支持高效的离散表示。
    - **时间掩码变换器（Temporal Masked Transformer）**：基于 Transformer 的状态空间模型（TSSM），使用掩码自注意力与相对位置编码，建模长程依赖，输出隐藏状态 \( h_t \in \mathbb{R}^{T \times D} \)。采用截断反向传播（TBTT）和缓存键值对以保留跨批次信息。
    - **空间 MaskGIT 预测器**：接收空间上采样的隐藏状态和部分掩码的潜在状态，预测被掩码的 tokens。训练时从余弦调度中采样掩码比例，最小化预测分布与目标分布的 KL 散度。在想象阶段使用多次（S=3 步）迭代解码：每步保留高置信度 tokens，重新掩码低置信度 tokens 并再次预测，逐步细化。
    - **解码器**：结合空间潜在状态和隐藏状态，重构图像，使用 MSE 损失。
    - **奖励和继续预测器**：采用 DreamerV3 的 symlog 交叉熵损失，预测奖励和回合结束标志。
  - **训练损失**：包括 MaskGIT 预测损失、动力学损失（含正则项）、重建损失、奖励损失和继续损失，所有损失按时间步平均。
  - **智能体学习**：在潜在空间通过想象轨迹，使用 actor-critic 方法。actor 和 critic 网络均为简单 MLP，接收组合状态 \( s_t = [z_t, h_t] \)。critic 学习 symlog 离散化的 λ-return，并加入 EMA 正则项；actor 使用 REINFORCE 与熵正则项最大化回报。想象步数 H=15。
- **算法流程**：首先从回放缓冲区采样轨迹序列，编码得到潜在状态；然后通过时间变换器生成隐藏状态；在训练 MaskGIT 预测器时随机掩码 tokens；优化世界模型参数。之后，利用缓存注意力的键值对，以 actor 采样的动作在潜在空间向前滚动 H 步，训练 actor 和 critic。

## 3. 实验设计

- **数据集/场景**：
  - **Crafter 基准**：模仿 Minecraft 的开放世界环境，具有 22 个成就、视觉输入、17 个离散动作和非确定性动态。评估指标为成就分数（几何平均成功率）和平均回合回报。
  - **Atari 100k 基准**：26 个 Atari 游戏，每个游戏 400k 环境帧（100k 交互步），评估人类归一化分数。
- **对比方法**：
  - Crafter：DreamerV3（M 和 XL 大小）、Δ-IRIS、人类专家。
  - Atari 100k：SimPLe、TWM、IRIS、DreamerV3、STORM、Δ-IRIS、DIAMOND 等。
- **评估设置**：使用 5 个不同随机种子，报告均值和标准差；评估时每个种子运行 256 个 episode（Crafter 上）或标准 Atari 流程。

## 4. 资源与算力

- **硬件**：单张 RTX 3090 GPU。
- **训练效率**：
  - Crafter 训练：EMERALD 达到 27 FPS（每秒收集环境帧数），优于 Δ-IRIS（12 FPS）和 DreamerV3 XL（23 FPS），但低于 DreamerV3 M（38 FPS）。
  - Atari 100k 训练（以 Breakout 为例）：EMERALD 需 17 小时，Δ-IRIS 需 27 小时，DIAMOND 需 75 小时。
- **模型参数**：EMERALD 约 30M 参数，低于 DreamerV3 XL（200M），略高于 Δ-IRIS（25M）。

## 5. 实验数量与充分性

- **主要实验组数**：
  - Crafter：1 个环境，5 个种子，报告得分和回报。
  - Atari 100k：26 个游戏，5 个种子，报告归一化均值和中位数。
  - 消融实验：
    - 世界模型架构消融（DreamerV3 RSSM vs EMERALD TSSM，空间 vs 向量潜在空间，是否使用 MaskGIT），在 Crafter 上 5 个种子。
    - 解码步数 S 的消融（No MaskGIT、S=1、3、8），5 个种子。
    - 预测准确率随解码步数的变化分析。
  - 对比实验包含了多个近期强基线，且重复多次，统计量完整。
- **充分性与公平性**：
  - 实验覆盖了不同复杂度环境（Crafter 需要长记忆与精细视觉，Atari 相对简单），结果展示全面。
  - 在 Crafter 上首次超越人类专家，在 Atari 上与其他方法相当，但效率更高。
  - 消融实验清晰地展示了每个设计选择（空间潜在状态、Transformer、MaskGIT）的贡献。
  - 未发现明显的偏差风险（如超参数调优偏向某一方法），所有对比使用公开基准和标准评估协议。

## 6. 主要结论与发现

- EMERALD 在 Crafter 基准上以 58.1% 的成就分数超越人类专家（50.5%），创下新纪录，成为首个在 10M 环境步内超过人类表现的方法，且成功解锁全部 22 个成就。
- 在 Atari 100k 上，EMERALD 取得与 Δ-IRIS、DIAMOND 相当的归一化均值和 median，但训练时间显著更短（约为 Δ-IRIS 的 63%，DIAMOND 的 23%）。
- 空间潜在状态显著提高了世界模型的重建质量（误差从 DreamerV3 的 0.000522 降至 0.000241），使智能体能够感知关键细节（如钻石、骷髅弓箭）。
- Transformer 架构在长程记忆建模上优于 RNN，进一步提升了性能。
- MaskGIT 的并行解码在 3 步迭代时达到最佳权衡：预测准确率高于单步或线性头，且解码效率远高于自回归顺序解码。

## 7. 优点

- **方法设计创新**：将空间潜在状态与 MaskGIT 预测引入世界模型，同时解决了准确性和效率问题，智能体在潜在空间学习，避免了从像素重建的额外开销。
- **高效性**：MaskGIT 的非自回归解码大幅提升训练和推理速度，同时利用缓存注意力机制进一步减少计算。
- **性能卓越**：在 Crafter 上超越人类专家，且参数规模适中（30M），体现了良好的扩展性。
- **通用性**：在 Crafter（需要长期记忆和精细感知）和 Atari（相对简单）两个基准上均取得有竞争力的结果，证明方法不局限于特定环境。
- **消融实验充分**：系统性地验证了空间潜在状态、Transformer 和解码步数等关键设计的影响，结论可靠。

## 8. 不足与局限

- **实验覆盖**：仅测试了 Crafter 和 Atari 两个基准，未在更复杂的 3D 环境（如 Minecraft 完整版、MineRL）或连续控制任务上验证，通用性有待进一步检验。
- **超参数依赖性**：解码步数 S=3 的选择可能依赖于环境复杂性，在其他场景下可能需要重新调参。
- **潜在空间大小**：空间潜在状态的大小（4×4×32×32）可能并非最优，文中未系统研究不同分辨率或组数的影响。
- **与其他方法的比较**：在 Atari 100k 上，归一化均值和 median 与 Δ-IRIS、DIAMOND 接近，但未超越 EfficientZero V2 或 BBF，而这些方法使用了搜索或模型无关技巧，本文未与之对比（文中说明 fair comparison 限于无搜索的 model-based 方法）。
- **缺乏对更多架构变体的探讨**：如是否可以使用更深的 MaskGIT 网络或不同的掩码调度，未充分实验。
- **安全与风险**：尽管世界模型可降低真实环境训练风险，但若模型预测偏差，可能导致智能体在模拟中学习到不安全行为，文中仅简要提及影响声明，未深入讨论。

（完）
