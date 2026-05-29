---
title: "SENSEI: Semantic Exploration Guided by Foundation Models to Learn Versatile World Models"
title_zh: "SENSEI: 基于基础模型引导的语义探索以学习通用世界模型"
authors: "Cansu Sancaktar, Christian Gumbsch, Andrii Zadaianchuk, Pavel Kolev, Georg Martius"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ZDPNmihkMR"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 基础模型引导语义探索以学习通用世界模型
tldr: 强化学习中的探索常基于信息增益等原则，但只能发现低级交互。本工作提出SENSEI，利用基础模型注入语义先验，引导智能体进行语义合理的探索，从而学习多用途世界模型。方法无需语言嵌入的环境或高层动作假设。在多个基准任务中，SENSEI学到的世界模型有效提升下游任务性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1705, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1724, \"height\": 679, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 824, \"height\": 290, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1746, \"height\": 1504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1770, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 824, \"height\": 959, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 852, \"height\": 436, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 864, \"height\": 846, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1775, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1780, \"height\": 608, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1783, \"height\": 607, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1121, \"height\": 2100, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1688, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1771, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 394, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1336, \"height\": 2284, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1766, \"height\": 1098, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1186, \"height\": 749, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1393, \"height\": 1522, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 658, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1295, \"height\": 1519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1779, \"height\": 486, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1780, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1778, \"height\": 499, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1512, \"height\": 314, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1771, \"height\": 1176, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zdpnmihkmr/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1765, \"height\": 820, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-zdpnmihkmr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1719, \"height\": 1352, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zdpnmihkmr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 760, \"height\": 508, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zdpnmihkmr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 991, \"height\": 318, \"label\": \"Table\"}]"
motivation: 现有内在动机探索只能发现低级交互，缺乏高层面语义引导。
method: 利用视觉语言基础模型为探索提供语义偏置，激励智能体执行有意义的行为，从而学习更通用的世界模型。
result: 在多个RL基准上，学到的世界模型在迁移和泛化上优于之前的方法。
conclusion: 语义探索结合基础模型可高效学习世界模型，为通用智能体奠定基础。
---

## Abstract
Exploration is a cornerstone of reinforcement learning (RL). Intrinsic motivation attempts to decouple exploration from external, task-based rewards. However, established approaches to intrinsic motivation that follow general principles such as information gain, often only uncover low-level interactions. In contrast, children’s play suggests that they engage in meaningful high-level behavior by imitating or interacting with their caregivers. Recent work has focused on using foundation models to inject these semantic biases into exploration. However, these methods often rely on unrealistic assumptions, such as language-embedded environments or access to high-level actions. We propose SEmaNtically Sensible ExploratIon (SENSEI), a framework to equip model-based RL agents with an intrinsic motivation for semantically meaningful behavior. SENSEI distills a reward signal of interestingness from Vision Language Model (VLM) annotations, enabling an agent to predict these rewards through a world model. Using model-based RL, SENSEI trains an exploration policy that jointly maximizes semantic rewards and uncertainty. We show that in both robotic and video game-like simulations SENSEI discovers a variety of meaningful behaviors from image observations and low-level actions. SENSEI provides a general tool for learning from foundation model feedback, a crucial research direction, as VLMs become more powerful.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：强化学习（RL）中的内在动机探索通常基于信息增益、预测误差等通用原则，但这些原则仅能发现低级交互，无法引导智能体进行高层次的、语义上有意义的行为。例如，机器人面对桌面物体时，自然探索应关注“拿起钥匙”“打开抽屉”等行为，而非随机移动手臂。
- **背景**：儿童在玩耍时会模仿或与照料者互动，从而获得语义上有意义的探索指导。受此启发，近期工作尝试利用大型语言模型（LLM）或视觉语言模型（VLM）向探索注入语义偏置。但现有方法往往依赖于语言嵌入的环境、预存的离线数据集或高级动作接口，这在机器人等具身智能场景中难以实现。
- **研究目标**：提出 SENSEI 框架，让模型基础RL智能体在仅有**图像观测和低层动作**的条件下，通过VLM引导的探索学习多用途世界模型，从而发现并利用语义合理的行为。

## 2. 方法论

### 核心思想
SENSEI 通过三步实现语义探索：
1. **蒸馏语义奖励函数**：利用VLM对初始自监督探索数据中的观察图像进行“有趣性”成对比较，将偏好通过MOTIF（偏好学习）蒸馏为可学习的奖励函数 $R_\psi (o_t)$，输出语义探索奖励 $r_t^{\text{sem}}$。
2. **学习世界模型**：基于 DreamerV3 的 RSSM，不仅预测观测、延续、任务奖励，还额外预测语义奖励 $\hat{r}_t^{\text{sem}}$，使智能体在想象状态中也能判断“有趣性”。
3. **结合信息增益进行探索**：训练集成预测器（8个模型）估计下一隐状态的集合差异作为不确定性奖励 $r_t^{\text{dis}}$。采用 **Go-Explore 动态切换策略**：
   - 若当前状态语义奖励低于阈值 $\hat{r}_t^{\text{sem}} < Q_k$，则主要优化语义奖励（$\beta_{\text{go}}$ 小）；
   - 若高于阈值，则更强地鼓励不确定性探索（$\beta_{\text{explore}}$ 大），从而从“有趣”状态出发分支探索。

### 关键技术细节
- **奖励蒸馏**：使用 VLM-MOTIF，输入图像对和简短环境描述，VLM（GPT-4）输出偏好，再通过交叉熵损失训练 $R_\psi$。
- **世界模型**：RSSM（Recurrent State Space Model），参数 $\phi$，包含后验、动态、先验以及多个输出头（重建观测、奖励、语义奖励等）。
- **不确定性量化**：N=8个集成模型预测下一隐状态 $\hat{z}_t^n$，计算状态维度的方差作为 $r_t^{\text{dis}} = \frac{1}{J}\sum_{j=1}^J \text{Var}(\hat{z}_{j,t}^n)$。
- **探索策略**：总探索奖励 $r_t^{\text{expl}} = \hat{r}_t^{\text{sem}} + \beta \cdot r_t^{\text{dis}}$，其中 $\beta$ 根据 $\hat{r}_t^{\text{sem}}$ 是否超过当前经验分位数 $Q_k$ 动态切换为 $\beta_{\text{go}}$ 或 $\beta_{\text{explore}}$。

## 3. 实验设计

### 数据集/场景
- **MiniHack**（基于 NetHack）：两个任务 KeyRoom-S15（拿钥匙开门离开）和 KeyChest（拿钥匙开宝箱）。观测：80×80 像素的自我中心视图 + 物品旗标。
- **Robodesk**：多任务机器人操作台，7类物体（按钮、抽屉、滑动柜、球、直立块、平放块、箱子）。观测：64×64 像素，连续动作，使用动作重复2。
- **Pokémon Red**：Game Boy 经典游戏，要求探索地图、战斗、训练宝可梦、击败道馆馆主。观测：原始游戏画面（64×64），离散动作。

### 对比方法
- **Plan2Explore**（P2X）：基于不确定性（集成模型分歧）的模型基础探索。
- **RND**（Random Network Distillation）：模型无关探索基线。
- **DreamerV3**：从头训练基于任务奖励的强化学习。
- **PPO**：近端策略优化，模型无关基线。
- **VLM-MOTIF**（消融）：SENSEI 去掉信息增益奖励（$\beta=0$）。
- **Oracle-based SENSEI**：用人工标注的“有趣性”替代VLM。
- **SENSEI with different initial data**：比较 Plan2Explore 初始数据 vs CEE-US 初始数据。
- **SENSEI with general prompt**：无需人工环境描述，由VLM自动生成。

### 实验设置与公平性
- **种子数**：MiniHack 10种子，Robodesk 3种子，Pokémon 5种子。
- **探索步数**：MiniHack 500K，Robodesk 1M，Pokémon 750K。
- **超参数**：附录B给出，包含动态切换阈值（分位数0.75–0.9）、各奖励权重等。文中对动态切换进行了超参数敏感性分析。
- **初始化数据收集**：统一使用 Plan2Explore 收集初始数据集 $D_{\text{init}}$，避免不公平的优势。

## 4. 资源与算力

- **VLM注释阶段**：通过 OpenAI API（GPT-4）在 CPU 上并行注释，Robodesk 200K 对使用 200 CPU 约 40 分钟完成。
- **奖励模型训练**：单 GPU（如 Tesla V100）20 分钟完成 50 epoch。
- **在线模型基础RL训练**：NVIDIA A100-80GB，SENSEI 约 7.5Hz，Plan2Explore 约 10Hz，VLM-MOTIF 约 8.7Hz。未明确报告总GPU小时数，但可估算每种子约1-2天（因环境不同）。
- **总体评价**：算力消耗中等，注释成本较高（每对约$0.002-$0.004），但注释为离线，不影响在线训练效率。

## 5. 实验数量与充分性

- **实验组数**：
  - MiniHack：2个任务，3种方法（SENSEI, P2X, VLM-MOTIF），10种子。
  - Robodesk：6种对象交互数量统计，多种奖励收集（见图16），含消融（Oracle vs VLM, 不同初始数据, 固定权重 vs 动态切换, 通用提示 vs 特殊提示），每种3种子。
  - Pokémon：4种方法（SENSEI, P2X, Dreamer, 以及第二代注释），5种子，多个评估指标（地图到达、宝可梦等级、队伍大小、徽章）。
  - 下游任务学习：MiniHack 2个任务 × 4方法（SENSEI, P2X, Dreamer, PPO），Robodesk 3个任务 × 2方法（SENSEI, P2X），均10种子。
- **充分性评价**：
  - **充分**：覆盖三种不同复杂度环境（离散/连续、2D/3D、简单/开放世界），对关键模块做了系统消融（VLM质量、初始数据质量、动态切换、固定权重、通用提示）。
  - **公平**：对比方法均为当前同类别最优，使用相同世界模型基座（DreamerV3）控制变量，超参数经过调优。
  - **不足**：部分消融仅3种子，统计显著性有限；未在真实机器人平台上验证；仅使用GPT-4一种VLM，未比较不同VLM的能力。

## 6. 主要结论与发现

1. **语义奖励函数有效**：VLM-MOTIF蒸馏的奖励在有趣事件（如捡钥匙、开抽屉、战斗伤害）处出现峰值，符合人类预期。
2. **SENSEI 发现更多语义交互**：在 MiniHack 和 Robodesk 中，SENSEI 探索到更多与任务相关物体的交互（例如捡钥匙、开门、操作抽屉等），显著优于 Plan2Explore 和 RND。
3. **信息增益至关重要**：纯语义奖励（VLM-MOTIF）容易陷入局部最优（如不断捡钥匙却不开门），必须结合不确定性奖励才能持续分支探索。
4. **动态切换策略稳健**：相比固定权重组合，动态 Go-Explore 策略对超参数不敏感，且表现更好。
5. **加速下游任务学习**：基于 SENSEI 探索预训练的世界模型，可使后续 DreamerV3 策略学习样本效率大幅提升（MiniHack 中比 PPO 快约2个数量级）。
6. **开放式环境中的任务探索**：在 Pokémon Red 中，SENSEI 首次到达第一个道馆并击败馆主、获得徽章，而基线均失败。
7. **初始数据分布影响**：初始数据集 $D_{\text{init}}$ 越丰富，SENSEI 效果越好；VLM 注释质量（Oracle vs GPT-4）影响探索效果。
8. **无需人工环境描述**：通过通用提示策略（SENSEI GENERAL），VLM 可自主生成环境描述，性能与人工描述版本相当。

## 7. 优点

- **方法设计**：
  - 将VLM偏好嵌入内在奖励，避免任务指定，实现任务无关的语义探索。
  - 学习“有趣性”的内部模型（世界模型预测语义奖励），无需在线查询VLM，提升效率。
  - Go-Explore动态切换巧妙融合语义与不确定性，平衡利用与探索。
- **实验设计**：
  - 在截然不同的环境（离散/连续，2D/3D，复杂开放世界）中验证泛化性。
  - 全面的消融分析（VLM质量、初始数据、动态切换、通用提示），揭示各组件影响。
  - 包含下游任务学习，展示实用价值。
- **假设较少**：仅需图像观测和低层动作，无需语言嵌入、预存数据集或高级接口，更贴近真实机器人场景。
- **可扩展性**：第二代注释实验证明可迭代优化，适应不断扩大的探索区域。

## 8. 不足与局限

- **依赖全观测**：VLM 注释要求图像清晰且包含所有相关信息，遮挡（如Robodesk的单目视角）会降低注释质量。虽可使用多个摄像头缓解，但并非所有环境可行。
- **初始数据偏差**：$D_{\text{init}}$ 若覆盖不全，VLM-MOTIF 可能对未见过状态产生不准确奖励信号（如图26中第一代奖励对道馆区域失效）。第二代注释可部分缓解，但需额外成本。
- **仅使用单一VLM（GPT-4）**：未探索不同VLM（如开源模型）对结果的影响，且VLM可能带有训练数据中的偏见（如文化、安全内容过滤）。
- **算力成本**：VLM 注释需大量 API 调用，实验规模较大时费用不菲。
- **泛化到真实世界的限制**：模拟环境观测与真实照片存在领域差异，VLM在仿真图像上的表现可能不如真实场景。作者认为真实场景可能效果更好，但未验证。
- **统计显著性**：部分实验（如Robodesk消融）仅3种子，方差较大，结论需谨慎。
- **未考虑部分可观测性**：方法假设观测基本反映完整状态，对于需要记忆或时序推理的POMDP可能不足。
- **动态切换引入额外超参数**：虽声称对超参数不敏感，但仍需调节分位数 $k$ 及两阶段权重，增加了调参复杂度。

（完）
