---
title: "Metis: A Foundation Speech Generation Model with Masked Generative Pre-training"
title_zh: Metis：基于掩码生成预训练的基础语音生成模型
authors: "Yuancheng Wang, Jiachen Zheng, Junan Zhang, Xueyao Zhang, Huan Liao, Zhizheng Wu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=RTjr4DnS79"
tags: ["query:speech-model"]
score: 9.0
evidence: 统一预训练的基础语音生成模型
tldr: Metis提出了一种基于掩码生成预训练的统一语音生成基础模型，在大规模无标签语音上预训练后通过微调适配多种生成任务。它使用SSL令牌和声学令牌两种离散表示，在多种语音生成任务（如TTS、语音转换）上均达到先进效果，验证了预训练-微调范式在语音生成中的有效性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-rtjr4dns79/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rtjr4dns79/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 614, \"height\": 598, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rtjr4dns79/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 655, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-rtjr4dns79/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 666, \"height\": 570, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-rtjr4dns79/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 706, \"height\": 725, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rtjr4dns79/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 704, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rtjr4dns79/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 711, \"height\": 539, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rtjr4dns79/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 708, \"height\": 808, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rtjr4dns79/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 651, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rtjr4dns79/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 787, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rtjr4dns79/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 904, \"height\": 416, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rtjr4dns79/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1361, \"height\": 472, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rtjr4dns79/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 672, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rtjr4dns79/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 504, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-rtjr4dns79/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1309, \"height\": 769, \"label\": \"Table\"}]"
motivation: 现有语音生成模型多为任务特定或简单多任务，缺乏统一的预训练基础模型。
method: 采用SSL令牌和声学令牌的双表示，在30万小时无标签语音上进行掩码生成预训练，再通过任务特定条件微调。
result: 在多种语音生成任务上达到最优或接近最优性能，且模型规模可扩展。
conclusion: Metis为统一语音生成与理解提供了有效的预训练框架，推动了基础模型在语音领域的发展。
---

## Abstract
We introduce ***Metis***, a foundation model for unified speech generation.
Unlike previous task-specific or multi-task models, Metis follows a pre-training and fine-tuning paradigm. It is pre-trained on large-scale unlabeled speech data using masked generative modeling and then fine-tuned to adapt to diverse speech generation tasks.
Specifically, 
(1) Metis utilizes two discrete speech representations: SSL tokens derived from speech self-supervised learning (SSL) features, and acoustic tokens directly quantized from waveforms. 
(2) Metis performs masked generative pre-training on SSL tokens, utilizing 300K hours of diverse speech data, without any additional condition. 
(3) Through fine-tuning with task-specific conditions, Metis achieves efficient adaptation to various speech generation tasks while supporting multimodal input, even when using limited data and trainable parameters.
Experiments demonstrate that Metis can serve as a foundation model for unified speech generation: Metis outperforms state-of-the-art task-specific or multi-task systems across five speech generation tasks, including zero-shot text-to-speech, voice conversion, target speaker extraction, speech enhancement, and lip-to-speech, even with fewer than 20M trainable parameters or 300 times less training data. Audio samples are are available at https://metis-demo.github.io/. We release the code and model checkpoints at https://github.com/open-mmlab/Amphion.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：现有语音生成模型多为任务特定（task-specific）或简单的多任务模型（如UniAudio、SpeechX），缺乏统一的预训练-微调（pre-training and fine-tuning）范式。这些模型要么需要大量配对数据进行训练，要么无法有效利用大规模无标签语音数据。
- **核心问题**：如何设计一个统一的语音生成框架，能够在大规模无标签语音数据上预训练，并通过微调高效适配多种语音生成任务（包括零样本文本到语音、语音转换、目标说话人提取、语音增强、唇语到语音）。
- **整体含义**：Metis借鉴了NLP和CV中基础模型的成功经验，首次将掩码生成预训练（masked generative pre-training）应用于语音生成领域，验证了预训练-微调范式在语音生成中的有效性，推动了语音生成领域向统一基础模型发展。

## 2. 方法论：核心思想、关键技术细节
### 2.1 核心思想
- **两阶段生成框架**：将语音生成任务分解为两个阶段——① **任务特定过程**：从任务条件（如文本、噪声语音、视觉特征）生成SSL tokens；② **任务无关过程**：从SSL tokens生成acoustic tokens，再合成波形。该框架将多样任务统一为“条件→SSL tokens→声学特征”的流程。
- **预训练目标**：在SSL tokens上进行无条件掩码生成预训练，不依赖任何任务条件，学习语音内在的语义和韵律结构。
- **微调策略**：通过引入任务特定条件（拼接或插值）进行微调，可适配多种任务，支持多模态输入（文本、音频、视频）。

### 2.2 关键技术细节
1. **离散语音表示**：
   - **SSL tokens**：从w2v-bert-2.0的17层提取特征，使用VQ模型（码本8192，维度8）量化，保留语义和韵律信息。
   - **Acoustic tokens**：使用DAC codec架构，将24kHz波形压缩为12层RVQ（每层码本1024，维度8），用于高质量波形重建。
2. **掩码生成预训练（Masked Generative Pre-training）**：
   - 随机掩码SSL token序列中的一部分，模型预测被掩码的token。
   - 以概率 p=0.8 引入前缀prompt（未被掩码），增强上下文学习能力。
   - 预训练损失：掩码token的交叉熵之和。
   - 推理时采用迭代解码：从全掩码序列开始，逐步解码，每次根据置信度重新掩码最低分数的 token。
3. **微调适配**：
   - **非帧级条件**（如TTS的文本）：直接沿时间维度拼接条件与输入序列。
   - **帧级条件**（如语音转换的源语音、增强的噪声语音）：对条件进行线性插值对齐时间维度，通过MLP适配器加至输入。
   - 支持全量微调和LoRA微调（rank=4/16/32，参数量2M~32M）。
4. **统一声学解码器**：
   - 训练一个SSL-to-acoustic的掩码生成模型，条件为SSL tokens和prompt acoustic tokens。
   - 训练时随机掩码某一层的acoustic tokens，下层保留作为条件；推理时分层生成。

## 3. 实验设计
### 3.1 数据集/场景
- **预训练数据**：300K小时多语言语音（Emilia 100K小时 + 自收集200K小时），涵盖中英德法日韩等。
- **微调数据**：从预训练数据中采样，不同任务使用不同规模：
  - **零样本文本到语音（TTS）**：1K/10K小时（Emilia子集）及LibriTTS（0.58K小时）。
  - **语音转换（VC）**：0.4K小时。
  - **目标说话人提取（TSE）**：10K小时，动态混合模拟多说话人。
  - **语音增强（SE）**：10K小时+噪声数据集（WHAM!、DEMAND）和RIR。
  - **唇语到语音（L2S）**：LRW+LRS2+LRS3训练集。
- **测试集**：
  - TTS：SeedTTS test-en/zh、LibriSpeech test-clean。
  - VC：VCTK、SeedTTS-VC。
  - TSE：LibriMix test、EmiliaMix test（自构建）。
  - SE：DNS2020（含混响、无混响、真实录音）。
  - L2S：LRS2、LRS3 test。

### 3.2 Benchmark与对比方法
- **TTS**：VALL-E、VoiceCraft、CosyVoice、XTTS-v2、MaskGCT、NaturalSpeech3、VoiceBox等。
- **VC**：HierSpeech++、LM-VC、UniAudio、Vevo。
- **TSE**：UniAudio、VoiceFilter、WeSep、TSELM。
- **SE**：TF-GridNet、VoiceFixer、SELM、MaskSR。
- **L2S**：Lip2Speech-Unit。

### 3.3 评估指标
- **客观指标**：Word Error Rate (WER，衡量可懂度)、Speaker Similarity (SIM，余弦相似度)、DNSMOS (SIG/BAK/OVRL)、NISQA。
- **主观指标**：仅对TTS和SE做了主观评测（QMOS、SMOS），各20个样本，提供95%置信区间。

## 4. 资源与算力
- **预训练**：8张GPU，1200K steps，动态batch size（每GPU 10K tokens ≈ 200秒语音），使用AdamW优化器（lr=1e-4，32K warmup）。未明确GPU型号，推测为A100或同等算力。
- **微调**：
  - TTS：4张GPU，200K steps。
  - VC：1张A100 GPU，10K steps（LoRA）或5K steps（全量）。
  - TSE/SE：未明确但推测类似。
- **LoRA参数量**：rank=4/16/32 对应 2M/9M/18M 可训练参数（不包括适配器）。

## 5. 实验数量与充分性
- **实验数量**：覆盖5个主要任务，每个任务对应2~3个测试集，对比多个baselines（每个任务4~8个）。
- **消融实验**：对比了有无预训练（w/o pre-train）、不同LoRA rank、不同微调数据量（1K/10K/0.58K）、条件概率p等。
- **多任务联合微调**：Metis-Omni在4个任务上同时微调，并展示了组合应用（文本引导目标说话人提取）。
- **充分性评估**：
  - 实验较为充分，任务全面，对比方法多样。
  - 但客观指标主要依赖自动评估，主观评测样本量较小（20个），且未覆盖所有任务。
  - 未测试跨语言或少资源语言的泛化能力。
  - 总体公平性较好，baselines均使用开源或论文报告结果。

## 6. 主要结论与发现
- **统一基础模型的有效性**：Metis在五个任务上均达到或超过SOTA，验证了预训练-微调范式在语音生成中的可行性。
- **数据与参数效率**：即使仅用1K小时数据+32M LoRA参数（TTS），性能即可媲美使用170K小时的CosyVoice；全量微调10K小时数据后，WER优于100K小时训练的MaskGCT。
- **LoRA微调的可行性**：少量可训练参数（如2M）即可在SE任务上达到SOTA，说明预训练模型学到了通用语音表示。
- **多任务联合微调的优势**：Metis-Omni不仅保持单任务性能，还能实现新任务组合（如文本引导目标说话人提取），WER从6.31降至2.70。
- **SSL tokens作为中间表示的优越性**：SSL tokens有效分离语义和声学，使得条件生成更鲁棒。

## 7. 优点
1. **框架创新性**：首次在语音生成中提出完整的预训练-微调基础模型，统一了多种任务。
2. **数据高效**：在大规模无标签数据上预训练后，微调仅需少量配对数据即可超越专业模型。
3. **参数高效**：LoRA微调只需1-2%的可训练参数，降低计算开销。
4. **多模态支持**：支持文本、音频、视频作为条件输入，扩展性强。
5. **模块化设计**：两阶段生成方式使阶段一（条件→SSL）与阶段二（SSL→声学）解耦，便于复用和升级。
6. **开源可复现**：代码和模型已开源，促进社区发展。

## 8. 不足与局限
1. **两阶段依赖两种离散表示**：系统复杂度较高，且SSL tokens和acoustic tokens分别训练，未完全统一为单一表示。
2. **零样本能力有限**：新任务仍需微调，不具备像LLM那样的零样本或小样本学习能力（作者在附录G中也指出这一点）。
3. **主观评测样本量小**：仅20个样本，且仅覆盖TTS和SE，说服力有限。
4. **未考虑公平性与偏见**：未分析模型在不同性别、口音、语言上的表现差异，预训练数据虽多语言但以中英为主，低资源语言可能泛化不足。
5. **可懂度（WER）未完全领先**：在TTS的LibriSpeech上WER（4.33）不如NaturalSpeech3（1.94）和VoiceBox（2.03），但SIM更高。
6. **安全性讨论不充分**：附录H提及潜在误用风险，但未给出具体检测机制或使用限制方案。
7. **计算资源需求较大**：预训练需8 GPU*1200K步（约数天至数周），对一般研究者门槛较高。

（完）
