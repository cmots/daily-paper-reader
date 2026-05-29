---
title: "Watch and Listen: Understanding Audio-Visual-Speech Moments with Multimodal LLM"
title_zh: 看和听：基于多模态大语言模型理解音频-视觉-语音时刻
authors: "Zinuo Li, Xian Zhang, Yongxin Guo, Mohammed Bennamoun, Farid Boussaid, Girish Dwivedi, Luqi Gong, Qiuhong Ke"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=kWGJa9ZO3M"
tags: ["query:speech-model"]
score: 4.0
evidence: 利用视觉、音频和语音三重模态进行视频理解的大语言模型
tldr: 本文提出TriSense，一个三重模态大语言模型，通过查询式连接器融合视觉、音频和语音信号，实现全面的视频时间理解。该模型能够定位如“科学家发言时伴随音乐和掌声”等复杂场景。实验证明其在多种视频理解任务上优于现有方法，尤其是在音频模态利用方面。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwgja9zo3m/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 709, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwgja9zo3m/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 547, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwgja9zo3m/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 565, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwgja9zo3m/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1428, \"height\": 805, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwgja9zo3m/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1439, \"height\": 808, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwgja9zo3m/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1423, \"height\": 1192, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwgja9zo3m/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1365, \"height\": 811, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwgja9zo3m/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1358, \"height\": 249, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwgja9zo3m/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1358, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwgja9zo3m/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1364, \"height\": 788, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwgja9zo3m/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1364, \"height\": 800, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwgja9zo3m/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1364, \"height\": 821, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kwgja9zo3m/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1356, \"height\": 720, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwgja9zo3m/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 349, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwgja9zo3m/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 121, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwgja9zo3m/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwgja9zo3m/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1440, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwgja9zo3m/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1303, \"height\": 511, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwgja9zo3m/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1224, \"height\": 529, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwgja9zo3m/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1445, \"height\": 463, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwgja9zo3m/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 401, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwgja9zo3m/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1441, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwgja9zo3m/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 873, \"height\": 118, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwgja9zo3m/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1297, \"height\": 669, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwgja9zo3m/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 876, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwgja9zo3m/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1157, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwgja9zo3m/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1443, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwgja9zo3m/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1034, \"height\": 374, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kwgja9zo3m/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1440, \"height\": 245, \"label\": \"Table\"}]"
motivation: 现有模型难以有效融合音频信息，限制了视频时间理解的全面性。
method: 设计查询式连接器（Query-Based Connector）将视觉、音频和语音特征对齐后输入LLM。
result: 在多个视频理解基准上取得最优结果，特别是涉及音频和语音的场景。
conclusion: 融合音频模态显著提升了视频时间理解能力，多模态LLM是该方向的有力工具。
---

## Abstract
Humans naturally understand moments in a video by integrating visual and auditory cues. For example, localizing a scene in the video like “A scientist passionately speaks on wildlife conservation as dramatic orchestral music plays, with the audience nodding and applauding” requires simultaneous processing of visual, audio, and speech signals. However, existing models often struggle to effectively fuse and interpret audio information, limiting their capacity for comprehensive video temporal understanding. To address this, we present TriSense, a triple-modality large language model designed for holistic video temporal understanding through the integration of visual, audio, and speech modalities. Central to TriSense is a Query-Based Connector that adaptively reweights modality contributions based on the input query, enabling robust performance under modality dropout and allowing flexible combinations of available inputs. To support TriSense's multimodal capabilities, we introduce TriSense-2M, a high-quality dataset of over 2 million curated samples generated via an automated pipeline powered by fine-tuned LLMs. TriSense-2M includes long-form videos and diverse modality combinations, facilitating broad generalization. Extensive experiments across multiple benchmarks demonstrate the effectiveness of TriSense and its potential to advance multimodal video analysis.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义

- **研究动机**：人类对视频事件的理解天然是多模态的（视觉、听觉、语音），但现有多模态大语言模型（MLLMs）往往只依赖视觉输入，难以有效融合和解读音频信息，导致在需要整合音频和语音的任务上表现不佳，尤其是在部分模态缺失或噪声干扰的真实场景中。
- **核心挑战**：
  - 缺乏大规模、高质量、覆盖视觉-音频-语音三模态且支持任意组合的标注数据集。
  - 现有模型缺乏根据查询内容动态调整各模态重要性的适应能力，在模态不完整时性能不稳定。
- **整体目标**：提出一个能够同时“看和听”的三模态大语言模型，实现全面的视频时间理解，包括片段描述和时刻检索。

## 2. 方法论

### 核心思想
- 提出 **TriSense**，一个融合视觉、音频和语音的三模态大语言模型。
- 核心组件为 **Query-Based Connector**，根据查询内容自适应地加权各模态贡献，从而在模态缺失时仍保持鲁棒性，并支持灵活组合。

### 关键技术细节
1. **多模态信息提取**：
   - 从视频中均匀采样64帧，每帧提取2秒音频段。
   - 使用预训练专家编码器：视觉用CLIP ViT-L/14-336，音频用BEATs_iter3+，语音用Whisper-large-v3。
   - 每个模态特征经Slot-Based压缩为固定16个token，并用Time Encoder编码时间戳（如“123.4”被token化为6个token）。

2. **Query-Based Connector**：
   - 将压缩后的模态特征通过Cross-Attention与文本查询交互，得到查询相关特征。
   - 对各模态进行全局平均池化，拼接后通过单层MLP生成未归一化权重，经softmax归一化为概率分布（和为1）。
   - 将加权后的特征拼接、再经Slot压缩和两层MLP，生成融合多模态表示。

3. **因果事件预测**：
   - 将视频分割成事件序列，模型基于先前事件、查询和融合特征预测下一个事件（时间戳+描述）。
   - 使用特殊`<sync>` token控制输出头在时间头（预测时间戳）和语言模型头（生成文本）之间切换。

### 训练流程（三阶段）
- **Stage 1（特征对齐）**：仅训练Query-Based Connector和LM Head，使用单模态数据，冻结其他部分。
- **Stage 2（连接器泛化）**：加入混合模态数据，训练Connector、Time Encoder、Time Head和LM Head，LLM backbone冻结。
- **Stage 3（指令微调）**：冻结Connector，训练Time Encoder、Time Head、LM Head和LLM backbone。

## 3. 实验设计

### 使用的数据集
- **TriSense-2M**（新构建）：200万样本，来自38,000个长视频，平均时长905秒，包含视觉、音频、语音三模态及其组合（AVS、VS、AV、V），支持模态缺失。
- **公共基准**：Charades-STA、ActivityNet-Captions、LongVALE数据集。

### 评测任务与指标
- **片段描述（Segment Captioning）**：BLEU-4、METEOR、ROUGE-L、CIDEr。
- **时刻检索（Moment Retrieval）**：Recall@IoU=0.5、Recall@IoU=0.7、mIoU。
- 覆盖四种模态配置：AVS、VS、AV、V。

### 对比方法
- 视频时间理解模型：VTimeLLM、TimeChat、VTG-LLM、TRACE、TRACE-uni。
- 全模态模型：LongVALE、Qwen2.5-Omni。
- 零样本对比还包括Momentor、HawkEye、NumPro-FT等（按官方报告引用）。

### 实验设置
- 在TriSense-2M测试集（11,415个样本）上进行测试，与基线在相同子集上对比。
- 零样本在Charades-STA和ActivityNet-Captions上测试（64帧输入），而某些基线使用更多帧（如TRACE用128帧）。
- 消融实验：训练阶段（Stage1 vs Stage1+2）、连接器设计（加法融合 vs 固定权重 vs 自适应）、帧数（32/64/128）。

## 4. 资源与算力

| 阶段 | GPU型号与数量 | 训练时长 |
|------|--------------|----------|
| Stage 1 | 4×A100 SXM4 80GB | 10小时 |
| Stage 2 | 16×A100 SXM4 80GB | 约3.5天 |
| Stage 3 | 16×A100 SXM4 80GB | 约5.5天（正文写7天，附录写5.5天，以附录为准） |
- 采用DeepSpeed ZeRO2（因BEATs模型不支持Zero3）。
- 总计约10,000 A100 GPU小时以上的计算资源。

## 5. 实验数量与充分性

- **主要实验**：在TriSense-2M上完成片段描述和时刻检索两大类任务，各4种模态组合，共8个实验。
- **零样本实验**：在2个公共基准（Charades-STA、ActivityNet-Captions）上测试时刻检索，共6个指标。
- **全模态零样本**：在LongVALE数据集上测试AVS-MR和AVS-SC。
- **消融实验**：
  - 训练阶段：Stage1 vs Stage1+2（2组）
  - 连接器设计：加法、固定权重、自适应（3组对比）
  - 帧数：32/64/128（3组）
  - 分支消融：V-Only、VS-Only、AV-Only、AVS-Full（4组）
  - 槽压缩数量：8/16/32/64（4组）
  - 任务头：统一头 vs 时间头+LM头（2组）
  - 此外还有在20K小样本上的额外消融。
- **通用理解评估**：在Video-MME上测试零样本整体得分。
- **充分性评价**：实验设计全面，覆盖了多种模态组合、多种任务、多种消融维度，对比了当前主流基线，结果统计充分。但未提供误差条或置信区间（因大规模实验资源限制），但已足够支持主要结论。

## 6. 论文的主要结论与发现

1. **TriSense在几乎所有全模态任务上显著优于现有方法**，尤其在AVS（音频-视觉-语音）配置下提升最大（片段描述CIDEr达8.3，时刻检索R@0.5达1.12，远超第二名0.61）。
2. **Query-Based Connector自适应加权有效**：相比固定权重或简单加法，动态权重在AVS/VS/AV任务上均提升性能（如AVS-MR R@0.5从0.71提升至1.12）。
3. **三阶段训练策略关键**：Stage1对齐+Stage2泛化+Stage3微调逐步提升，仅Stage1+2即可获得约50%能力。
4. **更多帧数带来更好性能**：从32帧到64帧再到128帧，各项指标持续提升（但收益递减）。
5. **全模态模型在视觉-only场景仍具竞争力**：在Charades-STA和ActivityNet-Captions上零样本取得与专用视觉模型相当甚至更好的结果（尤其在IoU=0.7上领先）。
6. **高质量长视频数据集TriSense-2M有效支撑长时时间理解**：平均905秒，远长于现有数据集（LongVALE 235秒）。

## 7. 优点

- **模态适应性融合**：Query-Based Connector可根据查询内容动态调整各模态权重，对模态缺失鲁棒，可处理任意组合（V/AV/VS/AVS）。
- **大规模高质量数据集**：TriSense-2M含200万样本，覆盖多样场景和时长，通过LLM自动生成和人工筛选确保质量。
- **统一框架支持多任务**：同一模型同时处理片段描述和时刻检索，通过`<sync>`令牌实现输出切换。
- **高效的Slot压缩**：将每模态特征压缩为16 token，控制LLM输入长度。
- **全面实验验证**：在多个基准、多种模态组合、零样本设置下与多个SOTA对比，消融实验详实。
- **开源承诺**：代码和数据集将在接受后公开，推动领域研究。

## 8. 不足与局限

- **视觉-only场景表现略逊于专用模型**：在TriSense-2M的V-only时刻检索上，TriSense (R@0.5=0.43) 低于TRACE-uni (0.48)，可能因模型优化偏向多模态。
- **帧数限制**：推理时仅使用64帧（远少于TRACE的128帧），在长视频中可能遗漏细节，增加帧数可提升但导致计算成本上升。
- **依赖特定LLM初始化**：基于TRACE（Mistral-7B）初始化，可能限制了LLM backbone的通用性，更换其他LLM需重新训练。
- **计算资源需求大**：三阶段训练需16×A100，总时数百小时，小型团队难以复现。
- **无不确定估计**：实验结果未提供标准误差或置信区间，统计显著性未严格验证。
- **数据集偏差**：TriSense-2M来自InternVid和VAST，可能存在场景分布偏差；自动生成+人工筛选虽质量高但可能引入标注风格模式。
- **仅支持英文**：数据集和模型目前仅针对英文语音和文本。

（完）
