---
title: Efficient Robotic Policy Learning via Latent Space Backward Planning
title_zh: 通过潜在空间后向规划实现高效机器人策略学习
authors: "Dongxiu Liu, Haoyi Niu, Zhihao Wang, Jinliang Zheng, Yinan Zheng, Zhonghong Ou, Jianming HU, Jianxiong Li, Xianyuan Zhan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=DJiouYdH19"
tags: ["query:wm-vla-sa"]
score: 8.0
evidence: 使用潜在空间后向规划的高效机器人规划，结合世界模型
tldr: 当前机器人规划依赖像素级预测，计算代价高且误差累积。本工作提出潜在空间后向规划，从最终目标逆向生成子目标序列，避免正向累积误差。该方法在长时域多阶段任务中实现高效准确的规划，显著降低计算开销，支持实时控制。在仿真和真实机器人上验证了有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-djiouydh19/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 888, \"height\": 811, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djiouydh19/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 907, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djiouydh19/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1758, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djiouydh19/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1759, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djiouydh19/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1773, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-djiouydh19/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1776, \"height\": 477, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-djiouydh19/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1768, \"height\": 525, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djiouydh19/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 823, \"height\": 499, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djiouydh19/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 822, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djiouydh19/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1433, \"height\": 884, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djiouydh19/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1759, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djiouydh19/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1561, \"height\": 765, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djiouydh19/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 861, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djiouydh19/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 859, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djiouydh19/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1045, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djiouydh19/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1416, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-djiouydh19/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1607, \"height\": 317, \"label\": \"Table\"}]"
motivation: 像素级世界模型预测成本高且累积误差大，影响长时域任务规划。
method: 提出潜在空间后向规划，从目标状态逆向采样子目标，用世界模型评估可行性，生成高效策略。
result: 在仿真和真实机器人任务中，该方法在规划准确性和实时性上均优于前向规划基线。
conclusion: 潜在后向规划为机器人长期任务部署提供了一种高效且准确的规划范式。
---

## Abstract
Current robotic planning methods often rely on predicting multi-frame images with full pixel details. While this fine-grained approach can serve as a generic world model, it introduces two significant challenges for downstream policy learning: substantial computational costs that hinder real-time deployment, and accumulated inaccuracies that can mislead action extraction. Planning with coarse-grained subgoals partially alleviates efficiency issues. However, their forward planning schemes can still result in off-task predictions due to accumulation errors, leading to misalignment with long-term goals. This raises a critical question: Can robotic planning be both efficient and accurate enough for real-time control in long-horizon, multi-stage tasks?
To address this, we propose a **B**ackward **P**lanning scheme in **L**atent space (**LBP**), which begins by grounding the task into final latent goals, followed by recursively predicting intermediate subgoals closer to the current state. The grounded final goal enables backward subgoal planning to always remain aware of task completion, facilitating on-task prediction along the entire planning horizon. The subgoal-conditioned policy incorporates a learnable token to summarize the subgoal sequences and determines how each subgoal guides action extraction.
Through extensive simulation and real-robot long-horizon experiments, we show that LBP outperforms existing fine-grained and forward planning methods, achieving SOTA performance. Project Page: [https://lbp-authors.github.io](https://lbp-authors.github.io).

---

## 论文详细总结（自动生成）

# 论文详细总结：Efficient Robotic Policy Learning via Latent Space Backward Planning (LBP)

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：当前机器人规划方法主要分为两类——（1）像素级精细预测（如视频预测），能提供丰富未来信息但计算成本高、误差累积严重，难以实时部署；（2）粗粒度子目标预测（如前向子目标规划），效率较高但仍存在前向预测的累积误差，导致偏离最终任务目标。两类方法共同面临一个“三难困境”：同时兼顾**计算效率**、**长时域一致性**（准确）和**充分的未来指导**。
- **研究动机**：是否存在一种既高效又足够准确的规划方法，能够满足长时域、多阶段任务的实时控制需求？作者受人类规划方式启发（先想象最终目标，再逆向分解子目标），提出**潜在空间后向规划**（LBP）。
- **整体含义**：LBP通过逆向递归生成子目标序列，从根本上缓解前向规划的误差累积，同时利用潜在空间降低计算复杂度，旨在打破上述三难困境，实现高效、准确、可实时运行的机器人规划。

## 2. 方法论

### 2.1 核心思想
- **后向规划范式**：从最终目标开始，递归预测距离当前状态越来越近的中间子目标。最终目标由语言指令和当前观测推断得到，从而保证整个子目标序列与任务完成条件对齐。
- **潜在空间操作**：所有预测（最终目标、子目标）均在决策导向的潜在特征空间（如 DecisionNCE、SigLIP 编码）中进行，避免像素级生成的高成本。
- **子目标融合自适应**：通过可学习的 token 对上下文序列进行交叉注意力压缩，使下游策略能动态权衡近距与远距子目标对决策的影响。

### 2.2 关键技术细节
1. **最终目标预测器 fg**：输入当前潜在状态 zt 和语言特征 φl，输出潜在最终目标 zg（式 2）。
2. **统一子目标预测器 fw**：递归生成子目标序列。设 w0 = zg，wi 由当前状态 zt、上一级子目标 wi−1 和语言特征 φl 预测（式 3-4）。定义递归系数 λ = (τ(wi) - t) / (τ(wi−1) - t)，控制子目标的时间稀疏性（λ 越大，子目标越接近最终目标）。
3. **训练损失（式 5）**：
   - 第一项：用真实子目标 zλi 监督 fw，学习任务进展；
   - 第二项：用 fw 自身的前一次预测 ˆzλi−1 作为输入再次预测，增强递归推演的一致性，减少测试时的误差累积。
4. **子目标融合模块**：使用 Perceiver 风格交叉注意力，将完整上下文 c = {wn, ..., w1, zg, φl} 压缩为一个融合嵌入 zc，驱动策略网络 πθ (a|zt, c)（式 6）。
5. **底层策略**：基于 ResNet-34 图像编码 + FiLM 语言注入 + 扩散损失（25步去噪）生成动作，支持多视图输入和动作块预测（chunk=6）。

### 2.3 算法流程（文字说明）
训练阶段：
- 联合训练 fg、fw 和 πθ；
- fg 拟合从当前状态到最终目标潜在特征的映射；
- fw 拟合任意起点到终点的中间子目标预测，并训练递归一致性；
- πθ 以融合后的上下文为条件，模仿专家动作。
测试阶段：
- 输入当前观测和语言指令 → 编码为潜在特征 zt、φl；
- fg 预测 zg，fw 递归生成 {wn, ..., w1, zg}；
- 目标融合模块生成 zc，πθ 输出当前动作；
- 每步闭环重复。

## 3. 实验设计

### 3.1 仿真实验：LIBERO-LONG
- **Benchmark**：包含 10 个不同的长时域操作任务（如将汤和酱放入篮子、打开炉子放锅、将杯子放入微波炉并关门等），每个任务 50 条专家演示，图像 256×256。
- **对比方法**：MTACT、MVP、MPI、OpenVLA、Seer（端到端预测逆动力学）、SuSIE（图像编辑子目标规划）。其中 MTACT、MVP、MPI、OpenVLA、Seer 的结果直接引用原论文（Seer 论文）。
- **评估指标**：每个任务 10 次 rollout，取 top-3 checkpoints 的平均成功率。

### 3.2 真实机器人实验：AIRBOT 6 DoF 平台
- **任务**：4 个长时域任务—— Stack 3 cups、Move cups、Stack 4 cups、Shift cups。每个任务分为 2~5 个阶段，阶段得分 {0,25,50,75,100}，必须完全完成当前阶段才能进入下一阶段。
- **对比方法**：LCBC（纯语言条件 BC）、GLCBC（语言+固定最终目标）、SuSIE、LBP。
- **训练数据**：Move cups 和 Shift cups 各 200 条，Stack cups 任务共 200 条。
- **评估设置**：每个任务 10 次 rollout，取最后 3 个 checkpoints 的平均阶段得分。

### 3.3 补充实验
- **后向 vs 前向规划误差对比**：从真实机器人数据集中随机采样 3000 个状态，计算预测子目标与真值的 MSE。
- **消融实验**：在 LIBERO-LONG 上测试不同规划步数（1~4 子目标）、不同 λ（0.5 vs 0.75）、有无目标预测器、不同融合策略（平均池化 vs 注意力融合）。
- **泛化实验**：在 Shift cups 任务上添加背景变化和干扰物，测试 LBP 稳定性。

## 4. 资源与算力

- 论文在附录 A 中提及：SuSIE 的高层图像编辑模型在 4 块 A6000 GPU 上训练。对于 LBP，仅说明训练步数（高层规划器 100k 步，底层策略 200k/400k 步），**未明确说明使用的 GPU 数量、型号或总训练时长**。
- 整体而言，LBP 的计算成本远低于像素级生成方法（如 SuSIE、Seer），因为高层规划器仅使用轻量 MLP。

## 5. 实验数量与充分性

- **仿真实验**：涵盖 10 个 LIBERO-LONG 任务，每个任务 10 次评估 × top-3 checkpoints，共 300 次 rollout。对比 6 种强基线，结果具有统计稳定性。
- **真实机器人实验**：4 个任务，每任务 10 次 rollout 评估最后 3 个 checkpoints（共 120 次），基线包括 3 种（LCBC、GLCBC、SuSIE）。
- **消融实验**：系统性地剥离了高层规划器（→ LCBC）、改变规划步数和 λ、替换融合策略（平均池化），共计 8 种变体配置。
- **误差分析**：3000 点采样对比前向、后向、并行规划范式。
- **泛化实验**：Shift cups 任务下额外测试了不同背景和干扰物。
- **整体评价**：实验设计较为充分，覆盖了仿真和真实场景、多种基线、关键消融和泛化，结果统计上可信；但真实任务数量（4个）相对有限，且大部分消融仅在仿真上进行。

## 6. 主要结论与发现

1. **LBP 在 LIBERO-LONG 上达到 SOTA**：平均成功率 88.6%（DecisionNCE 潜在空间），超越所有基线（第二名 Seer 78.6%）。在 10 个任务中的 7 个取得最佳或并列最佳。
2. **真实机器人上后程优势显著**：在早期阶段 LBP 略微优于基线，但在后几个阶段（特别是最后阶段）大幅领先，例如 Shift cups 任务 LBP 最终阶段得分 26.6，而 LCBC 为 0.0。证明后向规划有效维持长时域一致性。
3. **后向规划误差远小于前向规划**：在 3000 点采样中，前向规划 MSE 随任务进展快速增大，而 LBP 保持低误差（图 5）。后向规划也优于同时预测所有子目标的并行规划（图 6）。
4. **关键消融验证**：最终目标 zg 提供 6% 的提升；一个子目标即可带来提升，过多子目标反而下降（3 子目标最优）；子目标融合注意力优于平均池化（+9.6%）。
5. **轻量高效**：仅使用 MLP 作为规划器，无需复杂生成模型，支持实时控制。

## 7. 优点

- **方法论新颖性**：首次将后向规划（粗到细递归）应用于机器人潜在空间子目标规划，从根本上解决了前向累积误差问题。
- **性能与效率的平衡**：避免像素级预测，潜在空间 + 轻量 MLP 使规划成本极低，同时通过后向递归保持预测准确性，实现实时部署。
- **子目标融合自适应**：注意力机制可使策略根据不同任务阶段自适应地关注近距或远距子目标，提升规划灵活性。
- **实验严谨**：对比了多种前沿基线（包括预训练大模型 OpenVLA、视频预测方法 Seer、图像编辑方法 SuSIE），消融完整，误差分析直观。
- **泛化能力**：在真实机器人上验证了不同背景和干扰物下的鲁棒性。

## 8. 不足与局限

- **真实机器人任务数量有限**：仅 4 个场景（均为桌面粉杯操作），多样性不足，未在更复杂场景（如抓取-放置、组装等）或动态环境中测试。
- **潜在空间依赖预训练编码器**：使用 DecisionNCE 或 SigLIP，这些编码器的质量直接影响规划性能；在未见过的场景中编码器的泛化能力未深入分析。
- **子目标递归假设线性进展**：λ 系数基于均匀时间间隔采样子目标，对于非线性任务进展可能不是最优；论文未探讨自适应子目标选择（如关键帧检测）的可行性。
- **未与强化学习方法对比**：实验均基于行为克隆范式，未与基于值函数或模型的在线强化学习方法比较。
- **资源可重复性**：未明确报告完整训练的 GPU 型号、数量和时长，可重复性稍弱。
- **泛化实验较弱**：仅在 Shift cups 单任务上测试了背景和干扰物变化，未系统评估跨任务迁移或零样本能力。

（完）
