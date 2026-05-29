---
title: "PoE-World: Compositional World Modeling with Products of Programmatic Experts"
title_zh: "PoE-World: 通过程序化专家乘积实现组合式世界建模"
authors: "Wasu Top Piriyakulkij, Yichao Liang, Hao Tang, Adrian Weller, Marta Kryven, Kevin Ellis"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=obwRcksFZw"
tags: ["query:wm-vla-sa"]
score: 8.0
evidence: 使用程序合成进行组合式世界建模
tldr: 针对传统深度学习世界模型需要大量训练数据且难以从稀疏观测更新知识的问题，提出利用LLM进行程序合成来学习以源代码表示的世界模型。创新地将世界模型表示为程序化专家的指数加权乘积，有效建模复杂非网格世界领域。实验表明该方法在少量数据下实现了强泛化能力，并且支持灵活更新。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-obwrcksfzw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1282, \"height\": 1035, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-obwrcksfzw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1126, \"height\": 580, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-obwrcksfzw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1389, \"height\": 1182, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-obwrcksfzw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1165, \"height\": 599, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-obwrcksfzw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1367, \"height\": 1002, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-obwrcksfzw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 725, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-obwrcksfzw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1171, \"height\": 1198, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-obwrcksfzw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 419, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-obwrcksfzw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-obwrcksfzw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1439, \"height\": 267, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-obwrcksfzw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 214, \"label\": \"Table\"}]"
motivation: 解决深度学习世界模型数据需求大且难以灵活更新知识的问题。
method: 将世界模型表示为程序化专家的指数加权乘积，利用LLM合成程序。
result: 在少量数据下实现了强泛化，并能灵活更新。
conclusion: 提出了一种程序化组合式世界建模新方法。
---

## Abstract
Learning how the world works is central to building AI agents that can adapt to complex environments. 
Traditional world models based on deep-learning demand vast amounts of training data, and do not flexibly update their knowledge from sparse observations. 
Recent advances in program synthesis using Large Language Models (LLMs) give an alternate approach which learns world models represented as source code, supporting strong generalization from little data. 
To date, application of program-structured world models remains limited to natural language and grid-world domains. We introduce a novel program synthesis method for effectively modeling complex, non-gridworld domains by representing a world model as an exponentially-weighted product of programmatic experts (PoE-World) synthesized by LLMs.
We show that this approach can learn complex, stochastic world models from just a few observations. 
We evaluate the learned world models by embedding them in a model-based planning agent, demonstrating efficient performance and generalization to unseen levels on Atari's Pong and Montezuma's Revenge.

---

## 论文详细总结（自动生成）

# 论文总结：PoE-World: Compositional World Modeling with Products of Programmatic Experts

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：传统基于深度学习的世界模型（如Dreamer）需要海量训练数据，难以从稀疏观测中灵活更新知识；而基于LLM程序合成的世界模型（如WorldCoder）虽数据高效，但此前仅成功应用于简单自然语言和网格世界领域，难以扩展到复杂非网格世界（如Atari游戏），主要原因是它们试图搜索一个单一的、巨型程序来描述所有动态，导致组合爆炸和可扩展性差。
- **总体目标**：提出一种新的程序化世界建模方法，能够在仅有少量演示数据的情况下，高效学习复杂、随机的环境动态，并支持组合泛化到新的场景，最终服务于下游的规划和决策。

## 2. 方法论：核心思想与关键技术细节

- **核心思想**：将世界模型表示为一组小型程序化专家（programmatic experts）的指数加权乘积（Product of Experts, PoE）。每个专家只描述一个简单的因果规律，多个专家通过概率聚合共同预测下一观测。这种分解大大降低了单个程序的复杂度，提高了学习效率和可组合性。
- **关键公式**：预测分布为 \( p_{\theta}(o_{t+1}|o_{1:t},a_{1:t}) \propto \prod_i p_{\text{expert}_i}(o_{t+1}|o_{1:t},a_{1:t})^{\theta_i} \)，其中 \( \theta_i \) 为可学习的权重。结合**硬约束**（Hard Constraints）进一步锐化输出，形式为乘以指示函数 \( \mathbf{1}[\bigvee_j c_j(o_{t+1})] \)。
- **算法流程（文字说明）**：
  1. **程序合成**：基于少量演示轨迹（<1分钟游戏画面），将观测转化为自然语言描述，用LLM（GPT-4o）生成多个因果解释程序。每个程序对应一个专家，只修改某个对象类型的单一属性（如速度），未设置属性服从均匀分布，从而解释为概率分布。
  2. **权重优化**：给定专家程序，通过最大似然估计（MLE）优化权重 \( \theta \)，使用L-BFGS优化器（小数据下比Adam好）。加入L1正则化，并剔除权重低于阈值（δ=0.01）的专家。
  3. **迭代更新**：每次收集新轨迹后重复以上步骤，不断“调试”模型。
  4. **规划使用**：将学习到的世界模型嵌入模型基规划agent，采用分层规划（类似任务与运动规划TAMP）：先在高层次抽象图（节点定义对象接触）中搜索路径，再用低层规划器（MCTS或贪心搜索）在动作空间细化执行。

## 3. 实验设计

- **数据集/场景**：Atari游戏Pong和Montezuma's Revenge（MR），以及它们的变体Pong-Alt（3球3敌人）和MR-Alt（类似Kangaroo的重组关卡）。使用OCAtari从像素图像中提取对象列表（包括类别、边界框、速度等符号信息）。
- **Benchmark方法**：
  - **PPO**（模型无关RL，100k步和20M步两个版本）
  - **ReAct**（LLM直接作为agent）
  - **WorldCoder**（单一程序世界模型 + 本文规划器）
  - **PoE-World + Planner**（本文方法）
- **评价指标**：游戏得分（Pong为分数差，MR为是否拿到钥匙）；下一观测预测准确率；下一观测对象属性预测准确率；硬约束消融实验。

## 4. 资源与算力

- **算力说明**：论文在附录A.5中明确：
  - 世界建模部分运行在4个CPU（Cascade-Lake/IceLake/SaphireRapids）和64GB内存上，无GPU依赖（因为LLM通过API调用）。
  - OpenAI API费用：每个运行约$20。
  - 执行时间：PoE-World单独约8小时（含LLM请求等待）；规划器（分层规划）时间不确定，但多数运行在24小时内完成（使用多CPU集群并行构建抽象图）。
  - **未明确说明**：PPO基线的训练算力细节（通常需要GPU），但论文使用了stable-baselines3的默认配置。

## 5. 实验数量与充分性

- **主要实验组数**：
  - 四个环境（Pong, Pong-Alt, MR, MR-Alt）上的agent得分比较（表1），重复5次（error bars）。
  - 训练曲线（图5）：不同环境下的得分随训练步数变化（对数尺度）。
  - 下一观测预测准确率（表2、3）：训练集和测试集（1000随机帧）上的比较。
  - 硬约束消融（表4）：在有/无硬约束时，MR和MR-Alt上的规划成功率和预测准确率。
  - 策略预训练实验（图6）：利用PoE-World世界模型进行PPO预训练后微调的效果。
- **充分性与公平性**：
  - 实验覆盖了基础环境及其变体，测试了组合泛化能力。
  - 对比了多种主流方法（PPO、ReAct、WorldCoder），且WorldCoder使用了相同的规划器以确保公平。
  - 消融实验验证了硬约束的作用。
  - 但局限是实验仅基于两个Atari游戏，且依赖OCAtari的场景提取（需要手动修补），泛化到更多游戏可能受限。

## 6. 主要结论与发现

- PoE-World能够在仅有少量演示（<1000帧）的情况下学习出可用的世界模型，并在规划agent中实现比其他方法更好的得分，尤其在Montezuma's Revenge上取得了唯一正奖励。
- 世界模型具有良好的组合泛化能力：在未见过的新关卡变体（Pong-Alt、MR-Alt）上零样本表现优异。
- 与WorldCoder相比，PoE-World能捕捉更复杂的因果规律（如平台、梯子约束），避免幻觉（如虚构的子弹），并处理部分可观测性和随机性。
- 预训练策略使用PoE-World世界模型可以加速PPO学习（缩短达到超越随机agent所需步数）。
- 硬约束对长时域规划至关重要，虽然对下一观测预测准确率影响不大，但能提升规划成功率。

## 7. 优点：方法与实验设计的亮点

- **创新性**：首次将程序化世界模型扩展到非网格世界的复杂环境（Atari），提出乘积式专家分解，克服了单一程序的可扩展性难题。
- **数据高效**：仅需短演示即可学习，符合人类学习模式。
- **模块化与可组合**：每个专家独立学习，可以复用和重新组合，支持对未见场景的泛化。
- **可解释性**：专家程序用Python编写，因果规律清晰可见；硬约束也以条件形式给出。
- **规划集成**：通过分层规划器（TAMP风格）有效解决长时域稀疏奖励问题，实验设计表明世界模型能支撑实际决策。
- **实验公平**：对比方法均适配了同样的观测表示和规划器，排除了其他因素干扰。

## 8. 不足与局限

- **依赖符号输入**：方法需要OCAtari从像素提取对象列表，且需要为每个游戏手动调试OCAtari（论文提到无法在全Atari套件运行），因此不直接从像素学习，限制了通用性。
- **未解决探索问题**：方法专注于从给定演示中学习世界模型，不处理环境探索和奖励函数学习（模型基RL中的核心挑战）。
- **规划器计算成本高**：分层规划（尤其是抽象图构建）可能需要大量并行计算，且对随机种子敏感。
- **实验范围有限**：仅在两个Atari游戏上进行，且变体环境也是人为构造，未测试其他复杂域（如3D、机器人）。
- **LLM API依赖**：程序合成依赖GPT-4o，成本较高，且每次运行约$20，不适合大规模实验。
- **模型预测仍不完美**：随机专家产生的模糊预测可能违反物理约束，硬约束虽改善但未彻底消除。
- **未与最先进的模型基RL方法（如DreamerV3）对比**：虽然强调数据效率，但缺乏与基于像素的世界模型在相同设置下的直接比较（因为输入模态不同）。

（完）
