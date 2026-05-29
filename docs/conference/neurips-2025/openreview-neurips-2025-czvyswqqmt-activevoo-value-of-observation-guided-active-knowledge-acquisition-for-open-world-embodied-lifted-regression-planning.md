---
title: "ActiveVOO: Value of Observation Guided Active Knowledge Acquisition for Open-World Embodied Lifted Regression Planning"
title_zh: "ActiveVOO: 观察价值引导的主动知识获取用于开放世界具身抬升回归规划"
authors: "Xiaotian Liu, Ali Pesaranghader, Jaehong Kim, Tanmana Sadhu, Hyejeong Jeon, Scott Sanner"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=cZVYswQQMt"
tags: ["query:wm-vla-sa"]
score: 4.0
evidence: 面向开放世界具身规划的主动知识获取
tldr: 开放世界具身规划面临部分可观察性和不完整知识，现有方法多采用被动感知或假设已知目标类别。本文提出ActiveVOO，通过观察价值（Value of Observation）指导智能体主动获取任务相关信息，在复杂家庭环境中显著提升了规划效率与目标达成率。该方法为主动感知在具身规划中的应用提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-czvyswqqmt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1438, \"height\": 719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-czvyswqqmt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1396, \"height\": 977, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-czvyswqqmt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 698, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-czvyswqqmt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 868, \"height\": 406, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-czvyswqqmt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1438, \"height\": 1953, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-czvyswqqmt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1438, \"height\": 214, \"label\": \"Table\"}]"
motivation: 开放世界具身规划需要主动识别与任务相关的对象，现有被动感知方法效率低。
method: 提出ActiveVOO方法，利用观察价值（VoO）指导智能体主动获取信息。
result: ActiveVOO在复杂家庭环境中提升了规划效率。
conclusion: 观察价值引导的主动知识获取是提升开放世界规划性能的有效方法。
---

## Abstract
The ability to actively acquire information is essential for open-world planning under partial observability and incomplete knowledge. However, most existing embodied AI systems either assume a known object category or rely on passive perception strategies that exhaustively gather object and relational information from the environment. Such a strategy becomes insufficient in visually complex open-world settings. For instance, a typical household may contain thousands of novel and uniquely configured objects, most of which are irrelevant to the agent’s current task. Consequently, open-world agents must be capable of actively identifying and prioritizing task-relevant objects to enable efficient and goal-directed knowledge acquisition. In this work, we introduce ActiveVOO, a novel zero-shot framework for open-world embodied planning that emphasizes object-centric active knowledge acquisition. ActiveVOO employs lifted regression to generate compact, first-order subgoal descriptions that identify task-relevant objects, and provides a principled mechanism to quantify the utility of sensing actions based on commonsense priors derived from LLMs and VLMs. We evaluate ActiveVOO on the visual ALFWorld benchmark, where it achieves substantial improvements over existing LLM- and VLM-based planning approaches, notably outperforming VLMs fine-tuned on ALFWorld data. This work establishes a principled foundation for developing embodied agents capable of actively and efficiently acquiring knowledge to plan and act in open-world environments.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：开放世界环境下，具身智能体面临部分可观测性和不完整的任务相关知识。传统方法要么假设已知对象类别，要么采用被动感知策略（如穷尽收集所有对象和关系信息），这在视觉复杂、对象繁多且大部分与任务无关的家庭场景中变得低效甚至不可行。
- **整体含义**：智能体需要**主动识别并优先获取与当前任务相关的对象信息**，以实现目标导向且高效的知识获取，从而在开放世界中生成可行规划。为此，论文提出了ActiveVOO框架，旨在通过原则性的决策量化解耦“哪些对象相关”和“如何优先感知”两个子问题。

## 2. 论文提出的方法论

- **核心思想**：结合**提升回归（Lifted Regression）**与**观察价值（Value of Observation，VOO）**，以对象为中心的主动知识获取。首先通过向后搜索生成一组**提升子目标**（描述可行世界配置的统一阶公式），接着从子目标中提取**对象和关系描述**，然后利用**LLM/VLM的常识先验**估计感知成功的概率，最后计算每个候选对象的VOO来排序并指导探索与感知。
- **关键技术细节**：
    1. **提升回归生成子目标**：从自然语言目标解析为PDDL符号目标，通过向后回归（Lifted Backward Search）获得一系列提升子目标-计划对 $(g_i, \pi_i)$。
    2. **对象/关系描述提取**：从每个子目标的合取式中提取每个变量的**一元谓词集**作为对象描述，以及**多元谓词**作为关系描述。
    3. **信念概率估计**：通过LLM对“是否存在某个对象满足描述”等问题的logits，采用softmax计算概率 $p_o$ 和 $p_{\rho}$。
    4. **VOO计算**：将知识状态建模为MDP，定义效用 $U(s) = \max_g \prod_{o\in\text{unk}(g,s)} p_o \cdot \prod_{\rho\in\text{unk}(g,s)} p_{\rho}$，则VOO为 $\text{VOO}_o(s) = p_o [U(s'_+) - U(s'_-)]$，表示主动感知o带来的预期效用增益。
    5. **主动感知循环**：每步选择VOO最高的对象描述作为探索目标，由LLM建议探索位置，VLM在观测图像中检测该对象并更新知识状态，直到某个子目标被满足，然后执行对应计划。
- **算法流程**：见Algorithm 2，包括初始化、循环计算VOO、探索、对象观察、子目标满足检查及计划执行。

## 3. 实验设计

- **数据集/场景**：使用**ALFWorld**模拟器，包含视觉输入的家庭环境任务（Pick、Clean、Heat、Cool、Look、Pick2共6类）。智能体仅接收原始RGB图像和自然语言指令，无分步指导。
- **基准（Benchmark）**：ALFWorld的视觉版本，要求智能体在30步内完成任务，评价指标为**成功率**（平均3次运行）。
- **对比方法**：
    - **纯视觉模型**：MCNN-FPN、ResNet-18（需任务特定微调）。
    - **纯语言模型（文本输入）**：GPT-4o (Text)、ReAct、Reflexion（3和10次尝试）、DEPS、AutoGen。
    - **视觉语言模型**：BUTLER（微调）、GPT-4o (Vision)（零样本）、LLaVA-13B（零样本）、LLaMA-Adapter、InstructBLIP、EMMA（需多轮和微调）。

## 4. 资源与算力

- 文中说明：所有实验在 **6核AMD CPU + 32GB RAM** 上运行，**依赖API调用**（GPT-4o用作LLM和VLM，LLaVA-13B用于替换实验，GPT-3.5用于替换实验）。
- **未明确提供**：GPU型号（推测未使用本地GPU）、训练时长（方法为**零样本**，无需训练，仅推理阶段）。因此计算资源需求较低，但具体API调用次数和耗时未量化。

## 5. 实验数量与充分性

- **主要实验**：表1报道了**6个任务**的**平均成功率**，每个任务进行**3次独立运行**取平均。对比了**13个基线**，涵盖不同范式和资源需求（零样本/微调、单次/多轮）。
- **消融实验**（表2）：包含**7类消融分析**：
    - 消融主动知识获取：对比穷举对象、目标导向对象、LLM子目标对象三种被动策略。
    - 消融VOO计算：对比无VOO（仅用最高信念概率）、无VOO+无对象划分。
    - 更换组件：替换VLM为LLaVA-13B、替换LLM为GPT-3.5。
- **充分性**：实验覆盖了多种竞争设置，消融设计合理，结果客观展示了每个组件的贡献。但仅在一个模拟器（ALFWorld）上评估，且未报告置信区间或多次随机种子细节（仅有3次平均），因此**泛化性有限**。

## 6. 论文的主要结论与发现

- ActiveVOO在视觉ALFWorld上取得 **86% 的平均成功率**，显著优于所有基线，包括需要大规模微调的模型（如EMMA-10约82%）以及零样本VLM（如GPT-4o Vision仅8%）。
- **主动知识获取**极大地提升了效率：被动穷举策略仅22%成功率，而VOO引导的主动策略达到86%。
- **提升回归**生成的结构化子目标比LLM直接生成计划（47%）更可靠。
- **VOO**的量化机制是性能关键：移除后成功率降至75%，且平均步数增加。
- 更强的LLM/VLM（GPT-4o vs GPT-3.5/LLaVA-13B）能进一步提升性能，说明常识推理质量直接影响主动感知效果。

## 7. 优点

- **零样本与无需微调**：仅需预定义的动作模型（PDDL），无需任何任务特定训练数据，便于部署到新环境。
- **原则性主动感知**：将主动知识获取形式化为MDP，用VOO进行决策论优化，而非启发式规则。
- **结合符号规划与神经先验**：利用提升回归处理开放世界不确定性，同时用LLM/VLM提供常识概率，实现了结构化与概率推理的有效融合。
- **全面消融验证**：清晰证明了主动策略、VOO、对象划分等各组件的贡献，实验设计公正。

## 8. 不足与局限

- **实验覆盖面窄**：仅在一个模拟器（ALFWorld）上评估，缺乏真实物理环境验证（如机器人硬件），因此**普适性存疑**。
- **模拟-真实迁移挑战**：论文自身承认需要进一步微调才能适配真实场景。
- **未考虑用户偏好**：智能体假设任务目标唯一，未纳入用户或上下文偏好影响效用函数。
- **依赖API与模型能力**：VOO计算依赖LLM/VLM的logits，不同模型（如GPT-3.5）性能下降明显，且API调用成本和时间未讨论。
- **计算效率未量化**：未报告每步推理时间或总执行时长，限制实际应用评估。
- **仅单次运行平均**：三次运行未给出标准差或置信区间，统计显著性有限。

（完）
