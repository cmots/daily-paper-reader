---
title: Training a Generally Curious Agent
title_zh: 训练通用好奇智能体
authors: "Fahim Tajwar, Yiding Jiang, Abitha Thankaraj, Sumaita Sadia Rahman, J Zico Kolter, Jeff Schneider, Russ Salakhutdinov"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=UeB3Hdrhda"
tags: ["query:wm-vla-sa"]
score: 6.0
evidence: 训练通用好奇智能体用于探索和决策
tldr: 语言模型在战略信息收集场景中表现不足。本文提出Paprika微调方法，通过在不同任务上的合成交互数据训练，使模型学会根据环境反馈在上下文内调整行为策略，无需额外梯度更新。实验表明，Paprika训练后的模型能够将决策能力迁移到完全未见过的任务中，为构建能持续探索的智能体提供了可行方案，对世界模型和强化学习规划领域有直接参考价值。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1588, \"height\": 642, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 623, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1770, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1755, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1759, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1766, \"height\": 524, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1767, \"height\": 1088, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1767, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1769, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1761, \"height\": 1084, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1765, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1767, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1769, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1326, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1324, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1327, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1762, \"height\": 842, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1749, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1748, \"height\": 523, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 556, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 855, \"height\": 553, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1625, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1814, \"height\": 2137, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1252, \"height\": 113, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 941, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 420, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 332, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 330, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1679, \"height\": 1471, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1700, \"height\": 443, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1736, \"height\": 95, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1427, \"height\": 599, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1765, \"height\": 1058, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1410, \"height\": 1850, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1759, \"height\": 2140, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1237, \"height\": 2093, \"label\": \"Table\"}]"
motivation: 现有语言模型缺乏在开放环境中主动探索和适应新任务的能力。
method: Paprika通过合成多任务交互数据进行微调，使模型学习基于环境反馈进行上下文策略调整。
result: 模型能有效将决策能力迁移到未见任务，无需额外训练。
conclusion: 为语言模型赋予通用探索能力，有望促进世界模型和自主规划的发展。
---

## Abstract
Efficient exploration is essential for intelligent systems interacting with their environment, but existing language models often fall short in scenarios that require strategic information gathering. In this paper, we present **Paprika**, a fine-tuning approach that enables language models to develop general decision-making capabilities that are not confined to particular environments. By training on synthetic interaction data from different tasks that require diverse strategies, Paprika teaches models to explore and adapt their behavior on a new task based on environment feedback in-context without more gradient updates. Experimental results show that models fine-tuned with Paprika can effectively transfer their learned decision-making capabilities to entirely unseen tasks without additional training. Unlike traditional training, our approach's primary bottleneck lies in sampling useful interaction data instead of model updates. To improve sample efficiency, we propose a curriculum learning strategy that prioritizes sampling trajectories from tasks with high learning potential. These results suggest a promising path towards AI systems that can autonomously solve novel sequential decision-making problems that require interactions with the external world.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有语言模型在需要战略性信息收集的交互任务中表现不佳，缺乏通用的探索与决策能力。传统的强化学习（RL）要求为每个任务单独训练，而离线数据集难以覆盖所有可能场景；直接部署到真实世界收集交互数据成本高且有风险。
- **整体含义**：作者提出一种可扩展的微调方法 **Paprika**，旨在教会语言模型通用的“好奇心”与“探索能力”，使其能够在全新任务中通过上下文交互自主收集必要信息并做出决策，而无需针对新任务再训练。这类似于“元强化学习”或“上下文强化学习”（In-Context RL），希望构建能自动解决新颖序列决策问题的AI系统。

## 2. 论文提出的方法论

- **核心思想**：通过在多个多样的文本型决策任务上生成合成交互数据，并对模型进行偏好优化（类似DPO），使模型学会从成功轨迹中学习策略，并将这些策略零样本泛化到未见过的任务上。
- **关键技术细节**：
  1. **任务设计**：设计了10个文本型任务组（如20问、猜城市、Wordle、细胞自动机、客户服务、谋杀谜案、Mastermind、战舰、扫雷、多臂老虎机最佳臂选择），每个任务需要多轮交互，部分可观测，需要战略探索与利用。
  2. **数据集构造**：使用基础模型（如Llama-3.1-8B-Instruct）以高温采样（Min-p采样，温度1.5，Min-p参数0.3）生成大量轨迹。对每个任务采样nsample条轨迹，选取最佳轨迹（成功且步数最少）作为首选，随机选一条失败或步数多的轨迹作为非首选，构建偏好对。
  3. **优化目标**：
     - 监督微调（SFT）：最大化首选轨迹的似然。
     - 直接偏好优化（DPO）的多轮变体：在动作token上计算偏好损失，忽略环境生成的token。
     - 组合目标（RPO）：DPO损失 + α × SFT损失（α设为1.0），防止无意识偏移。
  4. **课程学习**：提出基于变分系数（标准差/均值）的UCB算法，动态选择学习潜力高的任务组进行数据采样，以提高数据效率。
- **算法流程**（文字说明）：
  - 预定义一组任务组。
  - 对每个任务，用当前模型生成C条轨迹，计算变分系数作为该任务的学习潜力指标。
  - 使用UCB多臂赌博机算法选择下一个任务组（从该组随机采样一个任务），更新统计量。
  - 收集足够轨迹后，构建偏好数据集，用RPO目标训练模型。
  - 重复多轮（实验中3轮）。

## 3. 实验设计

- **数据集/场景**：
  - 训练集：自主构建的10个任务组，每个任务组有独立的训练/测试划分。例如20问训练集1499个任务，测试集367个。其他任务组类似。训练集总轨迹数约17,181条（SFT），偏好对5,260对。
  - 额外评估：使用LMRL-Gym的20问和猜城市子集作为零样本泛化测试。
  - 通用能力评估：MT-Bench、AlpacaEval、GPQA、Math (Hard)、MMLU-Pro、IFEval。
- **Benchmark**：
  - 主要在自建10任务组上评估成功率（平均成功率及pass@4成功率）和平均步数。
  - 标准基准用于检测模型退化。
- **对比方法**：
  - 基础模型：Llama-3.1-8B-Instruct、Gemma-3-12B-IT。
  - 最先进封闭模型：GPT-4o-mini。
  - 消融：SFT-only、单任务组训练、留一法（LOO）训练、随机课程（均匀采样）、基于WildChat的多轮对话微调。
- **评价指标**：平均成功率（4条轨迹平均）、pass@4成功率、平均解决步数。

## 4. 资源与算力

- 论文明确提及算力配置：
  - Llama-3.1-8B-Instruct训练：1个节点，8块NVIDIA L40S GPU。
  - Gemma-3-12B-IT训练：1个节点，8块NVIDIA H100 GPU。
  - 推理与数据生成：单块NVIDIA A40 GPU。
  - 总API费用约20,000 USD（用于GPT-4o-mini环境模拟）；一次完整实验约1,000 USD。
  - 未提及训练具体时长，但提及“主要瓶颈在于采样有用交互数据而非模型更新”。

## 5. 实验数量与充分性

- **实验数量**：
  - 主要结果：在10个任务组上对比Paprika vs 基础模型 vs GPT-4o-mini，包含不同温度（0.3, 0.7, 1.0）和两种成功率指标（平均、pass@4），以及平均步数。
  - 留一法泛化实验：对每个任务组，去除该组后训练，测试在留出组上的表现（共10组）。
  - 单任务组训练对比（每个任务组单独训练测试）。
  - 课程学习实验：在20问任务组上3轮训练，对比均匀采样，报告平均和pass@4成功率及分难度（易/中/难）成功率。
  - 消融：SFT vs SFT+RPO（在6个任务组上）。
  - 泛化测试：修改版Wordle（不同字母数）、LMRL-Gym子集、标准基准评估（6个）。
  - 基础模型对比：Llama、Qwen2.5、Mistral在3个任务组上的性能对比。
  - 标准老虎机任务对比（Krishnamurthy et al. 2024）的遗憾曲线。
- **充分性与公平性**：
  - 实验较充分，覆盖了多种任务、多种模型、多种温度、消融和泛化场景。
  - 考虑了随机种子（如课程学习实验报告标准误差），但对主实验未明确报告多次种子结果（部分图中有标准误）。
  - 对比方法包括更强基线GPT-4o-mini和多种消融，较为公平。
  - 不足之处：部分实验仅使用单一模型（Llama-3.1-8B-Instruct），Gemma验证仅报告主结果；未与在线RL（如PPO）对比；未在更大规模模型上验证。

## 6. 论文的主要结论与发现

1. **Paprika显著提升LLM在多任务上的决策能力**：平均成功率提升约47%（相对于原始模型），在Llama和Gemma上均有效。
2. **零样本泛化**：留一法实验表明，在从未见过的任务组上，Paprika可将成功率从基础模型提升，甚至超过单任务组训练的表现（9/10任务组有提升）。但存在个别负迁移（如Wordle）。
3. **多任务训练优于单任务**：训练所有10个任务组（Full）在7/10任务组上优于仅训练该任务组。
4. **课程学习提升数据效率**：基于变分系数的UCB采样在20问任务上3轮后优于均匀采样（平均成功率+1.4%，pass@4 +3.3%）。
5. **不损害通用能力**：在MT-Bench、AlpacaEval等标准基准上性能与基础模型相当。
6. **任务效率改善**：Paprika减少平均解决步数，说明学了更优的策略。
7. **多轮对话数据（WildChat）无法提供决策能力**：直接微调WildChat甚至损害性能。

## 7. 优点

- **方法新颖性**：将“上下文RL”思想扩展到多样化文本任务，不依赖已知最优算法生成数据，而是利用自生成轨迹的对比学习。
- **泛化能力强**：零样本迁移到完全不同的任务（如从文字游戏迁移到多臂老虎机）。
- **实验系统全面**：包括多模型、多任务、消融、泛化、课程学习、标准基准等，验证充分。
- **应用潜力**：为构建能自主探索和决策的智能体提供了可行路径，对世界模型和强化学习规划有直接参考价值。
- **开源释放**：公布代码、数据和模型，便于复现与后续研究。

## 8. 不足与局限

- **依赖基础模型能力**：Paprika需要基础模型能生成一定比例的好轨迹才能有效，若基础模型太弱则表现受限。
- **离线策略局限性**：当前使用离线偏好优化（RPO/DPO），作者预期在线RL（如PPO）可能效果更好但未实验。
- **任务设计人工成本高**：环境（尤其是LLM模拟环境）需要大量人工，且存在环境“黑客”风险（虽用裁判过滤但仍有1.5%误报）。
- **任务组规模有限**：仅10个任务组，泛化结论可能受限于此；部分任务（如Wordle）泛化失败。
- **课程学习依赖分组元数据**：需要预先知道任务难度分组，不具完全自主性。
- **资源开销大**：数据生成耗费大量API调用（约20K USD），是主要瓶颈。
- **公平性争议**：与GPT-4o-mini对比时，未控制API成本或推理时间；未与更专精的RL算法（如UCB）对比多步性能（仅在老虎机任务上简单对比）。
- **部分实验统计报告不足**：主实验未明确报告多次种子标准误差（除课程学习外）；平均成功率可能受低成功率任务影响。

（完）
