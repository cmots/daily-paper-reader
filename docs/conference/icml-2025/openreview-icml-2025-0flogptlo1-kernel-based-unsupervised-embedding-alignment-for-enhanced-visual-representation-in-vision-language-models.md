---
title: Kernel-based Unsupervised Embedding Alignment for Enhanced Visual Representation in Vision-language Models
title_zh: 基于核的无监督嵌入对齐：增强视觉语言模型中的视觉表示
authors: "Shizhan Gong, Yankai Jiang, Qi Dou, Farzan Farnia"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=0fLoGPTLo1"
tags: ["query:wm-vla-sa"]
score: 6.0
evidence: 增强视觉语言模型的视觉表示，可应用于VLA系统
tldr: 针对CLIP在细粒度视觉感知上的不足，本文提出基于核的无监督嵌入对齐方法，将CLIP的视觉表示与DINOv2对齐，在保持与文本兼容性的同时增强细节捕捉能力。实验证明对齐后的表示在多个视觉任务上提升了细粒度性能。该方法可提升下游VLA模型的视觉感知能力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-0flogptlo1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1737, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0flogptlo1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 807, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0flogptlo1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1736, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0flogptlo1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-0flogptlo1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1736, \"height\": 350, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1773, \"height\": 784, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1776, \"height\": 487, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 885, \"height\": 583, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 627, \"height\": 364, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1769, \"height\": 536, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1562, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 926, \"height\": 550, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1773, \"height\": 530, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1775, \"height\": 431, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1616, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 844, \"height\": 147, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1773, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1770, \"height\": 307, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-0flogptlo1/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1773, \"height\": 420, \"label\": \"Table\"}]"
motivation: CLIP的细粒度感知能力有限，影响下游多模态模型。
method: 通过核方法无监督对齐CLIP与DINOv2的视觉嵌入。
result: 对齐后的表示在多个视觉任务上提升了细粒度性能，且保持与文本的兼容性。
conclusion: 为增强视觉语言模型提供了有效的嵌入对齐方法。
---

## Abstract
Vision-language models, such as CLIP, have achieved significant success in aligning visual and textual representations, becoming essential components of many multi-modal large language models (MLLMs) like LLaVA and OpenFlamingo. However, numerous studies have identified CLIP's limited fine-grained perception as a critical drawback, leading to substantial failures in downstream MLLMs. In contrast, vision-centric foundation models like DINOv2 demonstrate remarkable capabilities in capturing fine details from images. In this work, we propose a novel kernel-based method to align CLIP's visual representation with that of DINOv2, ensuring that the resulting embeddings maintain compatibility with text embeddings while enhancing perceptual capabilities. Our alignment objective is designed for efficient stochastic optimization. Following this image-only alignment fine-tuning, the visual encoder retains compatibility with the frozen text encoder and exhibits significant improvements in zero-shot object recognition, fine-grained spatial reasoning, and localization. By integrating the aligned visual encoder, downstream MLLMs also demonstrate enhanced performance. The code and models are available at https://github.com/peterant330/KUEA.

---

## 论文详细总结（自动生成）

# 论文详细总结：Kernel-based Unsupervised Embedding Alignment for Enhanced Visual Representation in Vision-language Models

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：视觉语言模型（如CLIP）在细粒度视觉感知方面存在明显缺陷，包括颜色、空间关系、计数、文字识别等能力不足。这限制了其自身性能，也影响了以其为视觉编码器的多模态大语言模型（MLLMs，如LLaVA、OpenFlamingo）的下游表现。
- **现有局限**：
  - CLIP训练于图像-文本配对数据，受全局监督约束，难以学习像素级细节。
  - 直接使用多个视觉编码器（如CLIP+DINOv2）增加计算开销；直接微调CLIP可能破坏与文本编码器的对齐，损害零样本能力。
  - 现有增强方法（如区域级任务损失、蒸馏损失）需重新训练模型，计算成本高，且产生的新嵌入与原始CLIP嵌入差异大，导致下游MLLMs需重新对齐。
- **整体含义**：本文旨在通过轻量级的、仅基于图像的无监督对齐微调，在保持CLIP与文本嵌入兼容性的前提下，提升CLIP视觉编码器的细粒度感知能力，并且这种改进可无缝传递给下游MLLMs。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- 将CLIP视觉编码器的嵌入与视觉中心模型（如DINOv2）的嵌入在核空间（kernel space）中对齐。核空间能够捕捉样本之间的相对相似性，从而在保持原特征空间宏观结构的同时灵活调整样本间基于视觉细节的相似度。

### 关键技术细节
1. **核函数与核矩阵**：
   - 采用归一化多项式核（degree=3）：\( k_{\text{polynomial}}(x,y) = (\gamma x^T y + c)^d \)，并归一化使\( k(x,x)=1 \)。
   - 核矩阵反映了样本间的相似性结构。

2. **对齐目标函数**：
   - 最小化CLIP核函数与DINOv2核函数之间的期望平方差：
     \[
     \min_\theta \mathbb{E}_{I_i,I_j \sim D_{\text{train}}} \left[ \left( k_1(f_\theta(I_i), f_\theta(I_j)) - k_2(g(I_i), g(I_j)) \right)^2 \right]
     \]
   - 其中\( k_1 \)为CLIP的核函数（参数可训练），\( k_2 \)为DINOv2的核函数（固定）。
   - 支持随机优化，只需采样少量图像对即可计算梯度。

3. **正则化项**：
   - 加入L2距离正则化，防止对齐后的视觉嵌入偏离原始CLIP嵌入过远：
     \[
     \mathbb{E}_{I_i} \left[ \| f_\theta(I_i) - f_{\theta_0}(I_i) \|_2^2 \right]
     \]
   - 该正则化有效保持图像-文本对齐（经理论证明）。

4. **最终损失**：
   \[
   \min_\theta \; w \cdot \text{对齐项} + \text{正则化项}
   \]
   - 权重\( w \)平衡两项（实验设为0.5~1.0）。

5. **训练流程**：
   - 冻结DINOv2和CLIP文本编码器，仅微调CLIP视觉编码器。
   - 使用ImageNet-1K训练集（1.28M图像）进行纯图像无监督训练。

## 3. 实验设计：数据集、Benchmark、对比方法

### 评估场景与Benchmark
1. **视觉中心任务**：
   - **零样本分类**：12个数据集，包括常见对象（ImageNet, CIFAR-10/100, Caltech101）、细粒度对象（OxfordPets, DTD, FER2013）、域特定（PCAM, RESISC45, EuroSAT）、分布外（ImageNet-O, ImageNet-Sketch）。
   - **图像-文本检索**：Flickr30K, MSCOCO（零样本）。
   - **计数/空间/文字识别**：SVHN, GTSRB, CLEVR Distance, CLEVR Counts（零样本与线性探测）。
   - **定位能力**：使用Covert等人提出的probing benchmark（MSCOCO，局部/全局探测，宏平均召回率）。

2. **多模态大语言模型（MLLMs）下游任务**：
   - **LLaVA-1.5-7B**：12个Benchmark（AI2D, TextVQA, POPE, TallyQA, VSR, RefCOCO系列, VQA-v2, LLaVA-Bench等）。
   - **OpenFlamingo-3B (Instruct)**：7个数据集（COCO, Flickr30K, VQAv2, OK-VQA, TextVQA, VizWiz, HatefulMemes），测试0/4/16-shot上下文学习。

### 对比方法
- **直接基线**：
  - 线性投影（将DINOv2映射到CLIP空间）
  - 特征对齐（L2距离线性变换）
- **现有方法**：DIVA（利用扩散模型精炼CLIP）
- **额外对比**：AM-RADIO（知识蒸馏）、Additive-MoF（特征拼接）、其他VLM（SigLIP, DFN, MetaCLIP）、不同目标模型（MLCD）
- **消融实验**：训练轮数、正则化项、系数w、核函数类型、数据集规模。

## 4. 资源与算力

- **GPU型号与数量**：NVIDIA GeForce RTX 4090。
- **训练时长**：对于ViT-L-14，使用2张4090约30小时完成对齐微调。ViT-L-14-336使用4张4090，ViT-B-16使用2张。
- **显存与批大小**：ViT-B-16批大小128，ViT-L-14批大小64，ViT-L-14-336批大小32。
- **训练数据**：仅使用ImageNet-1K（1.28M图像），微调2~4个epoch。
- 文中强调该对齐步骤相比CLIP预训练非常轻量，硬件友好。

## 5. 实验数量与充分性

- **实验组数**：大量且系统。包括：
  - 3种CLIP骨干（ViT-B-16, ViT-L-14, ViT-L-14-336）在12个分类数据集上的零样本评估。
  - 检索任务（2个数据集 × 2个方向）。
  - 4个细粒度任务（SVHN, GTSRB, CLEVR Distance, CLEVR Counts）的零样本与线性探测。
  - 定位probing benchmark（2个指标）。
  - MLLM方面：LLaVA（12个数据集，有无LLM微调）、OpenFlamingo（7个数据集 × 3种shots）。
  - 额外VLM（SigLIP等3种）、不同目标模型（MLCD）验证泛化性。
  - 消融实验：训练轮数、正则化、系数、核函数、数据集大小。
  - 对比DIVA、AM-RADIO、Additive-MoF。
  - MMVP-VLM与MMVP基准测试。
- **充分性与公平性**：实验覆盖了多种视觉任务和下游应用，对比方法包含直接基线及近期工作。文中指出评估遵循标准库（CLIP-Benchmark、原论文设置），控制变量（如LLM微调单独做对照）。结论稳健且增量明显，但部分改善幅度较小（如零样本分类平均提升约1%），且未在大规模MLLM（如70B）上验证。

## 6. 主要结论与发现

- 核空间对齐方法在保持CLIP与文本编码器兼容性（零样本检索性能不降反升，见表2）的同时，显著提升了CLIP的细粒度视觉能力。
- 零样本分类平均准确率提升：ViT-B-16 (+0.82%), ViT-L-14 (+1.28%), ViT-L-14-336 (+1.03%)，尤其对低分辨率、小目标提升明显。
- 在计数、空间推理、文字识别等困难任务上，对齐后CLIP性能大幅提高（线性探测提升5.51%）。
- 下游MLLMs（LLaVA, OpenFlamingo）直接替换对齐后的视觉编码器，即使不微调LLM也获得提升；配合LLM微调，效果更显著（LLaVA平均提升1.66%，定位任务提升3.05%）。
- 方法对CLIP变体（SigLIP等）和其他VLM通用，且目标模型可替换（如MLCD）。
- 正则化项至关重要，缺失会导致零样本性能下降。

## 7. 优点

- **方法创新**：首次提出在核空间中对齐视觉表示，兼顾保持原始特征空间结构与灵活调整样本间相似性；理论保证（梯度估计误差界、对齐保持性质）。
- **轻量高效**：仅需少量图像数据（ImageNet-1K）和短时间微调，无需重新训练或改动文本编码器，计算资源要求低。
- **兼容性强**：对齐后的嵌入与原始CLIP嵌入差异小，可直接替换下游MLLMs中的视觉编码器，无需重新对齐或微调LLM。
- **泛化性好**：在不同CLIP骨干、不同VLM、不同目标模型上均有效；视觉能力增强可迁移至多种下游任务。
- **实验系统全面**：覆盖零样本分类、检索、精细任务、MLLM评估，并与多种基线对比，消融完整。
- **开源**：代码与模型公开，促进可复现。

## 8. 不足与局限

- **数据集规模有限**：仅在ImageNet-1K（1.28M图像）上微调，未在更大规模数据集（如DataComp-1B）上验证，可能限制效果的进一步提升。
- **MLLM规模局限**：只测试了7B参数级别的LLaVA和3B的OpenFlamingo，未在更大模型（如70B）上实验，扩展性未知。
- **仅使用DINOv2作为目标**：虽然扩展实验验证了MLCD等，但未探索更多视觉模型（如MAE, BEiT等），且未说明DINOv2是否是最优选择。
- **提升幅度有限**：零样本分类平均提升约1%，虽然一致性高但绝对值不高；定位probing提升较小；部分数据集（如ImageNet）提升不明显。
- **潜在偏差风险**：训练数据为ImageNet-1K，可能引入域偏差，影响其他域（如医疗、遥感）的泛化性（文中虽测试了PCAM等，但仅各一个数据集）。
- **缺乏理论收敛性分析**：虽给出了梯度估计的误差界，但未分析非凸优化下的收敛性。
- **核函数选择依赖经验**：多项式核（degree=3）表现最优，但其他核（高斯、余弦）各有问题，需针对不同模型调整。
- **未与更多最新方法对比**：如与LoRA微调、Prompt Tuning等结合提升CLIP的方法未对比，仅与DIVA等对比。

（完）
