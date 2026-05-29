---
title: Provable Ordering and Continuity in Vision-Language Pretraining for Generalizable Embodied Agents
title_zh: 具身智能体视觉语言预训练中的可证明顺序性与连续性
authors: "Zhizhen Zhang, Lei Zhu, Zhen Fang, Zi Huang, Yadan Luo"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=3fDypdR4VN"
tags: ["query:wm-vla-sa"]
score: 7.0
evidence: 用于机器人的视觉语言动作模型
tldr: 针对预训练视觉语言表示时过度关注未来帧导致错误关联的问题，本文提出Action Temporal Coherence Learning (AcTOL)，将视频视为有序连续过程而非仅关注末帧，学习顺序且连续的视觉语言表示。在虚拟环境导航和操控任务中，AcTOL预训练的表征显著提升了具身智能体的泛化能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-3fdypdr4vn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1437, \"height\": 313, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3fdypdr4vn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1446, \"height\": 632, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3fdypdr4vn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3fdypdr4vn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 730, \"height\": 191, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3fdypdr4vn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1349, \"height\": 609, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3fdypdr4vn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 731, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3fdypdr4vn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1439, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3fdypdr4vn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 728, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3fdypdr4vn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1422, \"height\": 986, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3fdypdr4vn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1353, \"height\": 1956, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-3fdypdr4vn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3fdypdr4vn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 725, \"height\": 149, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3fdypdr4vn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 726, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3fdypdr4vn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 583, \"height\": 138, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3fdypdr4vn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 603, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3fdypdr4vn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1031, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3fdypdr4vn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1455, \"height\": 1446, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3fdypdr4vn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1438, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3fdypdr4vn/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1438, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3fdypdr4vn/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1438, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3fdypdr4vn/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1436, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3fdypdr4vn/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1437, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3fdypdr4vn/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1440, \"height\": 290, \"label\": \"Table\"}]"
motivation: 现有时间对比学习过度对齐末帧，导致视觉语言关联错误。
method: 提出AcTOL，将视频视为有序连续过程，学习无刚性目标约束的视觉语言表征。
result: 在多个具身任务上提升了泛化性能和样本效率。
conclusion: 有序连续的视觉语言预训练能有效增强具身智能体的泛化能力。
---

## Abstract
Pre-training vision-language representations on human action videos has emerged
as a promising approach to reduce reliance on large-scale expert demonstrations
for training embodied agents. However, prior methods often employ time con-
trastive learning based on goal-reaching heuristics, progressively aligning language
instructions from the initial to the final frame. This overemphasis on future frames
can result in erroneous vision-language associations, as actions may terminate
early or include irrelevant moments in the end. To address this issue, we propose
Action Temporal Coherence Learning (AcTOL) to learn ordered and continuous
vision-language representations without rigid goal-based constraint. AcTOL treats
a video as a continuous trajectory where it (1) contrasts semantic differences be-
tween frames to reflect their natural ordering, and (2) imposes a local Brownian
bridge constraint to ensure smooth transitions across intermediate frames. Exten-
sive imitation learning experiments on both simulated and real robots show that the
pretrained features significantly enhance downstream manipulation tasks with high
robustness to different linguistic styles of instructions, offering a viable pathway
toward generalized embodied agents. Our project page is at https://actol-pretrain.github.io/.

---

## 论文详细总结（自动生成）

# 论文详细总结：AcTOL（Provable Ordering and Continuity in Vision-Language Pretraining for Generalizable Embodied Agents）

## 1. 核心问题与研究动机
- **背景**：利用大规模人类动作视频进行视觉语言预训练，可减少具身智能体对昂贵专家演示的依赖。现有方法（如 R3M、LIV、DecisionNCE）普遍采用**目标到达启发式的时间对比学习**，强制将语言指令与视频后期帧（甚至最后一帧）对齐。
- **问题**：这种刚性假设在真实人类视频中常被违反。例如，动作可能提前结束，或视频末尾包含无关帧，导致错误的视觉语言关联，损害下游策略学习。
- **目标**：提出一种无需刚性目标约束、仅依赖视频内在时间顺序和连续性的预训练方法，学习有序且连续的视觉语言表示，提升具身智能体的泛化能力。

## 2. 方法论
### 核心思想
- 将视频视为**连续轨迹**，而非仅关注“初始→目标”的过渡。
- 同时建模两个时间属性：**排序性（Ordering）** 和**连续性（Continuity）**。
  - 排序性：视觉特征与语言的语义差异应反映帧间的自然时间距离。
  - 连续性：视觉特征及其与语言的语义对齐应随时间平滑变化。

### 关键技术细节
1. **视觉语言排序损失（VLO Loss）**
   - 定义帧对间的语义对齐分数：`R(vi, vj, l) = -(sim(vi, l) - sim(vj, l))²`
   - 对于锚帧 i 和另一帧 j，构造负样本集：时间距离 ≥ di,j 的帧。
   - 对比损失形式：强制帧对 (i, j) 的语义差异小于 (i, k) 的语义差异（其中 k 离 i 更远）。
   - 不固定正样本为未来帧，而是利用帧间相对顺序进行无监督学习。

2. **布朗桥连续性损失（BB Loss）**
   - 在视频的任意局部片段 [n(i), n(j)] 上，假设视觉嵌入服从布朗桥过程。
   - 布朗桥的均值轨迹是端点间的线性插值，方差在中点最大。
   - 损失函数：`L_BB = (1/T) Σ_t (1 / (2 Var[B(t)])) * ||v_t - E[B(t)]||²`，惩罚偏离期望轨迹的帧。
   - 促进短时间跨度内的局部平滑过渡。

3. **总目标**：`L_AcTOL = L_VLO + λ * L_BB`（λ 经验设为 0.1）。

### 理论保证
- **定理1**：VLO损失达到理论下界时，表示满足排序性（VLO属性）——时间距离较近的帧语义差异更小，较远的差异更大。
- **定理2**：布朗桥正则化保证视觉表示的连续性，即嵌入距离小时，语义对齐分数变化有界。
- **定理3**：语言输入微扰（如同义词替换）导致的语义对齐分数变化有界，证明对语言变体的鲁棒性。

## 3. 实验设计
### 数据集与场景
- **预训练**：EPIC-KITCHEN-100（大规模人类动作视频）。
- **下游任务**：
  - 模拟环境：Franka Kitchen（5任务：滑柜、开左门、开微波炉、开炉、开灯）和 Metaworld（5任务：锤钉、按按钮、捡放块、套环、开抽屉）。
  - 真实机器人：Unitree D1 臂（3任务：拿杯子、开[x]抽屉、关[x]抽屉）。

### 基准方法
- CLIP（冻结初始化）、R3M（预训练于Ego4D）、LIV、DecisionNCE（同数据集和架构）。
- 消融变体：AcTOL w/o BB（去掉布朗桥损失）。

### 实验协议
- **语言条件行为克隆**：冻结预训练编码器，训练轻量MLP策略。模拟环境下使用5/15/25个演示，从两个摄像头视角，3个随机种子，报告50次滚动平均成功率。
- **视觉偏移测试**：在Franka Kitchen中加入YCB物体干扰（S1-S3）和纹理变化（S4、S5）。
- **语言扰动测试**：将原始指令改为4种变体（口语化、同义词替换、ChatGPT生成复杂句）。
- **视觉奖励评估**：在包含两个连续动作的视频上评估模型生成的密集奖励曲线。
- **微调实验**：使用25个机器人演示（每任务5个）对预训练编码器进行AcTOL目标微调。

## 4. 资源与算力
- **预训练**：2张 NVIDIA A800 GPU，训练约30小时（1000 epoch，batch size 128，帧数10/video）。
- **模拟LCBC实验**：总计972个episode（9任务 × 2视角 × 3数据规模 × 3种子 × 6模型），每episode约2小时，共约1944小时在24核CPU工作站。
- 文中未详细列出真实机器人实验的GPU时长。

## 5. 实验数量与充分性
| 实验类型 | 组数/条件 | 关键指标 |
|----------|-----------|----------|
| 模拟LCBC（Franka Kitchen + Metaworld） | 5任务 × 3数据规模 × 2视角 × 3种子 | 成功率 ± 标准差 |
| 真实机器人 | 3任务 × 10次 | 成功率 |
| 视觉偏移 | 5种干扰 × 5任务 | 成功率 |
| 语言扰动 | 4种变体 × 5任务 | 成功率变化 |
| 视觉奖励 | 3个视频（含多动作） | 定性曲线 |
| 消融（去掉BB） | 全部模拟条件 | 成功率对比 |
| 微调 | 1种设定（25演示微调+15演示LCBC） | 成功率 |

- **充分性**：实验覆盖不同领域（模拟/真实）、数据规模（少量到中等）、域偏移、语言变化，并进行了消融和统计误差报告。结果客观公正。
- **公平性**：所有方法使用相同预训练数据集（除R3M）和相同下游训练流程，超参数统一。

## 6. 主要结论与发现
- AcTOL在**所有环境下显著优于基线**，尤其在数据稀缺时（5演示下Franka Kitchen成功率42.6%，比最强基线提升48.95%）。
- 布朗桥约束至关重要：去掉后性能下降（如Franka Kitchen 5演示从42.6%降至32.8%）。
- 学习到的表示能生成**高质量密集奖励**，准确捕捉动作边界（如打开柜门时奖励峰值，随后下降）。
- 对**语言扰动高度鲁棒**：AcTOL成功率平均下降仅0.9%，而LIV下降11.9%，DecisionNCE下降2.7%。
- 使用少量机器人演示进行AcTOL目标微调可有效缩小人-机器人域差距（成功率从61.8%提升至86.4%）。

## 7. 优点
- **方法创新**：摆脱刚性目标到达假设，利用视频内在时间结构；同时建模排序性和连续性，理论完备。
- **理论保证**：证明了VLO的有序性下界、连续性的局部Lipschitz性质和语言抗扰性。
- **实验广泛**：涵盖模拟、真实、视觉偏移、语言扰动、奖励质量评估，验证充分。
- **开源友好**：提供项目页面和代码（补充材料），可复现。
- **应用潜力**：预训练表示可直接用于行为克隆，也可作为奖励函数，适用于零样本/少样本场景。

## 8. 不足与局限
- **动作类型限制**：方法假设动作具有时间排序和线性渐进特性，可能不适用于重复、循环或歧义动作（如搅拌、来回移动），文中已承认。
- **预训练数据偏差**：仅使用EPIC-KITCHEN-100，该数据集以厨房活动为主，可能无法迁移到其他领域（如医疗、建筑）。
- **计算资源**：预训练需2张A800约30小时，对普通实验室有一定门槛。
- **视觉偏移适应性有限**：尽管优于基线，但在强干扰（S3: 9个YCB物体）下成功率仅9.2%，仍有较大提升空间。
- **真实机器人实验规模**：仅3任务 × 10次，统计显著性有限；且机器人静止（Go2趴着），未展示移动操作。
- **未探索更长序列或复杂长程任务**：实验中的任务均为单一步骤（最多2个动作连续），未验证多步组合能力。

（完）
