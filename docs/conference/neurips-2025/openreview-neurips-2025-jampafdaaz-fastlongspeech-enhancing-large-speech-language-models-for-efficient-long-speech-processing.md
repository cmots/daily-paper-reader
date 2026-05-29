---
title: "FastLongSpeech: Enhancing Large Speech-Language Models for Efficient Long-Speech Processing"
title_zh: FastLongSpeech：提升大型语音语言模型的高效长语音处理能力
authors: "Shoutao Guo, Shaolei Zhang, Qingkai Fang, Zhengrui Ma, Min zhang, Yang Feng"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=jaMPaFDAaZ"
tags: ["query:speech-model"]
score: 8.0
evidence: 大型语音语言模型用于统一长语音理解和生成
tldr: 针对大型语音语言模型在长语音处理方面的不足，提出FastLongSpeech框架。该框架通过优化模型架构和训练过程，在不依赖专用长语音数据集的情况下，显著提升了长语音处理的计算效率和生成质量。实验证明，FastLongSpeech在长语音理解与生成基准上均优于现有方法，推动了LSLM在现实长语音场景中的应用。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-jampafdaaz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1335, \"height\": 728, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jampafdaaz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1389, \"height\": 420, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-jampafdaaz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 460, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jampafdaaz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 523, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jampafdaaz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 614, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jampafdaaz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 780, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jampafdaaz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 603, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jampafdaaz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1400, \"height\": 688, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jampafdaaz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 608, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jampafdaaz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 606, \"height\": 213, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jampafdaaz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 576, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jampafdaaz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1023, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jampafdaaz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 696, \"height\": 132, \"label\": \"Table\"}]"
motivation: 大型语音语言模型在长语音处理上面临数据集稀缺和高计算成本问题。
method: 提出FastLongSpeech框架，通过高效架构和训练策略扩展LSLM的长语音处理能力，无需专用数据集。
result: 在长语音理解和生成任务上大幅提升了效率和质量。
conclusion: 为LSLM处理长语音提供了实用的解决方案。
---

## Abstract
The rapid advancement of Large Language Models (LLMs) has spurred significant progress in Large Speech-Language Models (LSLMs), enhancing their capabilities in both speech understanding and generation. While existing LSLMs often concentrate on augmenting speech generation or tackling a diverse array of short-speech tasks, the efficient processing of long-form speech remains a critical yet underexplored challenge. This gap is primarily attributed to the scarcity of long-speech training datasets and the high computational costs associated with long sequences. To address these limitations, we introduce FastLongSpeech, a novel framework designed to extend LSLM capabilities for efficient long-speech processing without necessitating dedicated long-speech training data. FastLongSpeech incorporates an iterative fusion strategy that can compress excessively long-speech sequences into manageable lengths. To adapt LSLMs for long-speech inputs, it introduces a dynamic compression training approach, which exposes the model to short-speech sequences at varying compression ratios, thereby transferring the capabilities of LSLMs to long-speech tasks. To assess the long-speech capabilities of LSLMs, we develop a long-speech understanding benchmark called LongSpeech-Eval. Experiments show that our method exhibits strong performance in both long-speech and short-speech tasks, while greatly improving inference efficiency.

---

## 论文详细总结（自动生成）

# FastLongSpeech 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究背景**：大型语言模型（LLM）的进步推动了大型语音语言模型（LSLM）的发展，使其能够直接理解和生成语音。然而，现有LSLM大多专注于短语音（通常小于30秒）处理，长语音处理仍是一个未被充分探索的挑战。
- **核心问题**：长语音处理面临两大障碍：
  - 缺乏专用的长语音训练数据集，且构建长语音数据成本高昂；
  - 长语音序列导致极高的计算成本（语音表示的序列长度通常是同内容文本的4倍以上）。
- **整体目标**：提出一种无需专用长语音数据即可高效处理长语音的框架，同时保持或提升短语音任务的性能。

## 2. 论文提出的方法论

### 核心思想
在已有LSLM（Qwen2-Audio）基础上，引入一个**语音提取器（Extractor）模块**，通过**迭代融合策略**压缩语音表示，再利用**动态压缩训练**使模型适应不同压缩比，从而将短语音能力迁移到长语音任务。

### 关键技术细节
- **迭代融合策略**：
  - 使用CTC解码器输出每个语音帧的**内容密度**（非空白token概率之和）及相邻帧的**余弦相似度**。
  - 每轮迭代：计算当前序列长度T(m)，确定目标长度T(m+1)（若T(m) > 2L则减半，否则固定为L）。找出最相似的r(m)对相邻帧，将连续的相似帧划分为跨度（span），按内容密度加权融合每个跨度内的帧。重复直到达到目标长度L。
- **动态压缩训练**：
  - 第一阶段：仅训练CTC解码器（使用ASR数据），学习测量内容密度。
  - 第二阶段：在短语音Spoken QA数据上，均匀采样目标长度L（来自预定义集合，如{750,400,200,100,50,25,12}），对语音表示进行迭代融合得到长度为L的压缩表示，然后训练LLM（使用LoRA）。损失函数为负对数似然，其中L从集合中均匀采样。
- **公式**（文字描述）：
  - 内容密度：`d_j = sum(p_ctc(aj != blank | hj))`
  - 帧相似度：`e_{j,j+1} = cosine(hj, hj+1)`
  - 迭代目标长度：若T(m) > 2L则取floor(T(m)/2)，否则取L。
  - 动态压缩训练损失：`L_dct = - sum_{L~U(L)} log p(y | x, IF(h, L))`

### 算法流程
1. 输入波形 → 音频编码器得到25Hz帧率的语音表示h。
2. Extractor模块通过迭代融合策略将h压缩为长度L的h'（L≤预设窗口长度）。
3. LLM根据h'和指令x生成响应y。

## 3. 实验设计

### 数据集

- **训练数据**：
  - 第一阶段：LibriSpeech 960小时 + MLS 3k小时（ASR数据）。
  - 第二阶段：OpenASQA（5.9k小时，Spoken QA）、LibriSQA（360小时）、Common Voice（1.7k小时，转为Spoken QA格式）。
  - 所有训练样本时长<30秒。
- **评估数据**（9个数据集，5类任务）：
  - 短语音Spoken QA：speech_QA_iemocap (AIR-Bench)、LibriSQA test、LibriTTS test (OpenASQA)。
  - 长语音Spoken QA：自建**LongSpeech-Eval**（基于LongBench的MultiFieldQA-En和NarrativeQA，通过筛选、润色、TTS合成得到164个样本，平均时长132.77秒）。
  - 口语对话理解：speech_dialogue_QA_fisher (AIR-Bench)。
  - 情感识别：MELD。
  - ASR：LibriSpeech test-clean/test-other、GigaSpeech test。
  - 语音信息检索：SPIRAL-H。

### 对比方法

- **Random**：随机选择帧。
- **AvgPool**：固定分段平均。
- **MostSim**：选择最相似相邻帧后平均。
- **NTK-RoPE**：扩展位置编码使窗口匹配LLM上下文长度。
- **Cascaded**：Whisper转录+Qwen-7B-Chat。
- **Baseline**：原始Qwen2-Audio（仅用于短语音任务）。
- **FastLongSpeech**：本文方法。所有方法（除Baseline和FastLongSpeech外）都用相同数据LoRA微调。

### 评估指标
- Spoken QA/对话：Llama3.1-70B打分（1-5分）。
- ASR：WER。
- 情感识别：Accuracy。
- 效率：TFLOPs、运行时间。

## 4. 资源与算力

- 论文未明确提供训练所需的具体GPU型号、数量、训练总时长等详细信息。
- 仅提及效率实验在**NVIDIA L40**上运行，训练使用**DeepSpeed ZeRO-2**优化。
- 第二阶段LLM微调使用**LoRA**（r=128, alpha=256, dropout=0.05），学习率2e-4，余弦调度。
- 由于训练数据量较大（数万小时），推测需要多卡GPU集群，但具体数值未披露。

## 5. 实验数量与充分性

- **实验数量**：
  - 短语音Spoken QA：在3个数据集上测试不同压缩比（L=25,50,...,400）。
  - 长语音Spoken QA：与多种方法对比（即表1）。
  - 消融实验：去除动态压缩训练、去除迭代、去除内容密度加权（表2）。
  - 效率分析：短语音（表3）、长语音（表4）。
  - ASR任务（表5）。
  - 适用性实验：应用于vanilla Qwen2-Audio和Qwen2.5-Omni（表7、8），信息检索（表10），情感识别（表9）。
  - 扩展最大上下文长度测试（表11）。
- **充分性与公平性**：
  - 覆盖了多种任务类型和场景，对比方法合理（包括随机、平均、NTK-RoPE、级联等）。
  - 所有对比方法均经过相同的LoRA微调（除Baseline），避免不公平优势。
  - 不过，未报告多次运行的误差棒或统计显著性检验，对结果可靠性有一定影响。
  - 长语音基准LongSpeech-Eval是自建的，可能引入偏差（如TTS合成质量影响）。

## 6. 论文的主要结论与发现

- FastLongSpeech在**长语音Spoken QA任务上得分最高**（3.55），优于NTK-RoPE（3.44）和其他压缩方法。
- 在**短语音Spoken QA任务上**，FastLongSpeech在不同压缩比下均优于Random、AvgPool、MostSim，尤其在高压缩比（L=12）时仍保持显著优势。
- **效率显著提升**：长语音任务相比NTK-RoPE**减少60%计算量**和**70%推理时间**；相比级联方法**加速7倍以上**。
- 消融实验表明：动态压缩训练、迭代融合、内容密度加权三个组件均对性能有重要贡献。
- 动态压缩训练有效将短语音能力迁移到长语音，模型能适应不同压缩比。
- FastLongSpeech可直接应用于其他LSLM（如Qwen2.5-Omni），展示通用性。

## 7. 优点

- **无需专用长语音数据**：仅使用短语音数据即可实现长语音处理，降低了数据门槛。
- **高效压缩**：迭代融合策略基于内容密度和相似度，保留重要信息同时减少冗余，推理效率高。
- **灵活平衡**：通过调整目标长度L，可在效率和性能之间权衡，适应不同资源约束。
- **构建了长语音基准**：LongSpeech-Eval填补了评估空白。
- **方法通用性强**：可应用于不同基础LSLM（Qwen2-Audio、Qwen2.5-Omni）。
- **实验设计较全面**：涵盖多任务、多数据集、消融、效率分析、跨模型验证。

## 8. 不足与局限

- **缺乏统计显著性报告**：所有结果均为单次运行，未提供误差棒或置信区间，无法判断结果是否稳定。
- **长语音基准存在局限性**：
  - LongSpeech-Eval由TTS合成，可能与自然语音存在差异（如韵律、噪声）。
  - 样本数量较少（164个）。
- **高压缩比下ASR性能下降明显**：当L=100时WER大幅升高（LibriSpeech clean从3.85升到27.12），表明任务依赖性较大，需要谨慎选择压缩比。
- **未报告训练成本和详细的资源消耗**：难以复现或评估可扩展性。
- **仅基于英文**：未在多语言场景下测试，通用性受限。
- **未与最新端到端语音模型（如Phi-4-mini、Moshi等）对比**：对比方法主要为基线压缩策略，缺乏与同期先进LSLM的比较。
- **潜在偏差**：使用LLM打分可能引入评分偏差，且评估模板仅关注忠实度，忽略其他维度（如流畅性、完整性）。

（完）
