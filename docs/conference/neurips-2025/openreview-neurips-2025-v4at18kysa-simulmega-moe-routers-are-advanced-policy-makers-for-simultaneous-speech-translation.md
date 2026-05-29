---
title: "SimulMEGA: MoE Routers are Advanced Policy Makers for Simultaneous Speech Translation"
title_zh: SimulMEGA：MoE路由器作为同时语音翻译的高级策略制定者
authors: "Chenyang Le, Bing Han, Jinshun Li, Chen Songyong, Yanmin Qian"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=v4AT18kysa"
tags: ["query:speech-model"]
score: 9.0
evidence: 同时语音翻译，MoE策略学习
tldr: SimulMEGA针对同时语音翻译中质量-延迟权衡和策略学习问题，提出基于前缀训练和MoE精炼器的无监督策略框架。该方法隐式学习读写决策，无需额外推理开销，在多语言场景下显著提升翻译质量和语义连贯性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-v4at18kysa/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1432, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v4at18kysa/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1138, \"height\": 561, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v4at18kysa/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1420, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v4at18kysa/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1431, \"height\": 615, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v4at18kysa/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1436, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v4at18kysa/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1450, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v4at18kysa/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1141, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v4at18kysa/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1444, \"height\": 793, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-v4at18kysa/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1446, \"height\": 790, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-v4at18kysa/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1455, \"height\": 415, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v4at18kysa/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 293, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v4at18kysa/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1196, \"height\": 339, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v4at18kysa/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 917, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-v4at18kysa/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1035, \"height\": 764, \"label\": \"Table\"}]"
motivation: 现有同时语音翻译系统在多语言场景下难以学习统一读写策略，平衡质量与延迟。
method: 结合前缀训练和MoE门控机制的无监督策略学习，隐式优化读写决策。
result: 在多对多翻译任务上，SimulMEGA在延迟约束下取得更高的翻译质量和语义连贯性。
conclusion: SimulMEGA为实现高效实时语音翻译提供了新范式。
---

## Abstract
Simultaneous Speech Translation (SimulST) enables real-time cross-lingual communication by jointly optimizing speech recognition and machine translation under strict latency constraints. Existing systems struggle to balance translation quality, latency, and semantic coherence, particularly in multilingual many-to-many scenarios where divergent read/write policies hinder unified strategy learning. In this paper, we present SimulMEGA(Simultaneous Generation by Mixture-of-Experts GAting), an unsupervised policy learning framework that combines prefix-based training with a Mixture-of-Experts refiner to learn effective read/write decisions in an implicit manner, without adding inference-time overhead. Our design requires only minimal modifications to standard transformer architectures and generalizes across both speech-to-text and text-to-speech streaming tasks. Through comprehensive evaluation on six language pairs, our 500 M-parameter speech-to-text model outperforms the Seamless baseline, achieving under 7% BLEU degradation at 1.5 s average lag and under 3% at 3 s. We further demonstrate SimulMEGA’s versatility by extending it to streaming TTS via a unidirectional backbone, yielding superior latency–quality trade-offs.

---

## 论文详细总结（自动生成）

# 论文《SimulMEGA: MoE Routers are Advanced Policy Makers for Simultaneous Speech Translation》详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究问题**：同时语音翻译（SimulST）需要在严格的延迟约束下，实时地联合优化语音识别和机器翻译。现有系统难以在翻译质量、延迟和语义连贯性三者之间取得良好平衡，尤其是在多语言多对多（many-to-many）场景中，不同语言对之间存在差异化的读写策略，导致统一的策略学习非常困难。
- **整体目标**：提出一种无监督策略学习框架SimulMEGA，通过隐式学习读写决策，在不增加推理开销的前提下，同时提升翻译质量和降低延迟，并支持语音到文本（S2TT）和文本到语音（TTS）两种流式任务。
- **背景意义**：SimulST在实时跨语言通信（如国际外交、直播本地化、低延迟对话系统）中具有重要应用价值，但现有方法（如固定等待策略、基于注意力分数的策略、额外CTC头等）要么依赖于人工设计的策略信号，要么需要架构修改导致性能损失。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- **无监督策略学习**：利用一个辅助的Mixture-of-Experts（MoE）精炼器模块，在训练时隐式学习读写策略，推理时该模块被移除，不增加额外计算。
- **前缀训练（prefix-based training）**：模拟流式推理场景，对输入进行随机前缀截断，让模型学习根据有限的前缀信息决定是否生成下一个输出。

### 关键技术细节
- **架构组成**：
  - **流式语音编码器**：混合使用Chunk-AR（块级自回归）块（20层）和NAR（非自回归）块（4层），利用缓存KV机制提高推理效率，同时通过NAR块保持全局上下文。
  - **文本解码器**：标准Transformer自回归解码器（12层）。
  - **MoE精炼器**：仅训练阶段激活，由多个refiner块组成，每个块包含两个专家：前缀专家（Prefix Expert，使用交叉注意力）和全局专家（Global Expert，使用池化的全局特征+MLP）。路由门根据文本解码器的最终隐藏状态输出一个标量p，决定两个专家的权重（p给全局专家，1-p给前缀专家）。
  - **全局信息泄露防护**：用“前一出注意力”（previous-output attention）替换自注意力，防止全局信息通过自注意力传播。
- **训练损失**：
  - 阶段1：标准离线S2TT损失 \(L_{\text{offline}}\)。
  - 阶段2：联合损失 \(L_{\text{simul}} = L_{\text{offline}} + w_r L_{\text{refiner}} + w_p L_{\text{prefix}}\)，其中 \(L_{\text{refiner}}\) 让MoE精炼器预测解码序列，\(L_{\text{prefix}}\) 只在门控置信度高的位置计算解码loss。
- **推理策略**：根据路由器输出 \(p_{t,i}\) 与阈值 \(\lambda\) 比较：若 \(p_{t,i} < \lambda\) 则执行Read（继续接收输入），否则Write（生成当前输出）。
- **分数分布控制**：
  - 分数归一化损失 \(L_{\text{norm}}\)：让平均门控分数与输入前缀长度成比例。
  - 预Sigmoid高斯噪声：增强门控输出离散化，提高阈值选择的鲁棒性。

## 3. 实验设计

### 数据集
- **训练数据**：约10万小时的训练数据，涵盖6种语言（EN, ZH, DE, ES, FR, IT），来自开源语音识别数据集（LibriSpeech, MLS, VoxPopuli, Common Voice, WenetSpeech, KeSpeech, Emilia），通过云端文本翻译API生成伪翻译标签。
- **测试基准**：CoVoST2（含5个X-EN、2个EN-X语言对）和Fleurs（含30个语言对）用于S2TT评估；LibriSpeech-PC test-clean和Seed-TTS test-zh用于TTS评估。

### 基线方法
- **S2TT基线**：Seamless系列（SeamlessM4T Medium/Large-v2、SeamlessStreaming）、Wait-K、DiG-SST、EDATT、AlignATT。
- **TTS基线**：CosyVoice 2的默认流式模式、Seamless。
- **S2ST基线**：Seamless、NAST-S2S、StreamSpeech（后两者参数规模和训练数据较小）。

### 评价指标
- 翻译质量：大小写敏感的BLEU（S2TT）、ASR-BLEU（S2ST）。
- 延迟：平均滞后（Average Lagging, AL），采用SimulEval工具。
- TTS：词错误率（WER）、说话人相似度（SIM）、单元级AL。

## 4. 资源与算力

- **GPU**：8块Nvidia H800 GPU。
- **训练时间**：阶段1（离线预训练）约1周（100万步），阶段2（同时训练）约2天。
- **优化器**：AdamW，学习率线性调度，预热5000步，阶段1最大学习率1e-4，阶段2为1e-5。
- **批处理与精度**：FP16混合精度训练。

## 5. 实验数量与充分性

- **实验数量**：
  - S2TT主实验：在CoVoST2上7个语言对、Fleurs上30个语言对，共37个方向；同时报告离线BLEU、同时BLEU随AL变化曲线（5个阈值点）。
  - TTS实验：在LibriSpeech、SeedTTS_zh、CoVoST2_zh-en/en-zh上评估，含WER、SIM、AL。
  - S2ST实验：双向（中-英、英-中）对比Seamless、NAST-S2S等。
  - 消融实验：在CoVoST2 EN-ZH子集上，分别验证预Sigmoid噪声、分数归一化、训练损失的影响，每个因素设3组对比。
- **充分性与公平性**：
  - 覆盖多语言、多任务（S2TT、TTS、S2ST），基线和自身方法均使用相同离线基础模型或公开可用模型。
  - 消融实验针对关键设计，结果解释合理。
  - 不足之处：未报告统计显著性检验（如误差棒），但跨40+语言对的测试一定程度上抵消了随机性。

## 6. 论文的主要结论与发现

- **SimulMEGA-S2T**：在CoVoST2上，相比离线模型BLEU退化仅0.3%~3.1%，远优于Seamless的7%~8%退化；在Fleurs上亦然。
- **延迟-质量权衡**：在1.5秒平均滞后时BLEU退化<7%，3秒时<3%，显著优于Seamless和所有基线方法。
- **SimulMEGA-TTS**：在极端单token流式条件下，WER和SIM与离线CosyVoice 2相当，但AL极低（1.2和0.5个token）；跨语言场景下SIM比Seamless高10个点，WER低40%以上。
- **SimulMEGA-S2S**：级联S2TT+TTS系统，从S2TT到S2ST的BLEU降幅（7%/6%）低于Seamless（10%/20%），延迟仅增加<200ms。
- **消融结论**：预Sigmoid噪声σ=1最优；分数归一化能平滑延迟-质量曲线；去除 \(L_{\text{offline}}\) 会导致约1 BLEU下降，而 \(L_{\text{prefix}}\) 可忽略。

## 7. 优点

- **创新性**：首次将MoE路由器作为隐式读写策略制定者，结合前缀训练实现无监督策略学习，推理时无额外开销。
- **通用性**：仅需对标准Transformer进行极小修改，可同时适用于S2TT、TTS、S2ST，且兼容不同骨干（Whisper、CosyVoice 2）。
- **多语言鲁棒性**：在6种语言、30个语言对上验证，性能稳定。
- **效率**：推理额外延迟仅约50ms（计算感知），远低于Seamless的200ms；模型参数量（561M）仅为Seamless的1/3~1/2。
- **技术细节严格**：设计了全局信息泄露防护（前一出注意力）、分数分布控制（归一化+噪声）等机制，有效解决了训练不稳定和阈值难以迁移的问题。

## 8. 不足与局限

- **级联系统缺陷**：SimulMEGA-S2S为级联架构，存在文本令牌不一致（Whisper token vs Qwen token）、额外延迟（~0.1s）等问题。
- **多语言TTS支持有限**：目前TTS仅支持中英两种语言，限制了实际应用。
- **输入长度限制**：模型仅支持最长30秒输入，仍需依赖VAD进行片段切割；未实现持续流式生成（滑动窗口或历史选择）。
- **实验统计性不足**：未提供误差棒或置信区间，单一运行结果可能存在偏差。
- **潜在误用风险**：TTS的语音克隆能力可能被滥用（论文已提及）。
- **训练数据依赖**：使用伪标签（云端翻译API），虽规模大但质量可能不如人工标注，可能引入噪声。

（完）
