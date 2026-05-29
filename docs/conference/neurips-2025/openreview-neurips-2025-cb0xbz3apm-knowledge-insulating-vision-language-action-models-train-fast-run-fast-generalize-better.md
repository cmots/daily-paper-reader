---
title: "Knowledge Insulating Vision-Language-Action Models: Train Fast, Run Fast, Generalize Better"
title_zh: 知识绝缘的视觉-语言-动作模型：快速训练、快速推理、更好泛化
authors: "Danny Driess, Jost Tobias Springenberg, brian ichter, LILI YU, Adrian Li-Bell, Karl Pertsch, Allen Z. Ren, Homer Walke, Quan Vuong, Lucy Xiaoyang Shi, Sergey Levine"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=cb0xbZ3APM"
tags: ["query:wm-vla-sa"]
score: 8.0
evidence: 知识绝缘的高效VLA模型
tldr: 大型VLM带来实时推理障碍和离散token问题。本文提出Knowledge Insulating方法，将VLM语义知识与动作专家隔离，使VLA模型训练快、推理快且泛化更好，解决了大规模VLM在机器人控制中的效率瓶颈。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-cb0xbz3apm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cb0xbz3apm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 872, \"height\": 298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cb0xbz3apm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1426, \"height\": 238, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cb0xbz3apm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1436, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cb0xbz3apm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1155, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cb0xbz3apm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 843, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cb0xbz3apm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1251, \"height\": 496, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cb0xbz3apm/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 611, \"height\": 352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cb0xbz3apm/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 553, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cb0xbz3apm/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 730, \"height\": 510, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-cb0xbz3apm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 668, \"height\": 256, \"label\": \"Table\"}]"
motivation: 大型VLM参数多、输出离散，难以满足机器人实时连续控制需求。
method: 将VLM知识隔离到独立模块，动作专家直接使用连续输出，减少计算开销。
result: 在多个机器人任务上，训练和推理速度显著提升，泛化性能优于现有VLA方法。
conclusion: 知识绝缘策略有效平衡了VLM语义迁移与实时控制效率。
---

## Abstract
Vision-language-action (VLA) models provide a powerful approach to training control policies for physical systems, such as robots, by combining end-to-end learning with transfer of semantic knowledge from web-scale vision-language model (VLM) training. However, the constraints of real-time control are often at odds with the design of VLMs: the most powerful VLMs have tens or hundreds of billions of parameters, presenting an obstacle to real-time inference, and operate on discrete tokens rather than the continuous-valued outputs that are required for controlling robots. To address this challenge, recent VLA models have used specialized modules for efficient continuous control, such as action experts or continuous output heads, which typically require adding new untrained parameters to the pretrained VLM backbone. While these modules improve real-time and control capabilities, it remains an open question whether they preserve or degrade the semantic knowledge contained in the pretrained VLM, and what effect they have on the VLA training dynamics. In this paper, we study this question in the context of VLAs that include a continuous diffusion or flow matching action expert, showing that naively including such experts significantly harms both training speed and knowledge transfer. We provide an extensive analysis of various design choices, their impact on performance and knowledge transfer, and propose a technique for insulating the VLM backbone during VLA training that mitigates this issue. Videos are available at https://pi.website/research/knowledge_insulation and open-source model weights are available at https://github.com/Physical-Intelligence/openpi.

---

## 论文详细总结（自动生成）

# 论文《Knowledge Insulating Vision-Language-Action Models: Train Fast, Run Fast, Generalize Better》详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：现有的视觉-语言-动作模型（VLA）通常基于大规模预训练的视觉-语言模型（VLM）微调而来，目标是将互联网规模的语义知识迁移到机器人控制中。然而，VLM存在两大障碍：一是参数规模巨大（数百亿参数），难以满足机器人实时高频控制的要求；二是输出为离散token，而机器人需要连续值动作（如关节角度、末端位姿）。
- **现有方案的不足**：为解决实时性问题，近期VLA模型引入了专门的连续控制模块（如动作专家、扩散头、流匹配头）。但这些模块通常随机初始化，训练时梯度会反向传播至VLM骨干，从而损害VLM中预存的语义知识，导致训练速度变慢、语言指令遵循能力下降、泛化性能受损。
- **整体含义**：本文旨在回答一个关键问题——如何在不破坏VLM预训练知识的前提下，高效地将连续动作专家集成到VLA中，实现快速训练、快速推理和更好的泛化。

## 2. 方法论：核心思想、关键技术细节

- **核心思想 — 知识绝缘（Knowledge Insulation）**：在VLA训练过程中，将VLM骨干与连续动作专家（基于流匹配）的梯度流隔离开来。同时，使用离散化的动作token（FAST方法）作为表示学习目标，使VLM骨干获得适用于机器人控制的表示，而不会受到动作专家随机梯度干扰。

- **关键技术细节**：
  - **联合训练（Joint-Training）**：同时使用两种动作监督信号：
    - **离散动作预测**：采用FAST tokenizer将连续动作压缩为离散token，通过自回归下一个token预测（交叉熵损失）训练VLM骨干。
    - **连续动作预测**：通过流匹配（Flow Matching）训练一个参数更少的“动作专家”网络，输出连续动作chunk（H=50），用于实时推理。
  - **梯度停止（Stop-Gradient）**：修改注意力层，使动作专家对VLM骨干的梯度不进行反向传播（具体公式见论文式(5)-(6)）。VLM骨干只接收来自离散动作预测的梯度。
  - **共同训练（Co-Training）**：在训练数据中混合通用VLM数据（如图像描述、VQA、目标定位）与机器人数据，进一步增强语义知识迁移。
  - **注意力掩码设计**：设置掩码使得离散动作token与连续动作token之间互不关注，避免信息泄漏。
  - **状态表示**：对比了文本状态、特殊token状态和连续状态三种方案，最终采用文本状态或连续状态均可。

- **损失函数**：联合损失 L = -∑log p(离散token) + α * ‖ω - a - f(a_noised)‖²，其中α为平衡系数。由于梯度停止，连续损失不更新骨干。

## 3. 实验设计

- **数据集与场景**：
  - **真实机器人任务**（多种本体）：
    - 静态单臂：Table Bussing（12个物体）、Items in Drawer（3个物体）、Shirt Folding（双臂）。
    - 移动双臂：Make Bed、Dish in Sink、Mobile Items in Drawer、Laundry in Basket。
    - 评估均在未见过的环境（held-out scenes）中进行。
  - **公开基准**：
    - **LIBERO** (仿真)：LIBERO-Spatial, LIBERO-Object, LIBERO-Goal, LIBERO-90, LIBERO-Long。
    - **DROID** (真实世界)：桌面操作任务（抓取、放置、擦拭、开合抽屉等）。
  - **训练数据**：既有本体的专业数据（specialist），也有大规模多本体混合数据（generalist），并加入了通用VLM数据。

- **对比方法**：
  - π0（连续动作 + 流匹配，无隔离）
  - π0-FAST（纯离散自动回归）
  - OpenVLA-OFT（并行解码，VLA变体）
  - HybridVLA（联合训练但允许离散token关注连续动作）
  - Transfusion（在同一个transformer中同时扩散和离散预测）
  - 各种消融版本（仅联合训练、无VLM数据、不同tokenization等）

- **评估指标**：
  - 任务成功率/得分（分步计分）
  - 语言遵循率（Language Following Rate）
  - 训练收敛速度（步骤数）
  - 推理时间/控制频率
  - 泛化到新物体（OOD）的表现

## 4. 资源与算力

- **文中信息**：
  - 模型基于PaliGemma (2B) 作为VLM骨干，动作专家约300M参数。
  - 训练使用大集群，但**未明确给出具体GPU型号、数量和训练时长**。
  - 推理时，π0-FAST在RTX 4090上需约750ms预测1秒动作chunk；本文方法通过连续动作专家达到10 Hz控制频率（约100ms）。
  - 训练成本方面，由于同时使用离散和连续输出，计算开销增加了约20%，但由于收敛更快（训练步骤减少约7.5倍），总训练时间反而显著低于纯流匹配的π0。

- **说明**：论文未提供精确的算力资源表（如多少张A100、训练天数等），这是信息缺失点。

## 5. 实验数量与充分性

- **实验组数非常多**，覆盖了：
  - 6+ 真实机器人任务（每个任务10轮，共约100+轮评估）
  - 2个公开基准（LIBERO共5个子集，DROID）
  - 9+ 个对比基线/消融（包括不同梯度策略、动作表示、tokenization、状态表示、VLM数据使用与否等）
  - 还包含：数轮训练步骤曲线对比、语言遵循率对比、泛化到新物体、OOD泛化等。
- **充分性评估**：
  - 实验设计**较为充分**：在多个本体、多个复杂任务上验证，同时还做了模拟和真实世界对比。
  - 消融实验覆盖了方法中几乎所有关键设计（梯度停止、VLM数据、tokenization类型、状态表示），能清晰归因性能提升来源。
  - 统计显著性：图上标注了误差棒，且提及使用双尾t检验。
  - **潜在不足**：部分消融仅在特定任务（Table Bussing）上报告，未在所有任务上统一展示；但主要结论在多个任务上一致。

## 6. 主要结论与发现

1. **知识绝缘有效**：停止动作专家到VLM骨干的梯度流，显著提高了语言遵循能力和最终任务成功率（如Items in Drawer任务中，本文方法优于所有基线）。
2. **离散动作作为表示学习目标**：使用FAST token训练VLM骨干，收敛速度远快于纯流匹配训练（相同性能下步骤数减少7.5倍）。
3. **VLM数据共训增强泛化**：在Table Bussing和Mobile Manipulation等任务中，加入VLM数据（即使没有机器人数据）进一步提升了语言遵循和新物体泛化。
4. **快速推理**：连续动作专家（流匹配）只需少量推理步骤，控制频率可达10 Hz，远快于纯自回归的π0-FAST（~1.3 Hz）。
5. **新SOTA**：在LIBERO-90和LIBERO-Spatial上达到当前最优（96.0%和98.0%）。
6. 冻结骨干不可行（性能极低），证明VLM需要针对机器人数据微调表示。

## 7. 优点

- **方法创新**：创造性地提出梯度隔离（知识绝缘），解决了VLM微调中随机初始化模块梯度干扰的问题，理论清晰实现简单。
- **实用性强**：同时兼顾训练速度、推理速度和语义保留，非常适合实际机器人部署。
- **实验全面**：在多种本体、不同任务、开放性基准上验证，消融设计完整。
- **开源模型权重**：提供了DROID数据集训练的模型权重，便于复现。
- **分析深入**：不仅报告性能，还专门分析了语言遵循率、收敛曲线、OOD泛化等，揭示机制。

## 8. 不足与局限

- **训练成本增加**：同时使用离散和连续监督，计算开销增加约20%。虽然总训练时间仍更短，但对硬件要求依然较高。
- **语言遵循仍不完美**：尽管改善明显，但模型有时仍会忽略语言指令（由于数据偏差），距离完美理解仍有差距。
- **依赖FAST tokenizer**：离散动作表示需要额外设计（DCT + BPE），增加了系统复杂度。
- **部分实验未公开数据**：真实世界实验数据为Physical Intelligence内部数据，无法完全复现（但提供了公开基准和模型）。
- **资源信息不透明**：未提供详细的训练算力（GPU数量、训练天数），可重复性略打折扣。
- **应用限制**：主要针对桌面操纵和移动操作，未涉及人形机器人、触觉传感器等更复杂的机器人形态；长时域任务（如全屋清洁）未评估。

（完）
