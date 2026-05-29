---
title: Test-Time Adaptation for Online Vision-Language Navigation with Feedback-based Reinforcement Learning
title_zh: 基于反馈强化学习的在线视觉语言导航测试时自适应
authors: "Sungjune Kim, Gyeongrok Oh, Heeju Ko, Daehyun Ji, Dongwook Lee, Byung-Jun Lee, Sujin Jang, Sangpil Kim"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=K4GaB4fdIq"
tags: ["query:wm-vla-sa"]
score: 8.0
evidence: 基于强化学习的视觉语言导航测试时自适应
tldr: 视觉语言导航（VLN）代理在部署时面临陌生环境，现有方法缺乏在线自适应能力。本文提出FeedTTA框架，利用反馈强化学习，使代理在测试阶段根据交互结果（成功/失败）进行在线适应，同时保持塑性-稳定性平衡。该方法在多个VLN基准上取得显著提升，为机器人导航中的测试时适应提供了有效范本，与VLA模型中的视觉-语言-动作联合学习高度相关。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 859, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 864, \"height\": 256, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1774, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 866, \"height\": 325, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 880, \"height\": 232, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1780, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k4gab4fdiq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1741, \"height\": 411, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1733, \"height\": 552, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 855, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 851, \"height\": 154, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 854, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 755, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 873, \"height\": 155, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1724, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 865, \"height\": 155, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1539, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k4gab4fdiq/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 724, \"height\": 109, \"label\": \"Table\"}]"
motivation: 视觉语言导航代理在陌生环境中缺乏测试时自适应能力。
method: 提出FeedTTA，通过最大化二元情节反馈信号的奖励来在线调整代理策略。
result: 在多个VLN数据集上，FeedTTA显著提升了导航成功率。
conclusion: 测试时自适应是VLA系统实用化的关键，该工作为机器人导航提供了即插即用方案。
---

## Abstract
Navigating in an unfamiliar environment during deployment poses a critical challenge for a vision-language navigation (VLN) agent. Yet, test-time adaptation (TTA) remains relatively underexplored in robotic navigation, leading us to the fundamental question: what are the key properties of TTA for online VLN? In our view, effective adaptation requires three qualities: 1) flexibility in handling different navigation outcomes, 2) interactivity with external environment, and 3) maintaining a harmony between plasticity and stability. To address this, we introduce FeedTTA, a novel TTA framework for online VLN utilizing feedback-based reinforcement learning. Specifically, FeedTTA learns by maximizing binary episodic feedback, a practical setup in which the agent receives a binary scalar after each episode that indicates the success or failure of the navigation. Additionally, we propose a gradient regularization technique that leverages the binary structure of FeedTTA to achieve a balance between plasticity and stability during adaptation. Our extensive experiments on challenging VLN benchmarks demonstrate the superior adaptability of FeedTTA, even outperforming the state-of-the-art offline training methods in REVERIE benchmark with a single stream of learning.

---

## 论文详细总结（自动生成）

## 论文详细中文总结

### 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：视觉语言导航（VLN）代理在训练时通常基于大量标注的专家演示进行模仿学习，但在实际部署中不可避免地会遇到**未见过的环境**，导致策略性能下降。因此，**测试时自适应（TTA）**——即代理在测试阶段根据在线数据流即时调整策略——对机器人导航至关重要。
- **现有局限**：已有方法（如 FSTTA）采用熵最小化进行 TTA，但存在以下问题：
  - 对失败样本的过度拟合，降低策略韧性；
  - 限制探索，无法平衡利用与探索。
- **本文目标**：提出适用于在线 VLN 的 TTA 框架，需满足三个关键性质：
  - **灵活性**：适应不同导航结果（成功/失败）；
  - **交互性**：能够从外部环境（如人类用户或 AI）接收反馈信号；
  - **可塑性与稳定性**：既能学习新知识又避免灾难性遗忘。

### 2. 方法论

- **核心思想**：利用**二元情节反馈**（binary episodic feedback）进行强化学习。在每个测试导航片段结束后，由 oracle（人类或 AI）给出 +1（成功）或 -1（失败）的反馈。代理通过最大化累积反馈来调整策略。

- **关键技术细节**：
  1. **反馈机制**： oracle 根据轨迹是否完成指令给出二元标量反馈 \( F \in \{+1, -1\} \)。
  2. **反馈策略梯度**：基于 REINFORCE 算法，目标函数为：
     \[
     J(\theta) = \mathbb{E}_{\tau \sim \pi_\theta} \left[ \sum_{t=0}^{T-1} \gamma^{T-t-1} F \right]
     \]
     梯度近似为：
     \[
     \nabla_\theta J(\theta) \approx \mathbb{E}_{a_t,s_t \sim \tau} \left[ \sum_{t=0}^{T-1} \nabla_\theta \log \pi_\theta(a_t|s_t) \gamma^{T-t-1} F \right]
     \]
     更新仅依赖最终反馈，无需步骤级奖励，适用于在线场景。
  3. **随机梯度反转 (Stochastic Gradient Reversion, SGR)**：为解决二元反馈导致的非平稳性（梯度指向极端方向），SGR 随机选择参数子集，反转其梯度方向并缩放其他梯度以保持期望不变：
     - 从梯度向量 \(\nabla_\theta J(\theta)\) 中按概率 \(p\) 采样子集 \(G\);
     - 对 \(g_{\theta_m} \in G\) 乘以负系数 \(\alpha (<0)\)，对其余乘以 \(\frac{1}{\alpha p + (1-p)}\)。
     - 使得期望梯度不变，但实际更新更平滑，促进可塑性与稳定性。

- **算法流程**（Algorithm 1）：
  - 初始化策略 \(\pi_\theta\);
  - 对于每个在线数据 \(X_n\)：
    1. 遵循指令生成轨迹 \(\tau\);
    2. 接收二元反馈 \(F\);
    3. 计算原始策略梯度；
    4. 应用 SGR 修改梯度；
    5. 梯度上升更新参数 \(\theta\)。
  - 返回适应后的策略。

### 3. 实验设计

- **数据集与场景**：
  - **REVERIE**：目标导向任务，需要定位远程物体（高层面指令）。
  - **R2R**：细粒度导航指令，要求精确到达目标点（3米半径）。
  - **R2R-CE**：R2R 的连续环境版本。
- **Benchmark 与评价指标**：
  - 标准指标：TL（轨迹长度）、NE（导航误差）、SR（成功率）、OSR（oracle 成功率）、SPL（成功路径加权）、RGS/RGSPL（远程接地成功）。
  - 提出新指标：**自适应成功率 (ASR)**，衡量样本级过渡：\(ASR = \frac{1}{2} [P(S_{\text{TTA}}|S_{\text{base}}) + P(S_{\text{TTA}}|F_{\text{base}})]\)，其中 PSR 为保持成功率，CSR 为转化成功率。
- **对比方法**：
  - **离线训练方法**：HAMT、DUET、BEVBert、EPTNav 等。
  - **TTA 基线**：Tent（熵最小化）、FSTTA（ICML 2024），均进行了复现（†标记）。

### 4. 资源与算力

- 论文明确说明：**所有实验在单个 NVIDIA Tesla A100 GPU 上运行**。
- 但强调 FeedTTA **不需要高端服务器级 GPU**，可在实用硬件（如 GTX 1080）上高效部署。
- **未提供具体训练时长**，仅在 REVERIE 表 1 中报告了推断时间（每4个片段平均毫秒数），FeedTTA 为 384.2 ms（HAMT）和 672.0 ms（DUET），比离线推理略高但可接受。

### 5. 实验数量与充分性

- **实验数量**：丰富且系统。
  - 主实验：在 REVERIE、R2R、R2R-CE 三个数据集上对比多种方法。
  - 消融实验：
    - 反馈质量（精度从50%到100%）；
    - 反馈数量（前K样本比例、更新间隔）；
    - 使用 LLM 作为 oracle（GPT-4o 和 GPT-4o-mini）；
    - SGR 效果（对比无正则化、梯度丢弃 GD、梯度缩放 GS）；
    - 权重幅度与塑性分析；
    - 灾难性遗忘测试（适应后在原验证集上评估）；
    - 不同反馈策略比较（二元 vs 密集距离奖励）；
    - 轨迹可视化与不确定性区域分析；
    - 序列顺序影响（一般 TTA、连续 TTA、逐场景 TTA）。
- **充分性与公平性**：
  - 所有基线均使用官方或复现代码，确保公平。
  - 多次实验（不同种子）报告均值和标准差。
  - 引入 ASR 指标更细致地评估适应性。
  - 结论：实验设计全面，对比充分，结论可靠。

### 6. 论文主要结论与发现

- **FeedTTA 显著优于现有 TTA 方法**：在所有数据集上，SR、SPL 等指标大幅提升，例如在 REVERIE 验证未见分集上，DUET+FeedTTA 的 SR 从 46.98% 提升至 66.49%，SPL 从 33.73% 提升至 45.38%。
- **超过离线 SOTA**：仅用单流在线学习，FeedTTA 在 REVERIE 上超越了之前所有的离线训练方法。
- **SGR 的有效性**：反转梯度（α<0）比梯度丢弃或梯度缩放更优，有效提升 CSR 和整体 ASR，减少权重幅度增长，防止塑性丢失。
- **反馈鲁棒性**：即使反馈精度低至 50-60%，FeedTTA 仍优于基线；仅用前20%样本提供反馈即可超过基线。
- **LLM 可作为 oracle**：GPT-4o 达到 72% 反馈精度，能有效驱动适应，但可靠性仍需提高。
- **适应性分析**：FeedTTA 在长轨迹场景中保持稳定表现，而基线随轨迹长度增加性能下降。

### 7. 优点

- **方法简洁实用**：仅需要二元片段反馈（成功/失败），无需步骤级标注或地面真值位置，非常适合真实在线部署。
- **SGR 创新**：针对二元反馈非平稳性提出的梯度正则化，兼顾可塑性与稳定性，理论分析（EAV）和实验验证充分。
- **实验全面系统**：覆盖多个数据集、多类基线、大量消融，引入 ASR 指标更精细评估。
- **鲁棒性高**：对反馈噪声和稀疏性具有良好容忍度。
- **可扩展性**：支持人类或 AI 作为 oracle，为未来更高级反馈系统提供基础。

### 8. 不足与局限

- **LLM oracle 可靠性不足**：当前 LLM 的导航判断准确率（72%）仍低于人类，需谨慎使用于安全关键场景。
- **跨任务迁移能力有限**：在 REVERIE→R2R 或 R2R→REVERIE 的交叉任务实验中，性能提升较小（如 RGSPL 几乎不变），说明任务间知识共享有限。
- **反馈数量与性能正相关**：虽然少量反馈即可带来收益，但频繁更新效果更佳，实际部署中可能需平衡交互成本。
- **未验证大规模连续适应中的长期稳定性**：实验主要在有限长度的在线流上进行，长期持续适应中的灾难性遗忘风险未充分探讨。
- **资源开销**：虽然推理时间可接受，但参数更新仍带来额外计算，在资源受限的嵌入式设备上可能受限。

（完）
