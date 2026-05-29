---
title: "ESCA: Contextualizing Embodied Agents via Scene-Graph Generation"
title_zh: ESCA：通过场景图生成上下文化具身代理
authors: "Jiani Huang, Amish Sethi, Matthew Kuo, Mayank Keoliya, Neelay Velingker, JungHo Jung, Ser-Nam Lim, Ziyang Li, Mayur Naik"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=cjjPn1EIwq"
tags: ["query:wm-vla-sa"]
score: 7.0
evidence: 场景图生成用于具身代理上下文化
tldr: 针对多模态大模型在具身代理中细粒度感知不足的问题，提出ESCA框架，通过场景图生成来上下文化代理感知。其核心SGCLIP模型基于CLIP在87K+视频上训练，能够生成开放域时空场景图。该框架增强了代理对视觉特征与文本语义之间链接的捕捉，实验表明在多种具身任务中显著提升了感知准确性和任务成功率。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-cjjpn1eiwq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cjjpn1eiwq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cjjpn1eiwq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1455, \"height\": 286, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cjjpn1eiwq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cjjpn1eiwq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 922, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cjjpn1eiwq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 953, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cjjpn1eiwq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 414, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cjjpn1eiwq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1439, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cjjpn1eiwq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1437, \"height\": 957, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cjjpn1eiwq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1037, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cjjpn1eiwq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1440, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cjjpn1eiwq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1349, \"height\": 2189, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cjjpn1eiwq/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1225, \"height\": 2111, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cjjpn1eiwq/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1184, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cjjpn1eiwq/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1199, \"height\": 2022, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cjjpn1eiwq/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1297, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cjjpn1eiwq/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1200, \"height\": 2076, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cjjpn1eiwq/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1183, \"height\": 440, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-cjjpn1eiwq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1220, \"height\": 115, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cjjpn1eiwq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1348, \"height\": 639, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cjjpn1eiwq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1365, \"height\": 643, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cjjpn1eiwq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1480, \"height\": 640, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cjjpn1eiwq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1480, \"height\": 645, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cjjpn1eiwq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1204, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cjjpn1eiwq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 884, \"height\": 547, \"label\": \"Table\"}]"
motivation: 多模态大模型在细粒度视觉与语义联系上捕捉不足，导致感知不准确。
method: 提出ESCA框架，通过SGCLIP生成开放域时空场景图，将代理感知基于场景图进行上下文化。
result: 在多个具身任务上提升了感知和推理性能。
conclusion: 为具身代理提供了一种有效的情景理解与动作上下文化方法。
---

## Abstract
Multi-modal large language models (MLLMs) are making rapid progress toward general-purpose embodied agents. However, existing MLLMs do not reliably capture fine-grained links between low-level visual features and high-level textual semantics, leading to weak grounding and inaccurate perception. To overcome this challenge, we propose ESCA, a framework that contextualizes embodied agents by grounding their perception in spatial-temporal scene graphs. At its core is SGCLIP, a novel, open-domain, promptable foundation model for generating scene graphs that is based on CLIP.  SGCLIP is trained on 87K+ open-domain videos using a neurosymbolic pipeline that aligns automatically generated captions with scene graphs produced by the model itself, eliminating the need for human-labeled annotations. We demonstrate that SGCLIP excels in both prompt-based inference and task-specific fine-tuning, achieving state-of-the-art results on scene graph generation and action localization benchmarks. ESCA with SGCLIP improves perception for embodied agents based on both open-source and commercial MLLMs, achieving state of-the-art performance across two embodied environments. Notably, ESCA significantly reduces agent perception errors and enables open-source models to surpass proprietary baselines. We release the source code for SGCLIP model training at https://github.com/video-fm/LASER and for the embodied agent at https://github.com/video-fm/ESCA.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：多模态大模型（MLLMs）在通用具身代理（embodied agents）方面进展迅速，但现有模型难以可靠地捕捉低层视觉特征与高层文本语义之间的细粒度链接，导致感知接地（grounding）弱、感知不准确。
- **核心问题**：MLLMs 无法构建具空间和时间接地（grounded）的世界模型，对空间-时间关系的理解不足，造成概念语义与像素级观测之间的脱节。分析发现，高达69%的代理失败源于感知错误。
- **研究意义**：通过在 MLLM 代理的感知、推理和规划管线中融入结构化场景图（scene graph），弥合这一差距，提升具身代理在复杂环境中的鲁棒性和任务成功率。

## 2. 方法论

### 2.1 核心思想
提出 **ESCA（Embodied and Scene-Graph Contextualized Agent）** 框架，通过选择性地生成场景图来上下文化（contextualize）MLLM 的感知过程。其核心是 **SGCLIP**——一个基于 CLIP 的开放域提示式场景图生成基础模型，采用神经符号（neurosymbolic）训练管道，利用自动生成的 caption 和自我生成的场景图对齐，无需人工标注。

### 2.2 关键技术细节

- **ESCA 框架**：将 MLLM 的视觉描述模块分解为四个阶段：
    1. **选择性概念提取**：根据指令和历史，由 MLLM 提取相关实体类、属性、关系等结构化概念。
    2. **对象识别**：使用 Grounding DINO + SAM2 管线将概念接地到具体图像分割区域（bit-mask）。
    3. **场景图预测**：由 SGCLIP 对每个区域预测一元事实（实体类、属性）和二元事实（关系），并附概率置信度。
    4. **视觉摘要与验证**：将场景图转换为自然语言描述，结合图像和边界框，生成上下文摘要，供推理和规划模块使用。
- **传输协议（Transfer Protocol）**：通过定制两个提示模板（概念提取提示和视觉摘要提示），使 ESCA 适应不同任务（导航、操作、安排等），无需重新训练核心系统。
- **SGCLIP 模型**：
    - 基于 CLIP 微调，输入图像区域和候选概念集合，输出每个概念的 logit 分数。
    - 支持三种推理模式：实体类（softmax 归一化）、属性（与否定短语对比 softmax）、二元关系（将主体/客体预测类嵌入短语，与 `<norel>` 对比 softmax）。
    - 训练使用 **ESCA-Video-87K** 数据集（87K 视频-字幕对），通过自动生成的对象轨迹、开放域概念和编程规范（线性时序逻辑），利用 LASER 框架进行弱监督神经符号学习，对齐模型生成的场景图与规范。

### 2.3 公式与算法流程（文字说明）

- SGCLIP 的推理：对于实体类，`softmax(SGClip(σ, c_class_list))`；对于属性，`softmax(SGClip(σ, {c, ¬c}))`；对于关系，计算联合区域 `σ*_ij` 并引入预测类 `ν_i` 和 `ν_j`，形成 `(ν_i, c, ν_j)` 短语，再与 `<norel>` 对比 softmax。
- 训练损失：对比损失（匹配与不匹配的视频-规范对）、时间损失（事件时间位置对齐）、语义损失（常见感官否定）。
- 训练管道：使用 Scallop 语言实现可微分的符号对齐检查，结合语义损失和对比损失进行端到端梯度学习。

## 3. 实验设计

### 3.1 数据集与场景

- **具身环境**：EmbodiedBench 的四个环境：
    - **EB-Navigation**（AI2-THOR）：视觉导航任务。
    - **EB-Manipulation**（VLMBench）：低层机械臂操作。
    - **EB-Habitat**（Habitat 2.0，Language Rearrangement）：高层任务分解与规划。
    - **EB-Alfred**（ALFRED，AI2-THOR）：高层家庭任务（8种技能）。
- **独立场景图评估数据集**：OpenPVSG、Action Genome、VidVRD。
- **下游任务**：ActivityNet 动作识别。

### 3.2 对比方法

- **基线 MLLM**：InternVL-2.5-38B-MPO、Qwen2.5-VL-72B-Ins、Gemini-2.0-flash、GPT-4o。
- **感知增强基线**：Grounding DINO（GD）、Ultralytics-YOLO11。
- **SGCLIP 独立对比**：CLIP、InternVL-6B、BIKE、Text4Vis。
- **消融**：Base vs. +GD vs. +ESCA；不同训练数据量（1K/10K/87K）对 SGCLIP 的影响。

## 4. 资源与算力

- **计算设备**：128 核 Intel Xeon Gold 6338 CPU，10 张 NVIDIA H100 PCIe GPU。
- **训练时长**：SGCLIP 在 87K 数据点上微调 3 个 epoch 需要 **10 天**。
- 论文未明确给出单次具身环境实验的详细算力消耗，仅提供了上述训练资源信息。

## 5. 实验数量与充分性

- **具身实验**：在 4 个环境上，对 4 种 MLLM 分别测试 Base、+GD/YOLO、+ESCA 三种配置，共约 **48 组**（4 环境 × 4 模型 × 3 配置）。每个环境还按子任务（Common、Complex、Visual、Spatial、Long 等）报告详细成功率。
- **独立 SGCLIP 实验**：
    - 零样本：在 3 个场景图数据集（OpenPVSG、Action Genome、VidVRD）上测试实体类 R@1 和关系 R@10，对比 CLIP。
    - 微调：在 VidVRD 上 75 epoch 微调，报告 Precision@k/Recall@k（k=1,5,10）。
    - 动作识别：在 ActivityNet 上测试 0%、1%、5% 数据微调，与 BIKE、Text4Vis、InternVL-6B 对比。
- **错误分解分析**：手动检查 60（导航）+50（操作）+60（Alfred）+50（Habitat）个任务，定量分析感知、推理、规划错误分布。
- **消融**：评估 SGCLIP 训练数据量（1K/10K/87K）对零样本性能的影响。
- **总体评价**：实验覆盖多任务、多模型、多指标，进行了充分的消融和对比，采用温度 0 降低输出随机性，结果客观。但未提供多次运行的标准差（由于成本限制）。整体充分且公平。

## 6. 主要结论与发现

1. **ESCA 一致提升所有 MLLM**：在 EB-Navigation 和 EB-Manipulation 等环境中，ESCA 使开源模型（如 InternVL-2.5）的成功率超过专有模型 GPT-4o，且比仅使用 GD/YOLO 的基线获得额外显著提升（Gemini-2.0 提升超 10%，GPT-4o 再提升 6%）。
2. **显著减少感知错误**：错误分解显示，ESCA 将感知错误率从 69% 降至 30%（导航任务）。
3. **SGCLIP 具有强零样本泛化能力**：在面向开放域的场景图数据集上，SGCLIP 在实体类和关系预测上均优于 CLIP。
4. **SGCLIP 可微调至下游任务**：在 VidVRD 微调后取得最佳精度/召回；在 ActivityNet 上仅用 5% 数据（~800 视频）即达 92.1% 准确率，接近全监督 InternVL-6B。
5. **神经符号训练方法高效**：无需人工标注，仅利用视频本身和自动生成的数据即可训练出高质量场景图模型。

## 7. 优点

- **通用性**：ESCA 是通用框架，可适配不同 MLLM 和多样化的具身任务，通过传输协议灵活定制。
- **模块化设计**：将感知分解为概念提取、对象识别、场景图预测、摘要验证四个模块，易于集成和改进。
- **选择性接地**：不注入完整场景图，而是由 MLLM 自主选择最相关的实体、属性和关系，避免信息过载。
- **免人工标注**：SGCLIP 采用模型驱动的自监督学习范式，利用 GPT-4 生成的 caption 和自动提取的规范进行训练，大幅降低数据成本。
- **概率输出**：场景图附带置信度，可建模不确定性，适合部分可观测环境。
- **广泛验证**：在导航、操作、规划、场景图生成、动作识别等多个任务上均取得先进结果，证明其鲁棒性和迁移能力。

## 8. 不足与局限

- **延迟问题**：使用大型语言模型进行高层规划引入延迟，不适合实时低层控制。
- **仅 2D 视觉**：基于 2D 图像输入，缺乏 3D 点云深度感知支持，限制了深度感知推理和空间精度。
- **缺乏形式化验证**：虽然 ESCA 利用 MLLM 生成连贯规划，但没有正式的中间状态和最终状态验证机制，在安全关键场景中可能产生不可靠行为。
- **实验成本**：未提供多次运行的标准差，部分由于经济与环境原因；SGCLIP 训练耗时 10 天，且需要 10 张 H100 GPU，计算开销较大。
- **依赖 GPT-4 生成 caption**：ESC-Video-87K 的标注依赖 GPT-4，可能引入 LLM 偏见或幻觉，尽管有编译器验证，但仍有潜在误差。

（完）
