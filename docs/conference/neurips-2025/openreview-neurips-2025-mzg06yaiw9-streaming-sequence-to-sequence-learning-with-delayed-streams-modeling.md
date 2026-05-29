---
title: Streaming Sequence-to-Sequence Learning with Delayed Streams Modeling
title_zh: 基于延迟流建模的流式序列到序列学习
authors: "Neil Zeghidour, Eugene Kharitonov, Manu Orsini, Václav Volhejn, Gabriel de Marmiesse, Edouard Grave, Patrick Perez, Laurent Mazaré, Alexandre Défossez"
date: 2025-05-09
pdf: "https://openreview.net/pdf?id=MZg06yaIW9"
tags: ["query:speech-model"]
score: 8.0
evidence: 适用于语音翻译的流式序列到序列框架
tldr: 针对传统序列到序列模型需要完整输入才能生成输出的离线限制，提出延迟流建模（DSM）。通过引入流之间的延迟，并选择性馈送或采样，DSM能够对任意输出序列进行流式推理。特别地，对于音频和文本流，可配置实现自动语音识别或语音翻译。该框架以解码器-only语言模型为核心，具有灵活性和通用性。实验表明DSM在流式ASR和翻译任务上有效。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzg06yaiw9/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1024, \"height\": 461, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzg06yaiw9/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 533, \"height\": 458, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzg06yaiw9/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 689, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mzg06yaiw9/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1259, \"height\": 422, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzg06yaiw9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 381, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzg06yaiw9/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 973, \"height\": 338, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzg06yaiw9/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1139, \"height\": 476, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzg06yaiw9/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1071, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mzg06yaiw9/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 962, \"height\": 238, \"label\": \"Table\"}]"
motivation: 实现灵活的流式序列到序列生成，支持语音翻译等任务。
method: 通过延迟流建模并选择性馈送流，使用解码器-only语言模型进行流式推理。
result: 在流式ASR和翻译任务上验证了有效性。
conclusion: 提出了一种通用的流式序列到序列学习框架。
---

## Abstract
We introduce Delayed Streams Modeling (DSM), a flexible formulation for streaming, multimodal sequence-to-sequence learning. Sequence-to-sequence generation is typically cast in an offline manner: the model consumes the complete input sequence before generating the first output timestep. DSM instead models time-aligned streams with a decoder-only language model. By furthermore introducing delays between streams, and selectively feeding or sampling them, DSM provides streaming inference of arbitrary output sequences, from any input combination, making it applicable to many sequence-to-sequence problems. In particular, given a text and audio stream, automatic speech recognition (ASR) corresponds to the text stream being delayed, while the opposite gives a text-to-speech (TTS) model. We perform extensive experiments for these two major sequence-to-sequence tasks, showing that DSM provides state-of-the-art performance and latency while supporting arbitrary long sequences, being even competitive with offline baselines. We demonstrate DSM applications on https://delayed-stream-modeling.github.io/.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：传统的序列到序列（Seq2Seq）模型（例如 ASR、TTS）通常以离线方式运行——模型必须消费完整的输入序列后才能生成第一个输出时间步。这导致两大限制：1）无法支持实时流式推理；2）输入长度受到模型上下文窗口的限制。此外，不同模态（语音、文本）的采样率不同，进一步阻碍了流式应用（如会议转录、连续翻译）。
- **整体含义**：本文提出一种名为 **Delayed Streams Modeling (DSM)** 的通用框架，旨在实现流式的、多模态的序列到序列学习。DSM 将输入和输出建模为多个时间对齐的并行流，并通过引入流之间的延迟（delay）来控制质量与延迟之间的权衡。通过选择合适的延迟方向，DSM 可以统一处理 ASR（音频→文本，文本流延迟）和 TTS（文本→音频，音频流延迟）等任务，且支持任意长的序列和批量推理，具有极高的吞吐量。

## 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- DSM 使用 **解码器-only Transformer** 作为骨干网络，同时处理多个并行 token 流（如音频流、文本流、动作流）。这些流在时间步上对齐，每个时间步会输入所有流的 token（或 padding），模型自回归地预测输出流中未来的 token。
- 通过引入 **延迟**（delay）机制：将输出流相对于输入流延迟若干时间步（例如 ASR 中文本流延迟 2.5 秒），使得模型在预测当前输出时能利用更多未来的输入上下文，从而保证预测的因果合理性和质量。延迟越大，质量越高但实时性越差；反之亦然。
- 通过 **选择性馈送和采样**，模型可以在推理时从任意输入组合中连续生成任意输出序列，实现真正的流式推理。

### 关键技术细节
1. **输入表示**：
   - **音频**：使用 Mimi 编解码器（帧率 12.5 Hz，残差矢量量化，32 个码本，每个码本 2048 个条目）将 24 kHz 的波形离散化为 token 序列。
   - **文本**：训练专用的文本 tokenizer（词汇量分别为 ASR 4000、TTS 8000），并引入两个特殊 token：`PAD`（表示该时间步无单词）和 `WORD`（表示单词开始）。通过 Whisper-timestamped 工具获得单词级时间戳，将文本序列与音频帧率对齐。

2. **ASR 模型 (DSM-ASR)**：
   - 输入：音频流；输出：文本流（延迟）。
   - 损失：仅在文本流上计算交叉熵，包括对 `PAD` 和 `WORD` 的预测，从而学习单词边界。
   - **延迟条件化**：训练时对每个样本随机采样延迟（0.25~4 秒），并将延迟值作为余弦位置编码加到输入嵌入中，使得单一模型可在推理时动态调整延迟，无需重新训练。

3. **TTS 模型 (DSM-TTS)**：
   - 输入：文本流；输出：音频流（延迟 2 秒）。
   - 由于推理时文本未知，引入 **动作输出流**：模型预测何时应输入下一个单词（`WORD` token），从而控制输入文本的节奏。
   - **前瞻文本流 (Lookahead)**：额外馈送未来第 l 个单词的 token，帮助模型决定停顿和单词起始位置。
   - **说话人条件化**：使用 Pyannote 进行说话人 diarization，提取说话人音频嵌入，通过交叉注意力注入模型，支持最多 5 个说话人的对话生成。

4. **架构**：
   - 骨干：RoPE 位置编码的 Transformer，ASR 为 3B 参数（48 层、32 头、2048 维），TTS 为 1B 参数（16 层）。
   - 采样器：对音频的 RVQ 码本采用 RQ-Transformer 进行自回归建模（沿码本维度）。
   - 优化器：AdamW，cosine 学习率调度。

## 实验设计

### 数据集与场景
- **ASR 短时转录**（<30 秒）：使用 OpenASR Leaderboard 标准评测集，包括 AMI、Earnings22、GigaSpeech、LibriSpeech（clean/other）、SPGISpeech、TED-LIUM、VoxPopuli。
- **ASR 长时转录**（最长 2 小时）：TED-LIUM、Meanwhile、Rev16、Earnings21。
- **TTS 评估**：自建数据集（将公开），包含英语和法语的独白（来自 NTREX-128 新闻文章）和对话脚本（LLM 生成，三类主题）。说话人条件来自 VCTK（英语）和 CML（法语）的测试集。

### Benchmark 与对比方法
- **ASR 基准**：非流式（Whisper medium/large-v3、CrisperWhisper、Canary-Flash、Phi-4 Multimodal、Parakeet）和流式（Whisper 流式变体，延迟 2.5 秒）。
- **TTS 基准**：开源模型（Dia、Orpheus、CSM）和闭源商业模型（ElevenLabs Flash V2.5、Multilingual V2）。

### 评估指标
- ASR：微平均词错误率（WER）、延迟（平均单词转录延迟）、时间戳精度（附录 C）。
- TTS：WER（自动语音识别转录后计算）、主观质量（MUSHRA 评分）、说话人相似性（ELO 胜率）以及实时因子（RTF）和吞吐量。

## 资源与算力
- **ASR 预训练**：2.5M 小时公开音频（英语+法语），使用 Whisper-timestamped 伪标签，在 48 块 H100 GPU 上训练 160 万步。
- **ASR 微调**：24 小时公共数据集（附录 A.1），16 块 H100，10 万步；长时适应阶段：25k 步，批次大小 32。
- **TTS 训练**：120 秒音频切片，16 块 H100，25 万次更新，批次大小 64。
- 注意：论文未披露完整训练的总 GPU 小时数，但上述配置已提供关键算力信息。

## 实验数量与充分性
- **ASR**：1 个主要短时表（8 个数据集）、1 个长时表（4 个数据集）、1 个延迟-质量折线图、1 个吞吐量对比图。对比了 7 种非流式 + 2 种流式基线。进行了时间戳精度分析（附录）。
- **TTS**：1 个 WER 表（英语/法语，短时/长时推理）、1 个主观评价表（MUSHRA + ELO）、1 个延迟与吞吐量表。对比了 5 种基线。
- **消融实验**：延迟条件化（固定延迟 vs 随机延迟）在图 4 中展示；动作流和前瞻文本流的必要性虽未单独消融，但在方法描述中强调了其作用。
- **充分性评价**：实验覆盖了流式 ASR 和 TTS 的主要公开基准，并进行了主观评测，设计较为充分。然而，TTS 的消融实验不足（例如未单独验证动作流和前瞻文本流的贡献），且主观评测仅对比了少数基线。此外，所有实验均基于单一骨干架构，未验证框架对不同 backbone 的鲁棒性。总体上实验充分且客观，但可进一步加强。

## 论文的主要结论与发现
1. **DSM-ASR** 在短时转录上达到 6.3% 平均 WER，与顶级离线模型（如 Canary-Flash 6.4%、Phi-4 Multimodal 6.1%）相当，且是唯一进入排行榜前列的流式模型。在长时转录上（7.9%）全面超越所有基线的流式与非流式版本。
2. **DSM-TTS** 在英文和法文的 WER 上均显著低于所有开源基线（英文 3.6%，法文 6.4%），在主观质量上优于开源模型，与 ElevenLabs 商业模型差距较小（尤其在说话人相似性上持平）。
3. **延迟条件化** 允许单一模型在推理时灵活控制延迟（0.25~4 秒），且性能不逊于甚至优于分别训练固定延迟的模型。
4. **高吞吐量**：得益于并行流对齐和批量推理，DSM-ASR 在 H100 上可同时处理 400 个序列，吞吐量是 Whisper-Streaming 的约 100 倍。DSM-TTS 在批量 64 时可实现 111 倍实时因子。
5. DSM 可作为 LLM 的语音接口，结合 Gemma 3 实现亚秒级延迟的语音对话。

## 优点
- **统一框架**：DSM 用同一套方法（延迟流 + 解码器-only）解决了 ASR 和 TTS 两种相反的任务，展现了良好的通用性。
- **流式推理原生支持**：无需额外的对齐模块或手工分块，模型天然支持无限长序列。
- **批量推理友好**：传统流式模型（如 Whisper-Streaming）无法批量处理，DSM 通过固定帧率对齐实现了高效批量推理，大幅提升吞吐量。
- **延迟条件化**：创新性地在训练时引入随机延迟并条件化，实现推理时零代价调整时延，非常实用。
- **精准时间戳**：由于固定延迟，输出时间戳可精确回退到单词实际发音位置（精度 80ms），显著优于 Whisper 的模糊时间戳。

## 不足与局限
- **数据依赖**：训练需要具有精确单词级对齐的大量音频-文本数据，目前主要依赖 Whisper-timestamped 生成的伪标签，存在噪声。论文虽通过微调加以缓解，但数据质量仍是瓶颈。
- **模态限制**：当前仅验证了语音和文本两种模态，虽然框架理论上适用于图像、视频等，但文中未进行相关实验。
- **实验覆盖不够全面**：TTS 的消融实验较少（如未单独验证动作流、前瞻流、说话人条件化的贡献）；ASR 的消融也仅针对延迟，缺乏对骨干规模、码本数量等超参数的敏感性分析。
- **主观评价范围有限**：TTS 的主观评测仅对比了 Dia、CSM、Orpheus 和 ElevenLabs，且 ElevenLabs 为闭源商业模型，样本量受限于成本。未与其他最新开源 TTS（如 Tortoise、XTTS）比较。
- **潜在风险**：论文承认语音合成可能被用于欺诈性冒充，但仅提及“通过用户协议、水印等方式缓解”，未提供具体技术方案。
- **资源消耗**：模型规模较大（ASR 3B, TTS 1B+额外的编码器/采样器），训练成本高，小团队复现困难。

（完）
