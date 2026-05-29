---
title: "OWLS: Scaling Laws for Multilingual Speech Recognition and Translation Models"
title_zh: OWLS：多语言语音识别与翻译模型的缩放定律
authors: "William Chen, Jinchuan Tian, Yifan Peng, Brian Yan, Chao-Han Huck Yang, Shinji Watanabe"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=xnPW7yYomF"
tags: ["query:speech-model"]
score: 9.0
evidence: 多语言语音识别与翻译模型的缩放定律
tldr: 语音领域的缩放定律尚缺乏系统研究。本文开源了OWLS系列模型，覆盖0.25B到18B参数，基于360K小时多语言语音数据训练，在语音识别和翻译任务上系统研究了数据、模型和计算量对性能的影响。推导出的缩放定律表明，模型大小与性能之间遵循类似语言建模的幂律关系。该工作为设计更优的语音翻译模型提供了实证指导。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-xnpw7yyomf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 803, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xnpw7yyomf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1489, \"height\": 779, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xnpw7yyomf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1768, \"height\": 635, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xnpw7yyomf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 843, \"height\": 649, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xnpw7yyomf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1244, \"height\": 550, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xnpw7yyomf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 777, \"height\": 436, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xnpw7yyomf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 770, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xnpw7yyomf/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 860, \"height\": 649, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xnpw7yyomf/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 847, \"height\": 823, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xnpw7yyomf/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 827, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xnpw7yyomf/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 846, \"height\": 653, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xnpw7yyomf/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1651, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xnpw7yyomf/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1749, \"height\": 861, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xnpw7yyomf/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1780, \"height\": 1302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xnpw7yyomf/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1716, \"height\": 1342, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-xnpw7yyomf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1768, \"height\": 591, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xnpw7yyomf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 738, \"height\": 272, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xnpw7yyomf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 527, \"height\": 418, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xnpw7yyomf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 420, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xnpw7yyomf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 701, \"height\": 400, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xnpw7yyomf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1778, \"height\": 1187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xnpw7yyomf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1427, \"height\": 619, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xnpw7yyomf/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1092, \"height\": 403, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xnpw7yyomf/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1065, \"height\": 271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xnpw7yyomf/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1180, \"height\": 446, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xnpw7yyomf/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1430, \"height\": 806, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xnpw7yyomf/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1092, \"height\": 752, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xnpw7yyomf/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1000, \"height\": 2288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xnpw7yyomf/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1053, \"height\": 2284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xnpw7yyomf/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1041, \"height\": 2271, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xnpw7yyomf/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1104, \"height\": 2362, \"label\": \"Table\"}]"
motivation: 语音模态的缩放定律研究不足，缺乏大规模开源语音翻译模型。
method: 构建0.25B至18B参数的多语言语音识别与翻译模型套件，基于360K小时公共语音数据训练。
result: 推导出语音任务上的缩放定律，发现性能与模型大小存在幂律关系。
conclusion: 开源了当前最大的语音模型，为语音翻译和识别系统的资源分配提供依据。
---

## Abstract
Neural scaling laws offer valuable insights for designing robust sequence processing architectures. While these laws have been extensively characterized in other modalities, their behavior in speech remains comparatively underexplored. In this work, we introduce OWLS, an open-access, reproducible suite of multilingual speech recognition and translation models spanning 0.25B to 18B parameters, with the 18B version being the largest speech model, to the best of our knowledge. OWLS leverages up to 360K hours of public speech data across 150 languages, enabling a systematic investigation into how data, model, and compute scaling each influence performance in multilingual speech tasks. We use OWLS to derive neural scaling laws, showing how final performance can be reliably predicted when scaling. Scaling to larger models can improve ASR performance across the board, in both low and high resource languages, improving the accessibility of speech technologies. Finally, we show how OWLS can be used to power new research directions by discovering emergent abilities in large-scale speech models. Model checkpoints will be released on https://huggingface.co/collections/espnet/owls-scaling-laws-for-speech-recognition-and-translation-67ab7f991c194065f057ce8d for future studies.

---

## 论文详细总结（自动生成）

# OWLS：多语言语音识别与翻译模型的缩放定律 — 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：神经缩放定律在文本和视觉领域已得到充分研究，但在语音模态中仍然相对未被探索。现有的多语言语音识别（ASR）和翻译（ST）模型虽然规模不断增长（如Whisper、Canary等），但大多使用非公开数据，且缺乏对缩放行为的系统分析。
- **核心问题**：模型参数、训练数据量、计算量（FLOPS）如何影响多语言语音识别和翻译任务的性能？能否像语言模型一样建立可预测的缩放定律？
- **整体含义**：通过开源大规模、可复现的模型套件OWLS，系统地研究缩放行为，为设计更优的语音翻译和识别系统提供实证指导，同时促进低资源语言的技术可及性。

## 2. 论文提出的方法论

### 2.1 核心思想

- 构建一系列Whisper风格的编码器-解码器Transformer模型，参数从0.25B到18B，训练数据从11K到360K小时，覆盖150种语言。
- 通过系统地改变模型大小、数据大小和训练计算量，测量下游ASR（WER/CER）和ST（BLEU）性能，拟合幂律缩放曲线。
- 缩放定律公式（以WER为例）：  
  `WER(x) = β_x · x^{α_x}`，其中x ∈ {模型参数N, 数据量T, 计算量B}，β和α为待学参数。

### 2.2 关键技术细节

- **架构**：Transformer编码器-解码器，使用混合CTC/注意力损失。输入为80维log-Mel滤波器组（帧移10ms），经4倍下采样卷积层。文本使用50K子词词汇表（unigram语言模型）。
- **训练方式**：Whisper风格训练，所有话语填充至30秒，联合训练语言识别、ASR、ST和时间戳预测。
- **训练策略**：Adam优化器，分段学习率调度（前30K步线性预热至5e-5，再30K步升至2e-4，之后指数衰减）。批量大小256，训练675K步。使用bfloat16、Flash Attention 2、DeepSpeed ZeRO Stage-2。
- **模型配置**：对7种模型大小（0.25B/0.5B/1B/2B/4B/9B/18B），统一分配编码器与解码器参数，按比例增加层数、隐藏维度、前馈维度和注意力头数。

## 3. 实验设计

### 3.1 数据集与场景

- **训练数据**：
  - 基础180K小时：来自OWSM v3.2的25个公开语料库（如MLS、Common Voice、GigaSpeech、MuST-C等），含150K小时ASR + 30K小时ST数据。
  - 扩展360K小时：额外从YODAS数据集中清理出180K小时数据（仅用于两个模型：OWLS 1B 360K和OWLS 18B v2）。
- **评估基准**：
  - **多语言ASR**：FLEURS 102语言测试集（报告WER/CER）。
  - **英文多领域ASR**：AMI、LibriSpeech、SPGISpeech、Tedlium、VoxPopuli、GigaSpeech。
  - **翻译**：FLEURS的英→X和X→英翻译对（15对语言），使用BLEU评分。
  - **特殊能力**：正交理解（日/中文）、代码切换（12种语言与英文混合）、空耳语义质量（人类MOS评分）、上下文偏置（LibriSpeech偏置测试）、上下文学习（克丘亚语ICL）。

### 3.2 对比方法

- **SOTA对比**：Whisper Large v3、Qwen2Audio、SenseVoice S/L、Seamless M/L、Canary等，在FLEURS、AISHELL、LibriSpeech、ReazonSpeech、KsponSpeech上比较。

### 3.3 实验分组

1. **模型缩放实验**：固定180K小时数据，训练7种参数规模的模型，评估所有基准。
2. **数据缩放实验**：固定1B模型，在11K/22K/45K/90K/180K/360K小时数据上训练6个模型。
3. **计算缩放实验**：对每个模型提取7个中间检查点（15K~675K步），计算TFLOPS并拟合WER随计算量的变化。
4. **进一步缩放**：训练18B v2模型（360K数据），与SOTA对比。
5. **测试时能力实验**：束搜索计算等量比较、正交理解、代码切换、空耳、上下文偏置、ICL（克丘亚语0~3示例）。

## 4. 资源与算力

论文明确报告了训练资源（如表7）：
- **GPU类型**：H100（主要）、H200（1B 360K模型）。
- **GPU数量与时长**：
  - 最小0.25B模型：2节点×8 GPU=16 GPU，训练3天，共1,164 GPU小时。
  - 最大18B模型：6节点×8 GPU=48 GPU，训练17天，共19,440 GPU小时。
  - 各模型训练总GPU小时从1,164到19,440不等。
- **总计算量**：所有模型训练合计约56,000 GPU小时（H100/H200）。
- **其他**：使用PSC Bridges2和NCSA Delta/DeltaAI集群，通过ACCESS项目分配。

## 5. 实验数量与充分性

- **实验总数**：约13个预训练模型（7种参数×不同数据组合）+ 多种评估配置，覆盖数百个语言-任务组合。
- **充分性评价**：
  - **充分**：系统地覆盖了模型、数据、计算三个缩放维度；评估了多语言ASR、多领域英文ASR、翻译、特殊能力（4种）、ICL等，实验设计完整。
  - **客观公平**：使用统一训练超参数，仅变化缩放变量；在多个标准公开基准上对比已知SOTA方法；报告了R²等统计量说明拟合质量。
  - **局限性**：数据缩放实验仅基于同分布下采样，跨域数据（YODAS）仅用于两个模型；翻译实验仅覆盖15对语言；特殊能力实验样本量有限（如空耳仅3种语言、13名志愿者）。

## 6. 论文的主要结论与发现

1. **模型缩放高度可预测**：对每种语言，WER与模型参数之间拟合幂律关系，平均R² ≈ 0.95。模型缩放一致降低所有语言（包括低资源语言）的WER。
2. **数据缩放效果受限**：语言内的数据量仅与WER中等相关（R² ≈ 0.5）。增加同分布数据收益递减；增加新分布数据（YODAS）可进一步改善饱和语言的性能。
3. **计算缩放可预测最终性能**：给定参数大小下，中间检查点WER与累计TFLOPS拟合良好（R² ≈ 0.82），可提前预测最终WER。
4. **缩放不能克服数据不足**：对于数据极少的任务（如日语→英语ST仅1小时），模型缩放无法显著提升性能。
5. **大规模模型展现涌现能力**：如正交理解（更准确地写出汉字/假名）、代码切换识别（拉丁字母语言改善显著）、上下文偏置（1B+模型可有效利用偏置词）、空耳（更大模型生成更语义连贯的误听文本）、上下文学习（仅9B/18B模型能利用3个示例）。
6. **OWLS 18B v2性能与SOTA持平或更优**：在FLEURS英文、日语、中文上优于Whisper Large v3等，尽管训练数据少14倍。

## 7. 优点

- **开源透明**：完全公开模型、代码、日志、检查点，使用公共数据集，促进可复现研究。
- **系统全面**：首次在语音识别+翻译多任务上建立缩放开定律，覆盖三个缩放维度。实验设计科学，从多个角度验证缩放定律的普适性。
- **规模领先**：18B参数为已知最大语音模型，探索了极大规模下的行为。
- **涌现能力发现**：发现了多个在语音模型上未见报道的涌现能力（正交理解、空耳、ICL等），开辟新研究方向。
- **公平对比**：在测试时计算等量条件下比较不同规模模型，验证大模型在相同推理资源下仍具有优势。

## 8. 不足与局限

- **数据偏差**：训练数据以英文和少数高资源语言为主，低资源语言表现仍较差（如非洲语言WER较高），可能存在语言多样性不足的问题。
- **结论泛化性**：缩放定律基于固定架构和训练配置，在其他架构（如仅编码器、自监督模型）上是否成立未知。
- **实验覆盖**：
  - 翻译仅评估了15对语言，未覆盖大量低资源翻译对。
  - 涌现能力实验样本量小（空耳仅3种源语言、13名志愿者），可能不够稳健。
  - 数据缩放实验未在更大模型上重复验证（仅1B模型）。
- **计算消耗**：大规模训练消耗大量能源，但论文已透明报告并讨论社会影响。
- **伦理方面**：模型可能产生幻觉和偏见；数据部分使用非商业许可，模型也仅限研究用途。
- **评估指标**：BLEU在低资源翻译上可能不够可靠，WER/CER对不同语言的正交复杂度敏感，未对所有语言进行调优。

（完）
