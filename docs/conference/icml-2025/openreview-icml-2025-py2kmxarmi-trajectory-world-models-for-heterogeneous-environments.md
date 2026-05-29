---
title: Trajectory World Models for Heterogeneous Environments
title_zh: 异构环境的轨迹世界模型
authors: "Shaofeng Yin, Jialong Wu, Siqiao Huang, Xingjian Su, Xu He, Jianye HAO, Mingsheng Long"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Py2KmXaRmi"
tags: ["query:wm-vla-sa"]
score: 10.0
evidence: 面向异构环境的预训练世界模型
tldr: 该论文针对传感器和执行器异构性阻碍大规模预训练世界模型的问题，提出UniTraj统一数据集（包含80个环境的百万轨迹）和TrajWorld架构。TrajWorld能灵活处理变长传感器信息并捕获环境动态，通过上下文学习适应新环境。预训练后在转移预测和下游任务上取得显著提升，直接支撑了世界模型在强化学习和规划中的应用。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-py2kmxarmi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 789, \"height\": 536, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-py2kmxarmi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1574, \"height\": 567, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-py2kmxarmi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1689, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-py2kmxarmi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 738, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-py2kmxarmi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1760, \"height\": 882, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-py2kmxarmi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1582, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-py2kmxarmi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1754, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-py2kmxarmi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1683, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-py2kmxarmi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1587, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-py2kmxarmi/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1762, \"height\": 896, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-py2kmxarmi/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1762, \"height\": 896, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-py2kmxarmi/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1759, \"height\": 649, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-py2kmxarmi/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 657, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-py2kmxarmi/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1392, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-py2kmxarmi/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1356, \"height\": 252, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-py2kmxarmi/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1363, \"height\": 252, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-py2kmxarmi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1780, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-py2kmxarmi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 769, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-py2kmxarmi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1484, \"height\": 1066, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-py2kmxarmi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 149, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-py2kmxarmi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1051, \"height\": 1346, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-py2kmxarmi/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 983, \"height\": 709, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-py2kmxarmi/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1757, \"height\": 555, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-py2kmxarmi/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1028, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-py2kmxarmi/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1780, \"height\": 2049, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-py2kmxarmi/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1768, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-py2kmxarmi/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1048, \"height\": 786, \"label\": \"Table\"}]"
motivation: 传感器和执行器的异构性阻碍了大规模预训练世界模型在不同环境间的迁移。
method: 构建包含80个环境的百万轨迹数据集UniTraj，并提出能灵活处理变长传感器信息的TrajWorld架构。
result: 在转移预测和下游任务上，TrajWorld相比基线模型实现了显著更优的性能。
conclusion: 大规模预训练世界模型是可行的，UniTraj和TrajWorld为通用世界模型奠定了数据和架构基础。
---

## Abstract
Heterogeneity in sensors and actuators across environments poses a significant challenge to building large-scale pre-trained world models on top of this low-dimensional sensor information. In this work, we explore pre-training world models for heterogeneous environments by addressing key transfer barriers in both data diversity and model flexibility. We introduce UniTraj, a unified dataset comprising over one million trajectories from 80 environments, designed to scale data while preserving critical diversity. Additionally, we propose TrajWorld, a novel architecture capable of flexibly handling varying sensor and actuator information and capturing environment dynamics in-context. Pre-training TrajWorld on UniTraj yields substantial gains in transition prediction, achieves a new state-of-the-art for off-policy evaluation, and also delivers superior online performance of model predictive control. To the best of our knowledge, this work, for the first time, demonstrates the transfer benefits of world models across heterogeneous and complex control environments. Code and data are available at https://github.com/thuml/TrajWorld.

---

## 论文详细总结（自动生成）

# 论文总结：Trajectory World Models for Heterogeneous Environments

## 1. 核心问题与整体含义

**研究动机**：传统世界模型在单个环境中从头训练，难以泛化到异构环境（不同传感器/执行器维度、不同动态规律）。现有大规模预训练世界模型多依赖同质模态（文本、图像、视频），忽视了低维传感器/执行器向量的异构性。本文旨在探索面向异构环境的世界模型预训练范式。

**研究目标**：通过构建大规模、多样化的轨迹数据集以及灵活可迁移的模型架构，实现世界模型在异构、复杂控制环境间的正迁移，从而提升转移预测、离策略评估（OPE）和模型预测控制（MPC）性能。

## 2. 方法论

### 核心思想
- **标量层面的一致性**：不同环境的状态/动作向量维度不同，但每个标量维度（如关节位置、力矩）可统一建模。
- **上下文识别环境**：利用历史轨迹提供上下文，使模型通过上下文学习（in-context learning）推断环境动态，无需环境标识。
- **二维归纳偏置**：轨迹数据天然具有时间步和变量两个维度，采用交错的时间注意力与变量注意力，增强结构表征和迁移能力。

### 关键技术细节
1. **标量化**：将轨迹矩阵化为 (T × M) 矩阵，M = 状态维度 + 动作维度 + 1（奖励）。
2. **离散化与嵌入**：每个变量（标量）均匀划分为 B 个区间，采用高斯直方图与独热编码，并加入时间、变量、预测三类可学习嵌入。
3. **交错注意力**：
   - 时间注意力（Causal Attention）：每个变量独立处理，捕获时间依赖。
   - 变量注意力（无因果掩码）：每个时间步内捕获变量间关系。
   - 配合前馈网络，形成 L 个 Transformer 块。
4. **预测目标**：基于当前时刻预测下一时刻的状态和奖励，使用交叉熵损失对离散化目标优化。
5. **训练流程**：先在 UniTraj 数据集上预训练（1M 梯度步），再在下游环境微调（最多 1.5M 步）。

## 3. 实验设计

### 数据集
- **预训练数据集 UniTraj**：整合 5 个公开数据集（ExORL、RL Unplugged、JAT、DB-1、TD-MPC2）及自行收集的 Modular RL 数据，共 80 个环境，1.3M 轨迹（719M 步）。刻意排除下游测试环境（HalfCheetah、Hopper、Walker2D）的数据。
- **下游测试集**：D4RL 的 15 个数据集（3 环境 × 5 质量等级：random、medium-replay、medium、medium-expert、expert）。

### 基准与对比方法
- **转移预测**：MLP Ensemble、TDM（一维注意力 Transformer），均对比 from scratch 和 fine-tuned 版本。
- **离策略评估（OPE）**：额外对比 FQE、DR、IS、DICE、VPM 以及当前 SOTA 方法 ETM。
- **模型预测控制（MPC）**：在 medium-replay 数据集上微调，采用两种规划器（proposal policy 和 random shooting），对比同上。

### 消融与分析实验
- 零样本泛化（环境参数转移、跨环境转移）。
- 少样本适应（不同数据量下预测误差）。
- 预训练规模与多样性影响（1/10、1/100 采样、JAT 子集）。
- 注意力可视化与离散化权重可视化。

## 4. 资源与算力

- **实现框架**：JAX（JIT 编译，支持 KV cache 加速）。
- **硬件**：单块 24GB NVIDIA RTX 4090 即可完成预训练和微调。
- **训练时间**（1.5M 步）：
  - MLP Ensemble：1.5 小时
  - TDM：36 小时
  - TrajWorld：28 小时
- 预训练步数 1M，微调步数最多 1.5M，批量大小 64。

论文未详细说明总 GPU 使用量（仅单卡）、能耗或分布式训练情况，但清晰给出了单卡可复现的配置。

## 5. 实验数量与充分性

- **转移预测**：15 个训练集 × 5 个测试集 = 75 组实验（每个模型 3 个随机种子）。
- **OPE**：3 环境 × 5 数据等级 × 多种方法，每组 3 种子。
- **MPC**：3 环境 × 2 规划器 × 多个模型，3 种子。
- **消融**：预训练规模（3 种子集）、少样本（4 种数据量）、注意力可视化（单独模型）、离散化分析。
- **零样本**：环境参数转移（Pendulum、Walker2D）及跨环境（Cart-2-Pole、Cart-3-Pole）定性/定量实验。

**评价**：实验覆盖全面，统计标准（均值±标准差，3 种子）符合规范；对比基线包括经典方法和最新 SOTA，确保公平性；对预训练数据质量和多样性的消融分析有助于理解贡献来源。但 OPE 中仅用 DOPE 基准，未在其他 OPE 基准（如 RL Unplugged 等）上验证，泛化性有待扩展。

## 6. 主要结论与发现

1. **数据集与架构有效**：UniTraj 提供了大规模、高多样性的数据基础，TrajWorld 的二维注意力架构能在异构环境间实现知识迁移。
2. **正迁移显著**：预训练后的 TrajWorld 在 75 个转移预测任务上平均误差降低（相比从零训练），在 OPE 上达到新 SOTA（MAE、秩相关优于 ETM 等），MPC 性能也优于基线。
3. **零样本能力**：预训练模型能在未见过的环境（Cart-2-Pole、参数变化环境）中做出合理预测，体现了上下文学习能力。
4. **预训练规模与多样性正相关**：更大、更丰富的预训练数据带来更好的下游泛化。
5. **架构对比**：TrajWorld 优于 TDM（后者顺序预测累积误差），MLP 预训练甚至出现负迁移，说明模型架构对异构转移至关重要。

## 7. 优点

- **问题新颖**：首次系统验证了低维传感器异构环境下的世界模型正迁移，填补了领域空白。
- **数据贡献**：UniTraj 数据集规模大（719M 步）、多样性高（80 环境、多种数据收集策略、多种策略水平），且开源。
- **架构创新**：标量级处理+二维注意力巧妙融合了异构适应性（变量数量可变）和动态建模（时间+变量关系）。
- **实验全面**：涵盖零样本、少样本、转移预测、OPE、MPC 等典型世界模型评估场景，且包含消融和可视化分析，结论扎实。
- **可复现性**：提供代码、数据、超参数，且单卡即可运行，门槛低。
- **性能突出**：在 OPE 上超越强大基线 ETM，在 MPC 上提升 fragile 环境（Hopper、Walker2D）表现。

## 8. 不足与局限

- **边界预测局限**：离散化方案将预测限制在训练数据观测范围内，无法准确预测超范围的奖励或状态（例如高性能策略的高回报），可能导致某些 OPE 指标（Regret@1）不是最优。
- **模型校准困难**：较大的容量和离散预测输出可能导致不确定性估计不准确，限制了在 offline RL 等需要不确定性量化的场景中的应用。
- **计算成本**：虽比 TDM 快，但相比轻量 MLP Ensemble 仍慢约 20 倍，不适合推理延迟敏感的场景。
- **零样本泛化受限**：仅对简单环境（Cart-2-Pole）展示，对复杂高维环境（如 Humanoid）的零样本能力未验证。
- **实验覆盖不够广**：只使用了 D4RL 的三种环境作为下游，未在人形机器人、真实机器人数据上验证；OPE 仅采用 DOPE 基准，未用更多基准集。
- **缺乏与视觉世界模型对比**：未与基于视频的世界模型（如 DreamerV3 等视觉方法）对比，尽管模态不同，但可增加讨论。

（完）
