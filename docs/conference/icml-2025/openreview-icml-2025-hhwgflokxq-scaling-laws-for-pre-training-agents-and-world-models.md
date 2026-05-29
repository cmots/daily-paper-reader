---
title: Scaling Laws for Pre-training Agents and World Models
title_zh: 预训练智能体和世界模型的缩放定律
authors: "Tim Pearce, Tabish Rashid, David Bignell, Raluca Georgescu, Sam Devlin, Katja Hofmann"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=HHwGfLOKxq"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 预训练智能体和世界模型的缩放定律
tldr: 虽然更大规模通常提升性能，但世界模型和模仿学习中的缩放规律尚不明确。本文系统研究了预训练智能体和世界模型的缩放行为，发现类似语言建模的幂律也出现在这些任务中，但系数受分词器、任务和架构影响显著。该发现为设计高效的世界模型和智能体训练方案提供了理论依据，直接服务于世界模型在强化学习和规划中的应用。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-hhwgflokxq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1479, \"height\": 1152, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhwgflokxq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1583, \"height\": 460, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhwgflokxq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 749, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhwgflokxq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1536, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhwgflokxq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1309, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhwgflokxq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1308, \"height\": 316, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhwgflokxq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1310, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhwgflokxq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1306, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhwgflokxq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1306, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhwgflokxq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1372, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhwgflokxq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1725, \"height\": 832, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhwgflokxq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1724, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhwgflokxq/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1725, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhwgflokxq/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1747, \"height\": 374, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhwgflokxq/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1732, \"height\": 2331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhwgflokxq/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 899, \"height\": 655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhwgflokxq/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1728, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hhwgflokxq/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 891, \"height\": 651, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-hhwgflokxq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 850, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hhwgflokxq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 738, \"height\": 502, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hhwgflokxq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1151, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hhwgflokxq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1143, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hhwgflokxq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1130, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hhwgflokxq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1108, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hhwgflokxq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1160, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hhwgflokxq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 711, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hhwgflokxq/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1134, \"height\": 279, \"label\": \"Table\"}]"
motivation: 世界模型和模仿学习的缩放规律尚不清晰，无法指导资源分配。
method: 在多种架构和任务上实证研究模型参数量、数据量与损失之间的幂律关系。
result: 发现世界模型和模仿学习存在与语言模型类似的缩放定律，但系数高度依赖设计选择。
conclusion: 为构建更优的世界模型和训练更高效的智能体提供了可量化的指导。
---

## Abstract
The performance of embodied agents has been shown to improve by increasing model parameters, dataset size, and compute. This has been demonstrated in domains from robotics to video games, when generative learning objectives on offline datasets (pre-training) are used to model an agent's behavior (imitation learning) or their environment (world modeling). This paper characterizes the role of scale in these tasks more precisely. Going beyond the simple intuition that `bigger is better', we show that the same types of power laws found in language modeling also arise in world modeling and imitation learning (e.g. between loss and optimal model size). However, the coefficients of these laws are heavily influenced by the tokenizer, task \& architecture -- this has important implications on the optimal sizing of models and data.

---

## 论文详细总结（自动生成）

# Scaling Laws for Pre-training Agents and World Models — 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：在大型语言模型（LLM）中，缩放定律（scaling laws）已得到精确刻画，例如模型参数、数据集大小与计算量之间存在幂律关系，可以指导最优资源分配。然而，在具身人工智能（embodied AI）领域，如世界建模（world modeling）和行为克隆（behavior cloning），虽然直观上“越大越好”已被验证，但缺少类似LLM中精确的缩放规律，无法回答“给定计算预算，如何最优地权衡模型大小与数据量”的问题。
- **核心目标**：系统研究世界建模和模仿学习（行为克隆）中的预训练损失与模型规模、数据量、计算量之间的幂律关系，探索缩放定律是否成立，并分析任务、架构和分词器（tokenizer）对缩放系数的影响。
- **整体含义**：揭示具身智能体预训练中的缩放规律，为高效利用计算资源、设计计算最优模型提供可量化的理论指导，推动世界模型和智能体训练的科学化。

## 2. 方法论

- **核心思想**：借鉴LLM缩放定律的研究方法，在无限数据区（infinite data regime，即每个数据点最多训练一次以避免过拟合）中，训练不同规模的GPT-2风格因果Transformer，观察预训练损失（交叉熵）与模型参数数（N）、数据集大小（D）、计算量（FLOPs）之间的幂律关系。重点关注计算最优（compute-optimal）配置：给定FLOPs预算，最小化损失的最优模型大小和最优数据量。
- **关键技术细节**：
    - **任务定义**：
        - 世界建模（WM）：预测未来观测 `P(o_{t+1} | ...)`，使用下一观测的token预测。
        - 行为克隆（BC）：预测未来动作 `P(a_t | ...)`，使用下一动作的token预测。
    - **架构**：
        - **Tokenized架构（WM-Token / BC-Token）**：使用冻结的VQGAN将图像观测编码为多个离散token（256或540个token），动作离散化后也作为token，序列混合输入Transformer。训练时只优化Transformer参数。
        - **CNN架构（BC-CNN）**：每个图像观测通过一个可训练的CNN编码为单一连续嵌入，动作维度独立预测（条件独立性假设）。Transformer参数量包括CNN部分（约0.6M参数）。
    - **分词器**：两种VQGAN——小VQGAN（28M参数，dz=256）和大VQGAN（150M参数，dz=540），均用4096词汇表。
    - **缩放分析方法**：
        - **Frontier fit**（优选）：在损失-FLOPs图上标记高效前沿（efficient frontier）上的模型，直接拟合 `N_optimal ∝ C^a` 和 `D_optimal ∝ C^b`。
        - **Parametric fit**（当前沿不清晰时）：拟合参数化损失函数 `L(N,D) = (N_c/N)^α + (D_c/D)^β + E`，由α、β导出a = β/(α+β)，b = α/(α+β)。
    - **训练设置**：常量学习率（避免多轮余弦退火），每个模型仅训练一次。学习率针对每个规模单独优化。

## 3. 实验设计

- **主要数据集**：
    - **Bleeding Edge游戏数据集**：与游戏开发商Ninja Theory合作收集的4v4多人对战游戏，超过7年匿名玩家数据，包含图像和控制器动作。分为“7 maps数据集”（约8.6年，530,713条轨迹，1.63B帧）和“Sky Garden数据集”（单地图子集，约1.12年，355.5M帧）。
    - **RT-1机器人数据集**：14天人类操作机械臂数据，用于验证结论在真实世界机器人领域是否成立，以及进行小规模消融实验（不同tokenizer压缩率影响）。
- **Benchmark与对比方法**：
    - 无传统benchmark。对比不同任务（WM vs BC）、不同架构（Tokenized vs CNN）、不同分词器（256 vs 540 tokens / image）、不同模型大小（从2M到894M参数）下的损失曲线和缩放系数。
    - 复现并扩展了Tuyls et al. (2023)对行为克隆缩放定律的初步研究，使用Transformer替代LSTM，并首次研究世界模型的缩放定律。
- **评估指标**：
    - **预训练损失**（交叉熵）作为主要代理指标。
    - 额外验证：在部分实验中验证了预训练损失与下游性能（如在线奖励、视频生成质量FVD/LPIPS）的相关性（R > -0.94 或 R > 0.8），证明在无限数据区下损失是好的代理。
- **消融实验**：包括不同分词器压缩率（zo = 16,36,64,100,256）对缩放系数的影响（在RT-1上）；小规模语言模型实验（字符级 vs GPT-2分词器）模拟稀疏损失和超类目标的影响。

## 4. 资源与算力

- **算力信息**：论文未明确列出GPU型号、数量、总训练时长等细节。仅提到训练了多种规模（2M-894M参数）的Transformer，最大模型使用约1.58×10^21 FLOPs（用于验证外推）。数据预处理和VQGAN训练均需要独立计算，但具体GPU资源未披露。作者指出大模型（894M）的超参数（学习率、batch size）未充分调优，因计算限制。

## 5. 实验数量与充分性

- **实验数量**：整体实验丰富。核心实验包括：
    - 世界建模（WM）：两个分词器（256和540 tokens）各训练5-6个模型规模（4M-206M），加上一个894M外推实验。
    - 行为克隆（BC）：Tokenized架构（540 tokens）4个规模（2M-27M）；CNN架构5个规模（3M-108M）。
    - 额外分析：小规模语言模型实验（7个参数规模）；RT-1上5个不同压缩率（各5个模型规模，重复3次）；预训练损失与性能相关性验证。
- **充分性与公平性**：
    - 实验设计较为全面，覆盖了不同任务、架构、分词器、数据集，并使用了两种拟合方法（Frontier和Parametric）确保结果稳健。
    - 方法对比：与Tuyls et al. (2023)和Hoffmann et al. (2022)等经典缩放研究保持一致，方法成熟。
    - 公平性：所有模型使用相同的训练框架，学习率分别调优，但未对所有模型进行精细调参（如大模型未充分调）。
    - 局限性：仅研究了生成性预训练损失，未覆盖奖励模型或表示学习目标；仅使用单一游戏环境和单一机器人数据集，泛化性需进一步验证。

## 6. 主要结论与发现

- **缩放定律存在性**：世界模型和行为克隆的预训练损失均服从类似LLM的幂律缩放定律，可以预测最优模型和数据大小。
- **世界模型（WM）**：
    - 使用256 tokens/图像时，最优模型/数据大小系数约为0.49/0.51，即应按相同比例增加模型和数据（与Chinchilla法则一致）。
    - 使用540 tokens/图像时，系数变为0.62/0.37，倾向于更多扩大模型。
    - **分词器压缩率影响**：压缩率越低（每个图像token数越多），最优模型大小系数越大（更偏模型），该现象在RT-1消融实验和语言模型实验中得到验证。
- **行为克隆（BC）**：
    - 使用Tokenized架构（BC-Token-540）时，模型损失难以饱和，最优系数偏向数据量（N≈0.32, D≈0.68），且计算最优模型规模远小于WM。
        - 原因：稀疏损失（只有3% token用于BC监督）和超类目标（相同动作对应不同情境）导致模型难以饱和。
    - 使用CNN架构（BC-CNN）时，每个观测仅一个嵌入，损失更快收敛，最优系数偏向模型（N≈0.66, D≈0.34），与Tuyls et al.结果一致。
- **外推能力**：在WM-Token-256上，由缩放定律预测的894M模型损失和最优配置与实际训练结果高度吻合，证明幂律可良好外推。
- **预训练损失与性能相关性**：在无限数据区下，预训练损失与在线奖励（BC）或视频生成质量（WM）强相关（R > 0.8或R<-0.94），支持将损失作为代理指标。

## 7. 优点

- **填补空白**：首次将LLM缩放定律系统性地引入世界模型和行为克隆，揭示了具身AI预训练中的精确缩放规律。
- **方法论严谨**：采用两种互补的拟合方法（Frontier和Parametric），并验证了无限数据区假设；通过关联下游性能论证损失代理的有效性。
- **多维度分析**：系统考察了任务（WM vs BC）、架构（Tokenized vs CNN）、分词器压缩率对缩放系数的影响，提供了可操作的设计准则（例如，BC应用CNN架构以更高效利用计算）。
- **外推验证**：通过训练一个10倍计算量的大模型证实了缩放定律的外推准确性，增强了结论可信度。
- **跨领域验证**：在游戏和机器人两个不同领域（Bleeding Edge和RT-1）均观察到类似规律，表明结果有一定泛化性。

## 8. 不足与局限

- **实验覆盖有限**：仅使用了单一游戏环境（Bleeding Edge）和一个机器人数据集（RT-1），未在更多样化的具身场景（如多机器人任务、开放世界模拟）中验证。
- **目标范围受限**：仅关注生成式预训练损失，未研究奖励模型（如Dreamer）、表示学习（如R3M）或微调后的下游性能的缩放规律。
- **计算资源未充分披露**：未提供GPU型号、数量、训练时长等具体信息，影响可复现性。最大模型（894M）的超参数未充分调优，可能偏离真正最优。
- **BC-Token场景的拟合困难**：BC-Token模型的损失曲线在有限计算预算下不饱和，依赖参数化拟合（Parametric fit），其假设较强（函数形式固定），可能引入偏差。作者虽用小规模语言实验解释，但直接证据不足。
- **推理成本未考虑**：缩放分析仅关注训练计算，未纳入推理计算（如Sardana & Frankle, 2023），在实际部署中可能改变最优配置。
- **潜在风险**：结论“预训练损失与性能强相关”仅在无限数据区成立，若数据有限或模型微调后，该相关性可能减弱，实际应用中需谨慎。

（完）
