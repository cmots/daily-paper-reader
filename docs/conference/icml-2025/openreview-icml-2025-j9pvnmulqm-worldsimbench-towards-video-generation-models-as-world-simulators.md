---
title: "WorldSimBench: Towards Video Generation Models as World Simulators"
title_zh: "WorldSimBench: 迈向将视频生成模型作为世界模拟器"
authors: "Yiran Qin, Zhelun Shi, Jiwen Yu, Xijun Wang, Enshen Zhou, Lijun Li, Zhenfei Yin, Xihui Liu, Lu Sheng, Jing Shao, LEI BAI, Ruimao Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=j9pVnmulQm"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: WorldSimBench将视频生成模型作为世界模拟器进行评估
tldr: WorldSimBench提出了预测模型功能的分层分类，并构建了双评估框架，包括显式感知评估和隐式操作评估，首次从具身角度评估世界模拟器的能力，为世界模型的研究提供了标准化基准。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-j9pvnmulqm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1757, \"height\": 584, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-j9pvnmulqm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1770, \"height\": 826, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-j9pvnmulqm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1738, \"height\": 605, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-j9pvnmulqm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1585, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-j9pvnmulqm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1576, \"height\": 777, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-j9pvnmulqm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1773, \"height\": 902, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-j9pvnmulqm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1766, \"height\": 869, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-j9pvnmulqm/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1766, \"height\": 1008, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-j9pvnmulqm/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1769, \"height\": 750, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-j9pvnmulqm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1646, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j9pvnmulqm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1770, \"height\": 448, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j9pvnmulqm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1775, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j9pvnmulqm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1769, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j9pvnmulqm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1139, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j9pvnmulqm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1771, \"height\": 160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j9pvnmulqm/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1195, \"height\": 1015, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j9pvnmulqm/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1076, \"height\": 401, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j9pvnmulqm/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 996, \"height\": 402, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j9pvnmulqm/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1139, \"height\": 401, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j9pvnmulqm/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 502, \"height\": 480, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j9pvnmulqm/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1777, \"height\": 474, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j9pvnmulqm/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1333, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j9pvnmulqm/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1057, \"height\": 252, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-j9pvnmulqm/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1056, \"height\": 339, \"label\": \"Table\"}]"
motivation: 现有预测模型缺乏基于内在特性的分类，且缺乏从具身角度评估世界模拟器的基准。
method: 提出分层功能分类和双评估框架，包括显式感知和隐式操作评估。
result: 为世界模拟器的能力提供了标准化评估。
conclusion: 推动了视频生成模型作为世界模拟器的发展。
---

## Abstract
Recent advancements in predictive models have demonstrated exceptional capabilities in predicting the future state of objects and scenes. However, the lack of categorization based on inherent characteristics continues to hinder the progress of predictive model development. Additionally, existing benchmarks are unable to effectively evaluate higher-capability, highly embodied predictive models from an embodied perspective. In this work, we classify the functionalities of predictive models into a hierarchy and take the first step in evaluating World Simulators by proposing a dual evaluation framework called WorldSimBench. WorldSimBench includes Explicit Perceptual Evaluation and Implicit Manipulative Evaluation, encompassing human preference assessments from the visual perspective and action-level evaluations in embodied tasks, covering three representative embodied scenarios: Open-Ended Embodied Environment, Autonomous, Driving, and Robot Manipulation. In the Explicit Perceptual Evaluation, we introduce the HF-Embodied Dataset, a video assessment dataset based on fine-grained human feedback, which we use to train a Human Preference Evaluator that aligns with human perception and explicitly assesses the visual fidelity of World Simulater. In the Implicit Manipulative Evaluation, we assess the video-action consistency of World Simulators by evaluating whether the generated situation-aware video can be accurately translated into the correct control signals in dynamic environments. Our comprehensive evaluation offers key insights that can drive further innovation in video generation models, positioning World Simulators as a pivotal advancement toward embodied artificial intelligence.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：当前预测模型（Predictive Models）发展迅速，但缺乏基于其内在特性（如输出模态）的合理分类体系，这限制了模型发展。同时，现有基准（如AgentBench、VBench等）主要评估文本规划或视觉美学，无法有效评估高度具身化的预测模型（如世界模拟器）在物理规则、动作可行性等方面的能力。
- **整体含义**：该论文旨在建立预测模型的功能层级分类，并首次从具身智能角度提出评估“世界模拟器”（World Simulators）的双轨框架WorldSimBench，推动视频生成模型向世界模拟器演进。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：将预测模型按输出模态分为S0（文本）、S1（图像）、S2（视频）、S3（可执行视频/世界模拟器）四个层级。针对S3层级，提出显式感知评估（Explicit Perceptual Evaluation）和隐式操作评估（Implicit Manipulative Evaluation）两种互补评估方式。
- **关键技术细节**：
  - **显式感知评估**：
    - 构建层次化评估维度：视觉质量（美学、背景/前景一致性）、条件一致性（指令对齐、场景对齐）、具身性（轨迹、视角、速度、交互、安全等）。
    - 通过LLM（ChatGPT）扩展指令提示，人工筛选后形成Task Instruction Prompt List。
    - 使用多个视频生成模型在三个场景（开放世界环境OE、自动驾驶AD、机器人操作RM）上生成大量视频，由人工标注多维评分及原因，构建HF-Embodied数据集（35,701个元组）。
    - 基于Flash-VStream（VideoLLM）微调Human Preference Evaluator（仅训练LoRA参数），输出维度评分，对齐人类感知。
  - **隐式操作评估**：
    - 在三个仿真环境（MineRL、CARLA、CALVIN）中，利用预训练的视频到动作模型（基于Steve-1、Susie、LMdrive）将世界模拟器生成的预测视频实时转换为控制信号，执行闭环任务。
    - 评估指标：OE中跟踪移动距离、物品收集数量等；AD中使用Route Completion、Infraction Score、Driving Score等8个指标；RM中使用CALVIN benchmark的成功率（1-5个连续任务）。

## 3. 实验设计：数据集/场景、Benchmark、对比方法

- **数据集/场景**：
  - OE：Minecraft（VPT数据集、自制探索轨迹）、HF-Embodied数据集包含8401个视频。
  - AD：nuScenes训练集（用于微调）、CARLA LangAuto-Tiny benchmark（8个城镇、16种环境条件）。
  - RM：RH20T-P（用于显式评估）、CALVIN（A,B,C训练，D测试）。
- **Benchmark**：WorldSimBench自身作为评估框架，对比了现有基准如AgentBench、VBench、EvalCrafter等。
- **对比方法**：共8个视频生成模型：Open-Sora-Plan（T2V和TI2V）、Lavie、ModelScope、OpenSora、AnimateDiff、Dynamicrafter、EasyAnimate。全部在三个场景上微调后进行两种评估。

## 4. 资源与算力

- **显式评估中的Human Preference Evaluator训练**：使用4张A100 80GB GPU，训练4个epoch，学习率2e-5，warmup比例0.03，优化器AdamW，余弦学习率衰减。仅训练LoRA参数。
- **视频生成模型微调**：每个模型在三个场景的数据集上微调，但论文未明确说明总GPU数量或总训练时长。仅在附录C.2中说明了每种模型生成短视频（约16帧）和长视频（约48-64帧）的配置，训练遵循官方实现，未改变训练设置。
- **隐式操作评估**：未明确说明视频到动作模型的训练资源。

## 5. 实验数量与充分性

- **实验数量**：
  - 显式评估：使用Human Preference Evaluator对8个模型在3个场景共20+维度打分（每个维度5个提示×5个视频），此外对HF-Embodied数据集进行了统计分析和零样本泛化测试（OpenSora、Lavie）。
  - 隐式评估：OE中5个任务×10次试验；AD中在LangAuto-Tiny benchmark上测试；RM中20次试验（主要结果）和100次试验（补充验证）。
  - 消融/对比：对比了Human Preference Evaluator与GPT-4o在多个维度上的相关性；比较了不同视频生成模型在两种评估下的性能；在RM中对比了UniPi基线。
- **充分性与公平性**：实验覆盖三个典型具身场景，评估维度全面；使用统一视频到动作模型消除下游任务偏差；HF-Embodied数据集平衡了多种生成模型和评估维度的分布；零样本测试验证了Human Preference Evaluator的泛化性。结论有理有据，实验设计较充分。

## 6. 主要结论与发现

- **显式评估结果**：
  - OE：多数模型在具身交互维度表现最差（如方块破碎等物理规律生成困难）；AD中模型间差异较小，但3D深度感知和元素渲染质量普遍不足；RM中静态场景表现好，但指令对齐和目的性动作生成困难。
  - Human Preference Evaluator在所有场景和维度上均优于GPT-4o（PLCC/Acc显著更高），零样本泛化能力强。
- **隐式评估结果**：
  - OE：带图像条件（TI2V）的模型成功率显著低于仅文本条件（T2V），表明当前模型难以准确生成物理规律和3D场景表示。不同模型在轨迹和复杂任务上差异大。
  - AD：轨迹生成能力强的模型（如Open-Sora-Plan）在驾驶任务中表现更好。
  - RM：简单任务各模型表现接近，但长序列任务中更鲁棒的模型（如Dynamicrafter、Open-Sora-Plan）成功率更高。
- **显式与隐式评估的一致性**：大部分结论一致（如Dynamicrafter轨迹生成好），但在需高频交互或长序列任务中存在分歧，表明两种评估互补，综合使用才能公平评价。
- **总体结论**：当前视频生成模型仍无法有效捕捉许多物理规则，距离真正的世界模拟器有显著差距。

## 7. 优点

- **首次提出预测模型分层分类**，为后续研究提供了统一框架。
- **双轨评估框架**：结合人类感知的显式评估和闭环任务执行的隐式评估，全面覆盖视觉质量和动作可行性，弥补了现有基准的不足。
- **HF-Embodied数据集**：包含35,701个具有细粒度人类反馈的多维标注视频，不仅用于评估，还可用于偏好对齐（如DPO训练提升模型性能）。
- **Human Preference Evaluator**：基于VideoLLM微调，在多个场景和零样本设定下表现优于GPT-4o，具有强泛化能力。
- **实验覆盖三个代表性具身场景**（游戏、自动驾驶、机器人），评估维度全面，结论具有普适性。

## 8. 不足与局限

- **场景覆盖仍有限**：论文承认世界模拟器可应用于更多场景（如医疗、建筑），当前仅覆盖三个场景，物理规律的表征多样性尚未穷尽。
- **隐式评估中的视频到动作模型**：依赖预训练模型（如Steve-1、LMdrive），这些模型的性能上限可能限制对世界模拟器的真实评估（即可能存在瓶颈在于动作转换而非视频生成）。
- **HF-Embodied数据集标注主观性**：人工标注可能存在偏差，虽然论文试图通过详细指南和in-context示例缓解，但未做交叉验证或一致性分析。
- **算力资源未完全公开**：仅说明了Human Preference Evaluator训练配置，视频生成模型微调和隐式评估的总算力未提及，影响复现性。
- **未评估最新闭源模型**（如Sora、VideoPoet等），评估范围局限于开源模型，结论的时效性有限。
- **HF-Embodied数据集在AD和RM中的维度定义存在差异**（如OE用二分评分，AD/RM用5分制），可能影响跨场景可比性。

（完）
