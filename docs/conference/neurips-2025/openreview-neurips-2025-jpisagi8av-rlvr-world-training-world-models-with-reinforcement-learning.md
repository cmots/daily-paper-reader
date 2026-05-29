---
title: "RLVR-World: Training World Models with Reinforcement Learning"
title_zh: RLVR-World：用强化学习训练世界模型
authors: "Jialong Wu, Shaofeng Yin, Ningya Feng, Mingsheng Long"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=jpiSagi8aV"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 用强化学习和可验证奖励训练世界模型
tldr: RLVR-World针对世界模型训练目标与任务指标不一致的问题，提出用可验证奖励的强化学习（RLVR）直接优化世界模型。将世界模型建模为自回归序列预测，利用解码后预测的指标作为奖励。在语言和视频世界模型上均取得显著性能提升。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-jpisagi8av/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1418, \"height\": 542, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jpisagi8av/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1417, \"height\": 712, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jpisagi8av/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 462, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jpisagi8av/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 488, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jpisagi8av/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1414, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jpisagi8av/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 812, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jpisagi8av/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1445, \"height\": 1110, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jpisagi8av/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 521, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jpisagi8av/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1432, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jpisagi8av/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1448, \"height\": 1137, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jpisagi8av/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1446, \"height\": 1118, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-jpisagi8av/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 939, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jpisagi8av/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 939, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jpisagi8av/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jpisagi8av/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 645, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jpisagi8av/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1169, \"height\": 739, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jpisagi8av/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1320, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jpisagi8av/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1278, \"height\": 1115, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jpisagi8av/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1272, \"height\": 1155, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jpisagi8av/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1231, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jpisagi8av/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1175, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jpisagi8av/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1326, \"height\": 515, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jpisagi8av/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1462, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jpisagi8av/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1340, \"height\": 520, \"label\": \"Table\"}]"
motivation: 标准的最大似然估计训练目标与世界模型的任务指标（如准确率、感知质量）不一致。
method: 提出RLVR-World框架，使用强化学习直接优化解码后预测的指标作为奖励。
result: 在多个语言和视频世界模型基准上，RLVR-World优于MLE基线。
conclusion: RLVR-World提供了一种通用训练范式，可提升世界模型的任务相关性能。
---

## Abstract
World models predict state transitions in response to actions and are increasingly developed across diverse modalities. However, standard training objectives such as maximum likelihood estimation (MLE) often misalign with task-specific goals of world models, i.e., transition prediction metrics like accuracy or perceptual quality. In this paper, we present RLVR-World, a unified framework that leverages reinforcement learning with verifiable rewards (RLVR) to directly optimize world models for such metrics. Despite formulating world modeling as autoregressive prediction of tokenized sequences, RLVR-World evaluates metrics of decoded predictions as verifiable rewards. We demonstrate substantial performance gains on both language- and video-based world models across domains, including text games, web navigation, and robot manipulation. Our work indicates that, beyond recent advances in reasoning language models, RLVR offers a promising post-training paradigm for enhancing the utility of generative models more broadly. Code, datasets, models, and video samples are available at the project website: https://thuml.github.io/RLVR-World.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：世界模型（world models）的标准训练目标——最大似然估计（MLE）——与任务特定指标（如状态预测的准确率、感知质量）不一致。MLE 仅优化似然，但无法直接反映预测的实用价值，例如导致重复生成、模糊预测、多步累积误差等问题。
- **背景**：世界模型在语言（文本游戏、网页导航）、视频（机器人操控）等模态中日益重要，但传统训练（如 next-token prediction 或扩散模型的变分下界）是代理目标，无法直接对齐最终评估指标。同时，非端到端架构（如离散 tokenizer + 自回归模型）无法直接优化不可微的指标。
- **整体含义**：论文提出 RLVR-World，利用**可验证奖励的强化学习（RLVR）** 直接优化世界模型的任务指标，作为一种通用后训练范式，能够显著提升生成模型在具体任务上的实用性。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：将不同模态的世界模型统一为自回归序列生成框架，用 RLVR 直接优化解码后预测结果的任务指标（如准确率、F1 分数、LPIPS 等），替代 MLE 代理目标。
- **关键技术细节**：
  - **统一序列模型**：将当前状态和动作编码为“问题” token 序列，下一状态编码为“回答” token 序列。不同模态使用对应的 tokenization 方案（文本用 BPE，视频用学习到的视觉 tokenizer，低维动作用均匀量化）。
  - **可验证奖励**：对模型采样的一组预测结果进行解码，计算与真实值的指标作为奖励。指标可以是二元准确率、F1 分数、MSE、LPIPS、SSIM 等，根据任务选择。
  - **强化学习算法**：使用 **GRPO（Group Relative Policy Optimization）**，无需价值函数，通过组内归一化计算优势函数，并包含 KL 散度惩罚项以防止偏离参考模型。
  - **公式**：GRPO 目标函数为  
    \[
    J_{\text{GRPO}}(\theta) = \mathbb{E}_{q, \{o_i\}_{i=1}^G \sim p_{\theta_{\text{old}}}(\cdot|q)} \left[ \frac{1}{G} \sum_{i=1}^G \frac{1}{|o_i|} \sum_{t=1}^{|o_i|} \min\left( \frac{p_{i,t}^\theta}{p_{i,t}^{\theta_{\text{old}}}} \hat{A}_{i,t}, \operatorname{clip}\left( \frac{p_{i,t}^\theta}{p_{i,t}^{\theta_{\text{old}}}}, 1-\varepsilon, 1+\varepsilon \right) \hat{A}_{i,t} \right) - \beta D_{\text{KL}}[p_\theta \| p_{\text{ref}}] \right]
    \]
    其中奖励通过解码后指标直接计算，优势 \(\hat{A}_{i,t}\) 由组内奖励归一化得到。

### 3. 实验设计：数据集/场景、benchmark、对比方法
- **语言世界模型**：
  - **文本游戏状态预测**：使用 **ByteSized32-State-Prediction** 数据集（76,369 个转移，2,954 个测试）。任务：根据当前状态和动作预测下一状态（JSON 格式）及奖励。对比：DeepSeek-R1-Distill-Qwen-1.5B/7B 的 SFT 版本、GPT-4。
  - **网页状态预测**：来自 **WebArena**，由 WMA 收集的约 7K 样本子集。任务：预测 accessibility tree 中的 item 变化。对比：同基线的 SFT 版本。
  - **下游应用**：Model Predictive Control（MPC）用于网页代理，与 SFT 世界模型对比成功率。
- **视频世界模型**：
  - **机器人操作轨迹预测**：主要使用 **RT-1** 数据集（87,212 条轨迹）。任务：单步/多步视频预测。指标：MSE、PSNR、SSIM、LPIPS。对比：iVideoGPT 预训练基线和扩展预训练基线。
  - **额外数据集**：**PushT**、**Rope**、**Granular**（来自 DINO-WM）。对比：R3M、ResNet、DINO CLS、DINO-WM（综合的循环潜空间模型）、AVDC（扩散模型）。
  - **下游应用**：Real2Sim 策略评估（在 SIMPLER 环境下），对比 handcrafted SIMPLER 模拟器。

### 4. 资源与算力（文中明确说明）
- **文本游戏**：
  - SFT：4 × 80G A100 GPU，6.5 小时。
  - RLVR：8 × 80G A100 GPU，22.5 小时。
- **网页状态**：
  - SFT：8 × 40G A100 GPU，17 小时。
  - RLVR：8 × 80G H100 GPU，25 小时。
- **机器人操作（RT-1）**：
  - 单步预测：tokenizer 预训练 ~360 GPU小时（A100），Transformer 预训练 ~530 GPU小时，RLVR 200步需 3.5 小时（4 × 40G A100）。
  - 多步预测：tokenizer 预训练 ~480 GPU小时，Transformer 预训练 ~500 GPU小时，RLVR 200步需 10 小时（4 × 40G A100）。
- 所有实验在 40G A100 集群上完成，RLVR 使用 verl 框架，SFT 和预训练使用 accelerate。

### 5. 实验数量与充分性
- **实验数量**：
  - 语言：两个主要任务（文本游戏 + 网页状态），每个任务含多个变体（两种奖励设计、两种模型大小），以及下游 MPC 应用。
  - 视频：RT-1 单步和多步预测（含主结果、消融、重复率分析、测试时缩放、组大小缩放、指标导向优化），三个额外小数据集（PushT、Rope、Granular），以及下游 Real2Sim 策略评估（4种策略×6个任务×30条轨迹=1440条生成轨迹）。
  - 消融实验：不同奖励函数（binary vs. task-specific）、不同视觉指标（MAE、MSE、PSNR 等）、重复惩罚奖励、组大小（4/8/16/32）、测试时采样数（1/5/100）。
- **充分性与公平性**：
  - 报告了多次采样的均值和标准差（Table 3）。
  - 与多种先进基线（DINO-WM、AVDC、SIMPLER）进行了公平对比。
  - 在视频实验中特别控制了重复率影响（增加了重复拒绝基线）。
  - 缺点：部分对比（如网页）因任务设定不同无法与 WMA 直接比较；Rope 数据集上弱于 DINO-WM，作者分析了原因且通过联合训练有所改善。

### 6. 论文的主要结论与发现
- RLVR 能显著提升世界模型在语言和视频模态上的任务指标，例如文本游戏准确率最高提升 30.7%，网页预测 F1 提升 15.1%，视频 LPIPS 相对改善 9.2%。
- RLVR 有效缓解了多步视频预测中的重复生成问题（重复率从 48.6% 降至 9.9%）。
- 训练效率极高：仅需数百步 RLVR 即可达到甚至超过数万步 MLE 预训练的指标。
- 指标导向优化：模型在特定指标上训练后在该指标上表现最好，验证了直接优化的有效性。
- 下游应用获益：RLVR 世界模型提升了模型预测控制（网页代理成功率 +18.4%）和 Real2Sim 策略评估的准确度。
- 局限性：训练很快收敛，难以持续改进；OOD 泛化尚未深入研究；基础模型能力有限制约上限；奖励设计仍需改进。

### 7. 优点：方法或实验设计上的亮点
- **方法论亮点**：
  - 统一框架：将不同模态的世界模型统一为自回归序列预测，便于利用 LLM 生态（tokenizer、RL 算法、工具链）。
  - 直接优化任务指标：通过解码后计算奖励，避免了代理目标与最终指标之间的 gap。
  - 轻量级后训练：仅需数百步 RLVR 即可显著提升，计算开销远小于预训练。
- **实验设计亮点**：
  - 覆盖语言和视频两大模态，并延伸到下游应用（MPC、策略评估）。
  - 深入分析了重复问题、测试时缩放、训练时组大小缩放、指标导向优化等多个维度。
  - 人工评估（Real2Sim 策略评估）确保了结论的可靠性。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制
- **实验覆盖**：
  - 缺乏在其他模态（如传感器数据、自动驾驶）上的验证，结论的通用性有待扩展。
  - 视频模型仅在特定数据集上预训练，未使用大规模通用世界模型作为基础（作者已指出此为未来方向）。
  - 网页状态预测因任务重新设定（精确 item 变化 vs. 自然语言描述），无法与 WMA 直接比较。
- **偏差风险**：
  - 某些消融的超参数（如任务奖励权重、不变/变化样本比例）是基于启发式选择的，可能并非最优。
  - Real2Sim 策略评估依赖人工标注，存在主观性，且只评估了“开门/关门”类任务，未覆盖其他类型。
- **应用限制**：
  - RLVR 很快收敛，难以持续提升性能，可能需要更复杂的算法设计（如更鲁棒的探索策略）。
  - 对于 OOD 动作的泛化能力尚未研究，这是世界模型实际部署的关键点。
  - 奖励设计仍然需要人工选择指标，无法自动捕捉用户真正意图（如物理合理性、时序一致性）。

（完）
