---
title: Reward-free World Models for Online Imitation Learning
title_zh: 用于在线模仿学习的无奖励世界模型
authors: "Shangzhe Li, Zhiao Huang, Hao Su"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=owEhpoKBKC"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 无奖励世界模型用于模仿学习
tldr: 该论文针对在线模仿学习在高维复杂动态任务中的困难，提出无奖励世界模型，在潜在空间中学习环境动态而无需重建，结合逆软Q学习目标在Q-策略空间中优化，提高了稳定性和效率。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-owehpokbkc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1036, \"height\": 686, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-owehpokbkc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1613, \"height\": 850, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-owehpokbkc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1607, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-owehpokbkc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1612, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-owehpokbkc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 686, \"height\": 1024, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-owehpokbkc/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1513, \"height\": 904, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-owehpokbkc/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1515, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-owehpokbkc/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1294, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-owehpokbkc/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1613, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-owehpokbkc/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1584, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-owehpokbkc/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1592, \"height\": 1065, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-owehpokbkc/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1588, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-owehpokbkc/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1585, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-owehpokbkc/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1591, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-owehpokbkc/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1613, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-owehpokbkc/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 883, \"height\": 660, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-owehpokbkc/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 763, \"height\": 601, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-owehpokbkc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1179, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-owehpokbkc/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1332, \"height\": 385, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-owehpokbkc/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 939, \"height\": 191, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-owehpokbkc/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 970, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-owehpokbkc/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 933, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-owehpokbkc/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 743, \"height\": 147, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-owehpokbkc/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 783, \"height\": 278, \"label\": \"Table\"}]"
motivation: 现有在线模仿学习难以处理高维复杂动态。
method: 构建无奖励世界模型，在潜在空间学习动态，使用逆软Q学习。
result: 在复杂任务上表现优于基线。
conclusion: 无奖励世界模型有效提升了模仿学习性能。
---

## Abstract
Imitation learning (IL) enables agents to acquire skills directly from expert demonstrations, providing a compelling alternative to reinforcement learning. However, prior online IL approaches struggle with complex tasks characterized by high-dimensional inputs and complex dynamics. In this work, we propose a novel approach to online imitation learning that leverages reward-free world models. Our method learns environmental dynamics entirely in latent spaces without reconstruction, enabling efficient and accurate modeling. We adopt the inverse soft-Q learning objective, reformulating the optimization process in the Q-policy space to mitigate the instability associated with traditional optimization in the reward-policy space. By employing a learned latent dynamics model and planning for control, our approach consistently achieves stable, expert-level performance in tasks with high-dimensional observation or action spaces and intricate dynamics. We evaluate our method on a diverse set of benchmarks, including DMControl, MyoSuite, and ManiSkill2, demonstrating superior empirical performance compared to existing approaches.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：在线模仿学习（IL）在处理高维输入和复杂动态的任务时存在困难，例如高维观测/动作空间、复杂动力学。传统方法（如GAIL、IQ-Learn）在reward-policy空间进行min-max优化，导致训练不稳定；且缺少对环境的深层理解，存在分布外误差和偏差累积。
- **动机**：世界模型在强化学习中表现出色，能够高效建模环境动态并用于规划，但在模仿学习中应用较少。本文希望利用无奖励的世界模型来提升在线IL在复杂任务上的性能和稳定性，同时避免显式奖励建模。
- **整体含义**：提出一种无需显式奖励信号的世界模型方法，通过在潜空间学习动态并结合逆软Q学习，实现稳定、专家级性能的高维控制任务，为复杂机器人任务提供高效IL框架。

## 2. 方法论：核心思想、关键技术细节、公式/算法流程
- **核心思想**：构建一个“无奖励世界模型”，在潜空间学习环境动态（编码器+潜动态模型），无需重建观测；利用逆软Q学习目标将优化从reward-policy空间转移到Q-policy空间，消除显式奖励模型，从Q值解码奖励；使用模型预测控制（MPC）进行规划，结合策略先验引导采样。
- **关键技术细节**：
  - **模型组件**：编码器 `z = h(s)`，潜动态 `z' = d(z, a)`，Q函数 `q = Q(z, a)`，策略先验 `a = π(z)`。
  - **模型学习**：联合最小化预测一致性损失（L2）和逆软Q critic目标（式12）。critic目标使用初始分布形式（式12第二项）稳定Q估计，并加入χ²正则化（α控制强度）。损失形式：
    \[
    L = \sum_{t=0}^H \lambda^t \mathbb{E}[\|z_{t+1} - \text{sg}(h(s'_t))\|^2_2] + L_{iq}
    \]
    \[
    L_{iq} = \sum_{t=0}^H \lambda^t \left[ -\mathbb{E}_{B_E}[Q(z_t,a_t) - \gamma \bar{V}^\pi(h(s'_t))] + \mathbb{E}_{s_0\sim B_E}[(1-\gamma)V^\pi(z_0)] + \mathbb{E}_B[\frac{1}{4\alpha}(Q(z_t,a_t)-\gamma\bar{V}^\pi(h(s'_t)))^2] \right]
    \]
  - **策略先验学习**：使用最大熵RL目标（式13），最小化负Q值与熵项。
  - **平衡训练**：加入Wasserstein-1梯度惩罚（式14）防止critic过强导致策略崩溃。
  - **规划（IQ-MPC）**：使用MPPI算法，基于解码的奖励 `r(z,a)=Q(z,a)-γV^π(z')` 和策略先验轨迹进行规划，执行最优动作序列的第一动作。
- **理论保证**：证明学习目标最小化了当前策略与专家策略期望回报的差距上界（Lemma 4.1，结合动力学误差和分布距离）。

## 3. 实验设计：数据集/场景、benchmark、对比方法
- **场景与数据集**：
  - **DMControl**：6个运动任务（Hopper, Walker, Quadruped, Cheetah, Humanoid, Dog），包含低维和高维任务。使用2-3个观测维度（例如Humanoid 67维，Dog 223维）。
  - **MyoSuite**：3个灵巧手操作任务（Key Turn, Object Hold, Pen Twirl），观测维度91-93，动作39维。
  - **ManiSkill2**：2个简单操作任务（Pick Cube, Lift Cube）。
  - **视觉实验**：DMControl的Cheetah Run、Walker Run/Walk，使用RGB 64×64×9输入（3帧堆叠）。
- **基准与对比方法**：
  - 对比方法：IQ-Learn+SAC（IQL+SAC），CFIL+SAC，HyPE（均为在线IL方法，均为SOTA模型）。
  - 视觉实验中对比修改后的IQL+SAC（加入卷积编码器）。
- **实验细节**：
  - 专家轨迹数量：低维任务100条，Humanoid 500条，Dog 1000条，MyoSuite 100条，视觉任务100条。每条轨迹500步（DMControl）或100步（MyoSuite）。
  - 每个任务3个随机种子，报告平均性能。

## 4. 资源与算力
- 论文中明确提及：所有基线训练使用单张RTX 2080 Ti GPU（在附录F图16中说明）。
- 训练时间对比：IQ-MPC在Humanoid Walk任务上训练时间高于IQL+SAC等模型无关方法，但低于HyPER（另一种模型基方法）。未给出具体小时数。
- 未说明训练总时长、模型参数量（约4.3M可学习参数）、多卡训练等信息。

## 5. 实验数量与充分性
- **实验数量**：主要实验包括6个DMControl运动任务、3个MyoSuite操作任务、2个ManiSkill2任务、3个视觉任务；消融实验包括专家轨迹数量（4种）、目标公式化（2种）、梯度惩罚（2种）、超参数α（5种）、噪声动态鲁棒性（2种噪声水平），以及额外Dog任务和少量演示实验。共计约30+组实验（含子任务）。
- **充分性与公平性**：
  - 对比方法代码开源、超参数一致，各实验均使用相同专家数据和种子。
  - 消融实验覆盖了关键设计选择（目标形式、正则化、数据量）。
  - 缺点：未在相同硬件和训练时间下严格对齐基线（但给出时间对比图）；未对比更多模型（如Dreamer-based方法）；视觉实验仅对比一个基线；MyoSuite任务基线在某些任务上完全失败（如Pen Twirl），但论文未深入分析原因。

## 6. 主要结论与发现
- 提出的IQ-MPC在几乎所有任务上**优于或显著优于**现有在线IL方法（IQ-Learn+SAC, CFIL+SAC, HyPE），尤其在复杂高维任务（Humanoid, Dog, MyoSuite）表现出稳定的专家级性能。
- 视觉实验也展示出优于卷积编码器加持的IQL+SAC。
- 奖励恢复分析显示IQ-MPC解码的奖励与真实奖励具有较高Pearson相关性（0.87-0.93），优于IQL+SAC。
- 消融实验验证了：初始分布形式的目标更稳定；梯度惩罚可改善Q估计收敛；α=0.5为最优；小样本（5-10条）下仍能学习但收敛慢。

## 7. 优点
- **方法创新**：将世界模型与逆软Q学习结合消除显式奖励模型，首次提出“无奖励世界模型”用于在线IL，避免了奖励建模的不稳定性。
- **理论支撑**：给出子优界分析，证明训练目标同时最小化动态误差和分布距离。
- **实验全面**：覆盖运动、灵巧操作、视觉输入，包含低维/高维、简单/复杂任务，消融系统。
- **鲁棒性**：在噪声动态下仍保持性能（附录E.4）。
- **高效性**：潜空间学习无重建，计算开销低于HyPER，与模型无关方法差距不大。

## 8. 不足与局限
- **低维观测/动作空间不稳定**：文中指出当观测/动作维度很低时，判别器过强导致训练不稳定（需梯度惩罚缓解），但未彻底解决。
- **计算开销**：由于使用MPC规划，训练时间仍比模型无关方法慢（附录F），可能限制实时部署。
- **实验覆盖有限**：未与Dreamer-based IL方法（如Ditto, CMIL）进行对比；未在真实机器人上验证；MyoSuite基线在某些任务完全失败，但未深入分析失败原因。
- **理论假设强**：分析中假设潜动态为高斯分布且方差相近（附录H.3），实际中可能不成立。
- **未讨论奖励恢复的鲁棒性**：仅一个环境（Cheetah Run）做相关性分析，其他环境仅列出数值，缺乏视觉化解释。
- **未给出完整超参数敏感性**：只对α进行系统消融，其他超参数（如λ, β, H）依赖经验设定。

（完）
