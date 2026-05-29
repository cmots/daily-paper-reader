---
title: "TaDiCodec: Text-aware Diffusion Speech Tokenizer for Speech Language Modeling"
title_zh: TaDiCodec：面向语音语言建模的文本感知扩散语音分词器
authors: "Yuancheng Wang, Dekun Chen, Xueyao Zhang, Junan Zhang, Jiaqi Li, Zhizheng Wu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=wHsFqmM1rp"
tags: ["query:speech-model"]
score: 8.0
evidence: 面向统一语音建模的语音分词器
tldr: TaDiCodec提出了一种文本感知的扩散语音分词器，通过扩散自编码器实现端到端优化，集成了文本引导的解码器，避免了传统多级残差量化或辅助模型依赖。该方法在语音重建质量和下游语音语言模型上表现优异，为统一语音生成与理解提供了高效令牌化基础。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-whsfqmm1rp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 998, \"height\": 818, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-whsfqmm1rp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 589, \"height\": 207, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-whsfqmm1rp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 700, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-whsfqmm1rp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 700, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-whsfqmm1rp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1000, \"height\": 315, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-whsfqmm1rp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 833, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-whsfqmm1rp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-whsfqmm1rp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 443, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-whsfqmm1rp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1444, \"height\": 544, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-whsfqmm1rp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 939, \"height\": 472, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-whsfqmm1rp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 402, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-whsfqmm1rp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1450, \"height\": 347, \"label\": \"Table\"}]"
motivation: 现有语音分词器依赖多层残差量化或复杂两阶段训练，且需要辅助模型提取语义特征。
method: 采用扩散自编码器框架，联合优化量化与重建，并在解码器中引入文本引导以增强重建质量。
result: 在语音重建质量和下游语音语言模型任务上取得先进结果，且训练流程简化。
conclusion: TaDiCodec为语音语言建模提供了高效且统一的令牌化方案，有助于推动语音生成与理解模型的融合。
---

## Abstract
Speech tokenizers serve as foundational components for speech language models, yet current designs exhibit several limitations, including: 
(1) dependence on multi-layer residual vector quantization structures or high frame rates,
(2) reliance on auxiliary pre-trained models for semantic distillation, and
(3) requirements for complex two-stage training processes.
In this work, we introduce the **T**ext-**a**ware **Di**ffusion Transformer Speech **Codec** (***TaDiCodec***), a novel approach designed to overcome these challenges.
TaDiCodec employs end-to-end optimization for quantization and reconstruction through a diffusion autoencoder, while integrating text guidance into the diffusion decoder to enhance reconstruction quality and achieve optimal compression.
TaDiCodec achieves an extremely low frame rate of **6.25 Hz** and a corresponding bitrate of **0.0875 kbps** with a **single-layer codebook** for 24 kHz speech, 
while maintaining superior performance on critical speech generation evaluation metrics such as Word Error Rate (WER), speaker similarity (SIM), and speech quality (UTMOS),
Notably, TaDiCodec employs a single-stage, end-to-end training paradigm, and obviating the need for auxiliary pre-trained models.
We also validate the compatibility of TaDiCodec in language model based zero-shot text-to-speech with both autoregressive modeling and masked generative modeling, demonstrating its effectiveness and efficiency for speech language modeling, as well as a significantly small *reconstruction-generation gap*.
To facilitate reproducibility and further research, we will make our source code and pre-trained checkpoints publicly available.
Audio samples are are available at https://tadicodec.github.io/. We release code and model checkpoints at https://github.com/AmphionTeam/TaDiCodec.

---

## 论文详细总结（自动生成）

# 论文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **现有语音分词器（speech tokenizer）在用于语音语言建模时存在三个主要缺陷**：  
  (1) 依赖多层残差向量量化（RVQ）或高帧率，导致建模困难和效率低下；  
  (2) 需要辅助预训练模型（如SSL模型）来提取语义特征，增加了外部依赖；  
  (3) 多数采用复杂的两阶段训练流程（先训练VQ模型，再训练扩散解码器）。  
- **核心目标**：设计一个单层、超低比特率、端到端训练且无需辅助模型的语音分词器，同时保持高重建质量和适用于下游语音语言建模（零样本TTS）的能力。

## 2. 方法论（核心思想、关键技术细节）
- **整体框架**：将语音分词器建模为**扩散自编码器**（Diffusion Autoencoder），利用流匹配（Flow Matching）损失进行端到端优化，统一量化与重建。
  - 输入输出均为梅尔频谱图，通过声码器可还原为波形。
- **编码器与量化（Encoder + Quantizer）**：
  - 使用纯Transformer架构（双向注意力），输入梅尔频谱，输出低维潜在序列。
  - 采用**二进制球形量化（BSQ）**：将潜在向量投影到单位球面，每个维度取符号（±1/√L），并利用STE（Straight-Through Estimator）进行梯度传播。无需显式可学习码本，码本大小为2^L（L=14，共16384个token）。
  - 量化后得到离散token序列，帧率低至6.25 Hz。
- **文本感知的解码器（Text-aware De-tokenization）**：
  - 解码器为DiT（Diffusion Transformer）结构，条件输入包括：量化后的token序列、对应文本序列、扩散时间步嵌入、以及来自输入梅尔频谱的随机前缀（prompt）信息。
  - 训练时随机采样前缀（长度0~25%总帧数）保持不变，仅对剩余部分计算扩散损失。
  - 文本序列使用预训练LLM的词汇表，与语音特征沿时间轴拼接后输入解码器。
- **训练目标**：仅使用扩散损失（流匹配速度场预测），无需对抗损失或辅助损失。公式：L_diff = E[∥(x - ε) - D_φ(Q(E_θ(x)), x_t, t, x_text)∥]。
- **下游TTS建模**：采用“AR + 扩散”或MGM（掩码生成模型）范式，AR模型预测token序列，然后由TaDiCodec解码器生成语音。

## 3. 实验设计
- **数据集**：使用**Emilia多语言数据集**（46.8K小时英语、49.9K小时中文、1.6K小时德语、1.4K小时法语、1.7K小时日语、0.2K小时韩语）。
- **评估基准与指标**：
  - 重建质量：WER（Whisper-large-v3/paraformer-zh）、SIM（WavLM-TDNN余弦相似度）、UTMOS（官方UTMOS）。
  - 主观评价：CMOS。
  - 零样本TTS测试集：SeedTTS test-en (Regular en)、SeedTTS test-zh (Regular zh)，以及更具挑战性的Articulatory（绕口令/重复）、Code-switching（中英混合）、Cross-lingual（跨语言）测试集。
- **对比方法**：
  - **重建对比**：EnCodec、DAC、SpeechTokenizer、Mimi、DualCodec、BiCodec、X-codec 2、WavTokenizer、BigCodec、TAAE、SemantiCodec、Vevo Tokenizer、FireRedTTS Tokenizer、CosyVoice/CosyVoice 2 Tokenizer、Ints Tokenizer。
  - **零样本TTS对比**：F5-TTS、MaskGCT、ARS、CosyVoice 2、FireRedTTS、Ints、SparkTTS、Llasa。

## 4. 资源与算力
- **训练硬件**：8张NVIDIA A100 80GB GPU。
- **训练批量**：动态批处理，每批200秒语音。
- **训练步数**：
  - Tokenizer：800K步（后续额外400K步微调解码器），AdamW优化器，学习率7.5e-5，32K步预热。
  - TTS模型：300K步（约1天可完成），学习率3e-4。
- **模型规模**：
  - TaDiCodec：编码器~160M，解码器~320M（默认），可缩放至160M/480M。
  - TTS AR模型：0.2B、0.5B、3B、4B；MGM模型：0.6B。

## 5. 实验数量与充分性
- **重建实验**：Table 1展示了与15+种tokenizer在主要指标上的对比；Table 2展示了多语言（6种语言）重建结果；Table 3提供了主观CMOS（5个对比系统）；Table 4进行了7项消融实验（量化方案、解码器大小、prompt机制、帧率、推理步数、decoder继续训练、扩散vs GAN）。
- **TTS实验**：Table 5报告了在8个测试集（Regular英文/中文、Articulatory英文/中文、Code-switching英文/中文、Cross-lingual英文↔中文）上的结果，并与7种SOTA零样本TTS对比；Table 6进行了模型规模缩放分析（5种规模），并给出RTF推理效率；Figure 3展示了重建-生成差距（4种tokenizer，英文+中文）。
- **充分性评价**：实验覆盖全面，包括客观+主观评价、多语言、多种困难场景、消融和效率分析。对比方法均为公开SOTA且设置公平（相同ASR模型、相同测试集）。实验设计客观、充分。

## 6. 主要结论与发现
- **超低比特率下的SOTA性能**：TaDiCodec以6.25 Hz单层码本、0.0875 kbps取得WER 2.73（decoder继续训练）、SIM 0.69、UTMOS 3.73，在极低码率下达到或超过更高码率方法。
- **无需辅助模型和两阶段训练**：端到端扩散自编码器设计有效，BSQ量化稳定。
- **文本感知和prompt机制关键**：消融表明移除prompt导致WER从3.02升至8.63，移除文本条件导致严重退化（12.5 Hz时WER>10）。
- **重建-生成差距极小**：在英文上生成WER甚至优于重建（-16.5%），表明TaDiCodec高度“生成友好”。
- **零样本TTS表现出色**：在Regular en/zh上WER为2.28/1.19，超越所有对比方法；在困难测试集（Code-switching、Cross-lingual）上优势明显。
- **效率优越**：4B AR模型RTF 0.29（可降至0.13 with vLLM），0.6B MGM模型RTF 0.12。

## 7. 优点
- **方法创新**：首次将扩散自编码器与文本感知解码结合用于超低比特率语音分词，端到端训练简化流程。
- **极端压缩效率**：6.25 Hz / 0.0875 kbps是目前已知最低且兼具高质量的分词方案。
- **无需辅助模型**：摆脱对SSL模型的依赖，避免两阶段训练。
- **生成兼容性好**：在AR和MGM两种模式下均验证有效，重建-生成差距极小。
- **实验充分且公平**：对比多种SOTA，设置一致；主观+客观评估覆盖多语言、多场景。

## 8. 不足与局限
- **扩散解码延迟**：推理需多步（10-50步），相比GAN类tokenizer速度较慢，未实现1-2步推理。
- **依赖文本输入**：解码器需要对应文本，这在非TTS场景（如只做理解）可能不适用；论文未探索纯语音场景。
- **应用范围有限**：未在语音理解（如情感识别、语种识别）或口语对话系统中评估其有效性。
- **实验的局限**：未测试在更大模型上的缩放行为（仅探索了有限规模）；超低帧率在极端情况下（如音高精细控制）可能丢失细节；主观评价仅针对重建，未对TTS生成进行较大规模主观测试。
- **潜在风险**：语音合成技术可能被误用于恶意模仿或深度伪造，需配套检测/水印机制。

（完）
