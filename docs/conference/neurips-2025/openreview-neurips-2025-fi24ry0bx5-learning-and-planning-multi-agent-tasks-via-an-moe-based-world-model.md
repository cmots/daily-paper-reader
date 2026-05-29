---
title: Learning and Planning Multi-Agent Tasks via an MoE-based World Model
title_zh: 通过基于混合专家（MoE）的世界模型学习与规划多智能体任务
authors: "Zijie Zhao, Zhongyue Zhao, Kaixuan Xu, Yuqian Fu, Jiajun Chai, Yuanheng Zhu, Dongbin Zhao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=fi24ry0BX5"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 基于混合专家（MoE）的世界模型用于多任务多智能体强化学习与规划
tldr: 多任务多智能体强化学习面临任务间最优策略差异大的挑战。本文发现任务动力学具有有界相似性，并基于此提出M3W方法，将混合专家（MoE）应用于世界模型而非策略，使得模型能够利用任务组内相似性进行高效学习与规划。实验表明该方法在多任务设置中显著优于基线。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 722, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1428, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1431, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1434, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1088, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 550, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1436, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1422, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1412, \"height\": 662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1409, \"height\": 1150, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1436, \"height\": 260, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1362, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1368, \"height\": 588, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1360, \"height\": 514, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fi24ry0bx5/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1368, \"height\": 583, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 605, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1205, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1264, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1376, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1459, \"height\": 709, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1462, \"height\": 1072, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1230, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1443, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 826, \"height\": 731, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1442, \"height\": 960, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1442, \"height\": 837, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1441, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1465, \"height\": 1013, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fi24ry0bx5/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1311, \"height\": 131, \"label\": \"Table\"}]"
motivation: 多任务多智能体强化学习因任务间最优策略差异大而泛化困难。
method: 提出M3W方法，将混合专家（MoE）应用于世界模型，利用任务动力学的有界相似性。
result: M3W在多任务多智能体设置中表现出更好的泛化性能。
conclusion: 将MoE应用于世界模型而非策略，是一种有效的多任务学习范式。
---

## Abstract
Multi-task multi-agent reinforcement learning (MT-MARL) aims to develop a single model capable of solving a diverse set of tasks. However, existing methods often fall short due to the substantial variation in optimal policies across tasks, making it challenging for a single policy model to generalize effectively. In contrast, we find that many tasks exhibit **bounded similarity** in their underlying dynamics—highly similar within certain groups (e.g., door-open/close) diverge significantly between unrelated tasks (e.g., door-open \& object-catch). To leverage this property, we reconsider the role of modularity in multi-task learning, and propose **M3W**, a novel approach that applies mixture-of-experts (MoE) to world model instead of policy, enabling both learning and planning. For learning, it uses a SoftMoE-based dynamics model alongside a SparseMoE-based predictor to facilitate knowledge reuse across similar tasks while avoiding gradient conflicts across dissimilar tasks. For planning, it evaluates and optimizes actions using the predicted rollouts from the world model, without relying directly on a explicit policy model, thereby overcoming the limitations of policy-centric methods. As the first MoE-based multi-task world model, M3W demonstrates superior performance, sample efficiency, and multi-task adaptability, as validated on Bi-DexHands with 14 tasks and MA-Mujoco with 24 tasks. The demos and anonymous code are available at \url{https://github.com/zhaozijie2022/m3w-marl}.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
- **研究动机**：多任务多智能体强化学习（MT-MARL）旨在训练单一模型解决多种任务，但不同任务的最优策略差异大，导致现有策略中心方法泛化困难。
- **核心发现**：任务间**动力学**存在“有界相似性”——相似任务（如开门/关门）动力学习性强，不相关任务（如开门、抓取）则差异显著。而策略分布几乎完全不同。
- **核心含义**：应利用这一性质，将模块化（MoE）应用于**世界模型**而非策略，以实现相似任务的动力学知识共享，同时隔离不相似任务的梯度冲突。

## 2. 论文提出的方法论
- **核心思想**：构建基于混合专家（MoE）的世界模型，包含学习与规划两阶段。
- **关键技术细节**：
  - **SoftMoE动力学模型**：将多智能体观测-动作对作为序列token，通过软路由将token分配到N个MLP专家，输出加权组合预测下一时刻隐状态。路由权重由任务嵌入驱动，实现相似任务共享专家，不同任务激活不同专家。
  - **SparseMoE奖励预测器**：通过稀疏Top-K路由选择自注意力专家，聚合后输出全局奖励。加入负载平衡损失避免专家过载。
  - **规划方法**：使用多智能体MPPI算法，直接基于世界模型滚动预测评估动作序列价值，不依赖显式策略。价值函数结合预测奖励和评论家估计的终端Q值。
- **公式/算法流程**：
  - 训练损失包括动态损失（隐状态预测误差）、奖励损失（soft交叉熵）、Q损失及负载平衡损失。
  - 规划阶段：采样动作序列→世界模型滚动→评估价值→选择精英轨迹→更新动作分布→迭代。

## 3. 实验设计
- **数据集/场景**：
  - **Bi-DexHands**（14个双手操控任务，包含语义相似/相反/无关任务）
  - **MA-Mujoco**（24个多智能体机器人任务，涉及多个机器人套件）
- **Benchmark**：与六种基线对比——MACD（模型基线）、HMASD（多任务技能发现）、MAT（序列建模）、MAPPO、HATRPO，以及单任务MAPPO（强基线）。
- **评价指标**：归一化回报（0-100），95%置信区间。

## 4. 资源与算力
- **文中说明**：在单个NVIDIA RTX A6000 GPU上运行。每步执行时间约**25.8 ms**（默认设置），满足多数机器人实时要求；早停策略可降至**9.8 ms**。
- **未明确**：总训练时长、使用的GPU数量、内存等细节未提及，但附录E.6提供了时间成本分析。

## 5. 实验数量与充分性
- **实验数量**：共38个任务（14+24）完整对比；多个消融实验：预测精度、规划器贡献（图7）、Actor先验（表13）、奖励尺度鲁棒性（图14）、时间成本、可扩展性（图16）；可视化分析：专家注意、路由相似性、隐空间轨迹。
- **充分性与公平性**：与所有基线在相同环境下同条件训练，报告误差与置信区间。M3W在**71%任务（27/38）**上达到最优，统计显著（p<0.05）。实验设计全面，覆盖多任务适应、样本效率、可解释性等多个维度。

## 6. 论文的主要结论与发现
- M3W在多任务多智能体场景中显著优于所有现有方法，包括模型基和无模型基方法。
- MoE世界模型能**有效利用任务间有界相似性**：相似任务共享专家加速学习，不相似任务隔离梯度避免干扰。
- 通过规划直接利用预测轨迹，无需显式策略，克服了策略中心方法的局限性。
- 专家具备**功能专化**，路由器能正确分配专家。

## 7. 优点
- **方法创新**：首次将MoE应用于多任务世界模型，而非策略网络，充分利用动力学相似性。
- **规划范式**：直接基于世界模型滚动进行动作优化，提升了灵活性和性能。
- **全面实验**：在38个任务上验证，包含消融、可解释性可视化、鲁棒性测试，结果统计显著。
- **开源代码**：提高可复现性。
- **计算效率**：推理时间满足实时性要求。

## 8. 不足与局限
- **动作空间限制**：当前MPPI规划器仅适用于连续动作，未扩展到离散动作（作者指出未来可结合MCTS/CEM）。
- **训练算力未完整披露**：未给出总训练时间和GPU数量，不利于成本评估。
- **可扩展性初步**：仅对10和56智能体进行了初步实验，未充分验证大规模智能体场景。
- **真实部署验证缺失**：实验在模拟环境中进行，未涉及真实机器人硬件。
- **专家数量等超参数敏感性**：未深入分析专家数、路由阈值等敏感度。

（完）
