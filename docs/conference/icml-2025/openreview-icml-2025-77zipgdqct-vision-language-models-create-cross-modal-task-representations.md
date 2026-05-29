---
title: Vision-Language Models Create Cross-Modal Task Representations
title_zh: 视觉语言模型创建跨模态任务表示
authors: "Grace Luo, Trevor Darrell, Amir Bar"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=77ziPGdQct"
tags: ["query:wm-vla-sa"]
score: 6.0
evidence: 视觉语言模型中的跨模态任务表示
tldr: 该论文揭示了视觉语言模型（VLM）将概念上等价的输入对齐到共享任务向量，该向量对模态和格式不变，且跨模态迁移效果优于完整任务提示，为理解VLM的表示机制提供了新见解，可能有助于VLA模型的设计。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 836, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 840, \"height\": 836, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1301, \"height\": 1224, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 779, \"height\": 283, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 774, \"height\": 496, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 858, \"height\": 1177, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1755, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1425, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1594, \"height\": 1118, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1798, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1517, \"height\": 2303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1137, \"height\": 2225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-77zipgdqct/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1432, \"height\": 1476, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1795, \"height\": 565, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1763, \"height\": 609, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 765, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1115, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1342, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 869, \"height\": 546, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 799, \"height\": 144, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1446, \"height\": 391, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1522, \"height\": 177, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1573, \"height\": 231, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1498, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1527, \"height\": 494, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-77zipgdqct/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 793, \"height\": 331, \"label\": \"Table\"}]"
motivation: 理解VLM处理多种任务时的内部表示机制。
method: 通过跨模态迁移实验测量任务向量的对齐程度。
result: 发现任务向量在压缩后仍优于完整提示。
conclusion: 任务向量简化了VLM的跨模态处理。
---

## Abstract
Autoregressive vision-language models (VLMs) can handle many tasks within a single model, yet the representations that enable this capability remain opaque. We find that VLMs align conceptually equivalent inputs into a shared task vector, which is invariant to modality (text, image) and format (examples, instruction), and may simplify VLM processing. We measure this alignment via cross-modal transfer--the ability of a task vector derived in one modality to trigger the correct generation in another--on a range of tasks and model architectures. Although the task vector is highly compressed, we find that this single vector outperforms prompting the model with the full task information, unique to this cross-modal case. Furthermore, we show that task vectors can be transferred from a base language model to its fine-tuned vision-language counterpart, and that they can be derived solely from instructions without the need for examples. Taken together, our findings shed light on how VLMs internally process task information, and how they map different modalities into common semantic representations.

---

## 论文详细总结（自动生成）

# 论文中文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：自回归视觉语言模型（VLM）能够在单一模型中处理多种任务，但其内部如何表示任务信息仍不透明。不同模态（文本、图像）和不同格式（示例、指令）描述的同一任务，模型是否具有共享的任务表示？
- **研究动机**：理解VLM的内部表示机制有助于揭示其灵活性背后的原理，并可能为模型压缩、跨模态迁移等应用提供理论基础。
- **整体含义**：论文发现VLMs将概念上等价的输入（无论模态或格式）对齐到一个共享的“任务向量”（task vector）中，该向量位于特殊token位置（通常为序列末尾的分隔符），并可通过跨模态修补（cross-modal patching）技术将任务从一个模态迁移到另一个模态。

## 2. 论文提出的方法论
- **核心思想**：任务向量是VLM中压缩任务信息的隐藏激活向量，对模态和格式不变。通过激活修补（activation patching）技术，将源模态的任务向量注入到目标模态的查询中，可以诱导模型执行正确的任务，而无需在上下文中提供完整任务信息。
- **关键技术细节**：
  - **跨模态修补（Cross-modal patching）**：给定一个任务 \(t\) 和模型 \(f\)，先通过源模态的规格（例如文本示例）前向传播得到任务向量 \(h_{t,l,txt}\)，该向量取自模型第 \(l\) 层最后一个分隔符token的激活。然后，对于目标模态的查询（例如图像），在相同层和t_token位置修补该向量，再进行前向传播生成输出 \(y_{img} = f_{\text{patch}}(x_{img} | h_{t,l,txt})\)。整个过程无需额外训练。
  - **任务规格类型**：三种常见规格：文本示例（text examples）、指令（instructions）、图像示例（image examples）。
  - **评估指标**：跨模态迁移的准确率（与预设标签精确匹配首生成token），以及余弦相似度（用于LLM到VLM迁移）。
- **公式/算法流程**（文字说明）：
  1. 准备任务规格（如5个文本示例），按照模板“Q: {x1}\nA: {y1}\n...\nQ: {xn}\nA: {yn}”构建输入。
  2. 将规格输入VLM，从指定层（通过验证集选取最佳层）的最后一个分隔符位置提取激活向量作为任务向量。
  3. 对于目标模态的查询（例如图像），在相同位置修补该任务向量，然后运行前向传播得到答案。

## 3. 实验设计
- **使用的数据集/场景**：
  - **主要评估集**：6个自定义跨模态任务：Country-Capital、Country-Currency、Animal-Latin、Animal-Young、Food-Color、Food-Flavor。每个任务包含文本示例、图像示例和指令三种规格。图像来自Wikipedia，标签部分由Claude 3.5自动生成并人工复核。
  - **扩展VQA任务**：从VQAv2中自动构建3个“in-the-wild”任务（Food-Class、Shirt-Color、Man-Holding），使用LLaVA-NeXT-34B生成的密集文本描述作为文本示例。
  - **任务覆盖（Task overriding）**：4种场景（语义、语法、创意生成、事实回忆），使用GPT4o自动评估正确性。
- **Benchmark**：对比方法包括：
  - **No Context**（无任务信息）
  - **Image Examples Prompt / Patch**（图像示例的提示或修补）
  - **Text Examples Prompt / Patch**（文本示例的提示或修补）
  - 以及随机基线（Random，多数类别）
- **模型**：三种代表性VLM：LLaVA-v1.5（晚融合，7B）、Mantis-Fuyu（早融合，8B）、Idefics2（晚融合，8B），覆盖不同架构和图像ICL能力。此外还使用对应的基础LLM（Vicuna、Mistral）进行LLM到VLM迁移实验。
- **超参数**：示例数N=5，图像resize至224像素；跨模型均通过验证集选择最佳修补层。

## 4. 资源与算力
- **文中未明确说明**：论文没有提及使用的GPU型号、数量、训练时长等具体算力信息。实验均为推理（forward pass）和少量验证，未涉及训练，因此算力需求相对较低。作者仅在附录A.2中报告了计算开销：对30个文本示例的上下文，修补方法相比提示方法在运行时减少了11倍（2.20秒→0.20秒），VRAM消耗减少2.4倍（20.02GB→8.21GB），几乎与仅处理查询相当。

## 5. 实验数量与充分性
- **实验数量**：论文进行了多组实验：
  - 主要跨模态迁移实验（表2）：3个模型 × 6个任务 × 3个种子 = 54个条件（含多个方法对比）。
  - LLM到VLM迁移（表3）：2个模型（LLaVA-v1.5和Idefics2）的余弦相似度和准确率。
  - 指令任务向量（图6）：在Idefics2上改变示例数量，比较指令、示例和集成。
  - 扩展VQA任务（表4）：3个任务，对比多种方法。
  - 任务覆盖实验（表5）：4种场景，比较三种方法。
  - 消融实验：模板格式（附录表10）、所有模态组合（附录表12）、噪声指令鲁棒性（附录表9）。
  - 表示演化分析（图8,13,14,15）：对每个任务和模态（文本ICL、图像ICL、指令）进行100组不同示例的统计分析。
- **充分性**：实验设计较为全面，覆盖了不同架构、不同任务类型、不同规格模态和格式；消融实验考虑了模板、模态组合、噪声等；定量与定性分析结合。但未涉及更大规模VLM（如GPT-4V）或更多实际应用场景，仅使用开源模型。总体客观、公平，但可进一步扩展。

## 6. 论文的主要结论与发现
1. **跨模态修补优于提示**：对于图像查询，从文本示例修补的任务向量显著优于将完整文本示例作为提示（Prompt），解决了提示常见的“输入复述”问题。例如在Idefics2上，文本修补平均准确率0.51 vs 提示0.18。
2. **任务向量跨模态可迁移**：文本示例的任务向量可以修补到图像查询，并往往优于图像示例的修补或提示。
3. **LLM到VLM迁移**：基础LLM（如Mistral）的任务向量与对应VLM（Idefics2）高度相似（余弦相似度≥0.89），且从LLM修补到VLM图像查询的性能甚至略优于VLM内部迁移。
4. **指令也可用作任务向量**：仅使用指令可以产生有效的任务向量，与示例向量集成后能提高样本效率。
5. **表示演化三阶段**：VLM内部处理文本ICL和图像ICL时，表示在层间经历三个相似阶段：早期编码输入（约前50%层）、中期压缩为任务摘要（约40%层）、晚期输出答案（后10%层）。任务向量在中期表现最佳，且不同模态的任务向量按任务聚类而非模态。
6. **任务覆盖**：修补指令比系统提示更有效地覆盖（override）提示中已有的任务。

## 7. 优点
- **新颖性**：首次系统性地研究VLM中跨模态任务表示，展示了任务向量对模态和格式的不变性，并验证其在多种架构上的泛化性。
- **方法简洁有效**：跨模态修补只需单次向量注入，计算开销远低于提示，且性能更高，具有实用价值。
- **实验设计合理**：涵盖多种任务、多种规格、多种模型，并进行了充分的消融和鲁棒性测试；定量与定性分析相结合（t-SNE、logit lens）。
- **应用潜力**：任务向量可用于高效的多模态任务迁移、长提示压缩、任务覆盖等，有助于提高VLM的交互性和可解释性。

## 8. 不足与局限
- **实验覆盖有限**：仅测试了6个合成任务和3个VQAv2派生任务，未覆盖更广泛、更复杂的真实世界场景（如细粒度分类、推理等）。模型也仅限于开源7B/8B规模，未验证更大模型或商业模型。
- **未提供解释机制**：论文承认缺乏对“为什么”任务向量存在跨模态不变性的机制解释，仅提供现象证据（如t-SNE聚类、logit lens解码）。
- **评估指标单一**：主要使用精确匹配（首token匹配）作为准确率，对于开放式生成任务可能不够全面（任务覆盖实验使用GPT4o评估，但仍有主观性）。
- **图像示例性能偏低**：在合成任务中，图像示例的修补或提示效果普遍不如文本示例，论文认为由于图像示例需要额外的视觉识别步骤，但未深入分析如何缓解这一差距。
- **应用限制**：任务向量在跨模态设置下（如图像→文本）可能不如同模态有效（附录表12），且对噪声指令敏感（附录表9），实际部署前需更多鲁棒性测试。
- **算力信息缺失**：未提供训练或微调所需的GPU算力，仅报告了推理开销。

（完）
