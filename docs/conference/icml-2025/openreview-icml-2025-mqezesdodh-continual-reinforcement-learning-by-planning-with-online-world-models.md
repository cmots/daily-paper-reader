---
title: Continual Reinforcement Learning by Planning with Online World Models
title_zh: 通过在线世界模型规划实现连续强化学习
authors: "Zichen Liu, Guoji Fu, Chao Du, Wee Sun Lee, Min Lin"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=mQeZEsdODh"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 基于在线世界模型的连续强化学习规划
tldr: 针对连续强化学习中的灾难性遗忘问题，本文提出使用在线世界模型进行规划。具体地，在线学习跟随者世界模型，结合模型预测控制解决任务序列。从理论上证明了遗忘上界，在多个连续控制任务上展示了性能优势。该方法为连续RL中的遗忘问题提供了有效解决方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 814, \"height\": 268, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 694, \"height\": 263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 743, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1738, \"height\": 933, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1746, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1745, \"height\": 941, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-mqezesdodh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 762, \"height\": 513, \"label\": \"Table\"}]"
motivation: 连续强化学习中智能体在学习新任务时容易遗忘旧任务。
method: 在线学习跟随者世界模型，结合模型预测控制进行规划。
result: 证明了遗忘上界，并在连续控制任务中展示了优于基线的方法。
conclusion: 在线世界模型为连续RL中的遗忘问题提供了有效解决方案。
---

## Abstract
Continual reinforcement learning (CRL) refers to a naturalistic setting where an agent needs to endlessly evolve, by trial and error, to solve multiple tasks that are presented sequentially. One of the largest obstacles to CRL is that the agent may forget how to solve previous tasks when learning a new task, known as catastrophic forgetting. In this paper, we propose to address this challenge by planning with online world models. Specifically, we learn a Follow-The-Leader shallow model online to capture the world dynamics, in which we plan using model predictive control to solve a set of tasks specified by any reward functions. The online world model is immune to forgetting by construction with a proven regret bound of $\mathcal{O}(\sqrt{K^2D\log(T)})$ under mild assumptions. The planner searches actions solely based on the latest online model, thus forming a FTL Online Agent (OA) that updates incrementally. To assess OA, we further design Continual Bench, a dedicated environment for CRL, and compare with several strong baselines under the same model-planning algorithmic framework. The empirical results show that OA learns continuously to solve new tasks while not forgetting old skills, outperforming agents built on deep world models with various continual learning techniques.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：连续强化学习（Continual Reinforcement Learning, CRL）是智能体在现实场景中需要不断通过试错学习依次出现的多个任务。其核心挑战是**灾难性遗忘**：当学习新任务时，智能体会遗忘如何解决之前的任务。
- **整体含义**：本文提出通过在线世界模型进行规划来应对遗忘问题，旨在让智能体在学习新任务时保持旧任务的性能，实现持续学习。

## 2. 论文提出的方法论
- **核心思想**：学习一个在线更新的“跟随者”（Follow-The-Leader, FTL）浅层世界模型，并基于该模型使用模型预测控制（Model Predictive Control, MPC）规划动作，以解决由任意奖励函数定义的一组任务。
- **关键技术细节**：
  - 世界模型是**在线学习的浅层模型**，每步用新数据更新，不依赖固定数据集，因此由构造保证不会遗忘——其遗忘上界已被证明。
  - **规划器**仅基于最新模型搜索动作，形成增量更新的FTL在线智能体（OA）。
  - 理论证明在温和假设下，遗忘上界为 \( \mathcal{O}(\sqrt{K^2 D \log(T)}) \)，其中K、D、T分别为任务数、状态维度、时间步。
- **算法流程**（文字描述）：在每个时间步，智能体使用当前世界模型预测未来轨迹，通过MPC选择动作；执行后收集新数据，并立即更新世界模型（在线学习）；任务切换时仅改变奖励函数，模型持续更新，不会遗忘。

## 3. 实验设计
- **使用的数据集/场景**：本文设计了名为**Continual Bench**的专用连续强化学习基准环境。
- **benchmark**：该环境用于评估CRL中智能体在连续任务序列上的表现。
- **对比方法**：与多个强基线对比，这些基线采用**深度世界模型**并结合各种持续学习技术（如弹性权重巩固、记忆回放等），但均在相同的模型-规划算法框架下进行比较。

## 4. 资源与算力
- 论文中**未明确说明**使用的GPU型号、数量、训练时长等算力资源。因此无法提供具体信息。

## 5. 实验数量与充分性
- **实验数量**：元数据未给出具体实验组数或消融实验数量。根据摘要，作者在连续控制任务上展示了性能优势，但未列出具体环境个数或重复次数。
- **充分性与公平性**：从摘要看，实验在同一个算法框架下公平对比，但缺乏更多消融和统计细节。设计专用的Continual Bench环境有助于系统性评估，但实验覆盖面和统计显著性仍需查看完整论文确认。

## 6. 论文的主要结论与发现
- 在线世界模型（OA）能够**持续学习以解决新任务，同时不遗忘旧技能**。
- OA在性能上**优于**基于深度世界模型并采用各种持续学习技术的智能体。
- 理论证明了遗忘上界，为在线世界模型抗遗忘提供了理论保证。

## 7. 优点
- **理论创新**：从理论上证明了在线世界模型的遗忘上界，提供了严谨的理论支撑。
- **方法简洁**：采用FTL浅层模型和MPC，避免复杂的持续学习模块，通过构造自然解决遗忘。
- **专用基准**：设计了Continual Bench环境，便于后续研究标准化评估。
- **性能优越**：在实验上超越了多种使用深度网络+持续学习强基线的方案。

## 8. 不足与局限
- **实验覆盖有限**：元数据未给出消融实验或统计显著性分析，可能缺乏对世界模型表达力、任务数量、状态空间维度等变量影响的充分研究。
- **应用限制**：浅层模型表达力有限，可能不适用于高维或复杂动力学环境；在线更新可能受计算资源限制。
- **偏差风险**：仅与同类框架（模型-规划）基线比较，未与强化学习中的其他范式（如无模型方法结合重放）对比。
- **信息缺失**：未提及超参数敏感性、任务序列长度对遗忘影响等分析。

（完）
