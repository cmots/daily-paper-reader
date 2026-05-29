---
title: Generative Audio Language Modeling with Continuous-valued Tokens and Masked Next-Token Prediction
title_zh: 基于连续值token和掩码下一token预测的生成式音频语言建模
authors: "Shu-wen Yang, Byeonggeun Kim, Kuan-Po Huang, Qingming Tang, HUY PHAN, Bo-Ru Lu, Harshavardhan Sundar, Shalini Ghosh, Hung-yi Lee, Chieh-Chi Kao, Chao Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=SvrLHOF0V5"
tags: ["query:speech-model"]
score: 8.0
evidence: 连续值token生成音频语言模型，可应用于表现力语音合成
tldr: "针对连续音频生成的挑战，该论文提出使用连续值token的因果语言模型，结合token-wise扩散来建模下一个token的连续分布。在AudioCaps数据集上，该方法相比离散方案AudioGen在FAD和KL上分别获得20%和40%的相对提升。这为高质量音频（包括语音）生成提供了新范式。"
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-svrlhof0v5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 802, \"height\": 694, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-svrlhof0v5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 824, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-svrlhof0v5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 840, \"height\": 602, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-svrlhof0v5/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1666, \"height\": 660, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-svrlhof0v5/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1060, \"height\": 580, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-svrlhof0v5/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1250, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-svrlhof0v5/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 810, \"height\": 669, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-svrlhof0v5/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1701, \"height\": 326, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-svrlhof0v5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1768, \"height\": 818, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-svrlhof0v5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 863, \"height\": 398, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-svrlhof0v5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1768, \"height\": 632, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-svrlhof0v5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 856, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-svrlhof0v5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 856, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-svrlhof0v5/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 855, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-svrlhof0v5/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1768, \"height\": 957, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-svrlhof0v5/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 797, \"height\": 231, \"label\": \"Table\"}]"
motivation: 现有音频生成方法使用离散token，限制了模型对连续音频的精细建模能力。
method: 提出连续值token语言模型，采用token-wise扩散在自回归框架中逐token生成连续音频。
result: "在AudioCaps上，FAD和KL指标相比AudioGen提升20%和40%，展示了连续token的优势。"
conclusion: 连续值token结合扩散模型为音频生成提供了更高质量和灵活性的方案。
---

## Abstract
Autoregressive next-token prediction with the Transformer decoder has become a de facto standard in large language models (LLMs), achieving remarkable success in Natural Language Processing (NLP) at scale. Extending this paradigm to audio poses unique challenges due to its inherently continuous nature. We research audio generation with a causal language model (LM) without discrete tokens. We leverage token-wise diffusion to model the continuous distribution of the next continuous-valued token. Our approach delivers significant improvements over previous discrete solution, AudioGen, achieving 20% and 40% relative gains on AudioCaps in Frechet Audio Distance (FAD) and Kullback-Leibler (KL) divergence, respectively. Additionally, we propose a novel masked next-token prediction task that incorporates masked prediction into the causal LM framework. On AudioCaps, the innovation yields 41% and 33% relative FAD improvements over AudioGen Base (285M) and AudioGen Large (1B) models, respectively, and is on par with the state-of-the-art (SOTA) diffusion models. Furthermore, we achieve these results with significantly fewer parameters—193M for our Base and 462M for our Large models.

---

## 论文详细总结（自动生成）

# 基于连续值token和掩码下一token预测的生成式音频语言建模——论文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：大型语言模型（LLM）中的自回归下一token预测在NLP领域取得了巨大成功，但将其直接扩展到音频生成面临本质挑战——音频数据是**连续的**，而传统方法依赖离散token（如AudioGen、UniAudio），这导致信息损失和生成质量瓶颈。
- **背景**：现有文本到音频（TTA）系统主要有两类：
  - **基于离散token的因果语言模型**（如AudioGen）：使用矢量量化音频token和交叉熵损失，但生成质量落后于扩散方法。
  - **基于连续潜变量的扩散模型**（如AudioLDM 2、Tango 2）：通过双向扩散过程建模联合概率分布，性能领先但牺牲了LLM的因果性、流式能力和基础设施优势。
- **核心目标**：**在保持因果语言模型架构的前提下，实现与SOTA扩散模型相匹敌的音频生成质量**，从而将LLM扩展至音频模态。

## 2. 论文提出的方法论：核心思想、关键技术细节

### (1) AudioNTP：连续值token + token-wise扩散损失
- **核心思想**：用**连续值token**代替离散token，通过**token-wise扩散损失**（来自MAR）替代交叉熵损失，使标准Transformer decoder能直接建模连续下一token分布。
- **关键技术**：
  - 使用预训练的VAE将Mel谱图编码为低维连续潜变量序列（256个token/10秒音频），每个token维度为128。
  - Transformer decoder编码当前上下文（文本嵌入 + BOS + 已生成token），输出上下文向量z_i。
  - 一个小型MLP扩散头以z_i为条件，通过去噪扩散概率模型（DDPM）建模p(x_i | z_i)，损失函数为噪声预测MSE。
  - 推理时，逐位置运行反向扩散过程（100步）采样token，再经VAE解码器和HiFi-GAN声码器合成波形。

### (2) AudioMNTP：掩码下一token预测（MNTP）
- **核心思想**：将掩码语言建模（MLM）的核心思想——**从稀疏上下文中预测未见过token**——迁移至因果LM，提出**MNTP**。
- **关键创新**：
  - **训练时**：随机丢弃（drop）一定比例的token，形成更短的序列，然后在该短序列上执行**标准下一token预测**。但每个位置预测的目标是**原始序列中该位置之后某个随机位置的token**（即跳过中间token），而不是紧邻的下一个token。为此引入**目标位置嵌入（target positional embedding）**，将其与内容位置嵌入一起输入模型，让模型知道要预测哪个未来位置。
  - **掩码策略**：混合正态分布（侧重高掩码率）和截断正态分布（侧重低掩码率），使模型既能学习高掩码率的MLM-like任务，又能保留标准下一token预测的情况。
  - **推理时**：与AudioNTP完全一致，仅需将目标位置嵌入设为当前内容位置+1，即恢复标准下一token预测。

### (3) 模型结构
- 基于MAR的Transformer decoder（Base: 24层, 768维；Large: 32层, 1024维）。
- 文本条件：拼接CLAP和FLAN-T5的文本嵌入（共78个token）作为输入前缀。
- 初始化：默认使用Image MAR预训练权重（消融显示非必需）。

## 3. 实验设计

### 数据集
- **训练**：AudioCaps（约50k对） + WavCaps（约400k对），总计约1000小时音频。所有音频裁剪/填充至10秒。
- **评测**：AudioCaps测试集（遵循AudioLDM评估协议）。

### Benchmark与对比方法
- 对比范围广泛，包括：
  - **离散因果LM**：AudioGen Base (285M)、AudioGen Large (1B)、UniAudio (1B)。
  - **离散双向模型**：MAGNet Small (300M)、MAGNet Large (1.5B)。
  - **连续双向扩散模型**：Tango (866M)、Tango 2 (866M)、Make-An-Audio 2 (937M)、AudioLDM 2 (346M/712M)。
- **评估指标**：FAD ↓、FD ↓、KL ↓、IS ↑、CLAP ↑，以及人工评价（REL和OVL，分语音/非语音）。

## 4. 资源与算力

- **训练配置**：
  - Base模型：40块 NVIDIA V100 GPU，有效batch size 2048个10秒片段，训练1000 epochs（约2天）。
  - Large模型：104块 GPU，同样1000 epochs（约5天）。
- 论文未明确说明使用的具体GPU显存型号（V100通常32GB），但提供了清晰的训练时长和卡数。

## 5. 实验数量与充分性

### 实验数量
- 主表（Table 1）比较12个现有方法与3个本文方法，涵盖5个客观指标。
- 人工评价（Table 2）对比4种方法，分语音/非语音两类别。
- 消融实验（Table 3）包含10个变体（A-K），系统性地分析了：
  - 初始化（Image MAR vs Audio MAR vs 随机）
  - 掩码类型（零掩码、高斯掩码、drop token）
  - 掩码调度（MAR调度、均匀分布、混合调度）
  - 是否预测跳过token、是否使用目标位置嵌入
  - MNTP vs 纯NTP vs 双向MAR
- 其他消融：
  - MLP扩散头大小（Table 4）
  - 文本嵌入组合（Table 5）
  - 不同解码方式（随机顺序 vs 因果顺序，Table 6）
  - CFG引导和温度的影响（Figure 5）
  - 掩码调度拆解（Table 8）

### 充分性和公平性
- **充分性**：实验覆盖了方法的核心组件、超参数、初始化影响、与多种基线对比，消融设计细致。
- **客观性**：所有客观指标使用统一评估工具（AudioLDM评估工具包），人工评价有至少10名参与者，分两类评测。
- **局限**：
  - 训练数据仅用AudioCaps和WavCaps，比AudioGen等使用的（超过10个数据集）少很多，但论文将其作为**数据效率**的优点。
  - 未报告流式推理的实际延迟等工程指标。
  - 与双向模型对比时，仅使用因果解码比较（Table 6），但MAR原始使用随机顺序解码，论文也对比了该设置。

## 6. 论文的主要结论与发现

1. **连续值token显著优于离散token**：193M AudioNTP Base在FAD和KL上分别比285M AudioGen Base相对提升20%和40%。
2. **MNTP进一步提升性能**：AudioMNTP Base相比AudioNTP Base在FAD上相对提升26%，在CLAP上提升9%。
3. **AudioMNTP Large达到SOTA**：462M模型在FAD和FD上超过所有现有方法（包括866M/937M扩散模型），在KL、IS、CLAP上接近最佳。
4. **因果LM可媲美双向模型**：在因果解码场景下，AudioMNTP甚至优于AudioMAR（双向模型使用因果解码），证实MNTP对因果LM的增强效果。
5. **模型和数据效率高**：使用更少参数、更小数据集达到优秀结果。

## 7. 优点

- **方法创新**：
  - 首次在因果LM框架中系统验证连续值token的音频生成优势。
  - 提出MNTP，巧妙地将MLM的思想融入因果LM，且不牺牲因果性（推理时无额外计算）。
  - 引入目标位置嵌入，使模型能灵活预测任意未来位置，并统一了NTP和MNTP框架。
- **实验设计**：
  - 消融实验全面，清晰验证每个组件的必要性（如drop token比zero mask好、目标位置嵌入至关重要）。
  - 主客观结合，且分语音/非语音，细致评估。
  - 与多个公开SOTA公平对比（使用统一评估工具）。
- **性能与效率**：以较小模型和较少数据达到接近或超越大模型的效果，体现方法的有效性。

## 8. 不足与局限

- **实验覆盖范围**：
  - 未在更大规模数据集（如AudioSet全部）上验证，也未展示众包或真实场景的用户实验。
  - 未提供流式推理的延迟、内存占用等工程指标，虽提及KV-cache等基础设施可复用。
  - 缺少对音乐、语音合成等具体领域（如MusicLM风格）的评测，仅TTA通用场景。
- **偏差风险**：
  - 评估指标（FAD、KL等）依赖特定特征网络（如PANNs），可能存在偏置。
  - 人工评价样本量（20个样本，每样本至少10人）中等，未见跨语言或鲁棒性测试。
- **应用限制**：
  - 推理仍需100步扩散采样，速度比标准自回归一步解码慢（论文报告约3.9秒/10秒音频在V100上）。
  - 模型依赖VAE和HiFi-GAN预训练组件的质量，组件误差可能传播。
  - 未讨论文本与音频的对齐控制（如长句子、罕见事件生成能力）。
- **理论分析缺失**：MNTP为何比NTP更好？论文仅给出直觉（避免局部平滑、促进稀疏上下文学习），缺少严格证明或深入分析。

（完）
