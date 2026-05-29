---
title: Learning Interactive World Model for Object-Centric Reinforcement Learning
title_zh: 面向对象中心强化学习的交互式世界模型学习
authors: "Fan Feng, Phillip Lippe, Sara Magliacane"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=E0cjqfM55C"
tags: ["query:wm-vla-sa"]
score: 10.0
evidence: 用于强化学习与规划的世界模型
tldr: 针对对象中心强化学习中对象交互隐式建模导致策略泛化不足的问题，本文提出分解交互式对象中心世界模型（FIOC-WM），从像素中学习对象潜在表示和交互结构，并将其整合到世界模型中进行策略学习。实验证明，FIOC-WM显著提升了样本效率和策略泛化能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-e0cjqfm55c/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 489, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-e0cjqfm55c/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 557, \"height\": 757, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-e0cjqfm55c/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 619, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-e0cjqfm55c/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1448, \"height\": 286, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-e0cjqfm55c/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1445, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-e0cjqfm55c/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1450, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-e0cjqfm55c/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1306, \"height\": 558, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-e0cjqfm55c/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 589, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-e0cjqfm55c/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1068, \"height\": 1648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-e0cjqfm55c/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1446, \"height\": 286, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-e0cjqfm55c/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1021, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-e0cjqfm55c/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1239, \"height\": 404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-e0cjqfm55c/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 883, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-e0cjqfm55c/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1421, \"height\": 580, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-e0cjqfm55c/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1355, \"height\": 709, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-e0cjqfm55c/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1022, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-e0cjqfm55c/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1283, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-e0cjqfm55c/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1375, \"height\": 692, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-e0cjqfm55c/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 992, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-e0cjqfm55c/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1317, \"height\": 499, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-e0cjqfm55c/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1390, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-e0cjqfm55c/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1467, \"height\": 170, \"label\": \"Table\"}]"
motivation: 现有对象中心RL忽略对象间交互，导致策略鲁棒性和迁移性差。
method: 提出FIOC-WM，学习对象潜在表示和交互结构，构建统一的世界模型。
result: 在多个环境上样本效率和泛化性能优于基线。
conclusion: 显式建模对象交互能极大提升对象中心世界模型的效果。
---

## Abstract
Agents that understand objects and their interactions can learn policies that are more robust and transferable. However, most object-centric RL methods factor state by individual objects while leaving interactions implicit. We introduce the Factored Interactive Object-Centric World Model (FIOC-WM), a unified framework that learns structured representations of both objects and their interactions within a world model. FIOC-WM captures environment dynamics with disentangled and modular representations of object interactions, improving sample efficiency and generalization for policy learning. Concretely, FIOC-WM first learns object-centric latents and an interaction structure directly from pixels, leveraging pre-trained vision encoders. The learned world model then decomposes tasks into composable interaction primitives, and a hierarchical policy is trained on top: a high level selects the type and order of interactions, while a low level executes them. On simulated robotic and embodied-AI benchmarks, FIOC-WM improves policy-learning sample efficiency and generalization over world-model baselines, indicating that explicit, modular interaction learning is crucial for robust control.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：现有的对象中心强化学习（Object-Centric RL）方法通常将状态分解为独立的物体表示，但将物体间的交互隐式处理或完全忽略。这导致学习到的策略在面对复杂动态环境时鲁棒性不足，且难以迁移到新任务或新场景。
- **背景**：真实世界中的物理交互（碰撞、支撑、抓取等）对系统演化起决定性作用。如果世界模型不能显式地建模这些交互，则无法准确预测状态变化，进而制约下游规划与决策的效率和泛化能力。
- **目标**：研究**何种类型与程度的分解结构**才能使潜在表示最有效地支持高效、可迁移的策略学习。

## 2. 方法论

### 2.1 核心思想
提出 **Factored Interactive Object-Centric World Model (FIOC-WM)**，一种统一的框架，学习**两级分解**：
- **对象级分解**：将场景拆分为多个物体，并显式建模物体间的交互（用交互图表示）。
- **属性级分解**：每个物体的状态进一步分为**静态属性**（如颜色、形状、质量）和**动态变量**（如位置、速度）。交互只影响动态部分，而静态属性影响动态演化。

### 2.2 关键技术细节

**第一阶段：离线世界模型学习**
1. **观察编码**：使用预训练视觉编码器（DINO-v2 或 R3M）提取特征，再用 Slot Attention 将特征聚类为对象级表示。
2. **属性分解**：通过 VAE 从对象表示学习潜在状态 \(s_i\)，并用两个独立编码器 \(f_c(s_i)\)（静态）和 \(f_d(s_i)\)（动态）分离属性。
   - 静态一致性损失 \(L_{static}\) 约束 \(f_c\) 随时间不变；
   - 对比损失 \(L_{con}\) 区分不同物体的静态属性。
3. **交互图学习**：引入潜变量 \(G_t\)（大小为 \(N \times N\) 的邻接矩阵）表示 \(t\) 时刻物体间的交互。学习方式有两种：
   - **变分掩码**（Categorical 或 Codebook 变体）；
   - **条件独立性检验**（CIT）。
4. **动力学与奖励模型**：动态变量通过 GRU 预测下一步状态，奖励由解码器 \(p_r(r_t | s_t, a_t)\) 给出。损失包括重建、预测、KL 散度、奖励回归等。

**第二阶段：在线分层策略学习**
- **高层策略** \(\pi_h\)：从当前状态选择目标交互图 \(G^g_t\)（即希望发生的物体间交互类型）。用任务奖励和多样性奖励 \(r_{div}\) 训练，避免重复选择。
- **低层策略** \(\pi_l\)：给定当前状态和目标交互图，执行具体动作以触达该交互。可使用 MPC（交叉熵方法）或 PPO 训练。
- **推理流程**：高层先选定交互子目标，低层执行，形成“链式交互”，将长时任务分解为可组合的交互原语。

## 3. 实验设计

### 3.1 数据集/场景
- **SpritesWorld**（合成环境，评估状态分解和交互图学习）
- **OpenAI Gym Fetch**（模拟 Fetch 机械臂推/拨物体）
- **Franka Kitchen**（7-DoF 机械臂完成厨房子任务序列）
- **iGibson**（具身 AI，家庭任务，如抓取和切割桃子）
- **Libero**（终身机器人学习基准，桌面操作任务）

### 3.2 对比方法
- 在线强化学习：DreamerV3, TD-MPC2, EIT（对象中心无模型方法）
- 离线规划：DINO-WM

### 3.3 评估指标
- **观察与动力学建模**：LPIPS（感知相似度）
- **交互学习**：归一化结构汉明距离（nSHD），对比注意力基线
- **分解质量**：线性探测 MSE（对真实属性的预测误差）
- **策略性能**：任务成功率（单任务、属性泛化、组合泛化、技能泛化）

## 4. 资源与算力

论文附录 E.3 明确列出了计算资源：
| 环境 | GPU 型号与数量 | 训练时长 |
|------|----------------|----------|
| SpritesWorld | 1× NVIDIA A100 | 3 小时 |
| Gym Fetch | 6× NVIDIA 4090 | 8 小时 |
| iGibson | 6× NVIDIA 4090 | 9 小时 |
| Libero | 1× NVIDIA A100 | 8 小时 |
| Franka Kitchen | 1× NVIDIA A100 | 6 小时 |

所有实验总计使用约 34 GPU 小时（A100）+ 17 GPU 小时（4090）。算力开销合理，可复现。

## 5. 实验数量与充分性

- **世界模型评估**：表1（LPIPS）、图5a（线性探测）、表A1（nSHD 对比）、表A3（完整 LPIPS）覆盖全部环境。
- **策略学习**：表2（4种环境×多种泛化设置）、图6b（学习曲线）、表A2（完整成功率）。
- **消融实验**：表3，去除状态分解、交互建模、分层策略、预训练低层等8个变体，系统分析各组件贡献。
- **额外分析**：表A4（在线微调影响）、表A5（预训练特征适配基线）、表A6（物体数量泛化）。

共涉及 **5个环境、4种泛化场景、8项消融、多个随机种子（5或10）**。实验设计全面，对比方法均为当前主流基线，评估指标多样且客观。结论有充分数据支撑。

## 6. 主要结论与发现

1. **显式建模交互至关重要**：去除交互模块导致成功率下降 18%（单任务）和 18%（组合泛化），是影响最大的因素。
2. **两级分解（对象+属性）有效**：状态分解带来 4-6% 的提升，尤其在泛化任务上更显著。
3. **分层策略提升长时任务效率**：去除高层策略后性能下降 23-28%，表明“交互作为子目标”的设计合理。
4. **预训练视觉特征（DINO/R3M）是良好起点**：结合 FIOC 后优于 DINO-WM 等仅用预训练特征直接规划的方法。
5. **交互图学习优于注意力推断**：变分掩码方法（Categorical）在 nSHD 上全面优于纯注意力基线，泛化差距更小。
6. **FIOC 在组合泛化上优势突出**：在属性组合、物体数量变化、技能组合等场景下均大幅领先 DreamerV3 和 TD-MPC2。

## 7. 优点

- **创新性**：首次将对象级、属性级分解与显式交互图学习统一在世界模型中，并支持端到端策略学习。
- **实用性强**：提出“交互原语”概念，使长时任务可分解为可组合的子技能，降低学习难度。
- **实验规范**：多环境、多指标、多消融，统计严谨（误差棒、随机种子），对比方法全面且代码将开源。
- **可解释性**：交互图结构可直接分析，支持因果发现（CIT 变体）。

## 8. 不足与局限

- **依赖预训练对象发现模型**：Slot Attention 需要预设物体数量，且无法处理未知类别物体。
- **交互泛化受限**：当前模型在“见过的物体类别”上表现好，但未验证对全新物体属性的泛化。
- **计算开销较大**：两阶段训练（离线+在线）和交互图推断增加了复杂度，在实时机器人部署上可能有延迟。
- **未在真实机器人上验证**：所有实验均在模拟器中进行，真实世界的感知噪声和动力学不确定性尚未测试。
- **超参数敏感**：交互图学习中的温度、阈值等需要针对不同环境调整，通用性有待加强。

（完）
