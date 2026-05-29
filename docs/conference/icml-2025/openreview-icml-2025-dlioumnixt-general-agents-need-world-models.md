---
title: General agents need world models
title_zh: 通用智能体需要世界模型
authors: "Jonathan Richens, Tom Everitt, David Abel"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=dlIoumNiXt"
tags: ["query:wm-vla-sa"]
score: 10.0
evidence: 世界模型用于目标导向智能体
tldr: 该论文通过形式化证明回答了世界模型是否是灵活、目标导向行为所必需的，结果表明任何能够泛化到多步目标导向任务的智能体都必须学习环境的预测模型，且性能提升依赖于更精确的世界模型，对开发通用安全AI具有重要意义。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-dlioumnixt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 559, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dlioumnixt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 842, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dlioumnixt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 852, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dlioumnixt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 690, \"height\": 287, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-dlioumnixt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1797, \"height\": 1646, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dlioumnixt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1772, \"height\": 345, \"label\": \"Table\"}]"
motivation: 探讨模型无关学习是否足以支持灵活的目标导向行为。
method: 通过理论分析证明，并从智能体策略中提取世界模型。
result: 证明世界模型是泛化到多步任务所必需的。
conclusion: 世界模型对通用智能体至关重要。
---

## Abstract
Are world models a necessary ingredient for flexible, goal-directed behaviour, or is model-free learning sufficient?
We provide a formal answer to this question, showing that any agent capable of generalizing to multi-step goal-directed tasks must have learned a predictive model of its environment.
We show that this model can be extracted from the agent's policy, and that increasing the agents performance or the complexity of the goals it can achieve requires learning increasingly accurate world models.
This has a number of consequences: from developing safe and general agents, to bounding agent capabilities in complex environments, and providing new algorithms for eliciting world models from agents.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：世界模型是否是实现灵活、目标导向行为的必要条件？还是说模型无关（model-free）学习足以达到通用人工智能？
- **研究背景**：人类智能的核心之一是能够零样本或少样本完成新任务，这依赖于丰富的世界心理表征（世界模型）。在语言模型和通用智能体快速发展的背景下，是否必须学习世界模型一直是争论焦点：Brooks 曾提出“世界是其自身最好的模型”，认为所有智能行为可以从无模型交互中涌现；但近期研究发现模型无关智能体可能隐式学习了世界模型甚至规划算法。
- **研究动机**：为这一争论提供形式化答案，证明任何满足遗憾界（regret bound）的、能够泛化到多步目标导向任务的智能体，必然已经学习了其环境的预测模型；并且该模型的精度随智能体性能和目标复杂度的提升而提升。这一结论对通用AI开发、安全性和可解释性有深远影响。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：通过反证法——假设智能体是遗憾有界的目标条件策略（定义5），证明它必须包含一个环境转移函数的近似（世界模型），并且可以从其策略中提取出来。
- **主要假设**：
  - 环境为有限、不可约、平稳的受控马尔可夫过程（cMP，定义1），且至少有两个动作。
  - 智能体为遗憾有界的目标条件策略（定义5），参数包括最大失败率 δ 和最大目标深度 n（复合目标，定义3）。
  - 目标采用线性时序逻辑（LTL）表示，包括“最终（Eventually）”、“下一时刻（Next）”等算子。
- **定理1**：对于满足假设的环境和满足定义5的智能体（δ 和 n > 1），智能体的策略 π 完全确定了转移概率的一个估计 \(\hat{P}_{ss'}(a)\)，且误差满足：
  \[
  |\hat{P}_{ss'}(a) - P_{ss'}(a)| \le \sqrt{\frac{2P_{ss'}(a)(1-P_{ss'}(a))}{(n-1)(1-\delta)}}
  \]
  当 δ ≪ 1, n ≫ 1 时，误差标度为 \(O(\delta/\sqrt{n}) + O(1/n)\)。
- **算法流程（算法1）**：
  1. 对于每个待估计的转移 (s, a, s')，选择一个替代动作 b。
  2. 构造一族复合目标 ψ_{a,b}(k, n) = ψ_a(k, n) ∨ ψ_b(k, n)，其中 ψ_a(k, n) 表示先采取动作 a，然后重复 n 次“尝试从 s 转移到 s'”，且成功次数 ≤ k；ψ_b(k, n) 表示先采取动作 b，且成功次数 > k。
  3. 查询智能体在 ψ_{a,b}(k, n) 下的第一个动作选择 a0。
  4. 通过二分或线性搜索找到最小的 k 使得智能体选择动作 a（即偏好 ≤ k 次成功的目标），记作 k*。
  5. 估计值 \(\hat{P}_{ss'}(a) = (k^* - 1/2)/n\)。
- **算法2**：简化版本，通过对比单个成功/失败序列的概率来估计，用于实验。
- **定理2**：对于仅优化单步（深度1）目标的近视智能体，无法从策略中获得任何非平凡的转移概率界（误差为1），证明世界模型仅对多步目标必要。

## 3. 实验设计

- **数据集/场景**：使用随机生成的受控马尔可夫过程（cMP），含20个状态和5个动作，转移函数稀疏（每个状态-动作对最多5个非零概率转移），满足不可约性假设。
- **基准（benchmark）**：没有与现有方法对比，而是测试算法2从智能体策略中恢复世界模型的精度随智能体能力的变化。智能体能力通过训练样本量（Nsamples）控制，从500到10000不等。
- **对比方法**：未对比其他方法。仅验证所提算法的有效性。

## 4. 资源与算力

- **文中未明确说明**使用的GPU型号、数量或训练时长。仅提及智能体基于采样的经验轨迹训练，且重复10次实验取均值。未提供具体硬件信息或计算时间。

## 5. 实验数量与充分性

- **实验数量**：共11个不同样本量（500,1000,...,10000），每个样本量训练10个智能体（不同随机种子），取平均值；对于每个智能体，测试10个不同的最大目标深度Ndepth（10,20,...,600）。
- **充分性**：实验覆盖了从低样本到高样本的广泛范围，且考察了不同目标深度下恢复误差的变化。实验设计能够展示误差随训练数据和目标深度增加而下降的趋势，验证了理论标度 \(O(n^{-1/2})\)。但仅使用单一环境（20状态5动作），未在更复杂或真实环境中验证，可能限制推广性。未与其他世界模型恢复方法（如机械可解释性中的探测法）直接比较。

## 6. 主要结论与发现

1. **世界模型的必要性**：任何能够泛化到多步目标导向任务的遗憾有界智能体，都必须学习一个准确的环境预测模型。即不存在“模型无关”的捷径实现通用智能体。
2. **世界模型的可提取性**：提出了从智能体策略中恢复转移函数的算法（算法1/2），且误差随智能体遗憾降低或目标深度增加而减小。
3. **能力上界**：智能体的最终能力受限于其世界模型的精度；学习现实世界模型非常困难，因此通用AI发展存在根本性限制。
4. **安全意义**：可以从强大智能体中提取世界模型，用于安全验证和可解释性，解决模型无关智能体难以审计的问题。
5. **近视智能体例外**：仅优化单步目标的近视智能体不需要世界模型，说明世界模型是从多步目标中涌现的必要条件。

## 7. 优点

- **理论严谨**：基于马尔可夫决策过程和线性时序逻辑给出了形式化定理和证明，填补了世界模型必要性在理论上的空白。
- **创新性**：提出从智能体策略（而非内部表征）恢复世界模型的算法，比机械可解释性方法更通用（不依赖激活值）。
- **实用性**：算法在智能体强烈违反假设（最坏情况遗憾为1）时仍能有效工作（实验显示平均误差良好）。
- **应用广泛**：为安全AI、可解释性、能力边界研究提供了理论基础和实用工具。

## 8. 不足与局限

- **环境假设限制**：仅考虑完全可观、有限、不可约、平稳的马尔可夫过程，未扩展到部分可观、非马尔可夫或无限状态环境。
- **目标类型有限**：证明中使用的复合目标仅限于“最终/下一时刻”算子，未检验更复杂时序逻辑（如“直到”或嵌套）是否同样蕴含世界模型。
- **智能体定义**：假设智能体为确定性策略，且满足全局遗憾界（所有目标深度≤n的复合目标）。实际智能体可能只满足平均遗憾界，理论界在平均情况下不保证。
- **实验规模小**：仅在一个合成环境（20状态）中验证，未在更真实或大规模场景（如机器人控制、游戏）中测试算法。未与其他世界模型提取方法（如探测、SAE）对比。
- **算力成本未讨论**：算法需要对每个转移进行多次策略查询，在状态-动作空间大时可能计算开销高，文中未分析复杂度或实际运行时间。
- **未能证明世界模型的“使用”**：定理证明策略中编码了世界模型，但未证明智能体实际使用它进行规划或推理，可能存在“学到但不使用”的情况。

（完）
