---
title: "MATS: An Audio Language Model under Text-only Supervision"
title_zh: MATS：仅文本监督的音频语言模型
authors: "Wen Wang, RuiBing Hou, Hong Chang, Shiguang Shan, Xilin Chen"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=fDzzshfELg"
tags: ["query:speech-model"]
score: 7.0
evidence: 仅文本监督的多音频任务模型，涵盖理解与生成
tldr: 本文提出MATS，一种仅使用文本监督训练的音频语言模型。它利用CLAP等预训练对齐模型，将共享音频-语言潜在空间投影到大语言模型空间，从而赋予模型音频理解与生成能力，无需音频数据参与训练。该方法大幅降低了数据采集成本，并在多种音频任务上展现了竞争力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-fdzzshfelg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 675, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fdzzshfelg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 825, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fdzzshfelg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 843, \"height\": 187, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fdzzshfelg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 839, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fdzzshfelg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1417, \"height\": 791, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fdzzshfelg/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 704, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fdzzshfelg/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1777, \"height\": 759, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fdzzshfelg/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1771, \"height\": 746, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fdzzshfelg/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1772, \"height\": 747, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fdzzshfelg/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1770, \"height\": 747, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fdzzshfelg/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1778, \"height\": 891, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-fdzzshfelg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 629, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fdzzshfelg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1765, \"height\": 562, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fdzzshfelg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1648, \"height\": 596, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fdzzshfelg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 854, \"height\": 575, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fdzzshfelg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1318, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fdzzshfelg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 748, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fdzzshfelg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1662, \"height\": 840, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fdzzshfelg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1661, \"height\": 657, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fdzzshfelg/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1184, \"height\": 822, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fdzzshfelg/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1761, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fdzzshfelg/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 852, \"height\": 134, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fdzzshfelg/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 736, \"height\": 136, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fdzzshfelg/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 501, \"height\": 134, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fdzzshfelg/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1424, \"height\": 131, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fdzzshfelg/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 502, \"height\": 134, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fdzzshfelg/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 520, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fdzzshfelg/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 572, \"height\": 204, \"label\": \"Table\"}]"
motivation: 训练音频语言模型需要大量音频-文本对，数据获取成本高。
method: 利用预训练音频-语言对齐模型，通过文本监督将共享潜在空间映射到LLM空间。
result: 无需音频数据，模型就能处理多种音频任务，性能接近有监督方法。
conclusion: 文本监督策略有效降低了音频语言模型的训练门槛。
---

## Abstract
Large audio-language models (LALMs), built upon powerful Large Language Models (LLMs), have exhibited remarkable audio comprehension and reasoning capabilities. 
However, the training of LALMs demands a large corpus of audio-language pairs, which requires substantial costs in both data collection and training resources. In this paper, we propose **MATS**, an audio-language multimodal LLM designed to handle **M**ultiple **A**udio task using solely **T**ext-only **S**upervision. By leveraging pre-trained audio-language alignment models such as CLAP, we develop a text-only training strategy that projects the shared  audio-language latent space into LLM latent space, endowing the LLM with audio comprehension capabilities without relying on audio data during training. To further bridge the modality gap between audio and language embeddings within CLAP, we propose the **S**trongly-rel**a**ted **n**oisy **t**ext with **a**udio (**Santa**) mechanism. Santa maps audio embeddings into CLAP language embedding space while preserving essential information from the audio input. Extensive experiments demonstrate that MATS, despite being trained exclusively on text data, achieves competitive performance compared to recent LALMs trained on large-scale audio-language pairs. The code is publicly available in [https://github.com/wangwen-banban/MATS](https://github.com/wangwen-banban/MATS)

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：大规模音频-语言模型（LALMs）虽然展现出强大的音频理解与推理能力，但其训练依赖于大量音频-文本配对数据，导致数据收集和训练资源成本极高。
- **研究背景**：现有LALMs（如Pengi、SALMONN、Qwen-Audio等）通常需要人工标注海量音频-问题-答案三元组，耗时费力；虽有一些文本-only的音频描述框架（如NoAudioCaptioning、DRCap）试图降低成本，但主要局限于单一声音类型的字幕任务，缺乏开放问答能力，且存在模态差距处理不充分的问题。
- **论文目标**：提出一种**仅使用文本监督**即可处理多种音频任务（分类、字幕、问答）的音频语言模型MATS，大幅降低数据与训练成本，同时保持竞争性能。

## 2. 论文提出的方法论

### 核心思想
- 利用预训练的**对比学习模型CLAP**，其共享音频-语言嵌入空间。训练时仅使用文本数据，通过CLAP的文本编码器提取文本嵌入，添加高斯噪声模拟模态差异，然后通过映射器（Mapper）将嵌入映射到大语言模型（LLM）的潜在空间；推理时用CLAP音频编码器处理真实音频，再通过**Santa机制**将音频嵌入转换为接近语言嵌入的表示，从而让LLM理解音频语义。

### 关键技术细节
1. **模型架构**：
   - 冻结CLAP的音频编码器（HTSAT）和文本编码器（GPT2）。
   - 可训练的映射器：8层Transformer + 线性层，使用可学习查询向量与CLAP嵌入交互，输出与LLM嵌入维度对齐。
   - LLM采用GPT2-125M或LLaMA-7B（经过Vicuna指令微调），通过LoRA低秩适配进行轻量训练。

2. **模态转移方法**（训练-推理两阶段）：
   - **训练阶段**：对文本嵌入添加零均值高斯噪声（方差σ通过30个随机样本计算音频/文本嵌入的无穷范数），然后经映射器送入LLM进行自回归训练，损失为交叉熵。
   - **推理阶段**：音频嵌入经过**Santa机制**后再由映射器处理。

3. **Santa机制（Strongly-related noisy text with audio）**：
   - 构建**记忆库M**：从训练文本集中随机选取M个文本，加噪声后得到增强语言嵌入。
   - 对M进行**K-means聚类**（K=100），得到聚类后的记忆S。
   - 给定输入音频嵌入za，找到最近的聚类中心，选择聚类内最相似的L个增强语言嵌入（L=32）。
   - 计算加权和（权重为za与各嵌入的点积相似度经softmax），并与原始音频嵌入进行平衡融合（平衡参数λ=0.3）：
     \[
     f_{\text{Santa}}(z_a) = (1-\lambda) z_a + \lambda \sum_{i=1}^{L} w_i \cdot m_i^{\text{closest}}
     \]
   - 该设计既保留了原始音频信息，又通过强相关语言嵌入缩小了模态差距。

4. **训练数据**：构建 **AudioTIA-5M** 数据集，仅包含文本三元组（文本描述、指令、答案），涵盖分类（约58.7%）、字幕（约40%）、简单QA（约1.3%）及开放式问答（约3.8M，来自OpenAQA和MusicQA的文本版本）。

### 理论分析
- 推导了文本监督音频模型的泛化误差界：误差由经验风险、模态差异和复杂度项组成。减小CLAP中音频-语言嵌入的分布差距是降低泛化误差的关键，从而为Santa机制提供了理论支撑。

## 3. 实验设计

### 使用的数据集与Benchmark
- **闭集任务**：
  - 音频分类：ESC-50、FSD50K、DCASE、TUT、VGG、US8K、GTZAN、BJO。
  - 音频字幕：AudioCaps、Clotho、MusicCaps。
  - 简单QA：ClothoAQA。
- **开放任务**：
  - 复杂QA：AIR-Bench Chat（声音、音乐两个子集）、MMAU（多任务音频理解与推理）。
- 评估指标：Accuracy、mAP、CIDEr、SPICE、SPIDEr、ROUGH-L、BLEU4、GPT4评分、ACC/B-ACC等。

### 对比方法
- **基于音频监督的方法**：Pengi、LTU、GAMA、SALMONN、Qwen-Audio、Audio Flamingo、LP-MusicCaps等。
- **基于文本监督的方法**：NoAudioCaptioning、PromptAAC、DRCap（均为音频字幕方法）。
- 自身变种：MATS-GPT2（125M）、MATS-LLaMA（7B）、MATS-Audio（音频监督版本）。

## 4. 资源与算力

- **MATS-GPT2**：在2张A100 GPU上，训练约25小时（90,000迭代），batch size=128，学习率5e-5，AdamW优化器。
- **MATS-LLaMA**：在2张A100 GPU上，训练约35小时（360,000迭代），batch size=96，学习率3e-5，余弦退火调度。
- 文中未明确说明显存具体占用，但基于2卡A100可推测规模适中。

## 5. 实验数量与充分性

- **实验数量**：共涉及**16个下游任务**（闭集+开放），包含零样本与监督设置。
- **消融实验**：
  - 比较不同模态转移方法（Santa vs Noise-only、Memory-only等）。
  - 拆解Santa各组件（去除K-means、记忆库、音频嵌入、高斯噪声）。
  - 分析超参数：噪声方差σ、温度τ、top L、平衡λ、记忆库大小M、聚类数K、LoRA秩/缩放因子、映射器层数。
- **充分性评估**：对比多种SOTA方法（音频监督和文本监督），在零样本下表现出显著提升（如DCASE+12%、VGG+7%、MusicCaps ROUGH-L+9.9%）。对于开放任务，MATS-LLaMA在MMAU上超越SALMONN(13B) 11.7%。消融实验验证了每个设计的必要性。
- **公平性**：文本监督模型与音频监督模型在同一benchmark上比较，且与同类文本方法（NoAudioCaptioning等）直接对比；但部分对比方法的结果引用自其他论文（如GAMA论文），可能存在实现细节差异，但总体可接受。

## 6. 论文的主要结论与发现

1. **MATS在仅文本监督下取得了与音频监督模型相当的性能**，在多个闭集任务上超越以往SOTA（零样本），在开放任务（MMAU）上仅次于Qwen2-Audio。
2. **Santa机制有效缩小了CLAP的音频-语言模态差距**，t-SNE可视化显示其嵌入分布更统一；消融实验表明，去除音频嵌入或高斯噪声会导致性能大幅下降（CIDEr从0.735降至0.343或0.384）。
3. **大型LLM（7B）对开放任务至关重要**，而小型GPT2足以胜任闭集感知任务，但开放推理能力不足。
4. **文本监督方法的训练效率远高于音频监督**，且具备多任务通用性，可同时处理声音和音乐。

## 7. 优点

- **创新性**：首次实现仅文本监督的多任务音频语言模型，覆盖分类、字幕、QA全流程，突破以往单字幕限制。
- **理论指导**：给出文本监督模型的泛化误差界，为模态差距缩小提供了理论依据。
- **资源高效**：无需任何音频数据参与训练，仅需文本描述，极大降低数据收集成本；LoRA微调LLM，显存和算力需求低。
- **结果扎实**：在16个基准上全面评估，消融实验完整，超参数分析深入，可视化支持充分。
- **开放性**：代码和数据集（AudioTIA-5M）已公开，可复现。

## 8. 不足与局限

- **细粒度信息丢失**：CLAP音频编码器在提取精细信息（如事件次数、精确频率）上能力有限，导致模型在AIR-Bench等需要精确数字的任务上表现弱于Qwen-Audio等基于Whitepser+BEATs的模型。
- **依赖CLAP质量**：性能上限受限于CLAP的跨模态对齐质量；若CLAP对某些音频类型（如语音、情绪）对齐不佳，MATS也会受波及。
- **零样本能力有限**：虽然零样本分类不错，但开放任务（如AIR-Bench）仍需依赖上下文选项（MMAU）才能超越部分音频监督模型，纯开放生成能力仍有提升空间。
- **语言偏差风险**：训练数据完全由文本生成（部分经ChatGPT产生），可能引入语言模式偏差或描述不全面，尤其在音乐类型（MusicCaps）上可能缺乏真实音频对应的多样性。
- **对比实验公平性**：部分对比方法（如GAMA、LTU-AS）的结果取自原文，并非在同一设置下复现，可能存在实验环境差异；音频监督模型使用了更多数据（如音频QA对），直接比较需谨慎。

（完）
