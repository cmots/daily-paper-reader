---
title: Improving Transformer World Models for Data-Efficient RL
title_zh: 改进Transformer世界模型以实现数据高效强化学习
authors: "Antoine Dedieu, Joseph Ortiz, Xinghua Lou, Carter Wendelken, J Swaroop Guntupalli, Wolfgang Lehrach, Miguel Lazaro-Gredilla, Kevin Patrick Murphy"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=IajCvMJw41"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 改进Transformer世界模型以实现数据高效强化学习
tldr: "该论文通过一系列设计改进，构建了高效的Transformer世界模型，在Craftax基准上以1M步达到69.66%奖励，超越DreamerV3并首次超越人类表现（65.0%）。方法包括构建SOTA无模型基线、改进模型架构等。"
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 813, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 742, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 783, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 807, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1718, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1724, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1685, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 810, \"height\": 547, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1767, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 883, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1462, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-iajcvmjw41/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1768, \"height\": 834, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 845, \"height\": 1480, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1474, \"height\": 693, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 855, \"height\": 611, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 812, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 719, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1653, \"height\": 991, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1476, \"height\": 712, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1258, \"height\": 716, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1076, \"height\": 813, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1602, \"height\": 824, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1605, \"height\": 452, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-iajcvmjw41/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1516, \"height\": 392, \"label\": \"Table\"}]"
motivation: 模型基强化学习在复杂开放世界游戏中样本效率不足。
method: 设计CNN+RNN策略架构，并添加三项改进到标准MBRL。
result: 在Craftax上达到新最优，超越人类表现。
conclusion: 精心设计的Transformer世界模型可显著提升样本效率。
---

## Abstract
We present an approach to model-based RL that achieves a new state of the art performance on the challenging Craftax-classic benchmark, an open-world 2D survival game that requires agents to exhibit a wide range of general abilities---such as strong generalization, deep exploration, and long-term reasoning. With a series of careful design choices aimed at improving sample efficiency, our MBRL algorithm achieves a reward of 69.66% after only 1M environment steps, significantly outperforming DreamerV3, which achieves $53.2\%$, and, for the first time, exceeds human performance of 65.0%. Our method starts by constructing a SOTA model-free baseline, using a novel policy architecture that combines CNNs and RNNs.
We then add three improvements to the standard MBRL setup: (a) "Dyna with warmup", which trains the policy on real and imaginary data, (b) "nearest neighbor tokenizer" on image patches, which improves the scheme to create the transformer world model (TWM) inputs, and (c) "block teacher forcing", which allows the TWM to reason jointly about the future tokens of the next timestep.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：模型基强化学习（MBRL）旨在通过学习世界模型（World Model）来减少训练策略所需的环境交互数据。然而，在具有程序化生成、部分可观测、稀疏奖励等复杂特性的开放世界环境（如Craftax-classic）中，现有MBRL方法（如DreamerV3、IRIS）的样本效率仍然不足，其表现甚至低于精心调优的无模型方法（MFRL）。
- **核心目标**：通过一系列精巧的设计改进，提升基于Transformer世界模型（TWM）的MBRL算法的数据效率，使其在Craftax-classic基准上首次超越人类专家水平，并显著超越已有SOTA。

### 2. 论文提出的方法论：核心思想、关键技术细节

论文提出了一套“改进阶梯”，从无模型基线出发，逐步叠加三项关键改进：

- **无模型基线（MFRL，SOTA）**：
  - 架构：使用Impala CNN提取图像特征（63×63×3 → 8×8×128 → 8192维），然后通过GRU（隐状态256维）注入记忆，将GRU输出与CNN嵌入拼接后送入Actor-Critic网络（两个2048维残差块）。
  - 训练：PPO算法，使用GAE、目标值标准化、熵正则化等技巧。
  - 结果：1M步后奖励55.49%，超过DreamerV3（53.2%），训练仅需15分钟（单GPU）。

- **改进①：Dyna with warmup（使用真实+想象轨迹训练策略）**：
  - 传统方法（如IRIS、DreamerV3）仅在世界模型生成的想象轨迹上训练策略；本文则混合使用真实环境轨迹和想象轨迹更新策略（类似Dyna方法）。
  - 关键技巧：**预热（warmup）**——前TBP=200k步仅使用真实数据训练，待世界模型足够准确后再引入想象轨迹，避免模型不准确导致策略崩溃。设定想象轨迹长度TWM=20（远小于环境轨迹长度Tenv=96），以降低累积误差。
  - 算法伪代码：如Algorithm 1所示，每轮先收集环境数据（Step 1），更新策略（Step 2），然后更新世界模型（Step 3），最后在预热条件满足后使用想象轨迹更新策略（Step 4）。

- **改进②：Patch Nearest-Neighbor Tokenizer（NNT）**：
  - 针对Craftax-classic图像的自然分块特性（7×7像素块，9×9网格），提出**逐块独立分词**。
  - 编码器：对每个7×7×3图像块，计算其与代码书中所有编码的欧氏距离；若最小距离≤阈值τ则取最近邻编码，否则将当前块作为新编码加入代码书（贪心核集近似）。解码时直接返回对应编码。
  - 优点：代码书一旦加入即冻结，目标分布平稳，简化世界模型学习；而VQ-VAE的代码书持续更新，导致非平稳问题。
  - 使用参数：K=4096, τ=0.75。

- **改进③：Block Teacher Forcing（BTF）**：
  - 传统Transformer世界模型训练时使用**全自回归教师强制**（causal attention，逐token预测）；BTF采用**块因果注意力**（block causal attention）：给定前m个时间步的所有token，并行独立预测下一时间步的所有token，不再在意同一时间步内的token顺序。
  - 公式：L_BTF = Σ_t Σ_i log p(q^i_{t+1} | q^{1:L}_{1:t}, a_{1:t})。
  - 优点：允许TWM在解码前联合推理所有未来token；缓解自回归漂移；由于可并行解码，生成速度快两倍，且精度更高。

**整体训练流程**：从一个增强的MFRL基线出发，依次加入Dyna、patch VQ-VAE、NNT、BTF，形成“改进阶梯”（类似Rainbow论文的叠加改进）。所有模块可独立工作并累积效果。

### 3. 实验设计：数据集/场景、Benchmark、对比方法

- **主要基准**：**Craftax-classic**（JAX实现的Crafter近似版），2D开放世界生存游戏。特点：程序化生成、部分可观测（63×63局部视图）、22层成就层次、稀疏奖励。
  - 评价指标：**Reward**（算术平均）和**Score**（几何平均，更侧重偶尔达成困难成就）；均为百分比。
  - 对比方法：DreamerV3、IRIS、Δ-IRIS、Curious Replay、Moon et al. (2024)的MFRL基线、作者自己的MFRL和MBRL变体。所有方法在1M环境步后比较。
- **额外验证环境**：
  - **MinAtar**（Atari的简化版，10×10符号观察）：4个游戏（Asterix、Breakout、Freeway、SpaceInvaders）。验证改进方法在另一种网格世界中的泛化性。
  - **Craftax（Full）**：Craftax的更完整版本，包含更多层级和成就（130×110图像，22个→226个成就）。测试扩展性。

- **消融实验**：移除每个改进（Dyna、NNT、patches、BTF）；改变patch大小（5×5/7×7/9×9）；改变预热起始步（0/100k/200k/400k/600k）；改变策略更新轮数（固定vs.退火）；以及基于MFRL的架构消融（移除RNN、模型大小等）。

### 4. 资源与算力

- **硬件**：所有实验在**8×H100 GPU**上运行。
- **训练时间**（1M环境步）：
  - MFRL（本文最佳）：~15分钟（单A100 GPU，原文提及）。
  - MBRL（fast版本，含BTF）：~759分钟（≈12.6小时）。
  - MBRL（slow版本，TWM更新轮数N_iters_WM=4k）：~2749分钟（≈1.9天）。
  - DreamerV3：~2100分钟。
  - IRIS：~8330分钟（单GPU）。
- **未明确说明**：实验的具体GPU数量（8×H100）及使用天数（仅slow版本近2天）；MFRL的15分钟可能是在单GPU上测得。

### 5. 实验数量与充分性

- **主实验**：每个方法在Craftax-classic上使用**10个不同随机种子**进行训练，报告均值±标准误。包含阶梯中5个变体（M1~M5）及两种速度模式。
- **消融实验**：超过10组，覆盖了每个改进的单独移除、patch大小、预热步数、连续vs.离散输入、MFRL架构变体等。均使用10种子或5种子。
- **跨环境验证**：在MinAtar（4个游戏）和Craftax Full上同样进行阶梯实验（5种子），结果一致。
- **定性评估**：对3个世界模型（M1、M3、M5）进行rollout质量分析（符号准确率、L2重建误差、可视化对比）。
- **客观性**：与已发表工作（DreamerV3、IRIS等）直接比较，其数值来自原文或复现；严格按1M步截断。消融实验设计完整。
- **公平性**：超参数在Craftax-classic上精细调整，在MinAtar上使用相同架构但适当调整部分超参数（如熵系数、损失权重），未过拟合单环境。

### 6. 论文的主要结论与发现

- **核心结论**：通过三项改进（Dyna with warmup、NNT、BTF）叠加，在Craftax-classic上实现了69.66%奖励和31.77%得分，首次超越人类专家奖励（65.0%）；且在MinAtar上同样显著提升。
- **每个改进均有独立贡献**：移除任意一项都会导致性能下降；预热对于想象训练至关重要；离散化（量化）对于世界模型学习至关重要；BTF同时提升准确性和速度。
- **MFRL基线本身也具有竞争力**：基于CNN+RNN的PPO agent在1M步达到55.49%奖励，超过DreamerV3，且训练极快。

### 7. 优点

- **模块化改进**：三项改进可独立应用并累积，类似Rainbow的叠加式路线；实验充分验证了每项改进的贡献。
- **高效性**：提出的MBRL（fast）在12小时左右即可达到SOTA，而MFRL仅需15分钟，计算效率远优于DreamerV3等。
- **新颖且实用的技术**：NNT提供静态代码书，简化TWM学习；BTF实现并行预测，加速训练并提升质量；混合真实/想象轨迹的Dyna+预热策略简单有效。
- **跨环境验证**：在Craftax（完整版）和MinAtar上均取得SOTA，展示了一定的泛化能力。
- **开源性**：基于开源库（purejaxrl、flashbax）实现，可复现性高。

### 8. 不足与局限

- **环境依赖**：NNT的patch分词依赖Craftax-classic的自然网格结构与有限精灵，对于真实世界连续变化图像可能代码书过大或分裂严重。作者承认这一点，并提出了未来使用预训练模型（SAM、Dino-V2）的改进方向。
- **未在Atari-100k等经典基准上验证**：论文聚焦Craftax和MinAtar，虽然MinAtar是简化版Atari，但与标准Atari视觉差异较大；在更复杂视觉域（如标准Atari、DM Control）上的表现未知。
- **计算资源需求**：slow版本需要2天、8 GPU（约384 GPU·小时），对于资源有限的实验室可能过高；但fast版本合理（~12 GPU·小时）。
- **策略算法限制**：使用PPO（on-policy），无法高效混合离线数据；作者提到未来改用off-policy算法（如SAC）可能进一步提升。
- **人类专家仅用于奖励对比，未用于得分**：论文指出虽然奖励超越人类，但得分（几何平均）仍低于人类专家（50.5% vs. 31.77%），说明在少数困难成就上仍有差距。
- **部分实践细节未充分解释**：如BTF的注意力掩码图（Figure 3）中“排除action tokens”的具体实现；PPO中“目标值标准化”的动机与影响缺乏理论分析。

（完）
