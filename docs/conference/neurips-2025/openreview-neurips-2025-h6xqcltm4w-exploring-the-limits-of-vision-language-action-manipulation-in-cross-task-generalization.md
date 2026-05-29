---
title: Exploring the Limits of Vision-Language-Action Manipulation in Cross-task Generalization
title_zh: 探索视觉-语言-动作操作在跨任务泛化中的极限
authors: "Jiaming Zhou, Ke Ye, Jiayi LIU, Teli Ma, Zifan Wang, Ronghe Qiu, Kun-Yu Lin, Zhilin Zhao, Junwei Liang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=h6xQClTm4W"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 面向跨任务操作泛化的视觉-语言-动作模型
tldr: 现有视觉-语言-动作（VLA）模型在未见任务上的泛化能力尚未充分探索。本文提出AGNOSTOS仿真基准，包含23个未见操作任务和两级难度，系统评估了VLA模型的跨任务零样本泛化性能，揭示了当前模型尽管在多样化数据集上训练但仍面临挑战。该工作为VLA模型泛化研究提供了标准化测试平台。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-h6xqcltm4w/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1431, \"height\": 1132, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-h6xqcltm4w/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1430, \"height\": 1144, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-h6xqcltm4w/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1449, \"height\": 299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-h6xqcltm4w/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 649, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-h6xqcltm4w/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1450, \"height\": 1321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-h6xqcltm4w/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1446, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-h6xqcltm4w/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1445, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-h6xqcltm4w/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1382, \"height\": 1210, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-h6xqcltm4w/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1440, \"height\": 993, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-h6xqcltm4w/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1163, \"height\": 527, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-h6xqcltm4w/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1459, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-h6xqcltm4w/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 1467, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-h6xqcltm4w/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 766, \"height\": 124, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-h6xqcltm4w/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 766, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-h6xqcltm4w/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1411, \"height\": 1097, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-h6xqcltm4w/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1042, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-h6xqcltm4w/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1272, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-h6xqcltm4w/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1150, \"height\": 344, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-h6xqcltm4w/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 864, \"height\": 197, \"label\": \"Table\"}]"
motivation: 当前VLA模型在开放世界中的跨任务泛化能力尚未被系统研究，缺乏标准化评估基准。
method: 提出AGNOSTOS基准，包含23个未见操作任务和两种泛化难度级别，用于评估VLA模型的零样本泛化。
result: 系统评估揭示了现有VLA模型跨任务泛化的局限性，即使经过多样化数据集训练仍表现不佳。
conclusion: AGNOSTOS为VLA模型泛化研究提供了重要评估工具，推动了通用机器人操作的发展。
---

## Abstract
The generalization capabilities of vision-language-action (VLA) models to unseen tasks are crucial to achieving general-purpose robotic manipulation in open-world settings.
However, the cross-task generalization capabilities of existing VLA models remain significantly underexplored.
To address this gap, we introduce **AGNOSTOS**, a novel simulation benchmark designed to rigorously evaluate cross-task zero-shot generalization in manipulation. 
AGNOSTOS comprises 23 unseen manipulation tasks for test—distinct from common training task distributions—and incorporates two levels of generalization difficulty to assess robustness. 
Our systematic evaluation reveals that current VLA models, despite being trained on diverse datasets, struggle to generalize effectively to these unseen tasks. 
To overcome this limitation, we propose **Cross-Task In-Context Manipulation (X-ICM)**, 
a method that conditions large language models (LLMs) on in-context demonstrations from seen tasks to predict action sequences for unseen tasks.
Additionally, we introduce a **dynamics-guided sample selection** strategy that identifies relevant demonstrations by capturing cross-task dynamics. 
On AGNOSTOS, X-ICM significantly improves cross-task zero-shot generalization performance over leading VLAs, achieving improvements of 6.0\% over $\pi_0$ and 7.9\% over VoxPoser.
We believe AGNOSTOS and X-ICM will serve as valuable tools for advancing general-purpose robotic manipulation.

---

## 论文详细总结（自动生成）

## 论文核心问题与整体含义（研究动机和背景）

- **研究动机**：视觉-语言-动作（VLA）模型在全开放世界环境中实现通用机器人操作，关键在于其对**未见任务**的泛化能力。然而，现有VLA模型在**跨任务零样本泛化**方面的能力远未被系统探索，缺乏标准化、可复现的评估基准。
- **核心问题**：当前VLA模型能否有效泛化到与训练任务在语义、物体或动作上不同的全新操作任务？如果不行，如何提升其跨任务泛化能力？
- **背景**：现有VLA模型（如π0、OpenVLA等）主要关注**任务内泛化**（如视觉变化、场景变化），但很少测试**任务间泛化**（从未见过的任务类型）。已有的模拟基准（如Colosseum、GemBench）也仅评估任务内泛化，缺乏跨任务零样本测试。

## 论文提出的方法论：核心思想、关键技术细节

- **整体思路**：提出**AGNOSTOS基准**（23个未见任务，分两级难度）用于系统性评估，并设计**X-ICM方法**，利用LLM的上下文学习能力，将**已见任务的演示**作为上下文示例，预测未见任务的动作序列。
- **关键技术细节**：
  1. **AGNOSTOS基准**：
     - 基于RLBench模拟环境，包含18个已见任务（训练集）和23个未见任务（测试集）。
     - 未见任务分为两级：
       - **Level-1**（13个）：与已见任务共享部分语义（如类似物体或动作）。
       - **Level-2**（10个）：完全新语义，无重叠物体或动作，要求更强泛化。
  2. **X-ICM方法**：
     - **问题定义**：给定已见演示集 \( D_s \)（含视觉、动作、语言描述），对于未见任务的初始观测 \( v_u \) 和语言指令 \( L_u \)，用LLM预测动作序列 \( A_u^{\text{pred}} \)。
     - **动力学引导样本选择模块**：
       - 训练一个**动力学扩散模型**G（基于InstructPix2Pix），以初始观测和语言指令为输入，预测最终观测，从而捕获任务的动态特征。
       - 提取每个演示的动态特征（视觉潜在特征+文本特征），计算与未见任务特征的余弦相似度，选出最相似的K个已见演示（K=18）。
     - **跨任务上下文预测模块**：
       - 将选定演示中的物体3D位置和关键动作序列文本化（例如“物体名: [x,y,z]”和“动作: [x,y,z,roll,pitch,yaw,gripper]”）。
       - 构造提示（system prompt + 已见演示序列 + 未见任务输入），送入LLM（主要使用Qwen2.5-7B/72B-Instruct）生成关键动作序列。

## 实验设计：数据集、基准、对比方法

- **数据集与场景**：AGNOSTOS基准基于RLBench模拟器，包含18个已见任务（3600条演示）和23个未见任务。此外在真实世界使用xArm7机器人进行5个任务的实验。
- **对比方法**：
  - **领域内训练模型**：PerAct、RVT、RVT2、Sigma-Agent、Instant Policy。
  - **人类视频预训练模型**：R3M、D4R、R3M-Align、D4R-Align。
  - **VLA基础模型**：OpenVLA、RDT、π0、LLARVA、3D-LOTUS、3D-LOTUS++、SAM2Act、VoxPoser。
- **实验设置**：所有学习型模型在18个已见任务上微调（消除领域差距），然后在23个未见任务上零样本测试。每个任务3个不同种子，每个种子25次滚动，报告均值与标准差。

## 资源与算力

- 论文明确说明了计算资源：
  - X-ICM (7B) 使用2块A6000 GPU，X-ICM (72B) 使用8块A6000 GPU。
  - 微调π0、OpenVLA、RDT等模型均使用官方推荐的GPU配置（文中提到π0训练100k步，batch size 64等，但未明确总时长）。
- 总体而言，算力信息部分具体（GPU型号和数量），但未给出具体训练小时数。

## 实验数量与充分性

- **实验数量**：主要实验在23个未见任务上对比了12种方法（包括X-ICM不同规模），并进行了消融实验：
  - 消融动力学引导选择模块（与随机选择对比）。
  - 消融上下文样本数量（1~24）。
  - 消融不同LLM骨干（7B/8B模型）。
  - 消融不同动态特征组合。
  - 消融模型规模（7B、14B、72B）。
  - 真实世界5个任务各20次测试。
  - 长时域任务（5次子任务成功率）。
- **充分性与客观性**：
  - 实验覆盖了三大类VLA模型，对比全面。
  - 所有模型均在相同微调策略下评估，使用官方协议，公平性较好。
  - 报告了标准差，统计严谨。
  - 消融实验设计合理，验证了各模块贡献。
  - 但真实世界实验仅5个简单任务，规模较小。

## 论文的主要结论与发现

- 现有VLA模型在跨任务零样本泛化上表现**显著不足**：所有先前模型在至少8/23个未见任务上完全失败；X-ICM (72B) 在所有23个任务上均有成功案例。
- X-ICM (72B) 在Level-1和Level-2平均成功率分别达37.6%和20.3%，总体30.1%，**优于所有对比方法**（次优π0总体17.5%）。
- 动力学引导样本选择对性能提升关键（与随机选择相比提升5%）。
- 上下文样本数量在12个左右达到饱和。
- LLM骨干选择显著影响性能，Qwen2.5系优于同期其他模型。
- 真实世界实验验证了方法的可行性，但长时域任务成功率低（5%）。

## 优点：方法或实验设计上的亮点

- **开创性基准**：第一个专门针对VLA模型跨任务零样本泛化的系统基准，填补了领域空白。
- **两级难度设计**：Level-1/Level-2清晰区分了语义相似性与完全新颖性，有助于诊断模型泛化瓶颈。
- **X-ICM方法创新**：
  - 提出动力学扩散模型提取任务动态表征，实现跨任务演示检索。
  - 将LLM上下文学习成功推广到跨任务设置，无需额外训练。
  - 动力学引导选择策略有效提升了上下文质量。
- **实验全面性**：覆盖了三大类共12种方法，消融实验完整，含真实世界验证。
- **开源承诺**：代码、数据、模型将在接受后公开，利于复现和后续研究。

## 不足与局限

- **模拟环境限制**：所有系统实验基于RLBench模拟器，真实迁移性仍需更多验证（真实世界仅5个简单任务）。
- **性能上限不高**：X-ICM (72B) 在Level-2平均仅20.3%，许多任务仍低于30%，泛化能力远非理想。
- **依赖物体位置文本化**：当前方法将视觉信息简化为物体3D坐标，丢失了丰富视觉上下文（如纹理、形状等），可能限制泛化。
- **长时域任务失败率高**：论文实验表明X-ICM在长时域零样本场景下累积误差严重（成功率仅5%）。
- **计算资源需求较大**：72B模型需8块A6000 GPU，推理成本较高。
- **未见任务数量有限**：23个任务虽覆盖两级，但类别仍有限，可能无法代表所有真实场景。
- **未探讨多机器人平台泛化**：仅在单一模拟机器人（Franka Panda）上评估，跨本体泛化未涉及。

（完）
