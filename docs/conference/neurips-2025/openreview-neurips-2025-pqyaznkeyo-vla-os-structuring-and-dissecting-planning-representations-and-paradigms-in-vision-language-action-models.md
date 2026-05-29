---
title: "VLA-OS: Structuring and Dissecting Planning Representations and Paradigms in Vision-Language-Action Models"
title_zh: "VLA-OS: 结构化和剖析视觉-语言-动作模型中的规划表示与范式"
authors: "Chongkai Gao, Zixuan Liu, Zhenghao Chi, Junshan Huang, Xin Fei, Yiwen Hou, Yuxuan Zhang, Yudi Lin, Zhirui Fang, Lin Shao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=PQYazNKEYo"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: VLA模型中规划表示与范式的系统性研究
tldr: 视觉-语言-动作（VLA）模型在复杂操作任务中表现出色，但不同方法的架构、规划范式和表示差异巨大，难以辨别性能来源。本文提出VLA-OS框架，系统分离这些因素，通过消融实验揭示了不同规划表示和范式对性能的影响，为VLA模型设计提供了重要指导。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqyaznkeyo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1457, \"height\": 923, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqyaznkeyo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqyaznkeyo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1441, \"height\": 967, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqyaznkeyo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1441, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqyaznkeyo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 590, \"height\": 688, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqyaznkeyo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 707, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqyaznkeyo/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 702, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqyaznkeyo/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1415, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pqyaznkeyo/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1434, \"height\": 1680, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqyaznkeyo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqyaznkeyo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1438, \"height\": 577, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqyaznkeyo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 731, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqyaznkeyo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 775, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqyaznkeyo/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1334, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqyaznkeyo/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1331, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqyaznkeyo/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 712, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pqyaznkeyo/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 582, \"height\": 220, \"label\": \"Table\"}]"
motivation: VLA模型在规划表示和范式上存在差异，难以确定性能提升的根本原因。
method: 提出VLA-OS框架，隔离网络架构和训练数据，系统比较不同规划范式与表示。
result: 揭示了不同规划表示和范式对VLA模型性能的差异化影响。
conclusion: 该研究为VLA模型的规划设计提供了系统性的理解与指导。
---

## Abstract
Recent studies on Vision-Language-Action (VLA) models have shifted from the end-to-end action-generation paradigm toward a pipeline involving task planning followed by action generation, demonstrating improved performance on various complex, long-horizon manipulation tasks. However, existing approaches vary significantly in terms of network architectures, planning paradigms, representations, and training data sources, making it challenging for researchers to identify the precise sources of performance gains and determine which component is more difficult to learn. To systematically investigate the impacts of different planning paradigms and representations isolating from network architectures and training data, in this paper, we introduce \name, a unified VLA architecture suite capable of various task planning paradigms, and design a comprehensive suite of controlled experiments across diverse object categories (rigid and deformable), visual modalities (2D and 3D), environments (simulation and real-world), and end-effectors (grippers and dexterous hands). Our results demonstrate that: 1) visually grounded planning representations are generally better than language planning representations; 2) the Hierarchical-VLA paradigm generally achieves superior performance than other paradigms, albeit at the cost of slower training and inference speeds.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 一、论文的核心问题与整体含义（研究动机和背景）

近年来，视觉-语言-动作（Vision-Language-Action, VLA）模型在机器人操作任务中逐渐从端到端的动作生成范式转向“任务规划 + 动作生成”的流水线模式，并在复杂、长程操作任务上取得了更优性能。然而，现有方法在网络架构、规划范式、表示形式、训练数据来源等多个维度上差异巨大，导致研究人员难以准确识别性能提升的真正来源，也难以判断任务规划与策略学习中哪个环节更困难。本文旨在系统性地隔离这些因素，通过可控实验回答五个核心问题：①任务规划应采用何种表示（语言、视觉、图像前瞻）？②应采用单一模型联合规划与学习（Integrated-VLA）还是分层模型（Hierarchical-VLA）？③规划与策略学习哪个是瓶颈？④VLA是否具有可扩展性和预训练优势？⑤采用任务规划的VLA在泛化和持续学习上是否优于端到端VLA？

## 二、论文提出的方法论：核心思想、关键技术细节

### 核心思想
提出 **VLA-OS** 统一模型家族，通过模块化设计实现不同的规划范式（ActionOnly-VLA、Integrated-VLA、Hierarchical-VLA），并支持多种规划表示（语言、视觉、图像前瞻）。在保持网络架构和训练数据一致的条件下，系统比较不同范式和表示的影响。

### 关键技术细节
- **VLA-OS-A (ActionOnly-VLA)**：直接生成动作，采用块级因果注意力结构，输入为多视图图像+语言指令，输出为动作块（chunk）。使用Qwen2.5系列LLM（0.5B~7B）作为骨干，双视觉编码器（DINOV2+SigLIP），支持2D/3D动作头。
- **VLA-OS-I (Integrated-VLA)**：在VLA-OS-A基础上增加规划头（语言/视觉/图像前瞻）。规划头与LLM共享KV缓存，支持隐式规划（规划头仅作为辅助损失，推理时不执行）和显式规划（先规划再生成动作）。
- **VLA-OS-H (Hierarchical-VLA)**：使用两个独立网络——一个VLM+规划头用于任务规划，另一个编码器-解码器变换器作为低层策略，接收规划结果和原始观测生成动作。低层动作头可接受冻结的AM-Radio图像特征和Qwen2.5语言特征。
- **三种规划表示**：
  - **语言推理**：包含任务、计划、子任务、动作、抓取位置等8个键，通过VLM+Gemini1.5标注后过滤优化。
  - **视觉推理**：使用离散位置标记（<loc_i>）表示目标边界框、末端执行器流、目标物体可供性，更贴近图像。
  - **图像前瞻推理**：从轨迹中选取K步后的未来帧作为短视目标图像，使用VAR+Bitwise Self-Correction自回归生成模型。
- **损失函数**：动作头采用L1损失或流匹配损失；规划头采用交叉熵（语言/视觉）或专用损失（图像前瞻）。

## 三、实验设计：数据集、benchmark、对比方法

### 数据集与Benchmark
- **LIBERO**（2D刚体操作）：包含Spatial、Object、Goal、Long四个子集（每子集10任务，每任务50演示），以及LIBERO-90（90任务，4500演示）。
- **The COLOSSEUM**（3D/泛化）：20任务，含100演示，测试No-Perturbation和ALL-Perturbation（颜色、纹理、光照、相机位姿等变化）。
- **FurnitureBench**（长程复杂操作）：4任务（柜子、台灯等），每任务100演示。
- **DexArt**（灵巧手操作）：4任务（水龙头、笔记本等），通过官方策略收集100演示。
- **PerAct2**（双臂操作）：5任务，每任务100演示。
- **真实世界可变形物体操作**：3任务（折叠手帕、展开牛仔裤、拉直绳子），每任务100演示，使用X-Arm+RealSense D435i。
- **真实世界刚体操作**：5任务，每任务50演示。

### 对比方法
- Diffusion Policy、OpenVLA、CoT-VLA、DiT Policy、π0、π0-FAST（表中结果取自原文）。
- 在相同架构下比较VLA-OS-A、VLA-OS-I（隐式/显式）、VLA-OS-H的三种表示及组合。

## 四、资源与算力

论文明确指出所有模型在 **8 × NVIDIA A100 80G GPUs** 上训练。训练时间未提供具体数值，但给出了图6b的训练成本（以总步骤×每步时间表示），语言规划表示因自回归特性导致成本最高。LLM骨干从0.5B到7B，预训练VLM使用FSDP+Bf16混合精度，在LLaVa v1.5数据上训练2个epoch。

## 五、实验数量与充分性

论文开展了大量系统性实验，涵盖：
- 规划表示对比（7种组合 × 隐式/显式 × VLA-OS-I/ H）共14组主实验（表2）。
- 三大范式在5个仿真+真实场景的性能比较（图6a：LIBERO-LONG、COLOSSEUM、FurnitureBench、DexArt、PerAct2、泛化、预训练）。
- 任务规划与策略学习分离评估（表3）：计算分解得分（DCS）和指令跟随得分（IFS）。
- 数据可扩展性（10%、40%、70%、100%数据）和模型可扩展性（0.5B~7B），结果见图7。
- 持续学习实验（附录C.5）：使用LIBERO-LONG 10任务序贯微调，报告FWT、NBT、AUC。
- 消融研究和计划头预训练（图6a中"Planning Head Pretraining"行）。
每实验结果取3个最佳checkpoints的平均值，每个checkpoint做20次rollout。实验设计公平，所有模型在相同架构、相同骨干、相同训练数据下比较，避免了混杂变量。因此实验充分且客观。

## 六、论文的主要结论与发现

1. **视觉接地表示优于语言表示**：视觉规划和图像前瞻规划在成功率、低层策略遵循、训练/推理速度、持续学习等维度均优于语言规划。
2. **Hierarchical-VLA整体最优**：在任务性能、泛化、可扩展性、规划分数、持续学习、预训练收益上匹配或超越Integrated-VLA和ActionOnly-VLA，但训练和推理成本更高。
3. **隐式规划优于显式规划（从零训练时）**：显式规划因累积误差导致性能显著下降，而隐式规划作为辅助损失可带来正向增益。
4. **策略学习比任务规划更困难**：在LIBERO-LONG上，无论采用哪种规划表示，政策学习的指令跟随得分（IFS）均低于任务规划的分解得分（DCS）。
5. **VLA范式均具有数据可扩展性**，但在约5000条演示的从零训练中，LLM骨干最好限制在0.5B参数（总模型<1B）。
6. **VLA-OS-A在较小模型（0.5B）上表现优于许多微调的大模型**，说明模型架构和算法设计仍然重要。

## 七、优点

- **系统性**：首次在同一框架下隔离网络架构和训练数据，全面比较三种主流VLA范式和三种规划表示，实验覆盖2D/3D、仿真/真实、刚体/可变形/灵巧手/双臂等多种场景。
- **可复现性**：统一代码、标注数据集和checkpoint将公开，使用开源HuggingFace模型和公开benchmark。
- **模块化设计**：VLA-OS系列可即插即用，支持不同骨干和规划头，适应性强。
- **深入分析**：通过DCS和IFS分离评估规划和策略导致失败的原因，提供独特洞察。

## 八、不足与局限

- **未涵盖所有规划变体**：例如使用隐式动作表示生成图像（如UniVLA）、视频生成规划、场景流规划等。
- **未探索跨本体迁移、仿真到真实迁移、2D到3D迁移问题**。
- **训练数据集小于1万条轨迹**，未在更大规模数据集（如OXE）上验证，结论可能受限于数据规模。
- **实验中都采用从零训练或微调**，未研究大规模预训练后不同范式的行为差异（除规划头预训练外）。
- **语言规划表示的质量依赖于自动标注和人工过滤**，可能引入偏好偏差。

（完）
