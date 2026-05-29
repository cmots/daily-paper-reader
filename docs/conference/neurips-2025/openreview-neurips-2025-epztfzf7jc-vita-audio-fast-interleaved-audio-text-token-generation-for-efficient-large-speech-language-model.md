---
title: "VITA-Audio: Fast Interleaved Audio-Text Token Generation for Efficient Large Speech-Language Model"
title_zh: "VITA-Audio: 用于高效大型语音语言模型的快速交错音频-文本令牌生成"
authors: "Zuwei Long, Yunhang Shen, Chaoyou Fu, Heting Gao, lijiang Li, Peixian Chen, Mengdan Zhang, Hang Shao, Jian Li, Jinlong Peng, Haoyu Cao, Ke Li, Rongrong Ji, Xing Sun"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=epZTfZF7JC"
tags: ["query:speech-model"]
score: 7.0
evidence: 端到端大型语音模型，支持快速音频-文本生成
tldr: 针对现有语音模型在流式传输中首次音频令牌生成延迟高的问题，提出端到端大型语音模型VITA-Audio。核心创新是轻量级多模态交叉令牌预测（MCTP）模块，可在单次模型前向中高效生成多个音频令牌，显著加速推理并降低延迟。实验表明该方法在保持生成质量的同时大幅提升了流式处理效率，适用于语音理解和生成统一场景。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-epztfzf7jc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1381, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-epztfzf7jc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1382, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-epztfzf7jc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1330, \"height\": 829, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-epztfzf7jc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1379, \"height\": 770, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-epztfzf7jc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1436, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-epztfzf7jc/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1450, \"height\": 467, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-epztfzf7jc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1171, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-epztfzf7jc/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 482, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-epztfzf7jc/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1292, \"height\": 631, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-epztfzf7jc/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1441, \"height\": 586, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-epztfzf7jc/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1248, \"height\": 614, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-epztfzf7jc/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1443, \"height\": 1419, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-epztfzf7jc/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1436, \"height\": 147, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-epztfzf7jc/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1071, \"height\": 829, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-epztfzf7jc/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 549, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-epztfzf7jc/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1094, \"height\": 1295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-epztfzf7jc/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 880, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-epztfzf7jc/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1414, \"height\": 181, \"label\": \"Table\"}]"
motivation: 降低语音模型在流式传输中首次音频令牌生成的延迟。
method: 引入多模态交叉令牌预测模块，单次前向生成多个音频令牌。
result: 显著降低流式推理延迟，保持生成质量。
conclusion: 提出了一种高效的流式语音语言模型加速方法。
---

## Abstract
With the growing requirement for natural human-computer interaction, speech-based systems receive increasing attention as speech is one of the most common forms of daily communication. However, the existing speech models still experience high latency when generating the first audio token during streaming, which poses a significant bottleneck for deployment. To address this issue, we propose VITA-Audio, an end-to-end large speech model with fast audio-text token generation. Specifically, we introduce a lightweight Multiple Cross-modal Token Prediction (MCTP) module that efficiently generates multiple audio tokens within a single model forward pass, which not only accelerates the inference but also significantly reduces the latency for generating the first audio in streaming scenarios. In addition, a four-stage progressive training strategy is explored to achieve model acceleration with minimal loss of speech quality. To our knowledge, VITA-Audio is the first multi-modal large language model capable of generating audio output during the first forward pass, enabling real-time conversational capabilities with minimal latency. VITA-Audio is fully reproducible and is trained on open-source data only. Experimental results demonstrate that our model achieves an inference speedup of 3~5x at the 7B parameter scale, but also significantly outperforms open-source models of similar model size on multiple benchmarks for automatic speech recognition (ASR), text-to-speech (TTS), and spoken question answering (SQA) tasks.

---

## 论文详细总结（自动生成）

# VITA-Audio 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有端到端语音模型在流式生成时，首次音频令牌（first audio token）延迟过高，成为实时人机交互的主要瓶颈。传统级联架构（ASR + LLM + TTS）存在累积延迟、副语言信息丢失和错误传播问题；而现有端到端模型虽然支持流式输出，但首次音频令牌仍需额外多次 LLM 前向才能生成，无法在第一次 LLM 前向完成后立即输出音频块。
- **研究动机**：探索如何在端到端语音模型中实现更实时的音频生成，以支持自然、低延迟的对话交互。
- **整体含义**：通过设计轻量级模块突破延迟瓶颈，首次实现首次前向即可生成音频令牌的端到端大语音模型，为实时语音交互系统设立新标准。

## 2. 论文提出的方法论

### 核心思想
- 发现：LLM 隐藏状态中对应文本令牌的语义信息已足够生成其对应的音频令牌，无需依赖整个文本序列的语义建模。
- 基于此，利用轻量级 **多模态交叉令牌预测（Multiple Cross-modal Token Prediction, MCTP）** 模块，学习从文本隐藏状态到音频令牌的简单映射关系，在单次 LLM 前向中同时生成文本令牌和多个音频令牌，实现零延迟输出首个音频块。

### 关键技术细节
1. **MCTP 模块架构**：
   - 级联预测结构：每个 MCTP 模块以上一模块（LLM 或前序 MCTP）的隐藏状态和输出序列为条件，预测下一个音频令牌。
   - 公式对比：标准自回归预测 `p(Y_t|Y_{t-1},...,Y_0)` 扩展到多步预测时存在分布偏移；MCTP 通过逐步引入上下文信息 `p(Y_{t+i}|... , h_{t+i-1}, o_{t+i-1},...,o_t)` 实现增量优化，减少误差累积。
   - 模块轻量：单个 MCTP 前向仅需约 0.0024 秒（占 LLM 骨干的 11%），包含 RMSNorm、线性投影、Transformer Block。
   - 每个 MCTP 模块与 LLM 共享嵌入层和输出头，生成的音频令牌直接参与 LLM 自回归过程。

2. **训练策略（四阶段渐进式训练）**：
   - **Stage 1 (Audio-Text Alignment)**：冻结音频编码器和解码器，在大规模 ASR、TTS、纯文本数据上训练 LLM，使其具备音频建模能力。
   - **Stage 2 (Single MCTP Module Training)**：用 LLM 最后一层参数初始化单个 MCTP 模块，预测下一个令牌，梯度与 LLM 断开。
   - **Stage 3 (Multiple MCTP Modules Training)**：将 Stage 2 的 MCTP 权重复制到所有后续 MCTP 模块，每个模块预测对应位置的令牌，梯度继续断开。
   - **Stage 4 (Supervised Fine-tuning)**：在语音 QA 数据上微调，同时保留少量 ASR、TTS、文本数据保持稳定性；对不同部分使用不同学习率。

3. **推理模式（四种）**：
   - **Turbo**：最快模式，LLM 每步生成 1 文本令牌 + MCTP 生成 10 音频令牌，首次前向即产生 11 个令牌（1 文本+10 音频），零延迟。
   - **Boost**：LLM 生成所有文本令牌，MCTP 生成所有音频令牌，加速比约 3×。
   - **Balance**：保持文本-音频令牌比例 1:2，分两批生成以提升语音质量。
   - **Vanilla**：仅 LLM 生成所有令牌，最慢但性能最高。

## 3. 实验设计

### 使用的数据集和场景

| 任务 | 数据集 | 说明 |
|------|--------|------|
| ASR | WenetSpeech, AIshell, LibriSpeech, Fleurs 等 | 约 100,000 小时开源数据 |
| TTS | Seed-TTS, LibriTTS | 评估中文/英文语音合成质量（CER/WER） |
| SQA (Spoken Question Answering) | WebQuestions, Llama-Question, TriviaQA | 两种评估：S→T（直接评估文本）和 S→S（ASR转写后评估） |
| 纯文本 | OpenHermes-2.5, LIMA, MetaMathQA 等 | 保持 LLM 语言能力 |

### Benchmark 指标
- ASR：词错误率（WER）或字符错误率（CER）
- TTS：Whisper-Large-V3（英）和 Paraformer（中）转写后计算 WER/CER
- SQA：准确率

### 对比方法
- 专有模型：MinMo
- 开源模型：Moshi, GLM-4-Voice, LUCY, VITA-1.5, Freeze-Omni, Step-Audio-chat, Qwen2-Audio/base, Qwen2.5-Omni, MiniCPM-o2.6, Llama-Omni 等

## 4. 资源与算力

- **明确信息**：论文未明确说明训练的 GPU 型号、具体数量和训练时长。
- **提及细节**：推理速度测试使用支持 148 TFLOPS 的 GPU，bfloat16 精度，采用 Transformers 和 FlashAttention-2。模型规模包括 0.5B、7B、72B。
- **推断**：基于 7B 模型和大量开源数据（约 20 万小时语音数据、数百万文本问答数据），训练应当消耗大量计算资源，但论文未公开具体训练成本。

## 5. 实验数量与充分性

- **实验组数**：覆盖 ASR（多个语料库共约10+个子集）、TTS（2个benchmark）、SQA（3个数据集×2种评估模式），以及推理速度对比（4种模式×3种模型规模），共计约 30+ 组主要实验。
- **消融实验**：展示了 VITA-Audio 在四个训练阶段的 TTS 和 ASR 性能变化（S1、S2、S3、S4），以及 VITA-Audio 与 VITA-Audio-Plus 的对比，验证了 MCTP 渐进训练的有效性。
- **充分性**：实验设计较为全面，对比了当前主流开源模型和专有模型，涵盖了三大核心语音任务。但论文未报告多次运行的标准差或置信区间，统计严谨性略欠；部分对比数据可能来自原始文献，未在相同条件下复现。

## 6. 论文的主要结论与发现

- **首次实现零音频令牌延迟**：VITA-Audio 是首个能在第一次 LLM 前向中直接生成音频块的多模态大语言模型，将首次音频块生成时间从 236ms 降至 53ms。
- **显著加速**：在 7B 规模下，Turbo 模式加速 5×，Boost/Balance 模式加速约 3×，且在 72B 模型上仍保持类似比例。
- **SOTA 性能**：在 ASR、TTS、SQA 多个基准上，VITA-Audio（尤其是 VITA-Audio-Plus）优于所有同等参数规模的开源模型，甚至接近或超过专有模型 MinMo。
- **质量保持**：尽管使用 MCTP 加速，TTS 和 ASR 性能在训练各阶段基本保持，证明轻量模块能有效对齐文本与语音。

## 7. 优点

- **创新性**：首次提出并验证了“文本隐藏状态已包含足够语义信息以生成对应音频”的发现，据此设计轻量 MCTP 模块，绕过复杂语义建模。
- **实用性**：四种推理模式覆盖从极致速度到最高质量的需求，适应不同应用场景。
- **训练效率**：采用四阶段渐进策略，有效解决多模块联合训练分布对齐难题，且仅需少量文本数据即可训练 MCTP。
- **开放可复现**：仅使用开源数据训练，并承诺完全开源代码、模型权重。
- **低延迟**：流式场景中首个音频块延迟极低（53ms），对实时交互至关重要。

## 8. 不足与局限

- **音频解码器瓶颈**：论文指出整体端到端延迟仍受限于音频解码器的生成速度，未进一步优化解码器。
- **文本理解能力下降**：经过 ASR/TTS 对齐后，模型在纯文本基准上的性能略有下降（如 MMLU 从 74.22 降至 66.92），可能与训练数据中缺少大规模高质量文本有关。
- **实验统计严谨性欠佳**：未报告误差棒或置信区间，结果可靠性评估不足。
- **资源消耗未公开**：缺少训练所需 GPU 数量、时长、内存等关键信息，不利于他人复现和评估性价比。
- **偏倚风险**：训练数据主要来自开源语音数据集，可能覆盖的语种、口音、场景有限；未评估模型在噪声环境或非正式对话中的表现。
- **应用限制**：MCTP 模块设计依赖于“文本隐藏状态已足够”的观察，若文本语义复杂度较高（如多义字、上下文依赖强烈），映射仍可能出错；虽对同音词测试良好，但极端案例鲁棒性未知。

（完）
