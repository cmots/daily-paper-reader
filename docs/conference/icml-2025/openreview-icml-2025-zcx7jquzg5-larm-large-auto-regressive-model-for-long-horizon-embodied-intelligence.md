---
title: "LARM: Large Auto-Regressive Model for Long-Horizon Embodied Intelligence"
title_zh: LARM：用于长时域具身智能的大自回归模型
authors: "Zhuoling Li, Xiaogang Xu, Zhenhua Xu, Ser-Nam Lim, Hengshuang Zhao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=zcx7jqUZg5"
tags: ["query:wm-vla-sa"]
score: 7.0
evidence: 大自回归模型结合裁判强化学习用于长时域具身规划与决策
tldr: 现有具身智能体要么效率高但任务少，要么通用但计算昂贵。本文提出LARM，一个轻量级大自回归模型（<5B参数），直接输出动作。引入裁判RL解决长时域探索中反馈消失问题，在多个任务上取得高效率与强泛化的平衡。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-zcx7jquzg5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1762, \"height\": 772, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcx7jquzg5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1760, \"height\": 904, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zcx7jquzg5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1762, \"height\": 1023, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-zcx7jquzg5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1505, \"height\": 598, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zcx7jquzg5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 856, \"height\": 272, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zcx7jquzg5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 771, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zcx7jquzg5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 814, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zcx7jquzg5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 821, \"height\": 246, \"label\": \"Table\"}]"
motivation: 强化学习agent效率高但泛化差，大语言模型agent通用但计算开销巨大。
method: 构建轻量级大自回归模型直接输出动作，并设计裁判强化学习机制应对长时域探索中的反馈稀疏问题。
result: 在多个具身任务上显著优于纯RL方法，且计算开销远低于大语言模型agent。
conclusion: 大自回归模型与裁判RL的结合为高效且通用的具身智能提供了新途径。
---

## Abstract
Recent embodied agents are primarily built based on reinforcement learning (RL) or large language models (LLMs). Among them, RL agents are efficient for deployment but only perform very few tasks. By contrast, giant LLM agents (often more than 1000B parameters) present strong generalization while demanding enormous computing resources. In this work, we combine their advantages while avoiding the drawbacks by conducting the proposed referee RL on our developed large auto-regressive model (LARM). Specifically, LARM is built upon a lightweight LLM (fewer than 5B parameters) and directly outputs the next action to execute rather than text. We mathematically reveal that classic RL feedbacks vanish in long-horizon embodied exploration and introduce a giant LLM based referee to handle this reward vanishment during training LARM. In this way, LARM learns to complete diverse open-world tasks without human intervention. Especially, LARM successfully harvests enchanted diamond equipment in Minecraft, which demands significantly longer decision-making chains than the highest achievements of prior best methods.

---

## 论文详细总结（自动生成）

# LARM: Large Auto-Regressive Model for Long-Horizon Embodied Intelligence — 详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）

- **背景**：现有具身智能体主要基于两类方法：
  - **强化学习（RL）代理**：部署高效、参数量小，但通常只能完成少数特定任务，泛化能力弱。
  - **大型语言模型（LLM）代理**：如GPT-4（>1000B参数），具备强大的通用知识和推理能力，但计算资源需求巨大，响应速度慢，难以在资源受限的机器人场景中部署。
- **核心问题**：如何结合两者的优势（RL的高效性 + LLM的泛化性），同时避免各自的缺点（任务专一性 vs. 计算成本高），实现一个**既高效又具备通用知识**的具身智能体。
- **研究意义**：本文在Minecraft开放世界中验证了该思路，首次实现了**获取附魔钻石装备**这一长时域决策链成就，标志着在长时域具身智能规划与执行上取得重要突破。

## 2. 提出的方法论

### 核心思想
- 构建一个**轻量级大型自回归模型（LARM）**，参数量 < 5B，直接输出动作（skill token）而非文本，从而兼具推理能力和快速响应。
- 引入**裁判强化学习（Referee RL）**，利用巨型LLM（如GPT-4）作为裁判，在长时域探索中提供**密集辅助奖励**，解决经典RL中奖励消失问题。

### 关键技术细节

1. **LARM模型结构**：
   - 骨干网络：轻量级decoder-only LLM（TinyLLaVA-3.1B），参数冻结。
   - 可训练模块：LoRA（低秩适应）模块，用于适应具身任务；两个预测头：**动作头（Actor Head）**和**价值头（Critic Head）**。
   - 输入：任务描述、文本观测（库存、历史动作、周围方块）、视觉观测（图像）以及一个可学习的技能token。
   - 输出：通过特征匹配选择一个预定义的技能（skill）。

2. **裁判强化学习（Referee RL）**：
   - **动机**：经典PPO在长时域任务中，奖励仅出现在最终步骤，导致TD误差和GAE趋近于零，策略无法有效更新。
   - **数学分析**：当任务链很长时，末尾的折扣因子使得GAE值趋近于零，优化目标失效。
   - **解决方案**：引入裁判π（GPT-4），根据执行动作前后的状态判断动作是否正确、是否产生正面结果，输出四级奖励（ra > rb > 0 > rc > rd）。
   - **流程**（算法1）：
     - 每步执行动作at，获得环境奖励rt和裁判辅助奖励brt。
     - 累计总奖励 = rt + brt，用于PPO更新。
   - **优势**：密集奖励信号解决了稀疏奖励下的梯度消失问题，使训练有效进行。

3. **预训练**：
   - 使用34GB网页数据（来自Minecraft Wiki）对LARM进行预训练，提升其对Minecraft领域的知识理解。

## 3. 实验设计

### 场景与Benchmark
- **MineDojo**：包含上千个自然语言指定的任务，动作空间为复合多离散动作，用于测试策略的探索和资源收集能力。
- **Mineflayer**：基于API（如收割木头、寻找石头）提供高级技能，侧重于高层决策，支持更复杂的成就链。

### 对比方法
- **MineDojo**：MineAgent、Plan4MC、LLaMA-Rider Base、LLaMA-Rider、RL-GPT。
- **Mineflayer**：AutoGPT、Voyager、STEVE。

### 任务列表
- **MineDojo**：收集物品/制作工具共13个任务（如Harvest stick, Harvest crafting table, …, Harvest iron sword, Harvest beef等）。
- **Mineflayer**：从木质剑到附魔钻石剑共5个成就（Wooden sword, Stone sword, Iron sword, Diamond sword, Enchanted sword）。

### 评估指标
- 成功率（Success rate），每个任务测试30次。

## 4. 资源与算力

- **GPU**：单张 **NVIDIA RTX 4090**。
- **训练时长**：最困难的任务（制作附魔钻石工具）大约需要 **42小时** 的在线探索与优化。
- **推断速度**：0.58秒/次推理，满足在线高层决策速度要求。

## 5. 实验数量与充分性

- **主要对比实验**：
  - MineDojo上对比4种方法，覆盖13个任务。
  - Mineflayer上对比3种方法，覆盖5个成就。
- **消融实验**（共4组）：
  1. **奖励设计**：比较环境奖励仅ER、ER+轻量LLM（LLaVA-7B）辅助奖励、ER+二值化专家奖励、ER+四级专家奖励（标准设置）。
  2. **LLM基础选择**：TinyLLaVA-0.5B vs. 3.1B，以及是否使用网页数据预训练。
  3. **噪声奖励分析**：将裁判奖励以0%、10%、30%、50%比例随机替换为错误奖励，测试鲁棒性。
  4. **LLM能力对比**：展示GPT-4o、Llama3-8B、TinyLLaVA-3.1B（有无预训练）对Minecraft问题的回答质量。
- **补充案例**：可视化探索村庄、建造下界传送门、多智能体协作战斗等行为。
- **分析**：实验较为充分，涵盖了主要场景、多种对比算法、核心消融变量。实验设计公平（随机初始化、相同测试次数、相同环境设置）。但仅测试了Minecraft单一平台，泛化到其他具身平台未验证。

## 6. 主要结论与发现

1. **LARM+裁判RL**在效率和泛化性之间取得了优秀平衡：单一模型完成多种任务，且成功率显著高于之前方法。
2. **奖励消失问题**在长时域探索中被数学验证并有效解决，裁判RL提供的密集奖励是关键。
3. **轻量级LLM（<5B）** 结合预训练和LoRA微调，可以获取足够的领域知识，无需巨型模型。
4. **首次在Minecraft中达成附魔钻石工具**，证明方法可支持极长决策链。
5. **裁判LLM的质量至关重要**：使用GPT-4等巨型LLM效果好，而轻量级LLM（如LLaVA-7B）作为裁判效果差；当裁判奖励噪声>10%时，性能明显下降。

## 7. 优点

- **方法创新**：首次将LLM风格的策略直接通过在线环境探索和RL优化，且引入巨模型裁判提供密集监督，克服稀疏奖励难题。
- **轻量高效**：模型参数量仅3.1B，可单卡运行，推理速度快（0.58s/步），适合实际部署。
- **泛化性强**：单一模型在多个任务上均达到或超过任务专用模型的表现。
- **实验设计扎实**：包含多个消融实验（奖励设计、模型大小、预训练数据、噪声鲁棒性），结论可靠。
- **开源贡献**：提供项目网页，便于复现和扩展。

## 8. 不足与局限

- **环境单一**：仅在Minecraft中验证，未在机器人操作、导航等其他具身场景测试，泛化性有待证明。
- **依赖巨型LLM裁判**：训练阶段需要调用GPT-4等商用模型，带来额外成本与隐私风险；且裁判存在噪声时性能显著下降。
- **预训练数据规模有限**：仅使用34GB网页数据，数据量相对较小，可能限制领域知识覆盖。
- **动作空间受限**：需要预定义技能库，新技能的添加依赖外部方法，未能完全端到端学习底层原子动作。
- **时间开销**：最复杂任务训练需42小时，虽可接受但仍有优化空间。
- **可解释性**：LARM输出为skill token，决策过程的推理链条不如直接文本输出的LLM透明。

（完）
