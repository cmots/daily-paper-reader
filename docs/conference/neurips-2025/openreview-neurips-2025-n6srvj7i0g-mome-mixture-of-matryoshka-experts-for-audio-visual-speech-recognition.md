---
title: "MoME: Mixture of Matryoshka Experts for Audio-Visual Speech Recognition"
title_zh: "MoME: 用于视听语音识别的混合套娃专家"
authors: "Umberto Cappellazzo, Minsu Kim, Pingchuan Ma, Honglie Chen, Xubo Liu, Stavros Petridis, Maja Pantic"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=n6SrVj7I0g"
tags: ["query:speech-model"]
score: 4.0
evidence: 使用混合专家和套娃表示的视听语音识别
tldr: 大语言模型在视听语音识别（AVSR）中表现优异，但计算成本高且对token粒度敏感。本文提出MoME方法，结合混合专家与套娃表示学习，使单一模型能够动态调整压缩率，平衡信息密度与效率，在资源受限场景下实现灵活且高效的AVSR。实验证明了方法的有效性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-n6srvj7i0g/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 715, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n6srvj7i0g/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 657, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n6srvj7i0g/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1417, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n6srvj7i0g/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 857, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n6srvj7i0g/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 716, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n6srvj7i0g/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1447, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n6srvj7i0g/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1422, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n6srvj7i0g/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1408, \"height\": 820, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-n6srvj7i0g/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1453, \"height\": 829, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n6srvj7i0g/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 734, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n6srvj7i0g/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 877, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n6srvj7i0g/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 676, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n6srvj7i0g/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 668, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n6srvj7i0g/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1460, \"height\": 464, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n6srvj7i0g/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 895, \"height\": 474, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n6srvj7i0g/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 971, \"height\": 228, \"label\": \"Table\"}]"
motivation: LLM在AVSR中计算成本高，且现有token压缩方法缺乏灵活性。
method: 提出MoME，将混合专家（MoE）与套娃表示学习（MRL）结合，支持动态粒度调整。
result: MoME在资源受限场景下实现了高效且灵活的AVSR性能。
conclusion: MoME为AVSR提供了一种可扩展且适应性强的解决方案。
---

## Abstract
Large language models (LLMs) have recently shown strong potential in audio-visual speech recognition (AVSR), but their high computational demands and sensitivity to token granularity limit their practicality in resource-constrained settings. Token compression methods can reduce inference cost, but they require fixing a compression rate in advance and produce a single fixed-length output, offering no flexibility to balance information density and efficiency at inference time. Matryoshka representation learning (MRL) addresses this by enabling a single model to operate across multiple token granularities, allowing compression rates to be adjusted dynamically. However, current MRL-based methods treat each scale independently during training, limiting cross-scale generalization, robustness at high compression, and interpretability. To overcome these limitations, we propose MoME (Mixture of Matryoshka Experts), a novel framework that integrates sparse Mixture-of-Experts (MoE) into MRL-based LLMs for AVSR. MoME augments a frozen LLM with top-k routed and shared experts, allowing dynamic capacity allocation across scales and modalities. A shared router promotes consistent expert activation across granularities, enabling compressed sequences to benefit from representations learned at lower compression. Experiments on LRS2 and LRS3 demonstrate that MoME achieves state-of-the-art performance across AVSR, ASR, and VSR tasks, while requiring significantly fewer parameters and maintaining robustness under noise. MoME unifies the adaptability of MRL with the efficiency of MoE, offering a scalable and interpretable solution for resource-aware speech recognition.

---

## 论文详细总结（自动生成）

以下是基于论文《MoME: Mixture of Matryoshka Experts for Audio-Visual Speech Recognition》的详细中文总结，按照要求的八个要点依次展开。

---

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **背景**：大型语言模型（LLM）在视听语音识别（AVSR）领域展现出很强潜力，但存在计算成本高、对输入 token 粒度敏感的问题。传统的 token 压缩方法（如平均池化、Q-Former、CTC 压缩等）需要预先固定压缩率，只能输出单一固定长度的序列，无法在推理时动态权衡信息保真度和计算效率。
- **现有局限**：Matryoshka 表示学习（MRL）允许单一模型支持多种 token 粒度，实现弹性推理，但当前 MRL 方法在训练时将不同尺度独立对待，缺乏跨尺度泛化能力，导致高压缩率下性能下降明显，且缺乏可解释性。
- **核心问题**：如何在保持单模型弹性推理的同时，促进跨粒度知识迁移，提升高压缩率下的鲁棒性，并降低参数量和计算开销。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将稀疏混合专家（Sparse MoE）与 Matryoshka 表示学习（MRL）相结合，提出 **MoME（Mixture of Matryoshka Experts）** 模块。模块插入在冻结的 LLM 层内（并行于 MHSA、FFN 或整个 Transformer 层），通过**共享路由器**和**共享专家**实现跨尺度专家激活一致性，使高压缩（低分辨率）序列能够借鉴低压缩（高分辨率）序列学到的知识。
- **关键技术细节**：
  - 使用预训练的音频编码器（Whisper）和视频编码器（AV-HuBERT）提取特征，并通过平均池化生成不同压缩率下的 token 序列，构成 Matryoshka 多尺度输入。
  - MoME 模块包含：
    - **路由专家（Routed Experts）**：K 个 Top-K 激活的稀疏专家，每个专家采用瓶颈结构（down-projection → GELU → up-projection），瓶颈维度可极小（甚至为1）。
    - **共享专家（Shared Experts）**：总是激活，用于捕捉跨尺度和跨模态的全局、尺度不变知识。
    - **共享路由器（Shared Router）**：对所有粒度的 token 使用同一路由器，选择相似的专家子集，促进跨粒度对齐。
  - 损失函数：对每个音频-视频尺度组合计算自回归下一个 token 预测损失，取平均；同时加入负载均衡损失（Load Balancing Loss）防止路由器崩溃。
- **公式**：MoME 输出 = 共享专家输出之和 + 路由专家输出的稀疏门控加权和；门控值通过 Top-K 选取。

### 3. 实验设计：数据集、benchmark、对比方法

- **数据集**：LRS2（约225小时）、LRS3（约433小时）。任务包括 AVSR、ASR、VSR。
- **基准 Benchmark**：词错误率（WER）。
- **对比方法**：
  - 固定压缩率方法：Llama-AVSR（每个尺度独立训练）、MoME-23/4-MHSA-I（独立训练版本）。
  - Matryoshka 方法：Llama-MTSK（MS/SS/MSS三种配置）。
  - 其他 SOTA 方法（在气泡图中比较）：UniVPM、USR、Whisper-Flamingo、Auto-AVSR、AV-HuBERT、MMS-Llama 等。
- **压缩率设置**：
  - ASR：{4,8,12,16,20}；VSR：{1,2,3,4,5}；AVSR：音频{4,16} × 视频{2,5}，共4种组合。
- **模型选择**：音频编码器 Whisper-small/medium，视频编码器 AV-HuBERT Large，LLM为 Llama 3.2-1B、3.2-3B、3.1-8B。

### 4. 资源与算力

- **训练资源**：使用 NVIDIA H200 GPU（具体数量未明确说明），训练 10 个 epoch，优化器 AdamW，余弦退火调度器，学习率 1e-3（ASR/AVSR）或 5e-4（VSR），权重衰减 0.1。
- **推理测量**：在单个 NVIDIA L40 46GB GPU 上进行推理时间测试。
- **备注**：论文未明确给出训练时使用的 GPU 数量和总训练时长，但提供了足够复现的超参数。

### 5. 实验数量与充分性

- **实验数量丰富**：主要实验包括：
  - 表1：AVSR 在 LRS2/LRS3 上 4 种压缩率下的 WER 对比（MoME 三种插入位置 vs. Llama-AVSR, Llama-MTSK）。
  - 表2：噪声鲁棒性实验（不同 SNR 下 WER）。
  - 图1：气泡图对比多个 SOTA 方法（WER vs. 激活参数量 vs. 训练数据小时）。
  - 图3：ASR 和 VSR 任务在 LRS3 上的 WER 曲线。
  - 表3：消融实验（路由专家数量、共享专家数量、专家瓶颈维度）。
  - 表4：Top-K 值消融。
  - 表7：共享路由器 vs. 分离路由器、非均匀权重消融。
  - 可视化分析：专家激活分布（图5、图9）、跨模态/跨粒度相似性矩阵（图4、图8）。
- **充分性评价**：实验覆盖了多个数据集、多种任务、多种压缩率、多种MoME配置以及噪声场景，消融分析全面，对比基线公平（与同类方法使用相同编码器/LLM）。结论可信。

### 6. 论文的主要结论与发现

- **性能领先**：MoME 在 AVSR、ASR、VSR 任务上均优于现有固定压缩率和 Matryoshka 方法，尤其是在高压缩率下，性能下降更小。
- **参数高效**：通过稀疏激活和极小瓶颈设计，MoME 激活参数仅 0.9M~14.1M，远少于 Llama-MTSK 等方法。
- **弹性推理**：单一模型可涵盖多种压缩率，推理时可根据资源约束动态选择压缩率，TFLOPs 最多降低 8 倍，WER 仅小幅上升。
- **鲁棒性**：在噪声环境下（SNR 低至 -5dB），MoME 明显优于基线。
- **可解释性**：可视化表明 MoME 促进了跨粒度专家激活一致性，且音频/视频 token 在不同压缩率下呈现线性相关，验证了跨尺度知识迁移。

### 7. 优点

- **创新性**：首次将 MoE 与 MRL 统一在同一框架，通过共享路由和共享专家实现跨粒度知识迁移。
- **灵活性**：MoME 可并行插入 LLM 的多个位置（MHSA、FFN、整个层），支持极低参数量（瓶颈维度=1）的微调。
- **实用性**：单模型满足多种计算预算，无需为每个压缩率重训练；推理时间和内存可大幅降低。
- **可解释性**：专家激活可视化揭示了模型如何在各层、各粒度间分配计算资源。
- **泛化潜力**：作者指出 MoME 可扩展至其他多模态任务（如视觉-语言），只需最小适配。

### 8. 不足与局限

- **内存开销**：尽管推理时只激活少量专家，但所有专家权重仍需驻留在 GPU 内存中，造成额外存储成本（MoE 的固有缺点）。不过由于专家瓶颈很小，整体尚可接受。
- **推理速度**：MoME 推理时间略高于 Llama-AVSR 和 Llama-MTSK（约 1.25 倍），主要来自路由和专家分派开销。
- **领域局限**：实验仅聚焦于音频-视觉语音识别，未在其他多模态任务（如视觉问答、图文检索）上验证，泛化能力尚待检验。
- **公平性/偏差**：依赖于预训练 LLM 和编码器，可能继承其偏见，论文建议部署前进行安全与公平性评估。

---

（完）
