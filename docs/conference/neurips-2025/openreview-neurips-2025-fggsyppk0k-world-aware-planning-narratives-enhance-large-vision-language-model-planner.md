---
title: World-aware Planning Narratives Enhance Large Vision-Language Model Planner
title_zh: 世界感知规划叙事增强大视觉语言模型规划器
authors: "Junhao Shi, Zhaoye Fei, Siyin Wang, Qipeng Guo, Jingjing Gong, Xipeng Qiu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=fggSyPPk0K"
tags: ["query:wm-vla-sa"]
score: 8.0
evidence: 面向具身智能体的世界感知规划，世界模型融合
tldr: 该论文针对大视觉语言模型在具身规划任务中对环境理解不足的问题，提出世界感知规划叙事增强框架（WAP）。WAP通过注入视觉外观建模、空间推理、功能抽象和语法基础四种认知能力，使模型在复杂多步任务中有效利用环境上下文进行规划。实验表明，该方法显著提升了模型在不熟悉环境中的规划成功率，为世界模型在具身智能中的应用提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-fggsyppk0k/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1402, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fggsyppk0k/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1416, \"height\": 1082, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-fggsyppk0k/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1474, \"height\": 1420, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fggsyppk0k/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1410, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fggsyppk0k/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1260, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fggsyppk0k/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1477, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fggsyppk0k/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1454, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fggsyppk0k/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 989, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fggsyppk0k/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1223, \"height\": 185, \"label\": \"Table\"}]"
motivation: 当前大视觉语言模型在具身规划任务中缺乏对环境的全面理解，导致复杂长时程规划表现不佳。
method: 提出世界感知规划叙事增强框架，通过四种认知能力注入（视觉外观、空间推理、功能抽象、语法基础）强化模型的环境理解。
result: 在多个具身规划基准上显著提升规划成功率，尤其在不熟悉环境中表现突出。
conclusion: 世界感知的规划叙事增强是提升视觉语言模型具身规划能力的有效途径。
---

## Abstract
Large Vision-Language Models (LVLMs) show promise for embodied planning tasks but struggle with complex scenarios involving unfamiliar environments and multi-step goals. 
Current approaches rely on environment-agnostic imitation learning that disconnects instructions from environmental contexts, causing models to struggle with context-sensitive instructions and rely on supplementary cues rather than visual reasoning during long-horizon interactions.
In this work, we propose World-Aware Planning Narrative Enhancement (WAP), a framework that infuses LVLMs with comprehensive environmental understanding through four cognitive capabilities (visual appearance modeling, spatial reasoning, functional abstraction, and syntactic grounding) while developing and evaluating models using only raw visual observations through curriculum learning.
Evaluations on the EB-ALFRED benchmark demonstrate substantial improvements, with Qwen2.5-VL achieving a 60.7 absolute improvement in task success rates—particularly in commonsense reasoning (+60.0) and long-horizon planning (+70.0). Notably, our enhanced open-source models outperform proprietary systems like GPT-4o and Claude-3.5-Sonnet by a large margin.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与研究动机
- **背景**：大视觉语言模型（LVLMs）在具身规划任务中展现出潜力，但面对不熟悉的环境、多步目标等复杂场景时表现不佳。
- **核心问题**：现有方法依赖于“环境无关的模仿学习”（environment-agnostic imitation learning），将任务指令与环境上下文割裂，导致模型无法理解视觉外观、空间关系、物体功能、语义消歧等关键认知能力，在长时程交互中依赖辅助线索（如动作反馈）而非纯粹的视觉推理。
- **整体目标**：提出一种**世界感知规划叙事增强（WAP）**框架，使LVLMs在仅使用原始视觉观察和自然语言指令（闭环控制）的情况下，获得全面的环境理解能力，从而提升复杂规划任务的成功率。

## 2. 方法论
### 2.1 核心思想
- 通过多维度增强指令和逐步推理生成，使模型内化四种认知能力：
  - **视觉外观建模**：捕捉物体纹理、形状、颜色等属性。
  - **空间关系推理**：理解物体相对位置和房间布局。
  - **功能抽象学习**：掌握工具-物体关系及符号化表示。
  - **语法基础（Syntactic Grounding）**：解读复杂语言，消解歧义。
- 采用**课程学习（Curriculum Learning）**策略分阶段训练，逐步增加认知复杂度。

### 2.2 关键技术细节
- **指令增强（Instruction Augmentation）**：使用更强的教师模型（Qwen2.5-VL-72B-Instruct）基于原始指令和最终观察图像，生成四个维度的增强指令（视觉、空间、功能、语法）。每个增强指令通过语义一致性验证（要求5次验证中至少4次认为与原始指令等价）以确保任务等价性。
- **逐步推理生成（Stepwise Reasoning Generation）**：对于每个动作步骤，生成自然语言推理过程，解释为何该动作在当前观察下合理，作为中间监督信号。
- **课程学习框架**：
  - 阶段1（Base）：使用原始指令-轨迹对训练，建立基础动作映射。
  - 阶段2（Environment Understanding）：加入视觉和空间增强数据，发展感知基础和场景理解。
  - 阶段3（Conceptual Reasoning）：加入功能和语法增强数据，发展高阶推理。
- **公式**：优化目标为交叉熵损失，在三个阶段数据集上依次微调：\(\Theta^* = \arg\min_{\Theta} \sum_{s=1}^3 \mathbb{E}_{(\tau, I) \sim D_s} \mathcal{L}_{\text{CE}}(f_\Theta(\{o_{1:t}\}, I), a_t)\)。

### 2.3 算法流程（文字说明）
1. 输入：原始指令I、专家轨迹τ（包含动作序列和观测图像）。
2. 使用教师模型M按照四种维度提示策略生成增强指令\(\tilde{I}_k\)。
3. 通过验证函数筛选语义一致的增强指令。
4. 为每个动作at生成推理rt，形成增强数据集。
5. 按照三阶段课程顺序训练学生模型fΘ，每个阶段仅在对应子集上微调。

## 3. 实验设计
### 3.1 数据集与Benchmark
- **数据集**：基于ALFRED数据集中的16,145条原始轨迹，通过多维度增强扩展为80,875条指令-轨迹对。
- **Benchmark**：EmbodiedBench中的EB-ALFRED任务套件，包含六类子任务（Base, Common, Complex, Visual, Spatial, Long），评估标准为成功率（SR）和标准差（STD）。
- 额外在VOTA-Bench的未见环境分割上测试泛化能力。

### 3.2 对比方法
- **闭源模型**：GPT-4o、Claude-3.5-Sonnet、Gemini-1.5-Pro、Gemini-2.0-flash等。
- **开源模型**：InternVL2.5系列、Qwen2.5-VL系列、Llama-3.2-Vision系列等。
- **消融变体**：
  - 基础模型（无增强）
  - 仅添加原始推理
  - +WAP增强（无课程）
  - +课程学习（完整WAP）

### 3.3 实验分组
- 主实验：在标准闭环设置下（仅视觉观察，无行动反馈）比较所有模型。
- 消融实验：逐步移除课程学习、逐步推理、WAP指令增强，观察性能变化。
- 自导向增强实验：模型自主选择增强策略，对比显式课程。
- 模态影响实验：对比单图像与完整观测历史。
- 教师模型规模实验：使用7B、32B、72B教师生成增强数据。
- 泛化实验：在VOTA-Bench未见环境上测试。

## 4. 资源与算力
- **训练算力**：
  - 指令增强：4×H100 GPU，约20 GPU小时。
  - 推理增强：4×H100 GPU，约200 GPU小时。
  - 模型微调：8×H100 GPU，约100 GPU小时。
  - 总计约320 H100 GPU小时（不含调优和消融的额外开销）。
- **训练细节**：使用AdamW优化器，学习率1e-5，余弦衰减，3个epoch，每设备batch size 4，分布式训练于8×A100-80GB节点（14小时），Flash Attention v2与BF16混合精度。

## 5. 实验数量与充分性
- **实验数量**：共进行了7组对比实验（主实验、消融、自导向、模态、教师规模、泛化、案例研究），每组内包含多个子实验。
- **充分性**：消融实验完整覆盖了框架的每个关键组件（课程、推理、指令增强），验证了各部分的贡献。对比了多类闭源/开源模型，包括更难的闭环设置。额外在VOTA-Bench上验证了跨环境泛化，说明实验设计较为全面、客观。
- **公平性**：所有对比模型在相同评估协议下测试，并明确指出闭源模型在更难的闭环设置下表现下降（如GPT-4o），但本文方法保持稳定。消融实验从完整框架逐步移除模块，避免了因果混淆。

## 6. 主要结论与发现
- **显著性能提升**：在EB-ALFRED上，Qwen2.5-VL-7B从4.67% SR提升至62.67%，绝对提升60.7%。常识推理（+60.0）和长时程规划（+70.0）提升最突出。
- **超越闭源模型**：增强后的开源模型在闭环设置下优于GPT-4o和Claude-3.5-Sonnet（平均SR 62.7 vs 57.3和26.0）。
- **课程学习降低性能方差**：完整WAP的STD为6.3，远低于基础推理（14.0），表明能力更均衡。
- **逐步推理至关重要**：去除逐步推理后，性能大幅下降（尤其常识推理从62降至16），表明维持环境-动作耦合推理是关键。
- **WAP指令增强主要有利于复杂和长时程任务**：移除WAP后，Complex和Long任务下降，但Common略微恢复，说明WAP在缺乏推理链时会放大不平衡。
- **闭源模型的局限性**：GPT-4o在闭环下长时程任务仅24%成功，而本文方法达70%，表明环境建模对长时程规划不可或故。

## 7. 优点
- **方法论创新**：首次系统地将四种认知能力（视觉、空间、功能、语法）融入具身规划，并通过课程学习逐步构建，符合认知发展理论。
- **贴近实际部署**：仅使用原始视觉观察和自然语言，无任何特权反馈（如动作成功信号、任务进度），更具真实机器人应用价值。
- **全面的实验验证**：包含多种消融、泛化、教师模型规模实验，结论稳健。
- **开源贡献**：增强数据集和代码将公开，促进后续研究。
- **透明度高**：提供了推理过程的可视化案例，展示了模型如何分解隐含步骤（如“冷藏苹果”）。

## 8. 不足与局限
- **缺少连续控制建模**：框架仅限于符号动作层面（如“拿起刀”），未建模连续控制参数，需与低级控制器集成才能实际部署。
- **场景局限性**：仅在ALFRED家庭环境上验证，未测试工业/户外动态障碍场景，泛化性存疑。
- **缺乏执行中错误修正**：主要关注指令增强和逐步推理，未设计动态的错误恢复机制。
- **计算成本较高**：教师模型生成增强数据需要约220 GPU小时（推理增强占大头），对资源有限的研究团队有门槛。
- **潜在偏差**：增强数据依赖教师模型（Qwen2.5-VL-72B），其偏见可能影响学生模型；语义一致性验证阈值（4/5）可能过于严格或宽松，未深入分析。
- **基准对比局限**：与其他闭源模型的对比仅在更高的闭环设置下进行，未完全对齐原文献的评估条件（需读者自行推断）。

（完）
