---
title: "Robot-R1: Reinforcement Learning for Enhanced Embodied Reasoning in Robotics"
title_zh: Robot-R1：用于增强机器人具身推理的强化学习
authors: "Dongyoung Kim, Sumin Park, Huiwon Jang, Jinwoo Shin, Jaehyung Kim, Younggyo Seo"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=N2bLuwofZ0"
tags: ["query:wm-vla-sa"]
score: 8.0
evidence: 用于机器人的视觉语言动作模型
tldr: 针对监督微调导致灾难性遗忘和泛化下降的问题，本文提出Robot-R1框架，利用强化学习增强大规模视觉语言模型（LVLM）的具身推理能力，预测完成机器人任务所需的下一个关键点状态。实验表明，在多个机器人操纵任务上，Robot-R1显著优于SFT方法，并提升了策略的鲁棒性和泛化性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-n2bluwofz0/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1429, \"height\": 683, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n2bluwofz0/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1303, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n2bluwofz0/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 237, \"height\": 241, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n2bluwofz0/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 616, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n2bluwofz0/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1331, \"height\": 208, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n2bluwofz0/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 233, \"height\": 233, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n2bluwofz0/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 673, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n2bluwofz0/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 683, \"height\": 445, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2bluwofz0/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1159, \"height\": 723, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2bluwofz0/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 566, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2bluwofz0/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1455, \"height\": 398, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2bluwofz0/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1451, \"height\": 467, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2bluwofz0/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1457, \"height\": 143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2bluwofz0/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 737, \"height\": 142, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2bluwofz0/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1435, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2bluwofz0/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1455, \"height\": 358, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2bluwofz0/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1453, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2bluwofz0/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1450, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2bluwofz0/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1454, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2bluwofz0/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1453, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n2bluwofz0/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1446, \"height\": 182, \"label\": \"Table\"}]"
motivation: 监督微调数据集启发式构造且未优化机器人控制，导致泛化差和遗忘问题。
method: 提出Robot-R1，通过强化学习优化具身推理，预测下一个关键点状态以控制机器人。
result: 在多个机器人操控任务上取得优于监督微调的性能。
conclusion: 强化学习能有效提升LVLM在机器人控制中的推理和泛化能力。
---

## Abstract
Large Vision-Language Models (LVLMs) have recently shown great promise in advancing robotics by combining embodied reasoning with robot control. A common approach involves training on embodied reasoning tasks related to robot control using Supervised Fine-Tuning (SFT). However, SFT datasets are often heuristically constructed and not explicitly optimized for improving robot control. Furthermore, SFT often leads to issues such as catastrophic forgetting and reduced generalization performance. To address these limitations, we introduce Robot-R1, a novel framework that leverages reinforcement learning to enhance embodied reasoning specifically for robot control. Robot-R1 learns to predict the next keypoint state required for task completion, conditioned on the current scene image and environment metadata derived from expert demonstrations. Inspired by the DeepSeek-R1 learning approach, Robot-R1 samples reasoning-based responses and reinforces those that lead to more accurate predictions. Our experiments show that models trained with Robot-R1 outperform SFT methods on embodied reasoning tasks. Despite having only 7B parameters, Robot-R1 even surpasses GPT-4o on reasoning tasks related to low-level action control, such as spatial and movement reasoning.

---

## 论文详细总结（自动生成）

# 论文《Robot-R1: Reinforcement Learning for Enhanced Embodied Reasoning in Robotics》详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：当前大型视觉语言模型（LVLM）在机器人控制中常采用监督微调（SFT）来训练具身推理能力，但SFT数据集通常是启发式构造的，未针对机器人控制进行优化，且容易引发灾难性遗忘和泛化性能下降。
- **背景**：LVLM已被用于机器人领域，通过生成高层动作描述或直接输出低层动作来实现控制。然而，它们往往缺乏精细的具身推理（如空间关系理解），需要额外领域数据微调。SFT方法存在数据设计欠佳、分布偏移下性能退化等问题。
- **动机**：受DeepSeek-R1启发，利用强化学习（RL）来激发和强化推理路径，有望克服SFT的局限，提升LVLM在机器人控制中的具身推理能力。

## 2. 论文提出的方法论

### 核心思想
- **目标**：训练LVLM预测完成机器人任务所需的下一个关键点状态（next keypoint state），通过显式推理过程优化状态预测准确性。
- **关键挑战**：连续空间的动作空间巨大，探索困难。
- **解决方案**：将下一状态预测转化成**多项选择问答（MCQA）** 问题，收缩动作空间；同时增加两个辅助QA任务（当前状态预测、运动预测），增强状态理解。
- **优化算法**：采用**Group Relative Policy Optimization (GRPO)**，为每个查询生成G个响应，计算优势值并优化策略，同时加入KL散度惩罚防止偏离参考模型。

### 关键技术细节
1. **数据生成**：
   - 从专家演示中提取元数据（环境固定参考点、3D坐标系统、物体尺寸等），用于生成问题提示。
   - 构建三种QA数据：
     - 航点预测QA：预测下一关键点状态，随机采样三个干扰选项。
     - 当前状态预测QA：从图像估计当前状态。
     - 运动预测QA：根据状态变化生成方向描述（如“move up”），并添加“slightly”修饰词。
   - 使用RLBench仿真环境生成训练数据：5个任务，每个约2.5K问题，总共约7.5K QA对。

2. **训练流程**：
   - 模型被要求输出<think>…</think>（推理过程）和<answer>…</answer>（最终答案）。
   - 奖励信号 = 格式奖励 + 答案正确性奖励（基于规则匹配）。

3. **GRPO公式**（文字说明）：
   - 对每个查询生成G个响应，计算每个响应的优势值（基于该查询内奖励的均值和标准差），然后通过最小化带裁剪和KL惩罚的目标函数更新策略。

## 3. 实验设计

### 使用的数据集/场景
- **训练数据**：RLBench仿真环境中的5个任务（pick_up_cup, push_button, put_rubbish_in_bin, phone_on_base, take_lid_off_saucepan），50个演示/任务。
- **评估基准**：
  - **Robot-R1 Bench**：新提出的基准，包含10个RLBench任务，215个开放性问题，覆盖规划、高层动作推理、运动推理、空间推理四种能力。使用GPT-4o作为评判（LLM-as-judge），打分0-3。
  - **EmbodiedBench Manipulation**：基于RLBench的视觉驱动智能体评估（4个任务，5种指令类别），衡量任务成功率。
  - **SpatialRGPT-Bench**：3D空间理解基准（定量和定性指标）。

### 对比方法
- **基线**：
  - Direct SFT：直接预测下一状态，无中间推理。
  - CoT SFT：包含手动构造的CoT推理路径（规划→高层动作→运动）。
- **商业模型**：GPT-4o、GPT-4o-mini、Claude系列（Opus, Haiku, Sonnet）、Gemini系列（1.5 Flash/Pro, 2.0 Flash）、Qwen2.5-VL-7B-Ins等。
- **基础模型**：Qwen2.5-7B-VL-Ins。

### 主要对比结果
- Robot-R1在Robot-R1 Bench上低层控制推理超越所有商用模型，运动推理得分0.76（GPT-4o为0.72），空间推理1.51（GPT-4o为1.43）。
- 高层控制推理（规划+高层动作）也显著提升，但规划略低于GPT-4o。
- 在EmbodiedBench上，Robot-R1比基础模型提升约31%（平均成功率11.68% vs 8.92%），而SFT基线全部失败（0%）。
- 在SpatialRGPT上，定量任务提升约60%，定性任务提升约40%。

## 4. 资源与算力

- **硬件**：单节点4块NVIDIA A100 80GB GPU。
- **训练时长**：Robot-R1训练约12小时（5个epoch，7.5K prompts）。
- **其他细节**：训练中使用批次大小128，GRPO每次生成5个样本，学习率1e-6。**论文明确说明了计算资源与训练时间。**

## 5. 实验数量与充分性

- **实验组数**：主实验包括对比多种商业模型和SFT基线（表2-3）；额外评估EmbodiedBench（表4）、SpatialRGPT（表5）；消融研究包括不同RL算法（表7）、随机种子（表8）、QA设计（表9）；冷启动实验（表13）；迁移到BridgeV2、VLABench、LIBERO及真实机器人（表11-15）。
- **充分性**：实验覆盖了多个仿真环境、真实机器人场景，验证了泛化能力。消融研究深入分析了不同成分的影响。所有评估使用温度0减少随机性，LLM评判与人类打分相关性高（Pearson ~0.9）。
- **客观性**：对比了多个业界顶级模型，结果具有说服力。但部分实验（如VLABench、LIBERO）仅训练1 epoch，可能未充分收敛。

## 6. 论文的主要结论与发现

1. **RL训练显式推理优于SFT**：Robot-R1在多项具身推理任务上显著优于SFT方法，且能避免灾难性遗忘。
2. **7B模型超越商业大模型**：仅7B参数的Robot-R1在低层控制推理（运动、空间）上超越GPT-4o、Claude等。
3. **推理能力可迁移**：训练于仿真环境的推理能力可迁移到真实环境（BridgeV2、真实机器人）和其他仿真基准（VLABench、LIBERO），提升实际任务成功率。
4. **运动预测是低层推理的关键**：辅助任务（当前状态预测、运动预测）有助于提升整体性能。
5. **RL算法选择重要**：GRPO和RLOO优于REINFORCE++，说明奖励归一化策略影响学习稳定性。

## 7. 优点

- **方法新颖性**：首次将DeepSeek-R1风格的RL训练引入机器人具身推理，解决SFT的固有问题。
- **设计巧妙**：将连续控制问题离散化为多项选择，有效降低探索难度；引入辅助任务增强状态理解。
- **基准贡献**：提出Robot-R1 Bench，专门用于评估机器人相关推理能力，且验证了LLM评判与人类一致。
- **实验全面**：涵盖多个仿真基准、真实机器人操作、多种RL算法消融，充分证明了方法的有效性和泛化性。
- **资源友好**：仅需4块A100 GPU和12小时训练，门槛较低，易于复现和推广。

## 8. 不足与局限

- **状态表示简化**：仅使用xyz位置（7维向量中只取3维），未考虑末端执行器旋转和抓取器状态，限制了复杂操纵任务的推理。
- **训练数据来源单一**：全部来自RLBench仿真，真实场景中低层推理提升有限（BridgeV2实验），因视角和坐标系差异。
- **部分任务泛化不足**：在VLABench的物理定律和复杂推理任务上性能下降，因为此类任务超出机器人操纵推理范畴。
- **训练epoch不统一**：部分消融实验仅训练1 epoch，可能未收敛；与主实验（5 epoch）不一致，影响直接比较。
- **高层规划能力略弱**：Robot-R1的规划任务得分略低于GPT-4o，因训练目标聚焦于下一状态预测而非长期规划。

（完）
