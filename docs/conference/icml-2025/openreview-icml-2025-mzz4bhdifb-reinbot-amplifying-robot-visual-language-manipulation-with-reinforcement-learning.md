---
title: "ReinboT: Amplifying Robot Visual-Language Manipulation with Reinforcement Learning"
title_zh: "ReinboT: 通过强化学习增强机器人视觉语言操作"
authors: "Hongyin Zhang, Zifeng Zhuang, Han Zhao, Pengxiang Ding, Hongchao Lu, Donglin Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Mzz4BhdIFb"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 用于机器人操作的视觉语言动作模型结合强化学习
tldr: ReinboT提出了一种端到端的VLA模型，将离线强化学习原理融入其中，通过预测稠密回报来理解数据质量分布，从而在机器人操作任务中生成更稳健的决策动作。该方法有效解决了模仿学习对数据质量敏感的问题，提升了策略的鲁棒性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1413, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 804, \"height\": 778, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 882, \"height\": 642, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1421, \"height\": 238, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 575, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 828, \"height\": 560, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 869, \"height\": 608, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1244, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1614, \"height\": 1120, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1249, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1613, \"height\": 1121, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1249, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1611, \"height\": 1116, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1249, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1609, \"height\": 1114, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mzz4bhdifb/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1577, \"height\": 952, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-mzz4bhdifb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1237, \"height\": 631, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mzz4bhdifb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1210, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mzz4bhdifb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1234, \"height\": 561, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-mzz4bhdifb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1270, \"height\": 561, \"label\": \"Table\"}]"
motivation: 现有VLA模型受限于训练数据质量不均，导致性能受限。
method: 提出ReinboT模型，集成离线强化学习，通过预测稠密回报实现数据质量感知。
result: 在多种操作任务上展示了更稳健的决策动作生成能力。
conclusion: 证明了将RL原理融入VLA模型的有效性，为机器人学习提供了新范式。
---

## Abstract
Vision-Language-Action (VLA) models have shown great potential in general robotic decision-making tasks via imitation learning. However, the variable quality of training data often constrains the performance of these models. On the other hand, offline Reinforcement Learning (RL) excels at learning robust policy models from mixed-quality data. In this paper, we introduce Reinforced robot GPT (ReinboT), a novel end-to-end VLA model that integrates the RL principle of maximizing cumulative reward. ReinboT achieves a deeper understanding of the data quality distribution by predicting dense returns that capture the nuances of manipulation tasks. The dense return prediction capability enables the robot to generate more robust decision-making actions, oriented towards maximizing future benefits. Extensive experiments show that ReinboT achieves state-of-the-art performance on the CALVIN mixed-quality dataset and exhibits superior few-shot learning and out-of-distribution generalization capabilities in real-world tasks.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义

- **研究动机**：现有视觉-语言-动作（VLA）模型主要基于模仿学习范式，在大规模预训练后在下游机器人数据上微调，取得了语义泛化能力。然而，训练数据源的质量往往参差不齐（即使来自成功的示范），传统的模仿学习方法难以有效区分和利用这种混合质量的数据，导致决策动作的准确性和鲁棒性受限。
- **整体含义**：本文试图将离线强化学习（offline RL）中最大化累积奖励的核心思想融入VLA模型，使模型能够从混合质量的数据中学习更稳健的策略，提升长程操作任务的性能。具体而言，通过引入稠密回报预测，模型能更深入地理解数据质量分布，从而在决策时不仅考虑当前状态，还考虑未来收益最大化。

## 2. 方法论

### 核心思想
提出ReinboT（Reinforced robot GPT），一种端到端的VLA模型，其核心是将回报最大化原则作为监督信号，在序列建模框架下同时学习动作和最大化回报的预测。

### 关键技术细节
1. **奖励稠密化（Reward Densification）**：
   - 将长程操作任务轨迹自动分解为多个子目标序列（基于启发式方法：关节速度接近零或夹爪状态变化时标记关键状态）。
   - 设计包含四个分量的稠密奖励 \( r = \sum_{i=1}^4 w_i r_i \)：
     - \( r_1 \)：子目标达成奖励，包括本体感知跟踪、像素强度、图像质量（SSIM）和特征点匹配（ORB）。
     - \( r_2 \)：任务进度奖励，越接近最终目标奖励越大。
     - \( r_3 \)：行为平滑度奖励，惩罚关节速度、加速度和动作突变。
     - \( r_4 \)：任务完成奖励（稀疏，轨迹成功时为1）。
   - 将累积回报（ReturnToGo）作为新模态数据，用于训练过程中的质量表征。

2. **模型架构**：
   - 主干网络为GPT风格的Transformer（12层，12注意力头，384维嵌入）。
   - 输入：语言指令（CLIP编码）、图像状态（ViT + Perceiver Resampler）、本体感知（MLP）。
   - 引入三个预测token：[RTG]、[ACTION]、[IMAGE]分别预测回报、动作和未来图像。
   - 回报预测采用期望回归损失（expectile regression）实现最大化：
     \[
     L_{\text{RTG}} = \mathbb{E}_t\left[|m - \mathbb{1}(\Delta g < 0)| (\Delta g)^2\right], \quad \Delta g = g_t - P_\phi(\text{features})
     \]
     其中 \( m > 0.5 \) 时模型倾向于预测高于实际值的回报，从而实现收益最大化。
   - 动作预测利用CVAE输出多步动作轨迹（CALVIN中5步，UR5中64步）。
   - 总损失：\( L = \lambda L_{\text{RTG}} + L_{\text{arm}} + 0.01 L_{\text{gripper}} + 0.1 L_{\text{image}} \)。

3. **推理流程**（无需设置初始回报值，无需环境返回奖励）：
   - 一次性从网络获得隐藏特征，再经解码器预测动作，只需一次前向推理（比Reinformer更高效）。

## 3. 实验设计

### 数据集/场景
- **模拟环境**：CALVIN（长期操作基准），包含ABC三个子环境（人工遥操作数据约50条/任务，无语言标注）和D环境（自动交互数据，含失败轨迹10000+条）。构造混合质量数据集（加入高斯噪声0.05、0.1、0.15以增加多样性）。
- **真实世界场景**：UR5机械臂，包括杯子抓取、碗抓取与放置、毛绒玩具抓取与放置，共约530条成功轨迹。评估少样本学习（每任务30条轨迹微调）和OOD泛化（未见指令、背景、干扰物、操作对象）。

### Benchmark与对比方法
对比方法包括三类：
- **模仿学习类**：RoboFlamingo、GR-1、PIDM（均使用标注数据训练）。
- **层次化模仿学习**：GR-MG。
- **离线RL类**：RWR（奖励加权回归，复现版）。
此外，对ReinboT自身进行了多种奖励形式消融（稀疏、子目标稀疏、稠密单维、稠密多维），以及超参数（λ, m）消融。

### 评测指标
链式指令成功率（1~5条指令的完成率）和平均完成长度（AL）。

## 4. 资源与算力

论文中未明确说明训练所用的GPU型号、数量及具体训练时长。仅在附录中提供了训练超参数（批次大小32，学习率0.001，50个epochs，预热1 epoch），以及网络配置（12层Transformer，384维嵌入）。推测使用单个或少量GPU（如A100或V100）即可在合理时间内完成训练，但具体算力资源信息缺失。

## 5. 实验数量与充分性

- **主要实验**：在CALVIN混合质量数据集上对比了多种基线（表1），并进行了充分奖励设计消融（表2）和超参数影响分析（图2）。
- **真实世界评估**：少样本学习（图6a）和OOD泛化（图6b），量化了成功率。
- **附加分析**：回报预测分布特性（图3），确认m增大导致回报偏移效果。
- **总体评价**：实验覆盖了主要基线和关键变量，消融实验完整，验证了每个组件的必要性；但未在更多数据集（如MetaWorld、Adroit）或更多机械臂型号上验证，存在一定的通用性局限。实验设计整体客观公平（基线代码复现合理）。

## 6. 主要结论与发现

- ReinboT在CALVIN混合质量数据集上达到SOTA，特别是稠密多维回报版本（AL=2.26）显著优于最佳基线RWR（AL=1.82）和PIDM（AL=1.73）。
- 稠密回报的每个分量都有贡献，其中任务进度和子目标达成影响最大；去除ReturnToGo模态后性能下降39.8%。
- 超参数λ=0.001、m=0.9时最优；过大的m（如0.99）会导致回报过度乐观估计而性能下降。
- 在真实世界任务中，ReinboT的少样本学习和OOD泛化能力显著优于GR-1和RWR，成功轨迹的回报分布仍不均匀，证明了引入RL思想的必要性。

## 7. 优点

- **方法创新**：巧妙地将离线RL中的回报最大化概念通过期望回归集成到端到端VLA模型中，避免传统RL需要引入额外Q函数或在线交互的问题，且推理时无需预设初始回报。
- **奖励设计**：自动分解子目标+多维稠密奖励设计广泛适用于多种操作任务，且可灵活组合。
- **高效推理**：通过一次前向即可同时获得回报和动作，优于Reinformer的三步推理。
- **实验充分**：在模拟和真实世界均进行了验证，消融实验覆盖核心方法和参数，结论可靠。

## 8. 不足与局限

- **算力资源未公开**：无法复现或评估计算成本。
- **数据集局限性**：只在CALVIN和UR5上测试，缺乏更广泛的任务领域（如双机械臂、移动操作）和基准（如MetaWorld、Adroit）的评估。
- **奖励设计依赖启发式规则**：子目标划分基于关节速度和夹爪状态，可能不适用于所有类型任务（如连续精细操作），且权重需手动调节。
- **期望回归参数敏感**：性能对m值敏感，需要调参才能达到最佳效果。
- **真实世界数据量较小**：仅530条成功轨迹，且少样本学习只有30条，可能不足以反映大规模数据下的泛化能力。
- **未探索更大规模模型和数据**：论文表明未来工作应关注扩展性，当前模型规模较小（384维、12层），可能无法直接推广到超大规模VLA模型。

（完）
