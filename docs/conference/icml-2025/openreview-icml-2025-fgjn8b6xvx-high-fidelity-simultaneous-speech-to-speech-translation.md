---
title: High-Fidelity Simultaneous Speech-To-Speech Translation
title_zh: 高保真同步语音到语音翻译
authors: "Tom Labiausse, Laurent Mazaré, Edouard Grave, Alexandre Défossez, Neil Zeghidour"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=fgjN8B6xVX"
tags: ["query:speech-model"]
score: 10.0
evidence: 高保真同步语音到语音翻译模型
tldr: 针对同声传译需要实时性的问题，本文提出Hibiki，一个解码器仅有的多流语言模型，同步处理源和目标语音，联合生成文本和音频token实现语音到语音翻译。采用弱监督方法基于文本翻译系统的困惑度确定逐词最优延迟。实验表明，该方法在翻译质量和延迟之间取得领先平衡，首次实现真正意义上的实时语音到语音翻译。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-fgjn8b6xvx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 697, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fgjn8b6xvx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 794, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fgjn8b6xvx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 861, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fgjn8b6xvx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 736, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fgjn8b6xvx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 760, \"height\": 498, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fgjn8b6xvx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 851, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fgjn8b6xvx/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 853, \"height\": 323, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fgjn8b6xvx/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 853, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fgjn8b6xvx/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1513, \"height\": 1252, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-fgjn8b6xvx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 870, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fgjn8b6xvx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1740, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fgjn8b6xvx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 829, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fgjn8b6xvx/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 675, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fgjn8b6xvx/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 658, \"height\": 177, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fgjn8b6xvx/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 819, \"height\": 840, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fgjn8b6xvx/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1772, \"height\": 210, \"label\": \"Table\"}]"
motivation: 现有语音翻译多为非同步或需要整句处理，无法满足实时同传需求。
method: 提出Hibiki多流解码器模型，联合预测文本和音频token，并通过弱监督对齐确定逐词延迟。
result: 在多个语言对上，翻译质量和延迟指标均优于先前工作，实现实时高保真翻译。
conclusion: Hibiki为实时语音翻译提供了高效解决方案，推动同传技术进步。
---

## Abstract
We introduce Hibiki, a decoder-only model for simultaneous speech translation. Hibiki leverages a multistream language model to synchronously process source and target speech, and jointly produces text and audio tokens to perform speech-to-text and speech-to-speech translation. We furthermore address the fundamental challenge of simultaneous interpretation, which unlike its consecutive counterpart --where one waits for the end of the source utterance to start translating-- adapts its flow to accumulate just enough context to produce a correct translation in real-time, chunk by chunk. To do so, we introduce a weakly-supervised method that leverages the perplexity of an off-the-shelf text translation system to identify optimal delays on a per-word basis and create aligned synthetic data. After supervised training, Hibiki performs adaptive, simultaneous speech translation with vanilla temperature sampling. On a French-English simultaneous speech translation task, Hibiki demonstrates state-of-the-art performance in translation quality, speaker fidelity and naturalness. Moreover, the simplicity of its inference process makes it compatible with batched translation and even real-time on-device deployment. We provide examples on *huggingface.co/spaces/kyutai/hibiki-samples* as well as models and inference code at *github.com/kyutai-labs/hibiki*.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义

- **研究动机**：现有语音翻译多采用**离线（连续）模式**，即等待完整源语句后才开始翻译，无法满足**实时同声传译**需求。同时，级联系统（ASR→MT→TTS）存在错误累积和丢失副语言信息（如说话人身份、韵律）的问题。
- **整体含义**：本文提出 **Hibiki**，一个**解码器专用**的**多流语言模型**，能够**同步处理源语音和目标语音**，并**联合生成文本和音频 token**，实现**流式、高保真、带声音保留**的语音到语音翻译（S2ST）与语音到文本翻译（S2TT）。这是首个在翻译质量、说话人相似度和自然度上**接近人类专业口译员**的机器系统。

## 2. 论文提出的方法论

### 核心思想
- 基于 **RQ-Transformer** 架构（Défossez et al., 2024），联合建模**两个音频流**（源和目标）的离散 token 序列，同时预测**内独白文本流**作为音频生成的脚手架。
- 通过**弱监督的上下文对齐方法**，利用现成文本翻译系统（MADLAD-3B）的**困惑度变化**确定**逐词最优延迟**，生成**符合因果关系**的训练数据。
- 训练后，推理时只需**简单的温度采样**即可实现自适应流式翻译。

### 关键技术细节
1. **神经音频编解码器（Mimi）**：因果、流式，帧率 12.5 Hz，使用残差向量量化（RVQ），第一级量化输出语义 token（对齐 WavLM），后续为声学 token。
2. **多流建模**：将源和目标音频 token 沿量化轴拼接，每个时间步由时间 Transformer（Temporal Transformer）处理，再由深度 Transformer（Depth Transformer）自回归预测各量化层 token。
3. **上下文对齐**：
   - 定义理想对齐：目标第 j 个词等待源第 a_j 个词以使不确定性最小。
   - 使用 **log-p 增量最大化**准则：`a_ctx^j = argmax_i [log P(T_j|S_1..S_i, T_1..T_{j-1}) - log P(T_j|S_1..S_{i-1}, ...)]`
   - 通过 Whisper 获得时间戳，插入静音或使用**对齐感知 TTS** 重新合成目标音频，实现因果对齐。
4. **说话人相似度条件训练**：将训练样本按说话人余弦相似度分为 5 个等级（非常差~非常好），将标签嵌入加入模型；推理时使用**分类器无关引导（CFG）** 增强声音保持。

### 形式化描述（文字）
- 输入：源波形 X，输出目标波形 Y（已对齐）。
- 模型：`P[Y|X]` 通过自回归预测两流离散 token 序列实现，损失函数包括交叉熵。
- 推理：温度采样，音频 token 温度 0.8，文本 token 温度 0.1-0.1，CFG 系数 γ=3.0。

## 3. 实验设计

### 数据集
- **短句**：CVSS（法英测试集，99% 序列 <10s）
- **长句**：Audio-NTREX（自制，10 小时真实人声，每个话语约 50s，10 个说话人，基于 NTREX 文本翻译录制）
- **真实同传**：VoxPopuli（欧洲议会 90 段真实口译，含背景源语言）
- **训练数据**：约 40k 小时法语数据（2.3M 片段，每段约 60s），通过 Whisper 转录 → MADLAD-3B 翻译 → 对齐感知 TTS 合成目标英语，得到约 900 小时用于微调。

### 基准方法
- **离线基线**：Translatotron、Translatotron 2、S2UT、UnitY、DASpeech、StreamSpeech (offline) 等。
- **同时基线**：Seamless（多语种） 和 StreamSpeech（指定分块 2560ms）。
- 人类口译（ground-truth）作为上限参考。

### 评估指标
- **翻译质量**：ASR-BLEU（Whisper 转写后计算）、ASR-COMET（XCOMET-XL）。
- **音频质量/自然度**：人工 MOS（1-5 分）。
- **说话人相似度**：WavLM 余弦相似度 + 人工 MOS。
- **延迟**：End Offset（输出结束与源结束的时间差）、LAAL（长度自适应平均滞后）。

## 4. 资源与算力

- **训练步骤**：
  - 文本预训练：600K steps，batch size 1024，序列长度 4096，学习率 4.8e-4，AdamW。
  - 音频预训练：1,450K steps，batch size 144，学习率 2e-4。
  - 语音翻译训练：150K steps，batch size 96，学习率 3e-5。
  - 微调：8K steps，batch size 8，学习率 2e-6。
- **硬件**：论文未明确说明训练所用 GPU 型号与数量；仅提到推理测试在 **H100 SXM**（批处理）和 **iPhone 16 Pro**（设备端）上进行。因此训练算力细节缺失。

## 5. 实验数量与充分性

- **实验数量**：共 7 张表格（Table 1~7）+ 多个消融对比 + 人评 + 推理速度测试。
  - Table 1：离线 S2ST 对比（7 个基线，Hibiki 最优）。
  - Table 2：同时 S2ST 对比（StreamSpeech、Seamless）在短句和长句上的表现。
  - Table 3：人评（质量、相似度、自然度）对比人类口译、Seamless、Hibiki。
  - Table 4：对齐策略消融（无滞后、常数滞后 2s/10s、句子级对齐、无内独白、无音频预训练）。
  - Table 5：CFG 参数消融（γ=0, 3, 10）。
  - Table 6：架构超参数（Hibiki & Hibiki-M）。
  - Table 7：英译法比对（Seamless vs Hibiki）。
- **充分性**：
  - 自动指标与人工评价结合，覆盖翻译质量、音频质量、延迟、说话人相似度。
  - 进行了关键的消融实验（对齐策略、CFG、多任务、预训练），验证各组件贡献。
  - 但对于**更多语言对**（仅法英和英法）和**噪声/真实场景**（如背景噪声、口音）的泛化性未充分论证。

## 6. 论文的主要结论与发现

1. **翻译质量**：Hibiki 在同时 S2ST 中 ASR-BLEU 达到 **35.5**（CVSS-C 短句）和 **26.6**（Audio-NTREX 长句），显著优于 Seamless（33.8 和 23.9）和 StreamSpeech。
2. **音频自然度**：人评自然度 MOS 达 **3.73**（接近人类 4.12），远高于 Seamless（2.18）。
3. **说话人相似度** ：余弦相似度 **0.48**（长句）优于 Seamless（0.43），CFG 有效提升。
4. **延迟**：Hibiki 的 LAAL 约 3.4~5.0s，比 Seamless 高约 0.7~0.8s，但可通过训练时调整 δctx 控制权衡。
5. **推理能力**：批量处理 320 个序列仍快于实时（H100）；Hibiki-M（1.8B）可在 iPhone 16 Pro 上实时运行。
6. **关键消融**：上下文对齐优于固定滞后或句子级对齐；内独白和音频预训练至关重要。

## 7. 优点

- **方法简洁**：无需复杂推理策略（如决策网络或分块），直接靠训练数据显式对齐 + 温度采样即可实现流式翻译。
- **弱监督对齐实用**：基于现成文本翻译模型引导，无需人工标注，且可推广到更多语言。
- **说话人保持可控**：通过条件训练 + CFG 实现，不用过滤数据即可提升相似度。
- **推理效率高**：可批量处理、支持设备端部署，适合实际应用。
- **开源**：模型权重、代码和合成数据集（900 小时）将公开发布，促进可复现研究。

## 8. 不足与局限

- **语言覆盖**：仅验证了**法英和英法**两个方向，对其他语言（特别是非印欧语系）的泛化能力未知。
- **数据依赖**：依赖 MADLAD-3B 的翻译质量来生成对齐训练数据，若翻译系统本身有偏差（如风格、术语）会传递到模型。
- **延迟略高**：相比于 Seamless，Hibiki 的 LAAL 偏高约 0.7~0.8s，虽然可调但可能影响实时体验。
- **说话人相似度评估偏见**：条件训练使用的说话人模型（WavLM）与评估器相同，可能高估相似度；虽然有人工验证，但同样依赖于同一嵌入空间。
- **极端 CFG 副作用**：过高的 γ 会导致输出音频出现**源语言口音**（法语口音），表明存在说话人模型的偏置。
- **训练算力未公开**：未报告 GPU 型号、数量、总时间，限制了可复现性评估。
- **合成数据质量**：对齐感知 TTS 可能引入伪影；训练数据中 CVSS-T 的原始说话人相似度很低（平均 0.23），虽经重合成改善但仍覆盖广泛。

（完）
