---
title: "ETTA: Elucidating the Design Space of Text-to-Audio Models"
title_zh: ETTA：阐释文本到音频模型的设计空间
authors: "Sang-gil Lee, Zhifeng Kong, Arushi Goel, Sungwon Kim, Rafael Valle, Bryan Catanzaro"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Z9BaaWDE0r"
tags: ["query:speech-model"]
score: 6.0
evidence: 文本到音频生成的设计空间探索
tldr: 该论文对文本到音频（TTA）生成模型的设计空间进行了大规模实证研究，包括数据集、模型架构、训练目标和采样策略。通过比较扩散和流匹配模型，揭示了各组件对生成质量的影响。构建了高质量合成字幕数据集AF-Synthetic，为TTA研究提供指导。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-z9baawde0r/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z9baawde0r/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 854, \"height\": 281, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z9baawde0r/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 815, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z9baawde0r/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1772, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-z9baawde0r/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1556, \"height\": 986, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1528, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1684, \"height\": 639, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1611, \"height\": 498, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 801, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 813, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 825, \"height\": 410, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 862, \"height\": 143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1483, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 865, \"height\": 175, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1819, \"height\": 533, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1820, \"height\": 789, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1728, \"height\": 1259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1393, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1392, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1337, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1331, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1324, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1324, \"height\": 406, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1390, \"height\": 504, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1780, \"height\": 1007, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1325, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1323, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1600, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1327, \"height\": 151, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1432, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1346, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1371, \"height\": 370, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1283, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1281, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1280, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1395, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1400, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1435, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-z9baawde0r/table-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1109, \"height\": 225, \"label\": \"Table\"}]"
motivation: TTA合成中设计因素对性能的影响未被充分理解。
method: 大规模对比实验，研究数据、架构、训练和推理的设计选择。
result: 提供设计指南，提出高质量合成数据集。
conclusion: 系统理解TTA设计空间有助于构建更优模型。
---

## Abstract
Recent years have seen significant progress in Text-To-Audio (TTA) synthesis, enabling users to enrich their creative workflows with synthetic audio generated from natural language prompts. Despite this progress, the effects of data, model architecture, training objective functions, and sampling strategies on target benchmarks are not well understood. With the purpose of providing a holistic understanding of the design space of TTA models, we set up a large-scale empirical experiment focused on diffusion and flow matching models. Our contributions include: 1) AF-Synthetic, a large dataset of high quality synthetic captions obtained from an audio understanding model; 2) a systematic comparison of different architectural, training, and inference design choices for TTA models; 3) an analysis of sampling methods and their Pareto curves with respect to generation quality and inference speed. We leverage the knowledge obtained from this extensive analysis to propose our best model dubbed Elucidated Text-To-Audio (ETTA). When evaluated on AudioCaps and MusicCaps, ETTA provides improvements over the baselines trained on publicly available data, while being competitive with models trained on proprietary data. Finally, we show ETTA's improved ability to generate creative audio following complex and imaginative captions -- a task that is more challenging than current benchmarks.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

文本到音频（TTA）合成技术在近年来取得显著进展，但影响生成质量的关键因素——如训练数据、模型架构、目标函数和采样策略——尚未被系统性地理解。现有工作大多独立探索某个因素，难以在不同实验之间直接比较。因此，本文旨在全面阐释TTA模型的设计空间，通过大规模对比实验，为构建高性能TTA模型提供结构化指导，并最终提出一个名为ETTA（Elucidated Text-To-Audio）的最优模型。

## 2. 方法论

### 核心思想
基于潜扩散模型（LDM）范式，采用“先训练变分自编码器（VAE）压缩波形，再在潜空间训练条件生成模型”的两阶段流程。对扩散模型和流匹配模型进行统一框架下的对比，系统研究数据、架构、训练目标和采样策略的影响。

### 关键技术细节
- **VAE（ETTA-VAE）**：44kHz立体声Audio-VAE，参数量156M，潜空间帧率21.5Hz。训练损失包括：立体声多分辨率STFT损失、对抗性损失（来自EnCodec）、KL散度损失。在公开数据集上从头训练。
- **潜生成模型（ETTA-LDM）**：以DiT（Diffusion Transformer）为骨干，默认配置为24层、24头、宽度1536。采用T5-base文本编码器（最大token长度512）。主要训练目标：
  - **v-预测扩散损失**（v-diffusion）
  - **最优传输条件流匹配损失**（OT-CFM），并结合对数正态时间采样（logit-normal t-sampling）。
- **ETTA-DiT改进**：相比基准实现，引入以下关键改进：
  - 自适应层归一化（AdaLN）应用于所有子层（self-attention、cross-attention、FFN），初始化scale=1、bias=0，使用FP32精度。
  - 最终投影层初始化为零（匹配VAE潜变量均值），提高稳定性。
  - GELU激活使用tanh近似，自注意力层使用旋转位置编码（RoPE），base=16384。
  - 所有模块应用dropout（p_dropout=0.1）。
- **采样策略**：对OT-CFM模型比较Euler和2阶Heun求解器，结合帕累托曲线确定最优步数与无分类器引导（CFG）尺度。最终选择Euler采样，NFE=100，w_cfg=3.5。

## 3. 实验设计

### 使用的数据集
- 训练数据：AudioCaps（5万条）、AF-AudioSet（16.1万条）、TangoPromptBank（121万条）以及本文提出的**AF-Synthetic**（135万条高质量合成字幕，通过Audio Flamingo生成并经过CLAP相似度≥0.45过滤）。
- 基准测试：**AudioCaps**（通用音效）和**MusicCaps**（音乐）作为主要benchmark；额外使用SongDescriber进行分布外（OOD）评估。
- VAE训练数据：包含公共语音、音乐、音效数据集（见表12）。

### 对比方法
与多个公开基线对比：AudioLDM2、TANGO（含TANGO-AF）、Stable Audio Open、GenAU等。同时与使用专有数据训练的模型（Audiobox、Jen-1、FluxMusic等）进行间接比较。

### 评价指标
- **客观指标**：FD（使用PANNs和OpenL3特征）、KL散度（使用PaSST和PANNs）、Inception Score（IS）、CLAP分数（两种CLAP模型：LAION版和MS-CLAP版）。
- **主观指标**：5分制人工评分，包括整体质量（OVL）和文本相关性（REL）。

## 4. 资源与算力

论文明确说明：**所有模型均使用8块A100 GPU训练**。具体设置：
- VAE训练：AdamW优化器，峰值学习率1.5×10⁻⁴，总batch size=64（每样本1.5秒），训练2.8M步，FP32精度。
- LDM训练：AdamW，峰值学习率1×10⁻⁴，总batch size=128（每样本10秒），最终模型训练1M步（消融实验训练250k步），BF16混合精度+FlashAttention-2。

## 5. 实验数量与充分性

论文进行了大量系统性实验，涵盖四个方面：
- **训练数据**：4种数据集对比（AudioCaps、AF-AudioSet、TangoPromptBank、AF-Synthetic）。
- **训练目标**：v-diffusion vs. OT-CFM，以及是否采用对数正态时间采样。
- **架构设计**：不同深度（4/12/24/36层）、宽度（384/768/1536）、卷积FFN核大小（1/3）；RoPE base、dropout等细节消融。
- **采样方法**：Euler vs. Heun求解器，NFE从5到200，CFG尺度从1到7，帕累托曲线分析。
- **额外探索**：音频修复预训练、不同文本编码器（T5-base/large、FLAN-T5-base/large、CLAP双编码器）、AutoGuidance、Min-SNR-γ、引导区间限制等（结果见附录F）。总计约数十组对比实验。

实验设计较为充分，采用了相同的基础配置（如统一的训练步数、batch size）进行公平对比。所有重要结论均通过多次独立报告（含表格）支撑，并提供了主观评估。但部分消融（如模型规模）仅在250k步下进行，可能未完全收敛；且未对所有组合进行跨因素交互分析，但整体而言覆盖全面、结果可信。

## 6. 主要结论与发现

1. **数据质量与规模均重要**：AF-Synthetic（135万高质量合成字幕）带来的改进最为显著。数据质量（如AF-AudioSet的小而精）比单纯数量（如TangoPromptBank）更重要。
2. **架构改进有效**：ETTA-DiT相比Stable Audio Open的DiT，在相同数据下显著提升各项指标。增加深度和宽度可提升性能，但增加卷积FFN核大小无益。
3. **训练目标选择**：OT-CFM比v-diffusion更稳定（尤其在长时间训练中），且在高CFG下质量更一致。对数正态时间采样可略微改善FD。
4. **采样策略**：Heun求解器在低NFE下优于Euler；提高NFE和适当的CFG均可提升指标，但CFG过大会损害多样性（FD变差）。推荐w_cfg=3.5、NFE=100。
5. **最终模型ETTA**：在AudioCaps和MusicCaps上超越所有公开数据训练的基线，与使用专有数据的模型相当或更优。在创造性的复杂字幕生成任务中显著优于基线。
6. **混合/负面结果**：音频修复预训练、更大文本编码器、AutoGuidance、Min-SNR-γ等在本设置下未带来明确提升，需进一步探索。

## 7. 优点

- **系统性**：首次全面、公平地对比TTA各设计维度，提供明确设计指导。
- **数据贡献**：发布AF-Synthetic数据集（135万高质量合成字幕），为社区提供重要资源。
- **架构创新**：ETTA-DiT在实现上有多项针对稳定性和收敛速度的改进（零初始化、AdaLN等），具有通用性。
- **帕累托分析**：绘制采样策略的帕累托曲线，为实际部署提供折中方案。
- **实验严谨**：大量消融控制变量，同时报告主观评价，结论可靠。

## 8. 不足与局限

- **实验未完全收敛**：部分消融仅训练250k步，可能未反映最终性能；最终模型1M步是否充分也未论证。
- **交互效应缺失**：未系统研究因素之间的交互（如数据规模+模型规模的协同效果），结论可能因组合而变化。
- **文本编码器选择不明确**：未给出最优统一选择，且T5-large表现反常，可能受限于训练设置。
- **创造性评估较主观**：“创造性音频”的评估采用人工评分且样本量较小（20个/模型），泛化性有限。
- **未覆盖所有可能设计**：如语言模型方法（MusicGen等）被声明为正交，未纳入比较；数据增强、重述等也未充分研究。
- **计算成本高**：依赖大量A100 GPU，限制了可复现性（但代码和数据集已开源）。
- **潜在数据偏差**：AF-Synthetic基于Audio Flamingo生成，可能继承原始数据中的偏差；CLAP过滤阈值0.45可能排除部分有效样本。

（完）
