---
title: World Model Implanting for Test-time Adaptation of Embodied Agents
title_zh: 面向具身代理测试时适应的世界模型植入
authors: "Minjong Yoo, Jinwoo Jang, Sihyung Yoon, Honguk Woo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=tpbtodnI1p"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 将LLM与世界模型结合的世界模型植入框架，用于具身代理自适应
tldr: 本文提出WorMI（世界模型植入框架），通过测试时组合将大语言模型的推理能力与独立学习的领域世界模型结合，使具身代理能快速适应新领域。采用基于原型的世界模型检索和轨迹抽象表示匹配，实现了高效跨域适应，无需重新训练。为具身AI的鲁棒泛化提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 852, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1631, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 832, \"height\": 959, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 832, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 829, \"height\": 628, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1760, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1590, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1748, \"height\": 299, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1520, \"height\": 603, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 694, \"height\": 527, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 863, \"height\": 436, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 677, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 861, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 832, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1109, \"height\": 586, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 967, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1001, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1195, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1029, \"height\": 1011, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 610, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 756, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 487, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 579, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 704, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 533, \"height\": 422, \"label\": \"Table\"}]"
motivation: 具身代理在新领域适应困难，需大量数据重训练。
method: 将LLM与领域特定世界模型通过测试时组合，利用原型检索和抽象匹配进行植入。
result: 代理在多种新领域实现高效适应，无需额外数据采集。
conclusion: 为具身代理的跨域适应提供了灵活可组合的解决方案。
---

## Abstract
In embodied AI, a persistent challenge is enabling agents to robustly adapt to novel domains without requiring extensive data collection or retraining. To address this, we present a world model implanting framework (WorMI) that combines the reasoning capabilities of large language models (LLMs) with independently learned, domain-specific world models through test-time composition. By allowing seamless implantation and removal of the world models, the embodied agent's policy achieves and maintains cross-domain adaptability. In the WorMI framework, we employ a prototype-based world model retrieval approach, utilizing efficient trajectory-based abstract representation matching, to incorporate relevant models into test-time composition. We also develop a world-wise compound attention method that not only integrates the knowledge from the retrieved world models but also aligns their intermediate representations with the reasoning model's representation within the agent's policy. This framework design effectively fuses domain-specific knowledge from multiple world models, ensuring robust adaptation to unseen domains. We evaluate our WorMI on the VirtualHome and ALFWorld benchmarks, demonstrating superior zero-shot and few-shot performance compared to several LLM-based approaches across a range of unseen domains. These results highlight the framework’s potential for scalable, real-world deployment in embodied agent scenarios where adaptability and data efficiency are essential.

---

## 论文详细总结（自动生成）

# 论文总结：World Model Implanting for Test-time Adaptation of Embodied Agents

## 1. 论文的核心问题与整体含义
**研究动机**：具身AI代理在遇到未见过的领域（新场景、新任务）时，通常需要大量数据收集或重新训练才能适应。传统的LLM-based方法要么依赖上下文学习（检索大量示例，效率低），要么将领域特定模型硬编码进策略（缺乏扩展性）。**核心问题**：如何在不重新训练大模型的情况下，使代理能动态、高效地融合多个领域知识，实现零样本或少样本的跨域自适应。

**整体含义**：本文提出WorMI框架，通过测试时“植入”领域特定的世界模型，并结合LLM的通用推理能力，使得代理策略可以灵活地组合和替换领域知识，从而在多样且未见过的域中保持鲁棒性能，为具身代理的实用化可扩展部署提供了新思路。

## 2. 论文提出的方法论
**核心思想**：将多个预先训练好的领域世界模型（domain-specific world models）与一个固定的LLM推理模型（reasoning model）通过测试时组合（test-time composition）集成。采用双阶段设计：
- **世界到世界的知识融合**：将多个相关世界模型的中间表示通过注意力机制融合。
- **世界到推理的对齐**：将融合后的表示与LLM的推理表示对齐，形成最终策略。

**关键技术细节**：
- **原型化世界模型检索（Prototype-based World Model Retrieval）**：对每个世界模型，从其训练数据集提取对象级状态嵌入，通过k-center聚类获得少量“原型”嵌入。测试时，对当前观察也提取原型，计算Wasserstein距离，选择最相关的K个世界模型。公式：δ(p_i, p_j) ≤ δ(E_i, E_j) + 2ρ（原型距离有界于数据集距离）。
- **世界级复合注意力（World-wise Compound Attention）**：包含线性投影层、世界级交叉注意力、推理级交叉注意力。世界级交叉注意力以LLM的当前隐藏状态作为查询，各世界模型输出作为键值，动态分配权重。推理级交叉注意力则将加权后的世界模型输出与LLM表示进一步对齐。公式：l_πR + Cθ({l_M1,...,l_MK}, l_πR)。
- **元学习训练**：复合注意力模块通过MAML-style元学习训练，内循环在子世界模型集和数据集上适应，外循环更新元参数，使模块能快速适应新领域。

**算法流程**（文字描述）：
1. 预训练N个世界模型，每个在各自领域数据集上通过动态预测、动作可行性、行为克隆三个辅助任务训练。
2. 元学习阶段：随机采样世界模型子集，对每个子集进行内循环梯度更新（使用行为克隆损失L = -log π(a|s)），外循环合并参数。
3. 测试阶段：对当前状态提取原型，检索K个最相关世界模型，通过复合注意力将其融合进推理模型，得到动作。

## 3. 实验设计
- **数据集/场景**：
  - VirtualHome：3D家庭仿真环境，78个任务（16个训练可见，62个测试不可见），20个场景（6个训练可见，14个测试不可见），收集1023条轨迹。
  - ALFWorld：文本交互室内仿真，3554条轨迹，按CL-ALFRED设定分为4种场景（3可见+1不可见）和6种任务类型（4可见+2不可见）。
- **Benchmark**：零样本（训练域数据+未见域测试）和少样本（每个未见域提供1/5/10条演示）。
- **对比方法**：
  - ZSP（零样本直接使用预训练LLM）
  - LLM+FT（微调LLM在少量域数据上）
  - LLM-Planner（通过检索示例进行上下文学习）
  - SayCanPay（将LLM与可学习成本模型集成）
- **评估指标**：成功率（SR）和待处理步骤数（PS，类似代价效率）。

## 4. 资源与算力
论文**未明确说明**使用的GPU型号、数量及训练总时长。仅在附录C给出了超参数：世界模型训练使用学习率3e-5，梯度步2000；复合注意力元学习使用学习率1e-5，元学习率1e-1，内环梯度步30，元更新步8；推理模型固定使用Llama-3.2-3B（也可扩展到11B）。可推测在消费级或单/多GPU环境下运行，但具体算力资源未公开。

## 5. 实验数量与充分性
- **主要实验**：零样本（表1）和少样本（表2）对比四个基线，在VirtualHome和ALFWorld两个数据集上，覆盖三种难度（seen tasks/scenes, unseen tasks/scenes）。
- **消融实验**：针对原型化检索（全选/随机选 vs 原型选择，表3a）和复合注意力（拼接/求和 vs 复合注意力，表3b）。
- **附加分析**：
  - LLM规模影响（1B/3B/11B，表4）
  - 世界模型数量影响（1-6个，表5）
  - 复杂指令场景（长程、多指令，表6）
  - 持续模型植入（逐步添加/移除世界模型，图5）
  - 注意力可视化（图4）
  - 鲁棒性/可扩展性分析（附录表A.9-A.12）
- **充分性评价**：实验覆盖全面，从性能、效率、可扩展性、鲁棒性多个角度验证。所有结果均报告95%置信区间（5个随机种子）。对比的基线涵盖主流方法，且所有方法使用相同基础模型（Llama-3.2系列）。**因此实验设计客观、公平，充分证明了WorMI的优势。**

## 6. 论文的主要结论与发现
- **零样本性能**：在VirtualHome和ALFWorld上，WorMI在未见任务和场景下分别比最强的基线SayCanPay高出20.41%和12.01%的成功率，同时减少步骤。
- **少样本性能**：在1/5/10-shot设置下，WorMI平均高出SayCanPay 26.58%和19.16%的SR，说明数据效率高。
- **关键设计有效性**：原型化检索和复合注意力均显著优于随机选择/全选、拼接/求和等变体；复合注意力能动态聚焦相关领域世界模型。
- **可扩展性与鲁棒性**：世界模型数量在2-4个时性能最优，多于或少于都下降；持续模型植入支持知识灵活增删；对不同规模LLM均优于基线。
- **复杂任务**：在处理长程指令和多任务时，WorMI的GC和PS指标也显著领先。

## 7. 优点
- **方法创新**：首次提出通过测试时“植入”多个世界模型到LLM策略中，实现了双阶段（世界-世界融合+世界-推理对齐）的知识集成。
- **高效率**：原型化检索大幅降低计算开销（仅用0.1%的嵌入数量），复合注意力模块的元学习使得少样本适应只需少量梯度步。
- **灵活性**：世界模型可以随时添加或移除（持续模型植入），无需重新训练推理模型。
- **实验设计严谨**：多个数据集、多种难度设置、多个消融/敏感性分析，置信区间报告，对比方法公平。
- **跨模态适用性**：论文附录展示了多模态版本（VLM作为推理模型）的潜力，性能略降但仍优于基线。

## 8. 不足与局限
- **计算开销**：尽管使用了原型检索，但推理时仍需要同时运行多个世界模型（每个约1B参数）和复合注意力，对资源受限设备可能造成压力。
- **依赖LLM能力**：整体性能受限于底层LLM的推理质量（从表4可见随LLM规模增大，增益更明显，但本身也依赖其推理能力）。
- **实验覆盖**：仅在两个仿真环境（VirtualHome、ALFWorld）上验证，缺乏真实机器人实验结果。另外，任务类型有限（主要是家务操作），未涵盖更复杂的多代理或连续控制场景。
- **世界模型训练假设**：论文假设已具备每个领域的预训练世界模型，但在实际中构建这些模型也需要数据收集和计算资源。
- **检索的潜在偏差**：原型依赖对象级状态，若目标领域对象类型与已有领域差异极大，检索可能失效（论文未讨论极端新对象情况）。
- **未详细分析失败案例**：虽然提供了注意力图分析，但未系统讨论失败模式，例如检索错误或融合失效的情况。

（完）
