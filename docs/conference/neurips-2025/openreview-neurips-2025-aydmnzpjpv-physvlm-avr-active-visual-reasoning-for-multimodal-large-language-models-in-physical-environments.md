---
title: "PhysVLM-AVR: Active Visual Reasoning for Multimodal Large Language Models in Physical Environments"
title_zh: "PhysVLM-AVR: 物理环境中多模态大语言模型的主动视觉推理"
authors: "Weijie Zhou, Xuantang Xiong, Yi Peng, Manli Tao, Chaoyang Zhao, Honghui Dong, Ming Tang, Jinqiao Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=AYDMNzpJPv"
tags: ["query:wm-vla-sa"]
score: 4.0
evidence: 物理环境中具身智能体的主动视觉推理
tldr: 多模态大语言模型在被动静态环境中表现良好，但在真实物理世界中因信息不完全而受限。受人类主动探索启发，本文提出主动视觉推理（AVR）任务，将视觉推理扩展到部分可观察环境中的具身交互范式，要求智能体通过闭环感知-推理-动作过程主动收集信息。该任务为具身AI研究提供了新基准。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-aydmnzpjpv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1437, \"height\": 493, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aydmnzpjpv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1387, \"height\": 789, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aydmnzpjpv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1398, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aydmnzpjpv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1444, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aydmnzpjpv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1441, \"height\": 919, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aydmnzpjpv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1458, \"height\": 677, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aydmnzpjpv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1205, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aydmnzpjpv/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1426, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aydmnzpjpv/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1407, \"height\": 944, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aydmnzpjpv/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1392, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aydmnzpjpv/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 377, \"height\": 289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aydmnzpjpv/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1398, \"height\": 1402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aydmnzpjpv/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1413, \"height\": 1660, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aydmnzpjpv/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1419, \"height\": 1666, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-aydmnzpjpv/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1012, \"height\": 742, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-aydmnzpjpv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 561, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-aydmnzpjpv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 593, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-aydmnzpjpv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 894, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-aydmnzpjpv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1428, \"height\": 546, \"label\": \"Table\"}]"
motivation: 现有MLLM在被动静态环境中研究视觉推理，缺乏处理真实世界部分可观察性的能力。
method: 提出主动视觉推理（AVR）任务，要求智能体在部分可观察环境中通过闭环交互主动探索。
result: AVR任务挑战了现有模型，为具身AI提供了新的评估基准。
conclusion: 主动视觉推理是推动具身智能体在真实世界中有效运行的关键方向。
---

## Abstract
Visual reasoning in multimodal large language models (MLLMs) has primarily been studied in passive, static settings, limiting their effectiveness in real-world physical environments where an embodied agent must contend with incomplete information due to occlusion or a limited field of view. Humans, in contrast, leverage their embodiment to actively explore and interact with their environment—moving, examining, and manipulating objects—to gather information through a closed-loop process integrating perception, reasoning, and action. Inspired by this capability, we introduce the Active Visual Reasoning (AVR) task, extending visual reasoning to a paradigm of embodied interaction in partially observable environments. AVR necessitates embodied agents to: (1) actively acquire information via sequential physical actions, (2) integrate observations across multiple steps for coherent reasoning, and (3) dynamically adjust decisions based on evolving visual feedback. To rigorously evaluate AVR, we introduce CLEVR-AVR, a simulation benchmark featuring multi-round interactive environments designed to assess both reasoning correctness and information-gathering efficiency. We present AVR-152k, a large-scale dataset that offers rich Chain-of-Thought (CoT) annotations detailing iterative reasoning for uncertainty identification, action-conditioned information gain prediction, and information-maximizing action selection, crucial for training agents in a higher-order Markov Decision Process. Building on this, we develop PhysVLM-AVR, an embodied MLLM achieving state-of-the-art performance on CLEVR-AVR, embodied reasoning (OpenEQA, RoboVQA), and passive visual reasoning (GeoMath, Geometry30K). Our analysis also reveals that current embodied MLLMs, despite detecting information incompleteness, struggle to actively acquire and integrate new information through interaction, highlighting a fundamental gap in active reasoning capabilities.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）

- **问题**：当前多模态大语言模型（MLLM）的视觉推理研究主要局限于静态、完全可观察的场景（如CLEVR、VQA），但在真实物理环境中，信息往往因遮挡、视角受限或容器封装而**部分可观察**。被动观察模式导致模型在需要主动探索的场景中表现不佳。
- **动机**：人类能够通过移动、操作物体等物理交互主动获取缺失信息，形成“感知-推理-动作”闭环。受此启发，作者提出**主动视觉推理**（Active Visual Reasoning, AVR）任务，将视觉推理从静态扩展到**部分可观察、可交互的环境**，旨在促进具身智能体更有效的环境理解与推理能力。

## 2. 方法论：核心思想、关键技术细节与流程

### 核心思想
- **AVR任务定义**：智能体在部分可观察环境 \(E\) 中，通过有限原子动作集 \(A\) 与环境交互，回答一个问题 \(Q\)。推理过程建模为**更高阶马尔可夫决策过程**（Higher-order MDP），每个时间步 \(t\) 智能体接收部分观测 \(o_t\)，维护历史 \(h_t\)，生成中间推理轨迹 \(Think_t\)，并判断是否足够回答；若不够，则选择最大化信息增益的动作 \(a_t\)，执行后获得新观测，更新历史，直到回答或达到最大步数。
- **关键技术要素**：
  - **主动信息获取**：通过物理交互（抓取、移动、开启抽屉、改变视角）主动获取缺失信息。
  - **时序视觉整合**：融合多步观测进行连贯推理。
  - **动态决策**：基于当前理解持续调整信念和动作，减少不确定性。

### 关键组件
- **CLEVR-AVR 基准**：基于Genesis物理仿真平台，包含3种场景类型（遮挡、堆叠、复合），10种遮挡、10种堆叠和10种复合场景。动作空间包括Pick、MoveViewer、RotateViewer、MoveObject。问题类型包括Query、Exist、Count、Compare、MathCount、MathCompare等。平均每个问题需至少2步推理，部分需4-6步。
- **AVR-152k 数据集**：
  - 包含三个子集：AVR-Caption（100k样本，密集字幕+边界框）、AVR-Embodied Reasoning（50k样本，多图像序列+问题+CoT推理链）、AVR-Core（2k样本，核心AVR任务）。
  - AVR-Core 以更高阶MDP建模，每步提供专家标注的Chain-of-Thought（CoT）注释，包括：①评估当前信息不确定性；②预测动作条件的信息增益；③选择信息量最大的动作或给出最终答案。CoT由人类专家初始撰写，再经Gemini精炼。
- **PhysVLM-AVR 模型**：基于LLaVA架构，采用Qwen2.5-3B作为LLM解码器、SigLIP-400M作为视觉编码器。引入最大池化层减少视觉token数量（3倍压缩），支持高效多图像推理。训练策略分三个阶段：特征对齐 → 单图像+多图像理解 → 通用推理+主动视觉推理。

## 3. 实验设计：数据集、基准与对比方法

### 使用数据集/场景
- **CLEVR-AVR**：专为AVR设计，基于Genesis仿真，确保训练集不包含类似图像。
- **OpenEQA**：具身问答基准（7个子任务）。
- **RoboVQA**：机器人长期推理基准。
- **GeoMath** 和 **Geometry3K**：静态视觉结构推理（几何数学）基准。

### 对比方法
- **开源MLLM**：Qwen2.5-VL-7B, LLaVA-OV-7B
- **视觉推理MLLM**：R1-Onevision-7B, Reason-RFT-7B
- **具身MLLM**：Embodied-Reasoner-7B, RoboBrain-7B
- **API模型**：GPT-4o, Gemini-2.0-flash
- 此外，作者还在Qwen2.5-VL-7B上微调得到AVR-Qwen2.5-VL-7B作为对比。

### 评估指标
- CLEVR-AVR：信息充分性判断准确率（ACC_ISJ）、信息增益率（IGR）、最终答案准确率（ACC_FA）。
- OpenEQA：LLM-score（GPT-4o作为评估器）。
- RoboVQA：BLEU1-4分数。

## 4. 资源与算力

- 论文在**附录C**中提到实验使用 **8 × NVIDIA A800 GPU** 进行训练，主要软件环境为PyTorch 2.6.0、Transformers 3.72.0、Flash Attention 2和DeepSpeed。
- **未明确说明**具体的训练时长、总GPU小时数或每个阶段的训练时间。因此，无法进一步量化算力消耗的细节。

## 5. 实验数量与充分性

- **实验组数**：
  - CLEVR-AVR主实验（表1）：对比8种基线模型+2个作者模型，共10个方法，在3种场景（遮挡、堆叠、复合）上报告3个指标，共30个数据点。
  - 具身推理（OpenEQA、RoboVQA）和视觉推理（GeoMath、Geometry3K）的对比实验（图4）：展示了多个子任务上的性能曲线。
  - 消融实验（表2）：对比完整模型、去掉CoT、去掉整个AVR-Core，共3组，在CLEVR-AVR上报告3个指标。
- **充分性与公平性**：
  - 覆盖了主动推理、具身推理、静态推理三大类任务，具有较好的泛化性验证。
  - 对比基线包括同规模模型、专用于推理/具身的模型以及API模型，比较全面。
  - CLEVR-AVR基准确保了训练与测试场景不重叠，避免了数据泄露。
  - 消融实验清晰证明了AVR-Core及CoT注释的关键贡献。
  - 不足：缺乏对更复杂真实场景的大规模用户研究；CLEVR-AVR场景相对受控，现实复杂性有限。

## 6. 主要结论与发现

- 现有MLLM（包括开源、推理专用、具身专用模型）在**静态被动设置下表现良好，但在主动交互的AVR环境下几乎失效**（例如，标准开源模型在CLEVR-AVR上ACC_FA近零）。
- 具身模型（如Embodied-Reasoner-7B）能检测到信息不完整（ACC_ISJ ~20%），但**不能有效选择和执行信息获取动作**，导致ACC_FA极低（~1.6%），暴露了“知而不能行”的根本缺陷。
- 提出的PhysVLM-AVR-3B和AVR-Qwen2.5-VL-7B在CLEVR-AVR上取得了最佳或次佳性能，ACC_ISJ达到90%以上，ACC_FA达到约39%，大幅超越其他开源模型，仅次于GPT-4o。
- **主动推理范式训练不仅提升了AVR能力，还泛化到具身推理（OpenEQA、RoboVQA）和静态视觉推理（GeoMath、Geometry3K）**，证实了方法的普遍适用性。
- 消融实验表明**AVR-Core中的CoT注释是不可或缺的**：去掉CoT后ACC_FA从39.7%降至16.9%；去掉整个AVR-Core则ACC_FA降为2.3%。

## 7. 优点

- **任务定义新颖**：针对“部分可观察环境下的主动视觉推理”这一未充分探索的关键问题，明确定义了面向具身智能体的闭环推理范式。
- **基准与数据集全面**：CLEVR-AVR提供了受控但丰富的仿真环境，AVR-152k涵盖感知、时序推理、主动决策三个层次，特别以AVR-Core呈现带细粒度CoT注释的更高阶MDP数据，支持端到端训练和评估。
- **模型设计有效**：PhysVLM-AVR通过多阶段训练策略，仅用3B参数即达到接近GPT-4o的水平，且泛化能力强。
- **实验充分且公正**：跨多种任务类型、多场景、多基线对比，消融实验清晰。
- **对现有方法的剖析深入**：揭示了“信息不完整检测能力”与“主动获取能力”之间的鸿沟，为后续研究指明方向。

## 8. 不足与局限

- **场景限制**：CLEVR-AVR基于仿真环境，物体数量、遮挡类型有限，与现实世界复杂性仍有差距；动作空间（抓取、移动、开关抽屉等）相对简单，缺乏更复杂的工具使用或导航。
- **数据集规模**：AVR-Core仅2k样本，虽精心标注但可能不足以覆盖所有边缘情况；需要更多真实世界交互数据。
- **模型性能上限**：尽管优于开源模型，但与GPT-4o相比仍有明显差距，尤其在最终答案准确率上（PhysVLM-AVR-3B 39.7% vs GPT-4o 45.7%），说明动作选择和多步整合仍需提升。
- **未提及计算开销**：未报告训练时间、推理效率等，不利于复现和实际部署评估。
- **潜在偏差风险**：数据集来源于特定仿真和真实场景（如餐桌、简单桌面），可能引入场景偏差，导致在更开放环境中泛化性有限。
- **伦理声明**：论文在附录中提及了伦理考量，但未具体讨论模型可能产生的负面社会影响（如误导性自主决策），也未提供使用限制的详细说明。

（完）
