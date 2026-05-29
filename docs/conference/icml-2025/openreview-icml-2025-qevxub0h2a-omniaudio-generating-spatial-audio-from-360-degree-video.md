---
title: "OmniAudio: Generating Spatial Audio from 360-Degree Video"
title_zh: OmniAudio：从360度视频生成空间音频
authors: "Huadai Liu, Tianyi Luo, Kaicheng Luo, Qikai Jiang, Peiwen Sun, Jialei Wang, Rongjie Huang, Qian Chen, Wen Wang, Xiangtai Li, ShiLiang Zhang, Zhijie Yan, Zhou Zhao, Wei Xue"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=qEVxub0h2a"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 从360度视频生成空间音频（一阶Ambisonics）
tldr: 传统视频到音频生成缺乏空间线索。本文提出新任务360V2SA，从360度视频生成空间音频（FOA）。构建了Sphere360数据集和半自动标注流水线。模型能根据全景视频合成带有方向感的3D音频，为沉浸式体验提供支持。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-qevxub0h2a/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 879, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qevxub0h2a/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 847, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qevxub0h2a/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1700, \"height\": 828, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qevxub0h2a/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1751, \"height\": 931, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qevxub0h2a/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1295, \"height\": 1455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qevxub0h2a/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1596, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qevxub0h2a/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1423, \"height\": 1408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qevxub0h2a/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1589, \"height\": 807, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qevxub0h2a/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1590, \"height\": 803, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qevxub0h2a/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1606, \"height\": 962, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qevxub0h2a/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1580, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qevxub0h2a/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1063, \"height\": 689, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qevxub0h2a/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 881, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qevxub0h2a/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1594, \"height\": 1214, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qevxub0h2a/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1595, \"height\": 879, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qevxub0h2a/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1601, \"height\": 885, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-qevxub0h2a/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 858, \"height\": 659, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qevxub0h2a/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1770, \"height\": 724, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qevxub0h2a/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 774, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qevxub0h2a/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 781, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qevxub0h2a/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 771, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qevxub0h2a/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1069, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qevxub0h2a/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1072, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qevxub0h2a/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1769, \"height\": 488, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qevxub0h2a/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1596, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qevxub0h2a/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 898, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qevxub0h2a/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1157, \"height\": 274, \"label\": \"Table\"}]"
motivation: 现有视频到音频生成方法仅关注透视视频和非空间音频，无法表示三维空间音源。
method: 提出360V2SA任务和Sphere360数据集，采用条件扩散模型从全景视频生成一阶Ambisonics空间音频。
result: 在客观指标和主观听感上均优于基线，能准确还原声源方向。
conclusion: 首次实现了从360度视频到空间音频的端到端生成，拓展了沉浸式音频应用。
---

## Abstract
Traditional video-to-audio generation techniques primarily focus on perspective video and non-spatial audio, often missing the spatial cues necessary for accurately representing sound sources in 3D environments. To address this limitation, we introduce a novel task, \textbf{360V2SA}, to generate spatial audio from 360-degree videos, specifically producing First-order Ambisonics (FOA) audio - a standard format for representing 3D spatial audio that captures sound directionality and enables realistic 3D audio reproduction. We first create \textbf{Sphere360}, a novel dataset tailored for this task that is curated from real-world data. We also design an efficient semi-automated pipeline for collecting and cleaning paired video-audio data. To generate spatial audio from 360-degree video, we propose a novel framework \textbf{OmniAudio}, which leverages self-supervised pre-training using both spatial audio data (in FOA format) and large-scale non-spatial data. Furthermore, OmniAudio features a dual-branch framework that utilizes both panoramic and perspective video inputs to capture comprehensive local and global information from 360-degree videos. Experimental results demonstrate that OmniAudio achieves state-of-the-art performance across both objective and subjective metrics on Sphere360. Code and datasets are available at~\href{https://github.com/liuhuadai/OmniAudio}{\texttt{github.com/liuhuadai/OmniAudio}}. The project website is available at \href{https://OmniAudio-360V2SA.github.io}{\texttt{OmniAudio-360V2SA.github.io}}.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：传统视频到音频生成方法存在两个关键局限：一是生成非空间音频（单声道/立体声），缺少方向信息；二是仅使用有限视角的透视视频，丢失了全景视觉上下文。而360度视频配合空间音频（如一阶Ambisonics, FOA）能同时解决这两个问题，提供沉浸式3D音频体验。
- **核心问题**：目前缺乏从360度视频生成空间音频的研究，面临数据稀缺、音视频对同步困难、高质量FOA音频生成复杂三大挑战。
- **整体含义**：作者提出新任务“360V2SA”（从360度视频生成空间音频），并构建了数据集Sphere360和框架OmniAudio，旨在首次实现端到端的全景视频→FOA音频生成，为VR/AR沉浸式应用铺路。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
采用**条件流匹配（Conditional Flow Matching）**作为生成主干，结合**自监督粗到细预训练**和**双分支视频编码**，从360度视频中生成FOA格式的空间音频。

### 关键技术细节
1. **空间音频表示**：设计一个四通道变分自编码器（VAE），初始化自预训练的立体声VAE，去掉专为立体声设计的MS-STFT，公平加权四个通道（W、X、Y、Z）的损失。
2. **双分支视频表示**：
   - 全局分支：使用预训练的MetaCLIP-Huge编码器处理全景视频（经矩形投影和填充）。
   - 局部分支：从全景视频中提取透视视频（120° FoV），同样通过MetaCLIP-Huge编码，再通过线性投影对齐。
   - 两者融合：全局特征经过最大池化作为全局条件（Global Condition），局部特征上采样后元素级相加作为局部条件，共同注入扩散Transformer。
3. **自监督流匹配预训练**（粗到细）：
   - 粗阶段：使用大规模非空间音频（FreeSound, AudioSet, VGGSound）转换为伪FOA格式（Y/Z为零，W=两声道和，X=两声道差），通过VAE压缩为隐变量，使用随机掩码训练扩散模型（掩码概率0.1，最小跨度lmask）。
   - 细阶段：仅使用真实的FOA音频（Sphere360中的空间音频）继续预训练，进一步适配空间特征。
   - 目标函数：条件流匹配损失（公式3）。
4. **监督微调**：冻结预训练流匹配模型，加入双分支视频特征作为条件，使用逻辑正态分布采样时间步，训练50,000步。推理时通过学习的向量场采样，再用VAE解码输出FOA音频。

## 3. 实验设计：数据集、Benchmark、对比方法

- **数据集**：
  - **训练数据**：Sphere360数据集（103,000个10秒视频片段，共288小时，包含288种音频事件，来自YouTube）。另有非空间音频数据集FreeSound、AudioSet、VGGSound（约200万样本）用于预训练。
  - **测试集**：Sphere360-Bench（约3,000个高质量测试片段，约180类事件）和YT360测试集（用于评估泛化能力，属于分布外数据）。
- **Benchmark**：作者建立Sphere360-Bench作为标准化评估框架。
- **对比方法**（Baselines）：
  - Diff-Foley + AS（视频→音频→音频空间化组件）
  - MMAudio + AS（视频+文本→音频→音频空间化）
  - ViSAGe（FoV）和 ViSAGe（360）（直接生成空间音频，但输入为透视视频或全景视频）
  - 所有基线在Sphere360上训练。
- **评估指标**：
  - 非空间指标：Fréchet Distance (FD)、KL散度（使用PaSST模型）
  - 空间指标：∆abs θ（方位角误差）、∆abs ϕ（仰角误差）、∆Angular（空间角误差）
  - 主观指标：平均意见得分（MOS-SQ空间音频质量、MOS-AF音视频对齐）

## 4. 资源与算力

- **VAE训练**：24张A800 GPU，批次大小144，训练500,000步；然后冻结编码器，再训练解码器300,000步。
- **预训练阶段**：8张A100 GPU，有效批次大小256，训练100,000步。
- **微调阶段**：8张A100 GPU，有效批次大小256，训练50,000步。
- 优化器：AdamW（生成器学习率3e-5，判别器6e-5；微调阶段5e-5）。
- 模型最大参数量：1.2B（Large），此外还有Medium（472M）和Small（291M）版本进行比较。

## 5. 实验数量与充分性

- **总实验组数**：主要实验包括：
  - 主实验结果（表2）：在两个测试集上对比4种基线，报告FD、KL、三个空间指标、MOS、推理时间。
  - 消融实验一（表3）：预训练策略四种配置（粗到细、仅细、仅粗、无预训练）。
  - 消融实验二（表4）：双分支设计五种变体（ERP+Per, EAC+Per, 仅Per, 仅EAC, 仅ERP）。
  - 模型规模影响（表5）：Large、Medium、Small对比。
  - 额外实验（附录G）：CFG-scale搜索（图12）、VAE模型比较（表10）、更多双分支切法比较（表11）。
  - 定性比较（图3）和失败案例分析（图11）。
- **充分性评价**：实验设计全面，覆盖了客观与主观评价、分布内与分布外测试、模型规模、设计消融。消融实验有控制变量，对比客观公平（基线使用相同训练集和评估指标）。主观测试招募15名线下测试者，随机抽取50个样本，标准合理。整体实验充分、客观、公平。

## 6. 论文的主要结论与发现

1. OmniAudio在所有客观指标（FD、KL、空间角度误差）上显著优于所有基线，在分布内（Sphere360-Bench）和分布外（YT360）数据集上均表现最佳。
2. 自监督粗到细预训练是有效的：同时使用非空间和空间音频比只用一种或不用预训练都要好。
3. 双分支设计（全景+透视视频）优于任何单分支变体，全景视角对空间音频生成至关重要。
4. 模型容量越大性能越好，1.2B参数模型优于472M和291M模型。
5. 主观听感实验中，OmniAudio的MOS-SQ和MOS-AF远高于基线，生成音频更自然且与视频对齐。
6. 案例研究显示，OmniAudio能捕捉物体移出视野后的声音变化（如火车驶过），而基线在声音来源离开视角后即丢失音频。

## 7. 优点

- **任务新颖**：首次提出360度视频→空间音频生成任务，填补了研究方法空白。
- **数据集贡献**：构建了最大的高质量360度视频+FOA音频数据集Sphere360，并公开半自动采集/清洗流程。
- **方法创新**：
  - 双分支视频编码有效融合全局上下文和局部细节。
  - 自监督粗到细预训练策略充分利用海量非空间音频数据，缓解空间音频数据稀缺问题。
  - 采用流匹配（Flow Matching）生成高质量音频，训练稳定。
- **实验扎实**：覆盖客观、主观、消融、泛化、模型规模等多维评估，对比基线设计公平。
- **开源**：代码、数据集、基准都已公开，促进后续研究。

## 8. 不足与局限

- **数据限制**：尽管有103K样本，但对复杂场景（含多个发声源）仍不够，如失败案例中模型将乐器误判为掌声。
- **模型限制**：无法处理过于复杂的多声源场景，空间定位精度（∆Angular约1.27°）虽好但仍有提升空间。
- **评估局限**：
  - 主观测试仅15人、50个样本，规模较小。
  - 客观空间指标基于能量强度估计，可能不如直接感知测试精确。
- **应用限制**：目前仅支持10秒片段生成，未讨论长视频生成；依赖YouTube数据，存在版权和领域偏差。
- **消融实验**：预训练策略中未对比专门的音频编解码器（如EnCodec）的影响；双分支设计中未探索不同投影格式（如Cubemap）的变体。
- **计算资源依赖**：1.2B模型需要8张A100训练50k步，复现成本较高。

（完）
