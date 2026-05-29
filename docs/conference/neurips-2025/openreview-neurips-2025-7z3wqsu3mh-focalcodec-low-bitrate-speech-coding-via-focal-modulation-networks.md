---
title: "FocalCodec: Low-Bitrate Speech Coding via Focal Modulation Networks"
title_zh: FocalCodec：基于焦点调制网络的低比特率语音编码
authors: "Luca Della Libera, Francesco Paissan, Cem Subakan, Mirco Ravanelli"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=7Z3wQSu3mH"
tags: ["query:speech-model"]
score: 7.0
evidence: 低比特率语音编码用于语音模型应用
tldr: 现有神经音频编解码器位率高或损失语义/声学信息，且多码本设计复杂。本文提出FocalCodec，基于焦点调制和单二进制码本，在0.16-0.65 kbps超低位率下压缩语音，同时保留语义和声学信息。它为语音翻译、合成等下游任务提供了高效、简洁的表示工具。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-7z3wqsu3mh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1436, \"height\": 524, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7z3wqsu3mh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 523, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7z3wqsu3mh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1052, \"height\": 1474, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-7z3wqsu3mh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 875, \"height\": 451, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7z3wqsu3mh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 864, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7z3wqsu3mh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 817, \"height\": 507, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7z3wqsu3mh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1447, \"height\": 521, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7z3wqsu3mh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 881, \"height\": 318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7z3wqsu3mh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1449, \"height\": 486, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7z3wqsu3mh/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1445, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7z3wqsu3mh/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1448, \"height\": 286, \"label\": \"Table\"}]"
motivation: 现有语音编码在低位率下容易丢失信息，多码本结构增加下游复杂度。
method: 利用焦点调制网络和单二进制码本，实现超低位率下语义和声学信息的联合保留。
result: 在0.16-0.65 kbps下重建语音质量优于可比方法，且简化了下游模型架构。
conclusion: 单码本焦点调制编解码器为高效语音表示提供了新途径。
---

## Abstract
Large language models have revolutionized natural language processing through self-supervised pretraining on massive datasets. Inspired by this success, researchers have explored adapting these methods to speech by discretizing continuous audio into tokens using neural audio codecs. However, existing approaches face limitations, including high bitrates, the loss of either semantic or acoustic information, and the reliance on multi-codebook designs when trying to capture both, which increases architectural complexity for downstream tasks. To address these challenges, we introduce FocalCodec, an efficient low-bitrate codec based on focal modulation that utilizes a single binary codebook to compress speech between 0.16 and 0.65 kbps. FocalCodec delivers competitive performance in speech resynthesis and voice conversion at lower bitrates than the current state-of-the-art, while effectively handling multilingual speech and noisy environments. Evaluation on downstream tasks shows that FocalCodec successfully preserves sufficient semantic and acoustic information, while also being well-suited for generative modeling. Demo samples and code are available at https://lucadellalib.github.io/focalcodec-web/.

---

## 论文详细总结（自动生成）

# FocalCodec 论文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有神经音频编解码器在低比特率压缩时存在以下矛盾：要么仅保留声学信息而丢失语义信息，要么依赖多码本设计来同时捕获两者，但增加了下游模型的架构复杂度。此外，高比特率也限制了在带宽受限场景下的应用。
- **研究动机**：受大型语言模型自监督预训练成功启发，语音领域通过神经音频编解码将连续音频离散化为标记，但现有方法在低比特率下难以兼顾重建质量与信息保留。旨在设计一种超低比特率、单码本的混合编解码器，既保留语义与声学信息，又简化下游任务模型。
- **整体含义**：提出 FocalCodec，在 0.16–0.65 kbps 的超低比特率下使用单个二进制码本压缩语音，在语音再合成、语音转换以及下游判别与生成任务上均表现出竞争力，为语音语言模型提供高效、简洁的表示工具。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

### 核心思想
- 基于 VQ-VAE 框架，引入**压缩器-量化器-解压缩器**结构，使用**焦点调制网络**替代自注意力，在编码器（WavLM-large 前6层）和解码器（Vocos）之间进行高效降维与量化。采用**二元球面量化（Binary Spherical Quantization, BSQ）**作为单码本量化方法，将码本大小与潜在维度绑定，实现高效的隐式码本。

### 关键技术细节
- **编码器**：冻结 WavLM-large 的前6层，输出 1024 维特征，保留丰富的声学与语义信息。
- **压缩器（Compressor）**：包含三个焦点降尺度模块（Focal Downscale Block），每个模块由线性投影、Snake 激活和焦点块（Focal Block）组成。焦点块替代自注意力，通过多个深度卷积（不同核大小）聚合多尺度上下文，再用逐点卷积生成门控信号，逐元素调制每个 token。公式为：  
  \( y_i = q(x_i) \odot h\left( \sum_{\ell=1}^{L+1} z_i^\ell \odot g_i^\ell \right) \)。  
  可选时间下采样以降低帧率（12.5 Hz、25 Hz、50 Hz）。
- **量化器**：BSQ，将压缩后的 13 维向量归一化到单位超球面，然后对其符号进行二值化（+1/-1），得到长度为 13 的二进制码，对应 2¹³=8192 个码字。量化误差有界，无需承诺损失。
- **解压缩器（Decompressor）**：与压缩器对称，使用焦点升尺度模块恢复原始特征维度。
- **解码器**：Vocos 架构，使用 ConvNeXt 块和逆 STFT 重建波形。采用非对称设计，编码器参数约为解码器的 5 倍，强调强编码器提取鲁棒表示。
- **判别器**：HiFi-GAN 中的多周期判别器与多尺度判别器，训练时使用，推理时丢弃。
- **训练流程**：两阶段解耦训练。第一阶段（冷冻编码器）训练压缩器-量化器-解压缩器，优化 L2 重建损失与熵损失（鼓励均匀码本使用）。第二阶段训练解码器，使用对抗损失、L1 谱图损失和特征匹配损失。两个阶段可并行训练。

## 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

### 数据集
- **训练**：LibriTTS（585 小时，16 kHz 英文语音）。
- **评估**：
  - 干净英文语音：LibriSpeech test-clean。
  - 多语言：Multilingual LibriSpeech（7 种语言，每语言 100 句，共 700 句）。
  - 噪声场景：VoiceBank（干净语音+噪声）、Libri1Mix（LibriSpeech + WHAM! 噪声）。
  - 语音转换：VCTK（2521 个样本）。
  - 下游任务：ASR（LibriSpeech）、SI（LibriSpeech）、SER（IEMOCAP）、SE（VoiceBank）、SS（Libri2Mix）、TTS（LibriSpeech）。

### 对比方法
- 声学编解码器：EnCodec (1.50 kbps)、DAC (1.00 kbps)、WavTokenizer (0.48 kbps)、BigCodec (1.04 kbps)。
- 语义编解码器：WavLM6-KM (0.45 kbps)。
- 混合编解码器：SpeechTokenizer (1.00 kbps)、SemantiCodec (0.65 kbps)、Mimi (0.69 kbps)、Stable Codec (0.70 kbps)。
- 额外对比（附录）：TS3-Codec（未公开，作者提供样本）。

### 实验场景
- **语音再合成**：干净、多语言、噪声下，评估 UTMOS、dWER、Sim、码本使用率、归一化熵、RTF。
- **语音转换**：VCTK 上单次语音转换，用 k-NN 或码本交换进行特征替换。
- **下游任务**：
  - 判别任务：ASR（浅层 BiLSTM + CTC）、SI（BiLSTM + 统计池化）、SER（BiLSTM + 分类头）。
  - 生成任务：SE、SS（Conformer 编码器）、TTS（自回归 Llama 3 解码器）。

## 4. 资源与算力

- **训练硬件**：单 GPU，V100（16/32 GB）或 A100（40 GB），根据集群资源选择。
- **训练数据**：第一阶段使用 LibriTTS 全部 585 小时，第二阶段仅使用 train-clean-100（约 100 小时）。
- **训练步数**：第二阶段约 3M 步直至收敛。
- **推理速度**：RTF 在 0.16–0.65 kbps 下为 79–185（NVIDIA V100），远快于实时。
- **参数与计算量**：FocalCodec 参数约 142–145 M，MACs 约 8–9 G。
- **无明确的 GPU 数量与训练时长**：论文仅提及单 GPU，未给出具体训练天数。

## 5. 实验数量与充分性

- **实验数量**：总计评估了 5 个再合成场景（干净英文、多语言、噪声 VoiceBank、Libri1Mix）、1 个语音转换场景、6 个下游任务（3 判别 + 3 生成），加上主观 MUSHRA 测试和消融实验（8 种配置）。
- **充分性**：
  - 覆盖了干净、噪声、多语言、不同比特率、不同任务类型，对比了 10 种基线方法。
  - 主观测试有 33 位有效参与者，采用标准 MUSHRA 格式。
  - 消融实验验证了焦点模块、BSQ、Snake 激活等关键组件。
  - **客观性**：使用标准指标（UTMOS、dWER、Sim、RTF、码本利用率），与官方开源基线对比，公平性较高。
  - **局限**：未报告多次运行的标准差，实验基于单次训练；主观测试样本量较小（10 个样本 × 33 人）。部分基线（如 TS3-Codec）仅通过作者提供的解码样本对比。

## 6. 论文的主要结论与发现

- FocalCodec 在 0.65 kbps 比特率下，在干净语音再合成上达到最好的 dWER（2.18%），优于 BigCodec（2.55%），同时保持高 UTMOS（4.05）和 Sim（97.4%）。
- 在噪声和跨语言场景下，FocalCodec 的 dWER 远低于所有基线（例如 VoiceBank 上 8.08% vs 最佳基线 20.32%），显示出强鲁棒性和语义保留能力。
- 语音转换中，FocalCodec 以单码本设计达到 92.2% Sim 和 21.27% dWER，超越专门优化的混合码本模型（如 SpeechTokenizer、Mimi）。
- 下游任务中，FocalCodec@50 在 ASR 和 SE 上表现接近或优于多码本混合模型；在 TTS 中，较低帧率的变体（FocalCodec@25）由于序列更短而表现更好。
- 消融实验表明，焦点模块、BSQ 和 Snake 激活对性能贡献最大，替换为 Conformer 或线性层导致显著下降。

## 7. 优点

- **创新性**：首次将焦点调制网络用于语音编码，并成功应用二元球面量化到语音领域，实现了单码本超低比特率压缩。
- **性能突出**：在极低比特率下同时保留语义和声学信息，dWER 大幅优于现有方法；语音转换中 speaker 相似度最高。
- **简洁架构**：单码本设计简化了下游模型（无需处理多码本展平），解耦训练流程（冻结编码器）便于扩展。
- **鲁棒性**：跨语言、噪声环境下表现稳健，且无需额外蒸馏或监督微调。
- **公正评估**：对比了 10 种开源基线，使用标准指标和公开数据集，主观测试严格筛选参与者。

## 8. 不足与局限

- **训练不充分**：仅使用 LibriTTS（~585 小时）进行第一阶段训练，第二阶段仅用 100 小时，远小于 WavTokenizer（8K 小时）、Stable Codec（105K 小时）和 Mimi（7M 小时）。可能限制了泛化能力。
- **缺乏误差棒**：未报告多次实验的标准差，单次运行结果可能存在偶然性。
- **未完全开源**：代码和演示网站已提供，但训练脚本、预训练模型权重全文未明确给出（附注中提及“code available”，检查时需确认实际开放程度）。
- **流式推理限制**：非因果模型，需通过分块加左上下文实现流式，延迟 500 ms 对于实时通信仍然较高；虽在附录中消减因果版本至 80 ms，但并非主模型。
- **主观测试样本量小**：仅 10 个样本和 33 人，统计显著性有限；未报告置信区间。
- **多语言评估局限**：测试语言仅 7 种，且训练只有英语，对非英语口音和场景覆盖不够。
- **下游任务中分离任务效果差**：SS 任务 dWER 极高（>73%），表明量化损失导致重要分离信息丢失，实际效用有限。

（完）
