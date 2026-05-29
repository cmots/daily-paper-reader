---
title: Long-Form Speech Generation with Spoken Language Models
title_zh: 基于口语语言模型的长语音生成
authors: "Se Jin Park, Julian Salazar, Aren Jansen, Keisuke Kinoshita, Yong Man Ro, RJ Skerry-Ryan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=4AmFA0qNQ2"
tags: ["query:speech-model"]
score: 7.0
evidence: 使用口语语言模型进行长语音生成
tldr: 针对文本无关口语语言模型难以生成长时语音的问题，本文提出SpeechSSM，利用线性时间序列建模，首次在单次解码中生成长达16分钟的可读或即兴语音，无需文本中间表示。在大规模实验上，SpeechSSM在长时语音生成质量上大幅超越现有模型。为长时语音生成提供了有效的口语语言模型方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-4amfa0qnq2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 808, \"height\": 747, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4amfa0qnq2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1765, \"height\": 461, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4amfa0qnq2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 794, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4amfa0qnq2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 834, \"height\": 628, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4amfa0qnq2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 754, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4amfa0qnq2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 760, \"height\": 457, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-4amfa0qnq2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 507, \"height\": 502, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-4amfa0qnq2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 857, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4amfa0qnq2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1772, \"height\": 580, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4amfa0qnq2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1771, \"height\": 539, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4amfa0qnq2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 691, \"height\": 375, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4amfa0qnq2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 454, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-4amfa0qnq2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 861, \"height\": 122, \"label\": \"Table\"}]"
motivation: 现有文本无关口语语言模型无法生成超过数十秒的连贯语音。
method: 采用线性时间序列建模扩展序列建模能力。
result: SpeechSSM能够生成16分钟的连贯语音，质量显著优于基线。
conclusion: 为长时语音生成提供了有效的口语语言模型方案。
---

## Abstract
We consider the generative modeling of speech over multiple minutes, a requirement for long-form multimedia generation and audio-native voice assistants. However, textless spoken language models struggle to generate plausible speech past tens of seconds, due to high temporal resolution of speech tokens causing loss of coherence, architectural issues with long-sequence training or extrapolation, and memory costs at inference time. From these considerations we derive **SpeechSSM**, the first 
speech language model family to learn from and sample long-form spoken audio (e.g., 16 minutes of read or extemporaneous speech) in a single decoding session without text intermediates. SpeechSSMs leverage recent advances in linear-time sequence modeling to greatly surpass current Transformer spoken LMs in coherence and efficiency on multi-minute generations while still matching them at the utterance level.
As we found current spoken language evaluations uninformative, especially in this new long-form setting, we also introduce: **LibriSpeech-Long**, a benchmark for long-form speech evaluation; new embedding-based and LLM-judged metrics; and  quality measurements over length and time. Speech samples, the LibriSpeech-Long dataset, and any future code or model releases can be found at https://google.github.io/tacotron/publications/speechssm/.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究动机**：现有文本无关的口语语言模型（Spoken Language Models, SLMs）在生成长达数分钟的语音时面临严重挑战：语音标记的高时间分辨率导致长程连贯性丧失；Transformer 架构在长序列训练和外推上存在困难；推理时内存成本过高。这些因素使得现有模型无法处理真实应用中的长时语音生成需求（如多媒体内容、语音助手等）。
- **整体含义**：首次提出**SpeechSSM**系列模型，能够在无需文本中间表示的情况下，在单次解码中生成长达16分钟的可读或即兴长语音。同时，针对长时语音评估缺乏标准化指标的问题，提出了新的基准数据集和评估方法。

### 2. 方法论

- **核心思想**：利用线性时间序列建模（State-Space Models, SSMs）克服 Transformer 在长序列上的二次复杂度和外推困难，实现恒定内存消耗下的无限自回归生成。
- **关键技术细节**：
  - **架构**：采用 **Griffin**（混合 SSM），交替使用门控线性递归单元（LRU）和滑动窗口局部注意力（MQA），在捕获近期上下文的同时通过状态传递远距离信息。
  - **初始化**：使用预训练的 RecurrentGemma-{2B,9B} 文本语言模型初始化，丢弃原有文本词嵌入，新建语音标记嵌入。
  - **语义分词器**：采用 **USM-v2**（32k 词汇量，25Hz 帧率），其高度说话人不变性有利于长时连贯性。
  - **语音合成**：使用 **SoundStorm**（非自回归）将语义标记转换为 SoundStream 声学标记，并通过 3 秒说话人提示实现声音模拟。
  - **窗口化标记与解码**：将音频分为固定长度窗口（30s，重叠4s），独立标记后合并，避免边界伪影。
  - **避免隐式终止**：通过将最后一个窗口用开头语音填充，防止分词器编码剩余长度信息导致生成中断。

### 3. 实验设计

- **数据集**：
  - 训练：**LibriLight** 未标记60k小时分集（读语音）。
  - 长时评估基准：**LibriSpeech-Long**（基于 LibriSpeech 裁剪为4分钟片段，共约51小时，涵盖 dev-clean/test-clean 等）。
  - 即兴语音变体（SpeechSSM-X）：使用 216k 小时的自发性长篇独白语料。
- **对比方法**：GSLM、TWIST（1.3B/7B）、AudioLM、VoxtLM、Spirit LM Expressive（7B）以及自定义的 SpeechTransformer（Gemma-2B 初始化）。
- **评估场景**：
  - 短时：3秒提示 → 7秒生成。
  - 长时：10秒提示 → 4分钟或16分钟生成。
  - 语义相似性（SBERT/Gecko 嵌入）、LLM 作为评判员（Gemini 2.0 Flash）的侧对侧评分、自然度 MOS 以及按时间分层的语义连贯性（SC-L）等。

### 4. 资源与算力

- 论文明确说明：每个模型使用 **16 个 TPU v5p**，数据并行，训练 **100k 步**，每批 768k 标记（约 5760 个 4 分钟片段）。学习率 5e-4，权重衰减 0.6，余弦衰减。
- 推理时：使用 **TPU v5e** 测量吞吐量和解码时间。
- 未详细给出总 GPU 时数或能源消耗。

### 5. 实验数量与充分性

- **实验数量**：包括短时（1个设置）、长时（4分钟和16分钟）评估，以及即兴语音变体（1个设置）。消融实验包括：有无 LM 初始化、Transformer 替代、不同训练片段长度（30s/4min/16min）。总计约 10 组主要对比。
- **充分性与客观性**：实验设计较为全面，覆盖了现有主要模型和多种指标。尤其基准数据集和评估指标（LibriSpeech-Long、LLM 评判、分层评估）填补了文献空白。但实验中未包含所有可能变体（如不同温度设置、更大模型规模），且部分消融仅在 2B 规模上进行。
- **公平性**：基线模型均采用官方或论文最优设置，但存在训练数据、词汇量、合成器质量差异可能影响公平比较。作者也讨论了这一点。

### 6. 主要结论与发现

- SpeechSSM 在短时生成上与现有 Transformer 模型匹配，在长时生成（4 分钟和 16 分钟）上显著优于所有基线（包括使用滑动窗口外推方法）。
- SpeechSSM 具有生成长度外推能力：训练于 4 分钟，能稳定生成 16 分钟甚至更长，而 Transformer 变体性能随长度迅速下降。
- 提出的新评估指标（SBERT/Gecko、LLM 评判、分层评分）更鲁棒且具有区分度，能够揭示模型间的质量差异。
- 说话人相似性通过将说话人特征隔离到合成阶段得到极大提升（0.85 vs 基线 0.3-0.4）。
- 推理效率：SpeechSSM 相比 SpeechTransformer 吞吐量提升超过 120 倍（批量解码 16.4k 标记时），且单样本解码速度更快。

### 7. 优点

- **方法创新**：首次将 SSM（Griffin）应用于口语语言模型，实现恒定内存和无界生成。
- **评估创新**：提出 LibriSpeech-Long 基准和面向长时语音的新评估指标（LLM 评判、时间分层评分），解决了现有指标饱和/噪声大的问题。
- **系统性消融**：验证了 LM 初始化、窗口化、避免隐式终止等技术贡献的有益性。
- **即兴语音扩展**：训练了 SpeechSSM-X 模型，证明方法可推广至自然对话风格。
- **代码/模型/数据开放**：公开数据集和示例，促进可重复性。

### 8. 不足与局限

- **实验覆盖**：仅在英文（LibriSpeech、LibriLight）上进行训练和评估，未验证多语言或方言泛化能力。
- **合成质量**：虽然自然度 MOS 接近真实语音，但长时生成中仍存在少量边界伪影或语速波动。
- **评估偏差**：LLM 评判依赖转写文本，可能忽略语音韵律、音色等非文本信息；ASR 误差可能影响文本指标。
- **安全影响**：虽声明权重不发布，但方法本身可被滥用生成深度伪造；论文讨论了这一点。
- **算力需求**：需要 TPU v5p 集群训练 2B/9B 模型，资源门槛高，不利于小实验室复现。
- **缺乏显式公式**：论文未提供 SSM 核心公式的详细推导（如选择性状态空间模型），仅引用 Griffin 论文。

---
（完）
