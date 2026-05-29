---
title: Overcoming Non-monotonicity in Transducer-based Streaming Generation
title_zh: 克服基于Transducer的流式生成中的非单调性问题
authors: "Zhengrui Ma, Yang Feng, Min zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=HfefR1baKA"
tags: ["query:speech-model"]
score: 8.0
evidence: 基于Transducer的流式生成用于同声传译，关联语音到语音翻译
tldr: 针对流式翻译中Transducer架构无法处理非单调对齐的问题，本文提出可学习的单调注意力机制，利用前向后向算法推断对齐后验概率，避免指数级搜索空间。实验表明该方法有效解决了非单调对齐问题，提升了同声传译的质量。该工作为流式生成模型在翻译中的应用提供了可行方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-hfefr1baka/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1764, \"height\": 997, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hfefr1baka/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1749, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hfefr1baka/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1769, \"height\": 999, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hfefr1baka/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1768, \"height\": 1005, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hfefr1baka/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1769, \"height\": 999, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hfefr1baka/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1768, \"height\": 1005, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-hfefr1baka/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hfefr1baka/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1772, \"height\": 550, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hfefr1baka/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 875, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hfefr1baka/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 797, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hfefr1baka/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 797, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hfefr1baka/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1640, \"height\": 539, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hfefr1baka/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1191, \"height\": 561, \"label\": \"Table\"}]"
motivation: Transducer的输入同步解码机制在同时翻译等需要非单调对齐的任务中受限。
method: 集成可学习的单调注意力，通过前向后向算法估计对齐后验。
result: 实验表明该方法有效解决了非单调对齐问题，提升了翻译质量。
conclusion: 为流式生成模型在同时翻译中的应用提供了可行方案。
---

## Abstract
Streaming generation models are utilized across fields, with the Transducer architecture being popular in industrial applications. However, its input-synchronous decoding mechanism presents challenges in tasks requiring non-monotonic alignments, such as simultaneous translation. In this research, we address this issue by integrating Transducer's decoding with the history of input stream via a learnable monotonic attention. Our approach leverages the forward-backward algorithm to infer the posterior probability of alignments between the predictor states and input timestamps, which is then used to estimate the monotonic context representations, thereby avoiding the need to enumerate the exponentially large alignment space during training. Extensive experiments show that our MonoAttn-Transducer effectively handles non-monotonic alignments in streaming scenarios, offering a robust solution for complex generation tasks. Code is available at https://github.com/ictnlp/MonoAttn-Transducer.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：Transducer 架构在流式生成中采用输入同步解码，每个输出 token 必须显式对齐到一个输入 token。这在语音识别等单调对齐任务中表现良好，但在需要非单调对齐的任务（如同声传译，因语言间词序差异需要重排序）中，其解码机制限制了模型利用输入历史的能力，导致翻译质量下降。
- **研究动机**：现有方法尝试在 Transducer 中引入交叉注意力来解决非单调性，但会导致状态空间指数级膨胀，无法使用标准的前向后向算法进行端到端训练。
- **整体含义**：本文提出 MonoAttn-Transducer，通过可学习的单调注意力让预测器能够根据输入流的实时历史进行上下文感知解码，同时保持训练和推理效率，为 Transducer 在复杂流式生成任务中的应用提供了可行方案。

### 2. 论文提出的方法论

- **核心思想**：在 Transducer 的预测器中引入单调交叉注意力，使每个预测器状态能关注已到达的源端历史。训练时利用前向后向算法推导预测器状态与输入时间戳之间的对齐后验概率，并用该后验概率估计期望的上下文表示，从而避免枚举指数级对齐空间。
- **关键技术细节**：
    - **后验对齐**：定义对齐后验概率 \(\pi_{u,t}\) 表示生成第 u 个目标 token 的时刻恰好是读到第 t 个源 token 的时刻。利用公式 (7) 通过前向变量 \(\alpha(t,u)\) 和后向变量 \(\beta(t,u)\) 快速计算，复杂度 \(O(TU)\)。
    - **单调注意力期望上下文**：基于后验对齐，用公式 (9) 计算每个预测器状态的期望上下文向量 \(c_u\)，其中使用了累积和操作实现高效计算。
    - **鸡生蛋问题**：后验对齐依赖于上下文表示，而上下文表示又依赖后验对齐。解法是先用一个先验对齐（如均匀分布或对角先验 \(p^{\text{dia}}_{u,t}\)）构造初始输出概率格子，推导出后验对齐，再用该后验训练单调注意力。
    - **块同步机制**：对于语音任务，输入被分成块（chunk），将同一块内所有帧的后验概率聚集到块的最后一帧，以使训练与推理的接收范围一致。
- **算法流程**（Algorithm 1）：
    1. 计算对角先验对齐 \(p^{\text{dia}}_{u,t}\)。
    2. 根据块大小 C 计算块同步后的先验 \(\tilde{p}^{\text{dia}}_{u,t}\)。
    3. 用 \(\tilde{p}^{\text{dia}}_{u,t}\) 估计上下文 \(c^{\text{prior}}_u\)。
    4. 使用 \(c^{\text{prior}}_u\) 前向传播 MonoAttn-Transducer，获得输出概率格子。
    5. 推导后验对齐 \(\pi_{u,t}\)。
    6. 块同步后验 \(\tilde{\pi}_{u,t}\)。
    7. 用 \(\tilde{\pi}_{u,t}\) 重新估计上下文 \(c_u\)。
    8. 使用 \(c_u\) 再次前向传播并计算总概率损失 L。

### 3. 实验设计

- **数据集与场景**：
    - 语音到文本同声传译：MuST-C 英→德（En→De）和英→西（En→Es）数据集。
    - 语音到语音同声传译：CVSS-C 法→英（Fr→En）数据集。
- **基准模型（Baseline）**：使用 Transformer-Transducer 作为基线，并与其自己的实现对比。
- **对比方法**：包括 Wait‑k、RealTrans、MU‑ST、Seg2Seg、EDAtt、AlignAtt（AED 类）、CAAT（Transducer 类）、NAST（CTC 类）、LSG（LLM 类）等。此外还与 TAED 进行了间接比较。
- **评估指标**：
    - 翻译质量：BLEU、COMET-22 分数。
    - 延迟：Average Lagging (AL)、Length‑Adaptive Average Lagging (LAAL)、Average Proportion (AP) 等。
- **实验设置**：通过改变块大小（320ms、640ms、960ms、1280ms、∞）获得不同延迟条件。报告了理想延迟和计算感知延迟。

### 4. 资源与算力

- **明确说明**：预训练阶段大约需要 1 天（50k 步），流式微调阶段再需 1 天，使用 4 块 Nvidia L40 GPU。训练时采用自动混合精度。
- **额外细节**：MonoAttn-Transducer 相比 Transducer 基线训练速度慢约 1.33 倍，峰值显存从 28GB 增加到 32GB（源帧数固定为 40000 时）。

### 5. 实验数量与充分性

- **实验数量**：进行了两组主要实验（ST 两个语言对各 5 种块大小 + 语音到语音 2 种块大小），并在 En→Es 上根据非单调性难易度（easy、medium、hard）进行了子集分析，以及训练效率对比（训练时间、内存）。
- **充分性**：实验设计较为全面：覆盖了多语言、多模态；对比了多种先进方法；进行了消融（Posterior vs Prior）；分析了不同延迟条件下的表现；提供了可视化对齐图。总体客观且公平，但缺少与 TAED 的直接对比（因其代码未公开）。

### 6. 论文的主要结论与发现

- MonoAttn-Transducer 在所有延迟条件下均显著优于 Transducer 基线，尤其在大块大小下提升更明显（En→Es 平均提升 0.75 BLEU，En→De 平均提升 2.06 COMET）。
- 使用后验对齐训练的模型（Posterior）优于直接使用先验（Prior），特别是在小块大小下，表明后验能提供更精确的对齐估计。
- 在语音到语音任务中，使用 320ms 块大小即可达到基线离线质量，延迟降低了 118ms；离线设置下进一步提高了生成质量（ASR‑BLEU 19.3 vs 18.0）。
- 在处理高非单调性样本（hard 子集）时，MonoAttn-Transducer 的改进更明显，证明了其对重排序的处理能力。

### 7. 优点

- **方法创新性**：首次将单调注意力与 Transducer 结合，通过后验对齐避免了指数级状态空间，训练和推理复杂度与标准 Transducer 相同（O(U) 推理、O(1) 注意力内存）。
- **实验全面性**：覆盖不同语言对、不同模态、多种延迟条件，并进行了消融和子集分析，结论可靠。
- **实用性**：代码开源，训练过程只需额外一次预测器前向传播，资源开销可接受。
- **可视化分析**：提供了先验与后验对齐的对比图，直观展示了后验的优越性。

### 8. 不足与局限

- **对比不完整**：未能与 TAED 在同一框架下直接对比，仅有间接比较；且部分基线（如 AlignAtt）在长延迟下表现更好，但论文主要关注短延迟。
- **实验范围有限**：仅验证了翻译任务，未扩展到其他流式生成任务（如流式语音识别、流式文本生成）。
- **对小块大小的适应性**：在 320ms 极小块下，MonoAttn-Transducer 的提升不如大块明显，且在 Prior 模式下性能甚至下降，表明细粒度对齐仍存在挑战。
- **训练复杂性**：需要两阶段训练（预训练离线+微调流式），且需要先验对齐的合理设计，可能增加调参成本。
- **潜在偏差**：实验仅使用 MuST-C 和 CVSS-C 数据集，语言对覆盖较少，在更多样化场景中的泛化性未验证。

（完）
