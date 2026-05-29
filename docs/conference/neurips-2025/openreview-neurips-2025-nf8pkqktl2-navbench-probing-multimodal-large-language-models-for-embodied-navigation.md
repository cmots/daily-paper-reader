---
title: "NavBench: Probing Multimodal Large Language Models for Embodied Navigation"
title_zh: NavBench：探针多模态大语言模型的具身导航能力
authors: "Yanyuan Qiao, Haodong Hong, Wenqi Lyu, Dong An, Siqi Zhang, Yutong Xie, Xinyu Wang, Qi Wu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=nf8PKQKtl2"
tags: ["query:wm-vla-sa"]
score: 4.0
evidence: 基于多模态大语言模型的具身导航基准
tldr: NavBench提出了一个评估多模态大语言模型具身导航能力的基准，包含导航理解与逐步执行两部分。通过全局指令对齐、时间进度估计、局部观测动作推理等认知任务以及432个场景的交互执行，揭示了当前模型在零样本导航中的表现与不足，为VLA模型的研究提供了标准测试平台。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-nf8pkqktl2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1387, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nf8pkqktl2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1425, \"height\": 530, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nf8pkqktl2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1450, \"height\": 493, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nf8pkqktl2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1453, \"height\": 273, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nf8pkqktl2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 462, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nf8pkqktl2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 699, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nf8pkqktl2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 691, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nf8pkqktl2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 473, \"height\": 224, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-nf8pkqktl2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 743, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nf8pkqktl2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 710, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nf8pkqktl2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 284, \"label\": \"Table\"}]"
motivation: 多模态大语言模型在视觉语言任务中泛化能力强，但其在具身导航中的理解与行动能力尚未充分探索。
method: "提出NavBench基准，包含导航理解（3,200问答对）和逐步执行（432集、72室内场景）两部分，分层评估空间、认知和执行复杂度。"
result: 实验揭示了MLLMs在导航理解与执行上的表现，分析了不同复杂度下的能力边界。
conclusion: NavBench为评估MLLMs具身导航能力提供了标准化工具，有助于推动VLA模型发展。
---

## Abstract
Multimodal Large Language Models (MLLMs) have demonstrated strong generalization in vision-language tasks, yet their ability to understand and act within embodied environments remains underexplored. We present NavBench, a benchmark to evaluate the embodied navigation capabilities of MLLMs under zero-shot settings. NavBench consists of two components: (1) navigation comprehension, assessed through three cognitively grounded tasks including global instruction alignment, temporal progress estimation, and local observation-action reasoning, covering 3,200 question-answer pairs; and (2) step-by-step execution in 432 episodes across 72 indoor scenes, stratified by spatial, cognitive, and execution complexity. To support real-world deployment, we introduce a pipeline that converts MLLMs' outputs into robotic actions. We evaluate both proprietary and open-source models, finding that GPT-4o performs well across tasks, while lighter open-source models succeed in simpler cases. Results also show that models with higher comprehension scores tend to achieve better execution performance. Providing map-based context improves decision accuracy, especially in medium-difficulty scenarios. However, most models struggle with temporal understanding, particularly in estimating progress during navigation, which may pose a key challenge.

---

## 论文详细总结（自动生成）

# NavBench：探针多模态大语言模型的具身导航能力 —— 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：多模态大语言模型（MLLMs）在静态视觉语言任务中表现优异，但其在物理世界中能否真正理解并执行导航行为（而非仅仅处理静态输入）尚未被充分探索。
- **核心问题**：现有的具身导航基准（如R2R、ObjectNav）主要依赖任务特定监督和最终成功率，无法揭示模型是否真正理解导航意图、能否进行时间推理和逐步决策。此外，不同导航任务的难度差异（空间、认知、执行复杂度）未被系统区分。
- **整体含义**：该工作旨在建立一个系统化的基准（NavBench），从“导航理解”和“导航执行”两个维度全面评估MLLMs在零样本设置下的具身导航能力，并引入难度分层以揭示能力边界。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：将具身导航能力分解为两个互补部分：
  - **导航理解**：通过三个认知任务测试模型对导航行为的理解（全局指令对齐、时间进度估计、局部观测-动作推理），共3200个问答对。
  - **导航执行**：在Matterport3D模拟器中让模型逐步选择下一个视点，评估其决策能力，共432个场景（72个室内场景），并按难度分层（简单/中等/困难）。
- **关键技术细节**：
  - **导航理解任务**：
    - *全局指令对齐*：给定全景轨迹和五个候选指令（含四个干扰项：基础无关、方向替换、物体替换、子指令打乱），模型选择正确指令（1200样本）。
    - *时间进度估计*：给定部分轨迹和子指令列表，模型预测最后完成的子指令序号（1000样本）。
    - *局部观测-动作推理*：两种变体——给定当前视图和动作预测未来视图；给定连续两帧预测导致过渡的动作（各500样本，共1000样本）。
  - **导航执行任务**：每个时间步，模型接收全景观测、自然语言指令和候选导航视点，输出下一步选择的视点，直到到达目标。评估指标为成功率（SR）和路径长度加权成功率（SPL）。
  - **难度分类**：从三个维度计算复杂度得分（每个维度归一化到1-9）：
    - 空间复杂度：路径长度、转角标准差、高程变化、2D覆盖面积。
    - 认知复杂度：指令长度、动词数、空间词数、地标提及数、从句数。
    - 执行复杂度：步数、转弯次数、楼层变化、决策点数量。
    - 最终将得分映射为三档：easy（1-3）、medium（4-6）、hard（7-9）。
  - **真实世界部署管道**：包含路点预测器、MLLM决策模块和低级控制器，将模型输出转化为真实机器人动作。
- **公式**：各复杂度得分公式如：
  - Φ_spatial = α1·log(1+d) + α2·log(1+θ) + α3·I(z>1.5) + α4·log(1+A)
  - Φ_cognitive = β1·log(1+L) + β2·log(1+V) + β3·log(1+S) + β4·log(1+M) + β5·C
  - Φ_execution = γ1·log(1+N) + γ2·log(1+T) + γ3·F + γ4·D

## 3. 实验设计：数据集/场景、基准、对比方法

- **数据集与场景**：
  - 导航理解数据来自R2R、RxR、GEL-R2R、FGR2R等基准，经重新组织和视觉渲染得到3200个问答对。
  - 导航执行使用Matterport3D模拟器，从72个场景中抽样432个导航案例，覆盖不同难度。
  - 真实世界实验在室内实验室环境进行，使用双臂移动机器人（Intel RealSense D435相机、Water Drop 2轮式底盘）。
- **对比方法**：
  - 闭源模型：GPT-4o、GPT-4o-mini、Gemini-2.0-flash、o4-mini。
  - 开源模型：InternVL2.5-2B/8B、Qwen2.5-VL-3B/7B、LLaVA-OneVision-7B、LLaVA-Next-7B、Llama3.2-Vision-11B。
  - 还包括随机基准和人类水平（在VLN-Bench(tiny)子集上评估）。
- **评估指标**：
  - 理解任务：准确率（Accuracy）。
  - 执行任务：成功率（SR）、路径长度加权成功率（SPL）。

## 4. 资源与算力

- **计算资源**：
  - 开源模型使用**单个NVIDIA A6000 GPU（48GB）**进行推理，通过vLLM和lmdeploy部署。
  - 闭源模型通过API访问。
  - 模拟器基于Matterport3D，无需额外训练。
  - 论文未提及训练时长（因为所有模型均为预训练模型，零样本评估），也未提及完整的GPU使用总时长。

## 5. 实验数量与充分性

- **实验数量**：
  - 导航理解：共3200个问答对，涵盖三个子任务（1200+1000+1000）。
  - 导航执行：432个导航 episodes，每个场景6个案例（72场景×6）。
  - 对比了8种MLLMs（含多个变体），覆盖闭源和开源。
  - 额外进行消融实验：
    - 地图信息影响（Table 2）。
    - Chain-of-Thought（CoT）提示影响（Table 3）。
    - 干扰项类型分析（Figure 6）。
    - 局部推理子任务分析（Figure 7）。
    - 误差分析（Figure 8）。
  - 真实世界验证：GPT-4o和Qwen2.5-VL-7B各10个案例。
- **充分性与公平性**：
  - 实验设计较为全面：多模型、多任务、多难度、多消融。
  - 使用标准指标（SR、SPL、Accuracy），确保可比性。
  - 随机基准和人类水平提供了上下界。
  - 但未提供统计显著性检验或误差条，且真实世界实验规模较小（各10例）。

## 6. 论文的主要结论与发现

- **总体趋势**：
  - 导航理解与执行能力高度相关：理解得分高的模型执行表现也更好。
  - **时间推理**（进度估计、指令时序）是当前MLLMs的主要瓶颈，所有模型在该任务上表现较差。
- **模型表现**：
  - 闭源模型中GPT-4o综合最优（执行平均41.33% SR），o4-mini理解最强（59.66%），但执行稍弱。
  - 开源模型中Qwen2.5-VL-7B最佳（理解45.26%，执行21.77%），接近GPT-4o-mini。
  - 轻量模型在简单任务中可靠，适合资源受限场景。
- **地图信息**：提供地图上下文可提升决策准确率，尤其在中难度场景（+4.51% avg）。
- **CoT提示**：对全局指令对齐有帮助，但对其他理解任务和执行任务无显著提升。
- **难度影响**：大部分开源模型只能在简单场景下成功，GPT-4o在所有难度保持较好表现。
- **误差类型**：主要包括错误计划、动作不对齐、停止失败、幻觉移动，其中停止失败与进度估计瓶颈一致。

## 7. 优点：方法或实验设计上的亮点

- **系统化分解**：将具身导航能力分为理解和执行，设计多层次的认知任务，提供更细粒度的诊断信息，超越传统成功率指标。
- **难度分层**：基于空间、认知、执行三个维度自动计算复杂度，并辅以人工验证，使评估更贴近真实复杂度变异。
- **真实世界管道**：不仅限于模拟器，还开发了从MLLM输出到机器人动作的完整管道，验证了模拟结果的可迁移性。
- **多维度分析**：包括干扰项类型分析、局部推理子任务、地图影响、CoT影响、误差分类等，提供了丰富的洞察。
- **开源与闭源全面覆盖**：评估了当前主流MLLMs，结果具有广泛参考价值。

## 8. 不足与局限

- **实验充分性**：
  - 未报告统计显著性（误差条、置信区间），缺乏对结果稳定性的量化。
  - 真实世界验证样本量小（每模型10例），可能不足以反映一般性。
  - 导航执行任务基于离散视点选择，未涉及低层连续控制（如转向、前进），与现实部署仍有差距。
- **模型偏差**：
  - 时间推理任务的设计可能对某些模型不够友好（如指令分段注释来自FGR2R，可能存在噪声）。
  - 干扰项生成策略可能未完全排除浅层线索（如语言模式）。
- **应用限制**：
  - 所有模拟场景来自Matterport3D（真实室内扫描），但场景多样性有限（72个室内环境）。
  - 零样本设置下，模型未进行任何微调，对于特定领域任务可能泛化不足。
  - 论文未讨论隐私、安全和公平性问题（如对于不同环境布局的潜在偏见）。
- **方法局限**：
  - 难度分层权重（α、β、γ）为经验设定，缺乏理论或数据驱动调优。
  - 理解任务中的进度估计仅依赖部分轨迹，未考虑可能的回溯或歧义。

（完）
