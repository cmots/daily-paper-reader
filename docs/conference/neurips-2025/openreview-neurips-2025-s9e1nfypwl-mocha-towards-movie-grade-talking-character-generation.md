---
title: "MoCha: Towards Movie-Grade Talking Character Generation"
title_zh: MoCha：迈向电影级说话角色生成
authors: "Cong Wei, Bo Sun, Haoyu Ma, Ji Hou, Felix Juefei-Xu, Zecheng He, Xiaoliang Dai, Luxin Zhang, Kunpeng Li, Tingbo Hou, Animesh Sinha, Peter Vajda, Wenhu Chen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=S9E1nfYPwl"
tags: ["query:speech-model"]
score: 4.0
evidence: 语音驱动从语音和文本生成说话角色动画
tldr: 针对现有视频生成在角色驱动叙事方面的不足，提出MoCha模型，它能够直接从语音和文本生成说话角色的全肖像动画。模型通过局部音频注意力机制精确同步语音与视频，并利用数据增强克服标注数据稀缺问题。实验表明，MoCha在同步质量和视觉真实感上显著优于基线方法，为电影级自动动画生成奠定了基础。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 1071, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1014, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 610, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1450, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 873, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1444, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1436, \"height\": 658, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1395, \"height\": 1120, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1327, \"height\": 628, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1331, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1429, \"height\": 172, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1431, \"height\": 174, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-s9e1nfypwl/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1436, \"height\": 172, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-s9e1nfypwl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 702, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-s9e1nfypwl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 661, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-s9e1nfypwl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 708, \"height\": 221, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-s9e1nfypwl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1279, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-s9e1nfypwl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1452, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-s9e1nfypwl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1452, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-s9e1nfypwl/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1393, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-s9e1nfypwl/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1454, \"height\": 121, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-s9e1nfypwl/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1445, \"height\": 297, \"label\": \"Table\"}]"
motivation: 现有视频生成缺乏角色驱动叙事，无法直接从语音生成全肖像动画。
method: 提出MoCha，首个完整说话角色生成模型，使用局部音频注意力机制对齐语音与视频令牌。
result: 在多项指标上展现了精确的语音-视频同步和高质量动画生成。
conclusion: 为自动化电影和动画中的角色驱动内容生成提供了新范式。
---

## Abstract
Recent advancements in video generation have achieved impressive motion realism, yet they often overlook character-driven storytelling, a crucial task for automated film, animation generation. 
We introduce Talking Characters, a more realistic task to generate talking character animations directly from speech and text. Unlike talking head tasks, Talking Characters aims at generating the full portrait of one or more characters beyond the facial region. 
In this paper, we propose MoCha, the first of its kind to generate talking characters. To ensure precise synchronization between video and speech, we propose a localized audio attention mechanism that effectively aligns speech and video tokens.
To address the scarcity of large-scale speech-labelled video datasets, we introduce a joint training strategy that leverages both speech-labelled and text-labelled video data, significantly improving generalization across diverse character actions. We also design structured prompt templates with character tags, enabling, for the first time, multi-character conversation with turn-based dialogue—allowing AI-generated characters to engage in context-aware conversations with cinematic coherence.
Extensive qualitative and quantitative evaluations, including human evaluation studies and benchmark comparisons, demonstrate that MoCha sets a new standard for AI-generated cinematic storytelling, achieving superior realism, controllability and generalization.

---

## 论文详细总结（自动生成）

# MoCha: Towards Movie-Grade Talking Character Generation — 中文详细总结

## 1. 论文的核心问题与整体含义

- **研究动机**：现有视频生成模型（如Sora、Pika等）主要面向叙事性、非对话场景，生成的角色嘴唇动作任意、面部表情与语音内容脱节，缺乏对话叙事能力。而传统的“说话头”生成局限于裁剪的面部区域、静态相机，无法表现全身动作、动态镜头和多角色交互。
- **核心问题**：如何直接从**语音和文本**生成电影级别的、具有完整身体动作和表情的“说话角色”动画，实现自动化对话驱动的电影制作。
- **整体含义**：本文提出新任务 **Talking Characters**，定义为从自然语言和语音输入生成逼真的数字角色，要求同步的唇部动作、真实情感、全身动作和动态镜头。该方法有望民主化电影级叙事内容的生成。

## 2. 论文提出的方法论

### 核心思想
MoCha是第一个基于**扩散变换器**（DiT）的端到端说话角色生成模型，仅使用文本和语音作为条件，**无需任何辅助控制信号**（如参考图像、姿态骨架、面部关键点）。

### 关键技术与公式

1. **局部音频注意力机制**：
   - 问题：DiT使用3D VAE对视频进行时间压缩（压缩因子r=4），导致视频令牌（τ帧）与原始音频令牌（T帧）时间分辨率不匹配；且DiT并行解码，全局注意力会造成错误关联。
   - 方案：对于第i个潜在视频帧，将其跨注意力限制在音频窗口 `j ∈ [max(1, (i-1)r-1), min(T, ir+1)]`，即仅关注其对应原始时间段附近（宽度为r+2）的音频令牌，实现局部对齐。

2. **课程式多模态训练策略**：
   - 混合模态采样：80%多模态（语音+文本） + 20%单模态（仅文本，将语音嵌入置零），兼顾音视频对齐与视觉多样性。
   - 基于镜头类型渐进训练：
     - 阶段0：在纯文本视频数据上预训练（建立视觉先验）。
     - 阶段1-4：从特写镜头（高音视频相关）开始，逐步引入中近景、中景、多角色/多片段场景。每阶段降低简单样本比例，保持多模态/单模态比例（80%/20%）。

3. **结构化提示模板（角色标签）**：
   - 格式：开头定义“Characters: Person1: … Person2: …”，后续片段描述仅使用标签（如Person1、Person2），减少冗余、避免混淆，支持多角色轮流对话。模型通过自注意力在视频令牌间保持角色和环境一致性。

### 模型架构
- 30B参数DiT骨干（基于MovieGen），包含48层、模型维度6144、FFN大小16384。
- 文本编码器：UL2 + ByT5 + MetaCLIP，输出拼接后经线性投影输入。
- 音频编码器：Wav2Vec2提取所有12层嵌入并拼接，通过线性插值与视频帧对齐，再经MLP投影到模型维度。每个帧的音频令牌包含前后5帧上下文。
- 训练目标：流匹配损失（Flow Matching），预测速度 `v_t = x_1 - ε`。

## 3. 实验设计

### 数据集与 Benchmark
- **训练数据**：
  - 约1亿条文本标注视频（大规模）。
  - 约80万条语音标注视频（经四阶段数据清洗：场景分割、突出角色过滤、动作/唇同步验证、结构化字幕生成）。
- **评估**：自建 **MoCha-Bench**（200个样本，涵盖多种镜头类型、情感、方向、动作），每个样本包含文本提示和对应音频。

### 对比方法
- SadTalker、AniPortrait（2D/3D人脸动画）、Hallo3（基于扩散的说话头）。这些方法均需参考图像等辅助输入，实验中统一使用MoCha生成视频的第一帧作为参考，并裁剪至头部区域以公平比较。

### 评估指标
- **自动指标**：Sync-C（越高越好）、Sync-D（越低越好），衡量唇同步质量。
- **人工评估**：5个维度（唇同步质量、面部表情自然度、动作自然度、文本对齐、视觉质量），评分1-4，每个模型得到超过1000份人工评分。

## 4. 资源与算力

- **模型规模**：MoCha-30B（30B参数DiT骨干，不含编码器和VAE）。
- **训练配置**：基于MovieGen预训练骨干；共4个训练阶段（不含阶段0预训练），总计700K迭代。
- **计算资源**：
  - 阶段0：1024 GPUs，全局batch size 512。
  - 阶段1-4：512 GPUs，全局batch size 512。
  - 训练分布式在64个计算节点上；所有输入调整至约720px分辨率（保留宽高比）。
  - 文中未明确GPU型号（如A100/H100），仅说明“64 compute nodes”。

## 5. 实验数量与充分性

- 进行了**多组实验**：
  - 定量对比：Sync-C/Sync-D自动指标（见表2）。
  - 人工评估：5维度评分，模型间差异显著（图7/表7）。
  - 消融实验：
    - 局部音频注意力机制（表3、表4详列多种注意力变体，如朴素注意力、可学习位置编码、正弦/RoPE等，共6种对比）。
    - 课程训练策略（表5，对比无课程训练、无混合多模态训练）。
    - 角色标签策略（表6，在轮流对话子集上对比）。
  - 定性示例：多组可视化比较（图8、图10、图11）。
- **充分性**：实验设计较全面，在多维度验证了各组件贡献。但未报告自动指标的置信区间或显著性检验；人工评估虽样本量大，但可能受标注者主观因素影响。总体客观且公平（基准方法均以统一方式适配）。

## 6. 论文的主要结论与发现

- MoCha在**所有评估维度**上显著优于现有说话头方法（SadTalker、AniPortrait、Hallo3），平均人工评分接近4分（近乎影院级）。
- **局部音频注意力机制**是唇同步的关键：去除该机制导致Sync-C下降19%，Sync-D上升8%（表3）。
- **课程式多模态训练**显著提升泛化能力：缺少课程训练或仅依赖语音数据时，文本对齐和动作自然度大幅下降。
- **角色标签提示**对多角色轮流对话至关重要：无标签时文本对齐评分从3.81骤降至2.01。
- 强音视频对齐可**完全通过端到端训练从语音信号中涌现**，无需辅助监督信号。

## 7. 优点

- **端到端设计**：无需参考图像、姿态、关键点等辅助信号，简化流程，提升灵活性和泛化能力。
- **局部音频注意力创新**：针对DiT时间压缩特性，设计窗口约束注意力，高效解决唇同步难题。
- **课程训练策略**：巧妙结合稀缺的语音标注数据和丰富文本数据，渐进增加任务难度，提升收敛速度和通用性。
- **结构化提示模板**：利用角色标签实现紧凑、一致的多角色多片段提示，首次支持上下文感知的轮流对话。
- **全面实验验证**：从自动指标、人工评估、消融到定性示例，多角度证实方法有效性。

## 8. 不足与局限

- **广角/极广角镜头唇同步失败**：当提示模糊导致生成广角镜头，角色面部过小，模型无法准确唇同步。
- **同画面多角色混淆**：当多个角色同时出现在一个镜头中，模型可能错误指定说话角色，影响唇同步质量（推测因训练数据中此类样本稀缺）。
- **高音频CFG导致过度表情**：增大语音引导权重时可能产生不自然夸张动作，降低真实感。
- **计算资源需求高**：30B参数模型需要大量GPU训练，不利于小规模复现。
- **合成媒体风险**：虽不从真实身份输入生成，但音频驱动可能被用于误导性内容。论文建议配合水印和检测工具，但未提供具体技术方案。
- **偏差与公平性**：模型可能反映训练数据中的偏见，需注意文化、性别、种族多样性。

（完）
