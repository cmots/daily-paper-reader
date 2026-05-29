---
title: "ThinkAct: Vision-Language-Action Reasoning via Reinforced Visual Latent Planning"
title_zh: ThinkAct：通过强化视觉潜在规划进行视觉-语言-动作推理
authors: "Chi-Pin Huang, Yueh-Hua Wu, Min-Hung Chen, Yu-Chiang Frank Wang, Fu-En Yang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=72UR53jN7T"
tags: ["query:wm-vla-sa"]
score: 8.0
evidence: 通过强化视觉潜在规划进行VLA推理
tldr: 本文提出ThinkAct，一个双系统VLA框架，结合高层推理和低层动作执行。它训练多模态LLM生成具身推理计划，并通过强化学习优化视觉奖励（基于目标完成和轨迹一致性）。该方法使VLA模型能够进行显式推理和多步规划，在复杂任务中显著优于端到端方法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-72ur53jn7t/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-72ur53jn7t/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-72ur53jn7t/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1436, \"height\": 748, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-72ur53jn7t/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1448, \"height\": 869, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-72ur53jn7t/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 642, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-72ur53jn7t/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1362, \"height\": 242, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-72ur53jn7t/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1369, \"height\": 239, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-72ur53jn7t/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 582, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-72ur53jn7t/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 594, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-72ur53jn7t/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 757, \"height\": 275, \"label\": \"Table\"}]"
motivation: 现有VLA模型端到端映射缺乏显式推理，难以适应复杂任务和多步规划。
method: 设计双系统框架，高层LLM生成推理计划，低层执行动作，通过强化学习优化视觉潜在规划。
result: 在多个具身推理任务上，ThinkAct显著优于现有VLA方法。
conclusion: 显式推理和强化规划是提升VLA模型泛化性和适应性的关键。
---

## Abstract
Vision-language-action (VLA) reasoning tasks require agents to interpret multimodal instructions, perform long-horizon planning, and act adaptively in dynamic environments. Existing approaches typically train VLA models in an end-to-end fashion, directly mapping inputs to actions without explicit reasoning, which hinders their ability to plan over multiple steps or adapt to complex task variations. In this paper, we propose ThinkAct, a dual-system framework that bridges high-level reasoning with low-level action execution via reinforced visual latent planning. ThinkAct trains a multimodal LLM to generate embodied reasoning plans guided by reinforcing action-aligned visual rewards based on goal completion and trajectory consistency. These reasoning plans are compressed into a visual plan latent that conditions a downstream action model for robust action execution on target environments. Extensive experiments on embodied reasoning and robot manipulation benchmarks demonstrate that ThinkAct enables few-shot adaptation, long-horizon planning, and self-correction behaviors in complex embodied AI tasks.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究问题**：现有视觉-语言-动作（VLA）模型通常采用端到端方式直接将输入映射到动作，缺乏显式推理步骤，导致难以处理多步规划（long-horizon planning）和复杂任务变化。
- **背景**：虽然多模态大语言模型（MLLM）在视觉问答等领域取得了进展，但在需要与环境交互的具身推理任务中，MLLM 仍缺乏行动感知和规划能力。已有 VLA 模型（如 OpenVLA、TraceVLA）在短视野技能上表现不错，但在真实世界场景下的长程推理、适应性和自校正方面存在局限。
- **整体含义**：ThinkAct 提出双系统框架，通过强化视觉潜在规划将高层推理与低层动作执行连接起来，使 VLA 系统具备“先思考再行动”的能力，从而提升复杂具身任务的性能。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：采用“双系统”架构——一个推理模块（MLLM Fθ）负责生成高阶推理计划和视觉潜在表示（visual plan latent ct），另一个动作模块（基于 DiT 的 πϕ）根据潜在表示执行具体动作。推理和动作可异步运行（慢思考、快控制）。
- **关键技术细节**：
    - **动作对齐的视觉奖励**：包括目标完成奖励 r_goal（比较预测抓取起止点与真实轨迹起止点的距离）和轨迹对齐奖励 r_traj（使用动态时间规整（DTW）衡量预测轨迹与演示轨迹的分布匹配度）。
    - **强化学习优化（GRPO）**：给定输入 (ot, l)，采样 M 个输出 {z_i}，用上述视觉奖励 + 格式正确性奖励 r_format 计算每个输出的奖励 r_i。最大化 GRPO 目标函数（公式 4），其中包含相对优势 A_i 和 KL 正则项。
    - **视觉潜在规划**：将 MLLM 生成的文本推理步骤压缩为紧凑的视觉计划潜在 ct，通过 Q-Former 投影到动作模型的输入空间。
    - **训练流程**：
        1. SFT 冷启动：让 MLLM 学习输出推理和视觉轨迹的正确格式。
        2. GRPO 强化学习：用动作对齐的视觉奖励优化推理能力。
        3. 动作适应：冻结 MLLM，仅更新状态编码器、投影器和 DiT 动作模型，通过模仿学习（公式 5）让动作模型接收 ct 进行执行。
- **公式说明**：
    - r_goal = 0.5 * (f(p1, p̂1) + f(pK, p̂K))，其中 f(p, p’) = max(0, 1 - ||p-p’||_2^2)
    - r_traj = max(0, 1 - d(τ, τ̂))，d 为 DTW 距离
    - 总奖励 r = 0.9 * (0.5 * r_goal + 0.5 * r_traj) + 0.1 * r_format
    - GRPO 目标：J_GRPO(θ) = (1/M) Σ_i (Fθ(z_i)/Fθ_old(z_i) * A_i - β * D_KL(Fθ || Fθ_old))

## 3. 实验设计：数据集、Benchmark、对比方法

- **训练数据集**：
    - SFT 冷启动：Open X-Embodiment（OXE）子集、RoboVQA、EgoPlan-IT、Video-R1-CoT。
    - RL 训练：OXE 子集、Something-Something v2（人类视频）、EgoPlan-IT/Val、RoboVQA、Reflect、LLaVA-Video-178K。
- **Benchmark**：
    - **机器人操作**：SimplerEnv（含 Google-VM、Google-VA、Bridge-VM 三种设置）和 LIBERO（Spatial、Object、Goal、Long 四个子任务），评估任务成功率。
    - **具身推理**：EgoPlan-Bench2（多步规划，准确率）、RoboVQA（自由回答，BLEU 分数）、OpenEQA（零样本具身理解，LLM 打分）。
- **对比方法**：包括 Octo-Base、RT1-X、OpenVLA、DiT-Policy、TraceVLA、CoT-VLA、Magma，以及多种纯 MLLM（GPT-4V、LLaVA-Video、Qwen2.5-VL 等）。

## 4. 资源与算力

- 文中明确说明（Section 4.1）：
    - 所有实验在 **16 张 NVIDIA A100 GPU（80 GB 内存）** 上进行。
    - SFT 冷启动：20K 迭代，batch size 32，学习率 1e-5。
    - GRPO 强化：6K 迭代，batch size 64，学习率 1e-6，rollout 大小 5。
    - 动作模型预训练：120K 迭代，batch size 256，学习率 2e-5。
    - LIBERO 额外微调：75K 迭代，batch size 128。
- 未说明总训练时长，但估算为数百 GPU 小时级别。

## 5. 实验数量与充分性

- **实验数量**：
    - 主要对比实验：两个机器人操作基准（SimplerEnv 共 3 个设置，LIBERO 共 4 个设置）中对比 7-9 种方法（表 1）；三个推理基准上对比 9 种方法（表 2）。
    - 消融实验：在 SimplerEnv、EgoPlan-Bench2、RoboVQA 上分别去掉 r_traj、r_goal、两者，以及 SFT 冷启动，共 5 组（表 3）。
    - 附加分析：少样本适应实验（LIBERO 三个子任务，10-shot 微调 100 次试验，图 5）；自校正定性展示（图 6）；推理速度比较。
- **充分性与公平性**：
    - 对比方法覆盖了主流开源和闭源 VLA 模型，包括 CoT 变体（CoT-VLA、Magma）。
    - 消融分析逐步验证各奖励分量的贡献，实验设计客观。
    - 采用标准评估指标（成功率/准确率/BLEU），并声明在 LIBERO 上使用 3 个随机种子报告结果（共 1500 次评估），具有统计意义。

## 6. 论文的主要结论与发现

- ThinkAct 在所有评测基准上均达到或超越最优表现：SimplerEnv 三个设置上分别比基线 DiT-Policy 提升 15.5%、16.9%、11.4%；LIBERO 总体成功率 84.4%，超过 CoT-VLA（83.9%）。
- 在具身推理基准上，ThinkAct 在 EgoPlan-Bench2（48.2%）、RoboVQA（59.8 BLEU）、OpenEQA（56.2%）均取得最佳结果。
- 消融实验证实**目标完成奖励**和**轨迹对齐奖励**均对性能有显著贡献，仅有 QA 奖励时改善微小。
- 通过推理引导，模型展现出**少样本适应**（10-shot 在 LIBERO 上超越 Magma 7-9%）和**自校正**能力（图 6 示例如抓取失败后重新规划）。
- 推理速度比端到端 OpenVLA 慢约 17%，但性能提升显著（尤其在长程任务上提升 15.3%），验证了“慢思考”带来的收益。

## 7. 优点：方法或实验设计上的亮点

- **方法层面**：
    - 创新性地将**强化学习引入 VLA 推理**，通过动作对齐的视觉奖励（非简单 QA 奖励）直接指导推理生成可执行的规划，避免了人工 CoT 标注的高成本。
    - 提出**视觉潜在计划**作为推理与执行的桥梁，允许推理模块异步、低频地提供高层意图，动作模块高频执行（慢思考+快控制）。
    - 双系统架构具有灵活性，可方便地与其他动作模型（如 DiT Policy）结合。
- **实验层面**：
    - 覆盖多个具身场景，包括模拟器操作和真实世界零样本推理，验证了方法的泛化性。
    - 提供了详尽的消融实验和少样本适应分析，并且展示了自校正涌现能力，实验设计全面且有说服力。
    - 对比方法包括近期的 CoT-VLA、Magma 等 SOTA，公平性较好。

## 8. 不足与局限

- **继承 MLLM 的幻觉问题**：论文在 Limitations 中指出，ThinkAct 依赖的预训练多模态 LLM 可能产生视觉或空间推理上的幻觉，导致计划引用错误物体属性或空间关系，影响下游执行。虽然视觉潜在规划和动作接地能部分缓解，但未来需要幻觉抑制或接地感知训练。
- **奖励设计仅使用 2D 轨迹**：当前动作对齐视觉奖励只包含了 2D 轨迹信息，缺少接触力等更丰富的信号。论文提出这只是一个起点，未来可扩展包括接触奖励等。
- **推理速度慢**：相比端到端模型，ThinkAct 推理时间增加约 17%，在实时性要求高的场景可能受限。
- **安全风险**：论文在 Broader Impacts 中指出，歧义指令或过度自信的 CoT 可能在高安全关键环境中导致意外行为。需要进一步研究与人类意图的对齐和保障措施。
- **实验未覆盖真实机器人平台**：所有实验均在模拟器（SimplerEnv、LIBERO）中进行，尽管这些模拟器具有视觉匹配和变体聚合等逼真设置，但真实世界部署的复杂性与分布外场景仍需进一步验证。

（完）
