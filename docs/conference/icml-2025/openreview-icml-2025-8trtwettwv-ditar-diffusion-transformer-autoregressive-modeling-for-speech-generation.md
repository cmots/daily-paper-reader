---
title: "DiTAR: Diffusion Transformer Autoregressive Modeling for Speech Generation"
title_zh: DiTAR：用于语音生成的扩散Transformer自回归建模
authors: "Dongya Jia, Zhuo Chen, Jiawei Chen, Chenpeng Du, Jian Wu, Jian Cong, Xiaobin Zhuang, Chumin Li, Zhen Wei, Yuping Wang, Yuxuan Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=8tRtweTTwv"
tags: ["query:speech-model"]
score: 7.0
evidence: 扩散Transformer自回归建模用于语音生成
tldr: 针对连续语音表示自回归生成计算量大的问题，本文提出DiTAR，采用分治策略：语言模型处理聚合的块嵌入，扩散变换器生成细节。该方法在保证生成质量的同时降低了计算需求。在多个数据集上的实验表明DiTAR优于基线。为连续语音生成提供了高效且高质量的自回归建模方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-8trtwettwv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1749, \"height\": 759, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8trtwettwv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 860, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8trtwettwv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8trtwettwv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 859, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8trtwettwv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 790, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8trtwettwv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 859, \"height\": 252, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8trtwettwv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1761, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8trtwettwv/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1684, \"height\": 1157, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8trtwettwv/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 845, \"height\": 280, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8trtwettwv/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 838, \"height\": 254, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-8trtwettwv/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 647, \"height\": 416, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-8trtwettwv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1751, \"height\": 696, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-8trtwettwv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 797, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-8trtwettwv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 885, \"height\": 466, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-8trtwettwv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 766, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-8trtwettwv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 906, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-8trtwettwv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 787, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-8trtwettwv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 632, \"height\": 442, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-8trtwettwv/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1184, \"height\": 640, \"label\": \"Table\"}]"
motivation: 现有结合扩散和自回归模型的连续语音生成方法计算量大且效果欠佳。
method: 提出基于块的自回归框架，语言模型+扩散变换器分步生成。
result: 在多个数据集上的实验表明DiTAR在生成质量和效率上均优于基线。
conclusion: 为连续语音生成提供了高效且高质量的自回归建模方案。
---

## Abstract
Several recent studies have attempted to autoregressively generate continuous speech representations without discrete speech tokens by combining diffusion and autoregressive models, yet they often face challenges with excessive computational loads or suboptimal outcomes.
In this work, we propose Diffusion Transformer Autoregressive Modeling (DiTAR), a patch-based autoregressive framework combining a language model with a diffusion transformer. This approach significantly enhances the efficacy of autoregressive models for continuous tokens and reduces computational demands.
DiTAR utilizes a divide-and-conquer strategy for patch generation, where the language model processes aggregated patch embeddings, and the diffusion transformer subsequently generates the next patch based on the output of the language model.
For inference, we propose defining temperature as the time point of introducing noise during the reverse diffusion ODE to balance diversity and determinism. We also show in the extensive scaling analysis that DiTAR has superb scalability. In zero-shot speech generation, DiTAR achieves state-of-the-art performance in robustness, speaker similarity, and naturalness.

---

## 论文详细总结（自动生成）

# DiTAR：扩散Transformer自回归建模用于语音生成——论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究背景**：自回归语言模型在文本生成中表现出色，但离散化 token 难以高质量重建语音等连续模态。现有方法常采用两阶段策略（先离散 token，再扩散细化），但存在误差累积和可扩展性受限问题。
- **核心问题**：如何高效、高质量地直接对连续语音表示进行自回归建模？此前尝试将扩散头接入语言模型（如 MAR）性能不足，而将语言模型参数全部用于扩散（如 ARDiT/Transfusion）则计算负担过重。
- **意义**：DiTAR 提出一种分治方案，在保持各自优势的同时显著降低计算量，并在零样本语音合成任务上达到 SOTA，为连续表示的自回归生成提供了高效、可扩展的新范式。

## 2. 方法论：核心思想、关键技术细节

### 2.1 核心思想：分治策略（Divide-and-Conquer）
- 将连续 token 序列划分为 **patch**（块），每个 patch 包含 P 个连续 token。
- 因果语言模型负责**跨 patch 预测**（inter-patch），聚合每个 patch 为单个向量后输入 LM。
- 双向扩散 Transformer（LocDiT）负责**块内预测**（intra-patch），根据 LM 输出生成下一个 patch 的所有 token。

### 2.2 关键技术细节

#### 2.2.1 架构组成（图1）
- **聚合编码器**：对每个 patch 的 token 序列（加上一个特殊 token）使用双向 Transformer 编码，取特殊 token 对应输出作为 patch 的聚合表示。
- **语言模型（LM）**：因果 Transformer，以聚合后的 patch 序列为输入，输出条件向量 \(h_i\)。
- **局部扩散 Transformer（LocDiT）**：以 \(h_i\) 为条件，同时注入历史 patch（作为上下文），采用双向注意力，预测当前 patch 的连续 token。训练时使用扩散损失（条件流匹配）。

#### 2.2.2 扩散公式与损失
- 采用方差保持扩散过程：\(x_t = \cos(\frac{\pi t}{2}) x_0 + \sin(\frac{\pi t}{2}) \varepsilon\)，\(t\in[0,1]\)。
- 训练损失为条件流匹配损失：\(\mathbb{E}_{t,x_0,\varepsilon} \| v_\theta(x_t,t) - (\dot{\alpha}_t x_0 + \dot{\sigma}_t \varepsilon) \|^2\)。
- 推理时使用 DDIM ODE 求解器（Euler 方法在信噪比空间）。

#### 2.2.3 推理温度定义（新方法）
- 传统扩散中的温度（噪声缩放）不适用于快速 ODE 求解器。
- 本文将温度 \(\tau \in [0,1]\) 定义为**在逆向 ODE 求解过程中引入噪声的时间点**：
  - \(\tau=1\)：从标准高斯噪声开始，完全随机。
  - \(\tau=0\)：从全零向量开始，完全确定。
  - \(0<\tau<1\)：在时刻 \(\tau\) 使用前向过程对当前估计的 \(x_0\) 加噪，然后继续求解。
- 这使得温度可快速平衡多样性与确定性，且兼容 ODE 求解器（详见 Algorithm 1）。

#### 2.2.4 LM Guidance
- 类似分类器无导引导（CFG），但只对扩散头计算两次（条件和无条件），LM 只计算一次。
- 无条件时用零向量替换 LM 输出 \(h_i\)。
- 推理时：\(\tilde{\epsilon}_\theta(z_t, h_i) = (1+w)\epsilon_\theta(z_t, h_i) - w\epsilon_\theta(z_t, h_\emptyset)\)。

### 2.3 公式/算法流程说明（文字）
- 训练：LM 输入聚合 patch 序列，输出 \(h_i\)；LocDiT 以 \(h_i\) + 历史 patch + 加噪当前 patch 为输入，预测速度场，计算流匹配损失；同时预测停止标志（stop token）。
- 推理：从文本/语音 prompt 开始，LM 逐 patch 生成 \(h_i\)，LocDiT 通过 ODE 求解（10步）得到当前 patch 的连续 token，循环直到遇到停止标志。

## 3. 实验设计

### 3.1 数据集
- **训练**：LibriLight（60K 小时英语），Emilia（~100K 小时多语言）。
- **评估**：
  - LibriSpeech test-clean（两个子集 A 和 B）
  - Seed-EN（Common Voice 子集，2020 样本）
  - Seed-ZH（DiDiSpeech 2 子集，1088 样本）

### 3.2 评估指标
- **客观**：WER（词错误率）、SIM（声纹余弦相似度）、UTMOS（自动音质）、FLOPs（计算量）。
- **主观**：N-MOS（自然度）、Q-MOS（音质）、S-MOS（音色相似度）、CMOS（对比听感）。

### 3.3 对比方法
- 多阶段系统：VALL-E、MegaTTS 2、NaturalSpeech 2/3、Voicebox、CosyVoice 系列、FireRedTTS。
- 单阶段非自回归系统：E2TTS、F5TTS、MaskGCT。
- 闭源系统：Seed-TTS DiT（Seed-TTS 中的 DiT 变体）。
- 所有对比结果均引用原论文或使用官方 checkpoint（标注 ♦, ♣, ♠）。

## 4. 资源与算力

- **训练**：使用 16 块 A100 GPU（每 GPU batch size 15K tokens），训练 0.5M 步；1B 参数模型使用 32 块 A100 GPU（每 GPU batch size 7.5K tokens）。
- **超参数**：AdamW 优化器，恒定学习率 1e-4，\(\beta_1=0.9, \beta_2=0.99\)。
- **推理**：在单块 A100 GPU 上测量吞吐量、RTF、延迟。

## 5. 实验数量与充分性

- **总体实验数量**：论文包含超过 6 组主要实验（SOTA 性能对比 ×3 测试集、缩放行为分析、组件消融、patch 尺寸、历史 patch 数量、LM guidance 强度、温度、效率对比）。每组实验都包含多组设置（如不同 NFE、不同温度值）。
- **充分性评价**：
  - 消融实验覆盖了关键组件（patch size、历史 patches、LM guidance、温度），且给出了定量结果。
  - 缩放实验涵盖了数据量和模型大小两个维度，并单独分析了 encoder/LM/LocDiT 各自的缩放效果。
  - 对比方法全面，涵盖了当前主流的多阶段和单阶段系统，并区分了公开/闭源。
  - 主观评估邀请了 10 名英语专家进行四项 MOS 评分，但未说明主观实验的样本量和置信区间。
  - **公平性**：使用了标准化评估子集、统一 ASR 工具，但在不同数据集上使用了不同的 ASR 模型（Hubert / Whisper / Paraformer），可能引入轻微不一致。与闭源系统对比时，其结果均来自原论文，可能存在环境差异。

## 6. 主要结论与发现

- DiTAR 在零样本语音合成上实现了 **SOTA 鲁棒性（WER 最低）、声纹相似度（SIM/主观 S-MOS 最优）和自然度**，同时计算量仅约为其他 NAR 系统的 1/3~1/43。
- 缩放实验表明 DiTAR 性能随数据和模型大小持续提升，**语言模型和扩散解码器**的缩放收益最显著。
- 分治策略有效缓解了因果注意力对连续 token 建模的不足；**历史上下文**对 LocDiT 至关重要（相当于外扩修复）。
- LM guidance 大幅提升生成质量，且仅需额外计算扩散头一次。
- 温度 \(\tau\) 能有效控制多样性与确定性，且适用于快速 ODE 求解器。

## 7. 优点

### 方法层面
- **分治架构创新**：将长序列划分为补丁，因果 LM 负责全局依赖，双向 DiT 负责局部细节，兼顾可扩展性与生成质量。
- **温度新定义**：首次在连续值 LM 推理中定义温度 \(\tau\) 为噪声注入时间点，兼容快速 ODE 求解器，简单有效。
- **LM guidance**：仅增加一次扩散头计算，显著提升条件遵循能力。

### 实验层面
- **对比全面**：覆盖多种架构、多尺度模型、公开/闭源系统，且对主要组件进行了系统消融。
- **可扩展性验证**：明确展示数据量和模型大小的 scaling 曲线，证明方法在更大规模下的潜力。
- **效率分析**：给出 FLOPs、RTF、延迟、吞吐量等详细指标，综合评测性能。

## 8. 不足与局限

- **应用局限**：论文主要聚焦零样本语音合成，未验证在其他连续生成任务（如音乐、图像、视频）上的泛化能力。
- **训练数据依赖**：使用 LibriLight 和 Emilia 等公开数据集，但 LibriLight 的转录使用了内部 ASR，可能引入噪声；闭源对比系统的训练数据可能更大，比较不完全公平。
- **主观评估**：主观测试仅 10 名专家，样本量偏少，未报告置信区间或 p 值，统计显著性不足。
- **温度效应**：温度实验仅在小样本（同一文本 500 次生成）上定性可视化，未给出量化的多样性指标（如说话人 embedding 方差/熵）。
- **潜在滥用风险**：论文在 Impact Statement 中承认了语音克隆可能被恶意使用，但未讨论具体缓解措施（如水印、审查机制）。
- **推理速度**：虽然 FLOPs 远低于其他 NAR，但实际 RTF 在 batch=1 时并不占优（0.66 vs 0.037），仅在大 batch 下显著领先；作者通过调整 patch 大小可 trade-off，但未充分讨论这一权衡。
- **架构复杂度**：同时包含 LM 和 DiT，且需要聚合编码器，整体系统设计相对复杂。

（完）
