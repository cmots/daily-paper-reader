---
title: Grammar-Forced Translation of Natural Language to Temporal Logic using LLMs
title_zh: 使用LLM的语法强制自然语言到时间逻辑翻译
authors: "William H English, Dominic Simon, Sumit Kumar Jha, Rickard Ewetz"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=p411a7WHox"
tags: ["query:wm-vla-sa"]
score: 6.0
evidence: 自然语言到时间逻辑翻译用于机器人
tldr: 该论文针对自然语言到时间逻辑翻译中准确接地和共指消解困难的问题，提出语法强制翻译框架（GraFT），通过限制语言模型词汇预测降低复杂度，在机器人任务中提高了翻译准确性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-p411a7whox/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1740, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p411a7whox/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1865, \"height\": 622, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p411a7whox/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1778, \"height\": 834, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p411a7whox/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 714, \"height\": 679, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p411a7whox/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1780, \"height\": 658, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-p411a7whox/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1778, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p411a7whox/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1734, \"height\": 586, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p411a7whox/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 852, \"height\": 414, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p411a7whox/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1043, \"height\": 415, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p411a7whox/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 961, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p411a7whox/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 993, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p411a7whox/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 993, \"height\": 285, \"label\": \"Table\"}]"
motivation: 现有方法在接地和共指处理上存在困难。
method: 通过语法强制减少语言模型预测空间。
result: 在机器人指令翻译任务上表现更好。
conclusion: GraFT简化了自然语言到形式语言的翻译。
---

## Abstract
Translating natural language (NL) into a formal language such as temporal logic (TL) is integral for human communication with robots and autonomous systems. State-of-the-art approaches decompose the task into a grounding of atomic propositions (APs) phase and a translation phase. However, existing methods struggle with accurate grounding, the existence of co-references, and learning from limited data. In this paper, we propose a framework for NL to TL translation called Grammar Forced Translation (GraFT). The framework is based on the observation that previous work solves both the grounding and translation steps by letting a language model iteratively predict tokens from its full vocabulary. In contrast, GraFT reduces the complexity of both tasks by restricting the set of valid output tokens from the full vocabulary to only a handful in each step. The solution space reduction is obtained by exploiting the unique properties of each problem. We also provide a theoretical justification for why the solution space reduction leads to more efficient learning. We evaluate the effectiveness of GraFT using the CW, GLTL, and Navi benchmarks. Compared with state-of-the-art translation approaches, it can be observed that GraFT improves the end-to-end translation accuracy by 5.49% and out-of-domain translation accuracy by 14.06% on average.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义（研究动机和背景）

- **问题**：将自然语言（NL）翻译为时间逻辑（TL）是机器人和自主系统人机交互的关键环节。但现有两步法（原子命题接地 + 翻译）在准确接地、共指消解、小样本学习等方面存在困难。
- **背景**：已有工作依赖大语言模型（LLM）在整个词表上自回归预测，导致搜索空间巨大、训练效率低、泛化差。本文旨在通过缩小有效输出 token 范围来提升翻译准确性和数据效率。

### 论文提出的方法论

- **核心思想**：将 NL→TL 分解为两个子任务，每个子任务都利用任务自身的约束（AP 接地用整数标签、TL 翻译用语法规则）将模型的输出词表从全词表（数万）缩小到寥寥数个，从而降低复杂度、提升学习效率。
- **关键技术细节**：
  1. **AP 接地**：使用掩码语言模型（MLM，如 BERT）进行**整数标签预测**。对输入 NL 中的每个 token 预测一个整数（0 表示非 AP，n 表示属于第 n 个 AP）。这使得 MLM 的输出词表从数万缩小到 6（0-5 标签）。  
  2. **翻译**：使用序列到序列模型（Seq2Seq，如 T5），并引入**语法强制解码**（Grammar-Forced Decoding）。在训练和推理阶段，利用 TL 的上下文无关文法动态维护一个解析状态，在每个解码步只允许输出符合语法的 token（通常 1–20 个），其余 token 的概率被置为 0（logit 设为 -∞）。  
  3. **理论依据**：证明了在合法 token 子集上计算交叉熵损失 ≤ 全集上的损失，且梯度更新仅作用于合法 token，减少了梯度噪声，使得 SGD 收敛方差更小，加快收敛。

- **算法流程**（文字说明）：
  - 输入 NL 句子 → MLM 模型（BERT）为每个 token 预测整数标签，将 AP 替换为 `prop_i` 得到“升格后的 NL”（Grounded NL）。
  - 升格后的 NL 输入 T5 模型，解码时每个时间步通过一个 LTL Logits Processor（Algorithm 1）根据当前语法状态计算合法 token 集合，掩码掉非法 token，仅从合法集合中选择 token，生成“升格后的 TL”（Grounded TL）。
  - 最后将步骤 1 的 AP 映射还原，得到最终 TL 公式。

### 实验设计

- **数据集与场景**：三个 NL→TL 基准：
  - **CW**（MacGlashan et al., 2015）：2130 条 NL，39 条唯一 TL。
  - **GLTL**（Gopalan et al., 2018）：11153 条 NL，188 条唯一 TL。
  - **Navi**（Wang et al., 2021）：7079 条 NL，142 条唯一 TL。
- **Benchmark 与对比方法**：
  - NL2LTL（Fuggitti & Chakraborti, 2023）— 使用 GPT-4o-mini，无接地。
  - NL2Spec（Cosler et al., 2023）— GPT-4o-mini，无接地。
  - Ungrounded Seq2Seq — T5 直接翻译，无接地。
  - NL2TL（Chen et al., 2023）— 使用 GPT-4o-mini / GPT-4 进行 AP 接地 + T5 翻译。
- **评估指标**：端到端翻译准确率（公式完全匹配）、AP 接地准确率、跨域泛化准确率。

### 资源与算力

- 硬件：**一台 NVIDIA RTX 4070 Ti Super GPU**（12GB VRAM），Intel i9-14900KF 32 核 CPU，64GB RAM。
- 训练设置：AP 接地模型（BERT/RoBERTa/DistilBERT）训练 3 epoch，学习率 1e-5；翻译模型（T5）训练 3 epoch，学习率 2e-5。文中未明确报告总训练时长，但基于单卡和少量 epoch，算力需求较低。

### 实验数量与充分性

- **实验组数**：
  - **AP 接地对比**（表 3）：3 种 MLM vs. 3 种 CLM（GPT-4o-mini/GPT-4o/GPT-4），在 1000 个 Navi 测试样本上评估。
  - **翻译模型消融**（图 5）：T5 标准解码 vs. T5 + 语法强制解码，数据量从 500 到 2000 步进，在 3 个数据集上对比。
  - **端到端翻译**（表 2）：在 500 和 2000 训练样本两个规模下，对比 6 种方法，每个数据集 1000 测试样本。
  - **跨域泛化**（表 4）：用两个域的数据训练，在所有三个域上测试，共 3 组跨域实验。
  - **AP 接地扩展性**（附录 A.3，表 6–7）：测试 6–10 个 AP 和 11–15 个 AP 的极端情况。
- **充分性与公平性**：实验覆盖了同域和跨域、多数据规模、多个 SOTA 方法，消融实验充分，对比基线均为近两年相关工作。评估使用 1000 个未见测试样本，可信度较高。但未报告多次运行的标准差，可能存在随机性。

### 论文的主要结论与发现

- GraFT 在端到端翻译准确率上平均提升 **5.49%**（对比 NL2TL），跨域翻译准确率提升 **14.06%**。
- AP 接地采用 MLM（BERT）显著优于 CLM（GPT-4 系列），在 Navi 数据集上接近 100%，且能够直接迁移到其他域（CW、GLTL 上 >97%）。
- 语法强制训练使得 T5 在小样本（500）下即获得高精度（>90%），且不会因数据量增加导致准确率下降（而标准训练在 CW 上出现退化）。
- 理论分析表明，限制输出 token 集合降低了交叉熵和梯度方差，从而加速收敛、提高泛化。

### 优点

- **方法创新**：首次将 MLM 整数标签用于 AP 接地，并利用 TL 语法进行动态输出约束，大幅缩小搜索空间。
- **理论扎实**：提供了严格的数学证明（交叉熵减小、梯度对齐改进、SGD 收敛方差降低），增强了方法的可信度。
- **数据高效**：仅需 500–2000 标注样本即可达到极高性能，且 MLM 接地模型仅在 Navi 上训练即可泛化到其他域，降低了标注成本。
- **实验全面**：涵盖同域、跨域、多数据量、多种基线，并进行了 AP 接地扩展性分析，验证了方法的鲁棒性。
- **开源友好**：采用常见模型（BERT/T5），单卡即可复现。

### 不足与局限

- **语法依赖**：方法需要预先定义目标 TL 的上下文无关文法，对于非标准或未预定义的形式语言无法直接应用。
- **AP 接地标注成本**：MLM 需要 AP 标注数据（本文只用 Navi 标注），但跨域泛化依赖 Navi 语料的完备性，若目标域出现全新类型的 AP 可能失败。
- **实验范围有限**：仅测试了三个相对小型的室内任务数据集（CW、GLTL、Navi），未在更大规模、更复杂的 NL 语料（如多步骤长句、嵌套时态）上验证。
- **未报告方差**：所有结果均为单次运行，未提供多次实验的均值和标准差，无法判断结果的统计显著性。
- **硬件限制**：仅使用单卡 RTX 4070 Ti Super，未探索更大模型（如 T5-3B）或更长训练是否能进一步提升性能；也未与其他基于 RL 的最新方法（如利用奖励微调）进行对比。

（完）
