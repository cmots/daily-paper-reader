---
title: Neurosymbolic World Models for Sequential Decision Making
title_zh: 用于顺序决策的神经符号世界模型
authors: "Leonardo Hernandez Cano, Maxine Perroni-Scharf, Neil Dhir, Arun Ramamurthy, Armando Solar-Lezama"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=qkeYxpB9w0"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 神经符号世界模型用于顺序决策
tldr: 针对强化学习中世界模型表示缺乏结构性的问题，本文提出SWMPO框架，无监督学习神经符号有限状态机作为世界模型，显式捕捉环境中的区域动态模式。该结构化表示可用于策略优化。在连续控制任务上的实验表明，SWMPO提升了决策性能。该框架为可解释世界模型提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-qkeyxpb9w0/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qkeyxpb9w0/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 869, \"height\": 447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qkeyxpb9w0/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 871, \"height\": 227, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qkeyxpb9w0/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 870, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qkeyxpb9w0/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1737, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qkeyxpb9w0/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1742, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qkeyxpb9w0/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1591, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qkeyxpb9w0/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 864, \"height\": 640, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-qkeyxpb9w0/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1775, \"height\": 792, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qkeyxpb9w0/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1777, \"height\": 712, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qkeyxpb9w0/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1774, \"height\": 717, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qkeyxpb9w0/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1773, \"height\": 710, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qkeyxpb9w0/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1774, \"height\": 716, \"label\": \"Table\"}]"
motivation: 传统无监督世界模型使用非结构化表示，无法捕捉环境中的高层模式。
method: 提出SWMPO框架，将环境建模为有限状态机，每个状态对应一个区域动态。
result: 在连续控制任务上验证了结构化世界模型能有效提升策略优化性能。
conclusion: 神经符号世界模型为强化学习提供了更可解释和高效的结构化表示。
---

## Abstract
We present Structured World Modeling for Policy Optimization (SWMPO), a framework for unsupervised learning of neurosymbolic Finite State Machines (FSM) that capture environmental structure for policy optimization. Traditional unsupervised world modeling methods rely on unstructured representations, such as neural networks, that do not explicitly represent high-level patterns within the system (e.g., patterns in the dynamics of regions such as \emph{water} and \emph{land}).
Instead, SWMPO models the environment as a finite state machine (FSM), where each state corresponds to a specific region with distinct dynamics. This structured representation can then be leveraged for tasks like policy optimization. Previous works that synthesize FSMs for this purpose have been limited to discrete spaces, not continuous spaces. Instead, our proposed FSM synthesis algorithm operates in an unsupervised manner, leveraging low-level features from unprocessed, non-visual data, making it adaptable across various domains. 
The synthesized FSM models are expressive enough to be used in a model-based Reinforcement Learning scheme that leverages offline data to efficiently synthesize environment-specific world models.
We demonstrate the advantages of SWMPO by benchmarking its environment modeling capabilities in simulated environments.

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义（研究动机和背景）

- **问题**：在强化学习（RL）中，传统无监督世界模型（如纯神经网络）使用非结构化表示，无法显式捕捉环境中的高层模式（例如水下/陆地的不同动力学区域）。这导致模型难以复用、泛化性差，且缺乏可解释性。
- **动机**：许多顺序决策任务（如两栖机器人导航）存在可复用的动力学“模式”（如“水模式”“地模式”），但现有方法需要为每个环境从头建模，不能有效利用跨环境的模式共性。
- **目标**：提出一种神经符号世界模型框架，能够无监督地从离线数据中学习一组“模式原语”（neural primitives），然后针对新环境快速组装成结构化的有限状态机（FSM）世界模型，并用于模型-based策略优化。

### 2. 方法论：核心思想与关键技术细节

- **整体框架**：SWMPO（Structured World Modeling for Policy Optimization）包含三个步骤：
  1. **神经原语学习**（Algorithm 1 `NeuralPrimitives`）：从多个离线POMDP的轨迹数据中，无监督地学习一组神经网络模式原语（每个原语模拟一种动力学区域）。
  2. **FSM合成**（Algorithm 2 `FSMSynth`）：利用新POMDP（目标环境）的少量在线数据，将神经原语组装成特定环境的FSM世界模型，包括模式间的转移谓词（由决策树学习）。
  3. **模型-based策略优化**（Algorithm 3 `SWMPO`）：反复迭代：在真实环境中收集数据 → 更新FSM转移 → 在FSM模拟中进行短程rollout（30步）并优化策略（SAC）。

- **关键技术细节**：
  - **模式发现**：通过联合优化两个神经网络——一个模式编码器 \( m_{\theta_2}(o_{t-1}, a_{t-1}, o_t) \) 和一个一阶预测器 \( f_{\theta_1}(m, o_t, a_t) \approx o_{t+1} - o_t \)；同时最小化与未来观测的互信息（\( I(M_t, O_{t+1}) \)），确保模式变量精简。
  - **聚类与剪枝**：使用k-means将编码后的模式向量聚类为离散模式；随后对时空上短暂且可容忍的误转移进行贪心剪枝（Algorithm 4 `greedyPrune`），减少状态机复杂度。
  - **转移谓词合成**：将模式之间的二元转移判定视为二分类问题，使用CART决策树从正负样本中学习。

- **核心假设**（论文第4节）：
  - 模式可从 \((o_{t-1}, a_{t-1}, o_t)\) 辨识（Assumption 4.1）；
  - 给定模式，动力学近似确定（Assumption 4.2）；
  - 模式具有最小互信息（Assumption 4.3）；
  - 模式向量在欧氏空间中形成聚类（Assumption 4.4）；
  - 目标环境的模式是离线数据模式集合的子集（Assumption 4.5）。

### 3. 实验设计

- **仿真环境**（四个）：
  - **Point Mass**（2D质点）：模拟两栖机器人，陆地/水两种模式，动作反转区别；
  - **LiDAR Racing**（2D车辆）：自行车动力学、LiDAR感知，五种轨道片段对应模式；
  - **Salamander**（3D）：使用Webots仿真Salamandra Robotica II机器人，水陆两栖；
  - **Bipedal Walker**（BipedalWH）：Gymnasium标准环境，四种障碍物对应模式。
- **Benchmark**：用于评估FSM合成准确性（预测模式标签 vs 真实标签）。
- **对比方法**：
  - HMM（高斯发射）、切换线性动态系统（SLDS）、递归SLDS（rSLDS）；
  - 每个基线有两种设置：仅用目标环境数据的“local”版本 + 同时用离线+目标数据的“global”版本。
- **RL实验**：仅在Point Mass上测试，对比标准模型-free SAC、模型-based SAC（在线学习单体神经网络世界模型）。

### 4. 资源与算力

- 论文未明确说明使用的GPU型号、数量或训练时长。仅提到使用PyTorch、Adam优化器，超参数表给出了学习率（0.0001~0.01）、批大小（1000~1024）、迭代步数等，但无硬件细节。
- 结论：文中未提供算力相关信息，无法评估训练开销。

### 5. 实验数量与充分性

- **数量**：
  - FSM合成实验：在四个环境上各测试了8个不同地形/场景，每个场景用4条测试轨迹，共计32次评估，并绘制了Levenshtein距离的箱线图。
  - RL实验：仅一个环境（Point Mass），64个随机种子，绘制奖励曲线及95%置信区间。
  - 消融实验：仅在图4中展示了剪枝效果的定性示例，未做系统性消融（如去除互信息正则、不同聚类方法等）。
- **充分性与公平性**：
  - 正面：对比了三种主流时序模式发现基线（HMM、SLDS、rSLDS），并考虑了local/global两种训练方式；基线实现均来自成熟库（hmmlearn、SSM）。
  - 不足：RL实验仅在一个环境上验证，缺乏多样性；未与最新的基于大型语言模型的世界模型（如WorldCoder）或端到端神经符号混合方法对比；模式数量假设已知（n=2或5），限制了实用性。

### 6. 主要结论与发现

- FSM合成：SWMPO在Point Mass、Salamander上显著优于所有基线；在LiDAR Racing上略优于HMM，远超SLDS/rSLDS；在Bipedal Walker上所有模型均较差，SWMPO仍微优。
- 模式表征质量：通过UMAP可视化显示，学到的模式向量与真实模式区域高度对应。
- 强化学习：在Point Mass上，SWMPO（利用离线数据学原语、在线合成FSM）的累积奖励显著高于标准模型-free SAC和在线单体模型-based SAC，且收敛更快。

### 7. 优点

- **创新性**：首次将神经符号FSM用于连续、低维、非视觉观测的世界模型，结合无监督模式发现与可迁移原语，为结构化世界模型在RL中的复用提供了新思路。
- **无监督性**：不需要模式标签，仅需已知模式数量，算法完全自监督。
- **可解释性**：FSM的每个状态对应一个专用神经网络，转移谓词可用决策树表示，便于理解和调试。
- **数据高效**：利用离线数据预训练原语，对目标环境仅需少量在线数据即可合成FSM，减少了与环境交互次数。

### 8. 不足与局限

- **假设限制**：需预先知道模式数量、模式需满足最小互信息和聚类性，且目标环境模式必须是离线数据模式的子集——这些在现实复杂环境中可能难以满足。
- **实验覆盖不足**：RL实验仅一个环境，且未在高维视觉或真实机器人上验证；未进行完整的消融实验（如不同互信息权重、剪枝阈值的影响）。
- **计算资源未报告**：无法判断其可复现性和实际训练成本。
- **可扩展性**：论文在复杂性分析中指出复杂度与模式数量m成线性关系，但未测试大规模模式（如10+）或高维观测（如图像）的性能。
- **与其他前沿方法的对比缺失**：未与最新的基于扩散模型的世界模型、隐变量切换模型（如HiP-MDP）或元强化学习方法比较。

（完）
