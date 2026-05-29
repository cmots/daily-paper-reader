---
title: "Freeze-Omni: A Smart and Low Latency Speech-to-speech Dialogue Model with Frozen LLM"
title_zh: "Freeze-Omni: 一种具有冻结LLM的智能低延迟语音到语音对话模型"
authors: "Xiong Wang, Yangze Li, Chaoyou Fu, Yike Zhang, Yunhang Shen, Lei Xie, Ke Li, Xing Sun, Long MA"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=s1EImzs5Id"
tags: ["query:speech-model"]
score: 9.0
evidence: Freeze-Omni是一种冻结LLM的语音到语音对话模型，实现低延迟语音翻译
tldr: Freeze-Omni提出了一种新颖的语音-文本多模态LLM架构，在保持LLM参数冻结的情况下将语音输入输出模态连接到文本LLM，实现了低延迟的端到端语音对话，并且语音模态的智能水平与文本模态相当。该方法简化了训练过程，同时保证了性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-s1eimzs5id/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1779, \"height\": 1538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s1eimzs5id/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1599, \"height\": 1331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s1eimzs5id/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1400, \"height\": 949, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s1eimzs5id/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1518, \"height\": 384, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-s1eimzs5id/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1547, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s1eimzs5id/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 925, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s1eimzs5id/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1522, \"height\": 429, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s1eimzs5id/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1315, \"height\": 320, \"label\": \"Table\"}]"
motivation: 现有语音对话模型计算开销大，且难以保持LLM智能水平。
method: 提出Freeze-Omni架构，冻结LLM参数，通过轻量模块连接语音输入输出。
result: 在保持低延迟的同时，语音模态智能与文本模态相当。
conclusion: 为实现高效语音对话系统提供了新思路。
---

## Abstract
The GPT-4o's excellent duplex speech interaction ability has given users an impressive experience. Researchers have recently proposed several multimodal LLMs to achieve user-agent speech-to-speech conversations. In this paper, we propose a novel speech-text multimodal LLM architecture called Freeze-Omni, and our main contribution is that the speech input and output modalities can be easily connected to a textual LLM while keeping the LLM's parameters frozen throughout the training process. We effectively ensure that the intelligence of the Freeze-Omni in the speech modality is at the same level as that in the text modality of its backbone LLM while achieving low latency in the end-to-end spoken response. In addition, we also designed a method to achieve duplex dialogue ability through multitask training, giving Freeze-Omni a more natural style of dialogue ability between users and agents. In summary, Freeze-Omni holds great potential to conduct speech-to-speech dialogue based on a multimodal LLM under the condition of a frozen LLM, avoiding the catastrophic forgetting problem caused by limited data and training resources.

---

## 论文详细总结（自动生成）

# Freeze-Omni: 一种具有冻结LLM的智能低延迟语音到语音对话模型——详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：现有语音对话模型（如GPT-4o）尽管性能出色，但多数方法在集成语音模态时需要对大语言模型（LLM）进行微调，这会导致**灾难性遗忘**——LLM原有的“智能”能力（如问题回答、角色扮演、指令遵循等）因微调而下降。同时，语音问答数据获取成本高昂（百万小时级），限制了微调方法的可行性。
- **核心问题**：如何在**不更新LLM任何参数**的前提下，将语音输入和输出模态连接到文本LLM，实现低延迟、高智能的端到端语音到语音对话。
- **整体含义**：提出Freeze-Omni架构，通过冻结LLM参数，仅训练轻量级语音编码器、适配器和语音解码器，使得语音模态的智能水平与文本模态相当，同时避免灾难性遗忘，大幅降低数据需求与训练资源消耗。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- **冻结LLM**：整个训练过程中，骨干LLM（Qwen2-7B-Instruct）的参数**完全冻结**，不参与任何梯度更新。
- **模块化连接**：通过独立的语音输入模块和语音输出模块，分别与LLM的输入嵌入空间和输出隐藏状态空间对齐。

### 关键技术细节

#### 2.1 语音输入建模（Speech Input Modeling）
- **流式语音编码器**：采用**分块（chunk-wise）** 的流式语音编码器，由下采样卷积层和Transformer块构成，输出帧率12.5Hz。适配器（Adapter）进一步下采样2倍，将特征映射到LLM嵌入空间。
- **三阶段训练**（见图2）：
  - **阶段1**：仅训练语音编码器，使用CTC损失进行ASR预训练（110k小时内部ASR数据）。
  - **阶段2**：语音编码器+适配器连接冻结的LLM，使用ASR转录文本作为标签，训练语音理解能力。引入可训练的特殊token引导LLM输出。
  - **阶段3**：使用**多轮问答数据**（6万条，由骨干LLM重新生成答案，再通过零样本TTS合成语音），仅训练**提示嵌入（Prompt Embedding）** 部分，语音编码器冻结，LLM冻结。该阶段使模型具备语音输入→文本输出的能力。

#### 2.2 语音输出建模（Speech Output Modeling）
- **基于Token的语音解码器**：采用**NAR（非自回归）预填充 + AR（自回归）生成**结构，包含NAR语音解码器、AR语音解码器、编解码器模型（TiCodec，单码本，40Hz帧率）。
- **三阶段训练**（见图3）：
  - **阶段1**：训练单码本编解码器（TiCodec），仅使用语音数据。
  - **阶段2**：使用**文本-语音配对数据**（3k小时，由零样本TTS生成），通过LLM的tokenizer和嵌入层获取文本嵌入，训练NAR和AR语音解码器（二者共享参数），实现文本输入→语音输出。
  - **阶段3**：引入**NAR前缀语音解码器**（Pre-network，两个Llama解码器层），**仅训练该前缀解码器**，其他部分冻结。利用多轮问答数据中LLM生成的**隐藏状态**和**文本token**，使语音解码器紧密耦合LLM输出，减少不良案例。

#### 2.3 双工对话设计（Duplex Dialogue）
- **分块级状态预测**：在LLM预填充阶段，对语音编码器每个chunk的最后一帧输出状态进行分类。定义三种状态：
  - 状态0：继续接收语音。
  - 状态1：用户打断对话，LLM重新生成。
  - 状态2：用户结束发言，无需打断。
- **“模型即服务器”策略**：同时启动多个模型实例，由服务器调度，分离每个用户的KV-cache和CNN缓存，实现任意模型响应任意用户chunk。

## 3. 实验设计

### 数据集
- **ASR数据**：110,000小时内部中英文语音-文本配对数据，用于语音输入阶段1和2。
- **TTS数据**：约3,000小时由零样本TTS系统生成的文本-语音配对数据，用于语音输出阶段1和2。
- **多轮问答数据**：从moss-003-sft-data中随机选取60,000条，用骨干LLM重新生成答案，再合成语音，用于语音输入阶段3和语音输出阶段3。
- **评测数据集**：
  - ASR：中文集aishell-1、test_net、test_meeting；英文集LibriSpeech的dev-clean/dev-other/test-clean/test-other。
  - 语音输出：随机选取1,000条LLM输出文本和隐藏状态，计算合成语音的CER（使用paraformer-zh评估）。
  - 口语问答：LlaMA-Questions、Web Questions、TriviaQA（文本通过edge-tts合成语音）。

### Benchmark与对比方法
- **语音输入**：对比Wav2vec2-base、Mini-Omni2、VITA-1.5。
- **语音输出**：对比有无前缀网络（pre-network）以及不同top-k取值。
- **口语问答**：对比SpeechGPT (7B)、Spectron (1B)、Moshi (7B)、GLM-4-Voice (9B)，以及对应的纯文本LLM（Helium、Qwen2-7B-Instruct）。

## 4. 资源与算力

- **训练硬件**：所有实验在**8块GPU**上完成。
- **训练时长**：文中**未明确**具体训练时长，仅说明使用Adamw优化器、warm-up学习率调度。各阶段学习率分别为：语音输入阶段1:2e-4、阶段2:1e-4、阶段3:6e-4；语音输出阶段2和3:5e-5。
- **模型参数量**：语音编码器约350M，语音解码器约120M，骨干LLM为Qwen2-7B-Instruct（7B）。
- **注意**：未说明GPU型号及总耗时，算力描述不够详细。

## 5. 实验数量与充分性

### 实验组数
- **ASR性能（表1）**：对比了三种配置（chunk=∞、chunk=4、无动态chunk训练），在7个评测集上进行，共21组结果。
- **语音输出CER（表2）**：对比了有无前缀网络、不同top-k（1~5），共20组结果。
- **口语问答（表3）**：在3个评测集上与4种语音模型和2种文本模型对比，共约18组结果。
- **延迟分析（表4）**：统计了平均、50%、90%延迟，涉及4个阶段。

### 充分性分析
- **优点**：覆盖了语音理解、语音生成、问答任务和延迟分析，核心能力均已评估；消融实验（如动态chunk训练、前缀网络）设计合理。
- **不足**：
  - 口语问答评测集仅3个，且均为英文集，缺乏中文集。
  - 未测试多说话人、不同语音风格、指令跟随等场景。
  - 双工对话能力仅定性描述（未给出准确率或打断成功率定量结果）。
  - 未与GPT-4o等商业系统直接对比（可能因无法获取）。
  - 所有对比方法均基于公开论文结果，可能存在实现差异。

综合来看，实验设计较为系统，但覆盖范围和定量指标仍有提升空间。

## 6. 论文的主要结论与发现

- **冻结LLM可行**：Freeze-Omni在完全不更新LLM参数的情况下，语音模态的智能水平（口语问答准确率）**与骨干LLM的文本模态非常接近**（44.73% vs 45.13%在Web Questions上；72% vs 77.67%在LlaMA-Questions上），显著优于其他语音对话模型（如Moshi、GLM-4-Voice）。
- **低延迟**：端到端平均延迟约745ms（考虑网络延迟约1.2秒），满足实时对话需求。
- **数据高效**：仅使用6万条多轮问答数据和3k小时TTS数据即可训练语音输出模块，远低于微调LLM所需数据量。
- **避免灾难性遗忘**：由于LLM全程冻结，其原有能力（如角色扮演、指令遵循）得以保留。

## 7. 优点

- **方法创新**：提出分阶段、模块化的冻结LLM训练策略，分别独立训练语音输入和输出模块，最后组合，思路清晰且实用。
- **低资源需求**：仅需少量对话数据和TTS数据即可完成训练，降低了门槛。
- **通用性**：可支持任意文本模态的LLM（论文验证了Qwen2-7B），且风格切换仅需用对应风格文本数据微调LLM（因LLM冻结，不影响语音模块）。
- **双工设计**：通过多任务学习实现打断检测，并采用“模型即服务器”调度策略，提升了对话自然度。
- **实验完整**：包含ASR、语音合成、QA和延迟四大维度，验证了模型在“智能”和“延迟”两个关键指标上的优势。

## 8. 不足与局限

- **单说话人限制**：论文明确说明“在单说话人情况下”评估语音输出，未支持多说话人或不同音色指令。
- **语音编码器单一**：仅处理语音，未扩展为通用音频编码器（如情感、音频字幕），限制了应用范围。
- **双工评估不足**：打断检测准确率、状态预测等定量指标缺失，仅依赖手动统计延迟。
- **教育资源不明确**：算力细节（GPU型号、训练时长）缺失，影响可复现性。
- **问答评测集有限**：仅3个英文集，未包含中文对话场景；且答案计算方式（greedy search、零样本）可能低估性能。
- **对比方法公平性**：部分对比模型（如SpeechGPT、Spectron）使用不同骨干LLM和训练数据，直接比较存在偏差；且Freeze-Omni使用内部数据（110k小时ASR）可能优于公开模型。
- **潜在偏差风险**：所有TTS数据由零样本系统生成，可能引入合成语音的固有问题（如韵律不自然），但论文未分析其对下游效果的影响。
- **应用限制**：仅支持单一码本的编解码器（TiCodec），对于高质量多说话人场景可能不够鲁棒。

（完）
