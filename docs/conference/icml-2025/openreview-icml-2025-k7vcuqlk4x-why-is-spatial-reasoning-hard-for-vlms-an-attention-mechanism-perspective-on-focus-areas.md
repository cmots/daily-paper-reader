---
title: Why Is Spatial Reasoning Hard for VLMs? An Attention Mechanism Perspective on Focus Areas
title_zh: 为什么空间推理对VLM来说很难？从注意力机制视角看焦点区域
authors: "Shiqi Chen, Tongyao Zhu, Ruochen Zhou, Jinghan Zhang, Siyang Gao, Juan Carlos Niebles, Mor Geva, Junxian He, Jiajun Wu, Manling Li"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=k7vcuqLK4X"
tags: ["query:wm-vla-sa"]
score: 5.0
evidence: 通过注意力机制分析VLM空间推理失败，与具身AI中的VLM理解相关
tldr: 大视觉语言模型在空间推理上表现不佳。本文通过解释性分析，发现模型在中间层对图像和文本token的注意力分配存在显著偏差，导致对空间关系理解错误。研究揭示了注意力焦点区域与错误模式的关联，为改进VLM的空间推理能力提供了重要洞察。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1773, \"height\": 663, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 790, \"height\": 418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 699, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 511, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1755, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 875, \"height\": 341, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 850, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1724, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1758, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1758, \"height\": 496, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1618, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1622, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1572, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1285, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1770, \"height\": 602, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 561, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 580, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 711, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1762, \"height\": 765, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1765, \"height\": 766, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1765, \"height\": 787, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1772, \"height\": 788, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1764, \"height\": 788, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1765, \"height\": 789, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1584, \"height\": 969, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1819, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-k7vcuqlk4x/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 516, \"height\": 358, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-k7vcuqlk4x/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1770, \"height\": 520, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k7vcuqlk4x/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 859, \"height\": 532, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k7vcuqlk4x/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 851, \"height\": 419, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k7vcuqlk4x/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k7vcuqlk4x/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 785, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k7vcuqlk4x/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1380, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k7vcuqlk4x/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 860, \"height\": 337, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k7vcuqlk4x/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 892, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k7vcuqlk4x/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 856, \"height\": 132, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k7vcuqlk4x/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 863, \"height\": 131, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-k7vcuqlk4x/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1159, \"height\": 266, \"label\": \"Table\"}]"
motivation: 当前VLM在简单空间关系任务上表现不佳，需要从机制层面理解原因。
method: 通过追踪中间层注意力得分，分析图像与文本令牌交互模式，对比正确与错误案例的注意力差异。
result: 发现错误样本中，模型对图像关键区域的注意力显著不足，且文本token主导了决策。
conclusion: 注意力分配不均衡是VLM空间推理困难的主要原因，为后续模型设计提供指导。
---

## Abstract
Large Vision Language Models (VLMs) have long struggled with spatial reasoning tasks. Surprisingly, even simple spatial reasoning tasks, such as recognizing “under” or “behind” relationships between only two objects, pose significant challenges for current VLMs. We believe it is crucial to use the lens of mechanism interpretability, opening up the model and diving into model’s internal states to examine the interactions between image and text tokens during spatial reasoning. Our analysis of attention behaviors reveals significant differences in how VLMs allocate attention to image versus text. By tracing the areas of images that receive the highest attention scores throughout intermediate layers, we observe a notable pattern: errors often coincide with attention being misdirected towards irrelevant objects within the image. Moreover, such attention patterns exhibit substantial differences between familiar (e.g., “on the left side of ”) and unfamiliar (e.g.,“in front of ”) spatial relationships. Motivated by these findings, we propose ADAPTVIS based on inference-time confidence scores to sharpen the attention on highly relevant regions when the model exhibits high confidence, while smoothing and broadening the attention window to consider a wider context when confidence is lower. This training-free decoding method shows significant improvement (e.g., up to a 50 absolute point improvement) on spatial reasoning benchmarks such as WhatsUp and VSR with negligible additional cost.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

大型视觉语言模型在空间推理任务上长期表现不佳，即便是简单的“左/右/上/下/前/后”等两个物体之间的基本空间关系也常常出错。例如，给定“蜡烛背后的书”的图片，VLM却错误描述为“蜡烛左边的书”。现有研究主要从视觉编码器（如CLIP）的局限性角度分析，但忽略了图像与文本 token 在模型内部状态中如何交互以构建几何理解这一关键环节。本文首次从**机制可解释性**的视角，通过分析模型内部状态中的注意力分布，揭示VLM空间推理困难的深层原因——不是简单的视觉信息不足，而是注意力在图像空间中的几何分布错位。

## 2. 方法论：核心思想、关键技术细节

### 2.1 核心思想
- **观察1**：图像 token 占输入序列约90%，但仅获得约10%的总注意力，文本 token 主导了决策。
- **观察2**：仅简单增加所有图像 token 的注意力权重并不能提升性能，关键在于注意力的**几何分布**。
- **观察3**：正确回答与错误回答的注意力模式不同：正确时注意力精确聚焦于相关物体；错误时注意力分散到无关区域。
- **观察4**：模型对熟悉的空间关系（如“left/right”）表现出高置信度，对不熟悉的（如“on/under/behind”）置信度低，且置信度与正确性正相关。

### 2.2 关键技术：AdaptVis
- **训练无关的解码方法**，在推理时动态调整图像 token 的注意力分布。
- 对模型最后一层输入 token（第n位）的注意力 logits 进行温度缩放：
  - 当模型置信度 **C < β** 时，使用 **α1 < 1** 平滑注意力分布，鼓励探索更广泛区域（如图9所示）。
  - 当模型置信度 **C ≥ β** 时，使用 **α2 > 1** 锐化注意力分布，强化对当前关注区域的聚焦（如图10所示）。
- 公式表示：
  - 低置信度：`A_nj^(l,h) = α1 * A_nj^(l,h)` 若 j∈图像token，否则不变。
  - 高置信度：`A_nj^(l,h) = α2 * A_nj^(l,h)` 若 j∈图像token，否则不变。
- 超参数 α1、α2、β 从验证集中选取，且实验表明超参数具有一定鲁棒性。

### 2.3 对比方法
- **ScalingVis**：统一对所有图像 token 使用固定系数 α（无自适应）。
- **DoLa**：对比中间层 logits 进行知识校准。
- **VCD**：视觉对比解码，对比有无图像时的logits。

## 3. 实验设计

### 3.1 数据集与场景
- **WhatsUp**：包含合成图像（Controlled A/B）和真实图像（COCO one/two、VG one/two），每个子集有不同选项数（4或6）。
- **VSR**：1223张图像-标题对，适配为问答格式，使用布尔标签。
- 额外通用基准：POPE（目标幻觉）、GQA（视觉推理）、TextVQA（文本读取）、VQAv2（通用QA）。

### 3.2 评估指标
- 主要指标：准确率（Exact Match）、F1分数。
- 对外，使用AUROC衡量注意力与YOLO标注重叠度，以预测回答正确性。

### 3.3 对比方法
- 基线：LLaVA-1.5、LLaVA-1.6、Qwen2-VL。
- 方法：+VCD、+DoLa、+ScalingVis、+AdaptVis。

## 4. 资源与算力

**论文中未明确说明使用的GPU型号、数量或训练时长。** 本文提出的方法属于推理时解码方法，无需训练，因此算力需求主要集中在推理阶段。文中仅提及“negligible additional computation cost”，并给出推理时间对比：ScalingVis 仅增加约2%的时间，AdaptVis 因需计算阈值而增加约64%的时间（见表9）。未提供具体硬件细节。

## 5. 实验数量与充分性

- **多模型验证**：在 LLaVA-1.5、LLaVA-1.6、Qwen2-VL 上均进行了实验，覆盖不同架构。
- **多数据集**：WhatsUp（6个子集）、VSR、POPE、GQA、TextVQA、VQAv2，共超过10个实验场景。
- **消融与对比**：对比了VCD、DoLa、ScalingVis，并进行了消融（如α值影响）。
- **鲁棒性测试**：改变选项数量（2选项 vs 4/6选项）、反向关系测试（reverse curse）、超参数OOD测试。
- **内部机制分析**：逐层注意力分析、AUROC曲线、YOLO标注重叠分析、熵/偏度分布。

**充分性评价**：实验设计较为全面，覆盖了合成/真实、熟悉/不熟悉、简单/复杂等多种情况，且进行了充分的消融和鲁棒性分析，对比方法涵盖当前主流解码增强策略，结果可信度高。但未在更多VLM（如GPT-4V、Gemini）上验证，是未来工作。

## 6. 主要结论与发现

1. **注意力分配严重失衡**：图像 token 数量虽多，但仅获得约10%的注意力。
2. **注意力位置比数量更重要**：均匀增加图像注意力无益；注意力必须精确对齐物体位置。
3. **中间层是关键**：中间层的注意力与YOLO标注重叠的AUROC最高（可达0.95左右），表明这些层是信息处理的核心。
4. **置信度可反映注意力可靠性**：模型对熟悉关系（left/right）置信度高，正确率高；对不熟悉关系（on/under/behind）置信度低，正确率低。
5. **AdaptVis显著提升空间推理性能**：在WhatsUp上最高提升50个绝对百分点（Controlled A，LLaVA-1.6），在VSR上提升约4%准确率和10% F1。
6. **通用性**：在通用QA基准上也保持或小幅提升性能，未出现负迁移。

## 7. 优点

- **机制洞察深刻**：从注意力分布角度解释了VLM空间推理失败的根本原因，而非简单归因于视觉编码器。
- **方法简洁高效**：AdaptVis 是不需要额外训练的解码方法，推理开销小，易于部署。
- **自适应性强**：利用模型自身置信度动态调整注意力，无需人工标注或外部知识。
- **实验扎实**：覆盖多个数据集、多种模型、多种关系类型，并进行了消融、鲁棒性、OOD测试。
- **开源性好**：代码和数据集已公开。

## 8. 不足与局限

1. **CLIP固有缺陷未处理**：方法仅缓解模型内部注意力偏差，无法解决CLIP对某些视觉模式的根本性失败（如Tong et al. 2024b所示的案例）。
2. **超参数依赖验证集**：α1、α2、β 需从验证集搜索，跨分布泛化性虽有一定验证，但仍需人工调优。
3. **适用场景有限**：实验仅针对VLM的空间推理，对其他模态错误（如文本幻觉）效果未知。
4. **计算开销**：AdaptVis需计算置信度阈值，导致推理时间增加约64%（表9），在实时应用中可能受限。
5. **模型覆盖不全**：仅测试了LLaVA系列和Qwen2-VL，未评估闭源模型（如GPT-4V、Gemini）或更大规模开源模型。
6. **置信度度量的局限性**：使用生成概率作为置信度，可能无法完全反映内部状态可靠性（如过度自信问题）。
7. **标签偏差风险**：真实数据集中“左/右”关系远多于“前/后”等，模型性能提升可能得益于对常见关系的调整，而对罕见关系改善有限。

（完）
