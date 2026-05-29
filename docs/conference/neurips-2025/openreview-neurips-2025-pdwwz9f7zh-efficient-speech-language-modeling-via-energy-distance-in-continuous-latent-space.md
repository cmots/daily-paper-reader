---
title: Efficient Speech Language Modeling via Energy Distance in Continuous Latent Space
title_zh: 通过连续潜空间中的能量距离实现高效语音语言建模
authors: "Zhengrui Ma, Yang Feng, Chenze Shao, Fandong Meng, Jie Zhou, Min zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=pDWwz9F7Zh"
tags: ["query:speech-model"]
score: 9.0
evidence: 统一语音语言模型用于生成和理解
tldr: 现有语音语言模型依赖残差量化，引入离散化误差和复杂层级架构。本文提出SLED，将语音波形编码为连续潜表示，利用能量距离目标进行自回归建模，无需量化即可捕获连续分布。SLED简化了流水线，并同时支持语音生成和理解任务，在语音语言建模上达到了竞争性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-pdwwz9f7zh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 639, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pdwwz9f7zh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 799, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pdwwz9f7zh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 418, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-pdwwz9f7zh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 896, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pdwwz9f7zh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 691, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pdwwz9f7zh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 563, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pdwwz9f7zh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1185, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pdwwz9f7zh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1280, \"height\": 451, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pdwwz9f7zh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1274, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pdwwz9f7zh/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 435, \"height\": 203, \"label\": \"Table\"}]"
motivation: 残差向量量化导致信息损失和架构复杂，需要更简洁的连续语音建模方法。
method: 将语音编码为连续潜变量序列，使用能量距离目标进行自回归训练，避免离散化。
result: 在语音生成和理解基准上取得与量化方法相当或更好的结果，且模型更简单。
conclusion: 连续潜空间语音语言建模是取代量化方法的有效且高效的方案。
---

## Abstract
We introduce \emph{SLED}, an alternative approach to speech language modeling by encoding speech waveforms into sequences of continuous latent representations and modeling them autoregressively using an energy distance objective. The energy distance offers an analytical measure of the distributional gap by contrasting simulated and target samples, enabling efficient training to capture the underlying continuous autoregressive distribution. By bypassing reliance on residual vector quantization, SLED avoids discretization errors and eliminates the need for the complicated hierarchical architectures common in existing speech language models. It simplifies the overall modeling pipeline while preserving the richness of speech information and maintaining inference efficiency. Empirical results demonstrate that SLED achieves strong performance in both zero-shot and streaming speech synthesis, showing its potential for broader applications in general-purpose speech language models. Demos and code are available at \url{https://github.com/ictnlp/SLED-TTS}.

---

## 论文详细总结（自动生成）

# 论文《Efficient Speech Language Modeling via Energy Distance in Continuous Latent Space》中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **现有问题**：当前语音语言模型普遍依赖残差向量量化（RVQ）将语音波形离散化为多流离散 token 序列，然后使用类似文本的自回归语言模型进行建模。这种方式存在两大缺陷：
  - **离散化信息损失**：量化过程引入信息瓶颈，丢失了波形中的丰富细节，影响重建质量。
  - **架构复杂**：多流 token 需要层级化的自回归架构（如 VALL-E 的 AR + NAR 结构），增加了模型复杂度和训练/推理成本。
- **研究动机**：探索是否可以在**连续潜空间**中直接进行语音自回归建模，从而避免离散化误差和层级架构，同时保持信息完整性和推理效率。
- **本文贡献**：提出 **SLED（Speech Language modeling via Energy Distance）**，将语音波形编码为连续潜向量序列，使用**能量距离（Energy Distance）** 作为训练目标进行自回归建模，无需任何离散化或后处理模块。实验在零样本和流式语音合成任务上验证了有效性。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：
  - 将语音波形通过音频编解码器（Encodec）编码为连续潜表示序列 \( h \in \mathbb{R}^{T f_h \times n} \)，每个时间步的潜向量 \( h_t \) 是一个 \( n \) 维连续向量。
  - 采用**自回归 Transformer**（LLaMA 风格）作为主干网络 \( \psi \)，根据历史潜向量 \( h_{<t} \) 提取条件特征 \( z_t = \psi(h_{<t}; \theta) \)。
  - 使用一个轻量级**隐式条件生成模块** \( g \)（6 层残差 MLP + AdaLN 调制）将随机噪声 \( \epsilon \) 和条件 \( z_t \) 映射为生成潜向量 \( \hat{h}_t = g(z_t, \epsilon; \phi) \)，从而隐式定义每个时间步的连续分布 \( p_g(h_t|z_t) \)。
- **训练目标——能量距离**：
  - 使用**广义能量距离（Generalized Energy Distance, GED）** 衡量生成分布与真实分布之间的差异，这是最大均值差异（MMD）的一种特例。
  - 损失函数为：\( \mathcal{L}_{GED} = \sum_t \mathbb{E}_{h_t, h'_t} \left[ 2\|h_t - h^*_t\|_2^{\beta} - \|h_t - h'_t\|_2^{\beta} \right] \)，其中 \( \beta \in (0,2) \)，实验中取 \( \beta=1 \)。
  - 该损失是严格适当的评分规则（strictly proper scoring rule），能正确引导模型捕获数据分布。第二项 \( \|h_t - h'_t\|_2 \) 是“排斥项”，防止模型退化为均方误差（MSE）回归，使分布拟合成为可能。
- **流式推理**：
  - 通过交错文本和语音位置（如 n 个文本 token 对应 m 个语音向量）实现增量生成，支持在文本未完全输入时开始语音合成。
  - 使用一个二分类头部预测生成何时停止（EOS）。
- **无分类器引导（CFG）**：在推理时，通过掩码文本提示进行两次前向传播，线性插值条件特征，提升对齐质量和生成效果。

## 3. 实验设计

- **数据集**：
  - **训练**：LibriHeavy（约 50,000 小时，6,736 个说话人，英文有声书）。
  - **零样本评估**：LibriSpeech test-clean 子集（过滤后 1,234 个样本，40 个未见说话人，时长 4-10 秒）。因训练数据含大小写和标点，评估使用 LibriSpeech-PC（恢复标点版本）。
- **评估任务与场景**：
  1. **3s Prefix as Prompt**：提供转录和前 3 秒语音提示，进行语音延续。
  2. **Reference Utterance as Prompt**：提供同一说话人的参考话语及其转录，合成目标文本的语音。
  3. **Streaming Inference**：不提供语音提示，仅输入文本，按交错比例流式合成。
- **对比方法**：
  - **离散 LM 方法**：VALL-E、VALL-E 2、ELLA-V、VALL-E R、Llasa 等。
  - **连续 LM 方法**：CLaM-TTS、MELLE、FELLE。
  - **传统 TTS**：MaskGCT、F5-TTS、MegaTTS 3 等。
- **评价指标**：
  - **WER**（词错误率）：使用 Conformer-Transducer（WER-C）和 HuBERT-Large（WER-H）两种 ASR 模型。
  - **SIM**（说话人相似度）：基于 WavLM-TDNN 提取嵌入的余弦相似度。
  - **DNSMOS**（感知质量）：ITU-T P.808 标准训练的非侵入式质量打分。

## 4. 资源与算力

- 文中未明确说明 GPU 型号、具体数量和训练时长。
- 训练配置：batch size = 512，总共 **300,000 步**，使用 **BF16 混合精度**。
- 优化器：AdamW（学习率 5e-4，weight decay 0.01），学习率线性衰减，前 32,000 步 warm-up。
- 模型参数量：约 **0.2B**（自回归 Transformer 12 层，每层 16 头，embedding 1024；生成模块 6 个残差块，隐藏维度 1024）。
- 附录提供了 RTF 和 FLOPs 分析（RTF=0.8，FLOPs=280G），但未提及具体硬件平台。

## 5. 实验数量与充分性

- **主要实验数量**：至少包括三个核心场景（两个零样本 + 一个流式），以及多个消融分析（能量距离 vs. MSE、CFG 参数影响、不同数据规模对比、流式策略对比）。
- **消融实验**：
  - 能量距离与 MSE 对比：只用 MSE 时 WER 高达 40.60，使用能量距离降至 1.59，证明了排斥项的关键作用。
  - CFG 系数 \(\lambda\) 的影响：对比 \(\lambda\) 从 1.0 到 2.5 的 WER、SIM、DNSMOS 变化（图 3）。
  - 数据规模对比（附录）：在 1000h LibriSpeech 与 50000h LibriHeavy 上的性能差异。
- **公平性**：与 VALL-E 使用相同的 Encodec 编码器，比较了连续 vs. 离散建模。但参数量不一致（SLED 0.2B vs. VALL-E 0.4B），SLED 仍取得更优或相近结果。与 Llasa（8B）相比，SLED 性能落后，但参数量小 40 倍。总体对比合理，但缺乏与同参数量级的多模型严格公平比较（如相同训练数据、相同步数）。
- **充分性**：实验覆盖了主要任务和关键变量分析，验证了方法有效性和设计选择，可认为较充分。

## 6. 主要结论与发现

1. **连续建模优于离散量化**：SLED 在零样本 TTS 上 WER 达到 1.59（3s prefix）和 1.51（reference utterance），优于同等 Encodec 编码的 VALL-E（WER-C 3.8 / 5.9），且无需层级架构。
2. **能量距离是关键**：若替换为均方误差（MSE），模型几乎无法生成有效语音（WER 40.60），证明排斥项对于捕获分布差异至关重要。
3. **无分类器引导显著提升对齐**：CFG 能大幅降低 WER，但对 SIM 和 DNSMOS 需适中强度（推荐 \(\lambda=2.0\)）。
4. **流式合成可行**：交错策略（5:20 或 5:45）下 WER 约 2.2，DNSMOS 接近离线模式（3.59 vs 3.58），证明了增量生成的实用性。
5. **效率优势**：SLED 的 RTF=0.8，FLOPs=280G，远小于 DiTAR（2750G），且支持纯自回归生成，无需后处理或迭代采样。
6. **数据规模扩展性**：50000h 训练相比 1000h 能进一步提升 speaker similarity 和 WER，说明了连续建模的可扩展潜力。

## 7. 优点

- **范式创新**：首次将能量距离应用于连续语音语言建模，完美替代了传统 softmax 分类或迭代扩散采样，成为轻量、稳定的生成目标。
- **简化架构**：完全消除层级化 RVQ 和 AR+NAR 流水线，模型仅需一个自回归 Transformer 和一个轻量 MLP，参数量小，推理快。
- **支持流式**：天然支持文本和语音交错的自回归生成，无需额外模块，适合低延迟交互场景。
- **训练稳定**：能量距离损失是严格适当的评分规则，可直接端到端训练，无需对抗训练或其他复杂技巧。
- **解释性强**：通过对比排斥项和 MSE 的实验，阐明了回归损失为何不能用于分布建模，以及 MELLE 中 flux loss 的真正作用。
- **实验分析深入**：提供了 CFG 参数、数据规模、效率对比等多维度分析，验证了设计决策。

## 8. 不足与局限

- **潜编码器非定制**：当前使用 Encodec（设计用于音频编解码）的连续潜表示，可能不是最优选择。作者也承认专门训练的连续潜编码器可能进一步提升性能。
- **模型规模有限**：SLED 仅 0.2B，与 Llasa（8B）等大模型相比仍有差距，缩放性（scaling law）未充分探索。
- **语言覆盖不足**：仅在英语（LibriSpeech）上测试，未见其他语言或多语言验证，通用性未证明。
- **语音克隆差距**：尽管优于某些离散方法，但与传统 TTS（如 MegaTTS 3）相比，speaker similarity 仍偏低（0.515 vs 0.78），语音克隆能力有限。
- **缺乏主观评测**：仅使用 WER、SIM、DNSMOS 等客观指标，缺少 MOS 人工评测，对合成语音自然度的判断可能不够全面。
- **实验可重复性**：未公开 GPU 具体型号和训练耗时，不利于复现；但提供了代码仓库和 demo 链接。
- **潜在滥用风险**：论文在 broader impact 中提及语音克隆可能被用于伪造，但未讨论具体防护措施（如水印、检测模型）。

（完）
