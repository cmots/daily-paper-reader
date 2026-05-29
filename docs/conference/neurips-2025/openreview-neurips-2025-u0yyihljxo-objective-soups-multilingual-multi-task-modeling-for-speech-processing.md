---
title: "Objective Soups: Multilingual Multi-Task Modeling for Speech Processing"
title_zh: 目标汤：多语言多任务语音处理建模
authors: "A F M Saif, Lisha Chen, Xiaodong Cui, Songtao Lu, Brian Kingsbury, Tianyi Chen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=u0YyIHljXO"
tags: ["query:speech-model"]
score: 8.0
evidence: 多语言多任务语音到文本翻译
tldr: Objective Soups针对多语言多任务语音处理中目标冲突问题，提出将多目标优化分解为独立优化再组合的“目标汤”方法。在ASR和语音到文本翻译联合建模中，该方法避免了梯度冲突难以找到共同下降方向的问题，在多个语对上取得性能提升，为多任务语音翻译提供了高效解决方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-u0yyihljxo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 866, \"height\": 418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-u0yyihljxo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 841, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-u0yyihljxo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 719, \"height\": 601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-u0yyihljxo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1432, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-u0yyihljxo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 781, \"height\": 621, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-u0yyihljxo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 985, \"height\": 381, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-u0yyihljxo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1407, \"height\": 797, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-u0yyihljxo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1358, \"height\": 448, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-u0yyihljxo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1270, \"height\": 449, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-u0yyihljxo/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 808, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-u0yyihljxo/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1402, \"height\": 1644, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-u0yyihljxo/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1036, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-u0yyihljxo/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 920, \"height\": 308, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-u0yyihljxo/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1040, \"height\": 327, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-u0yyihljxo/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1467, \"height\": 283, \"label\": \"Table\"}]"
motivation: 多语言多任务语音模型（如ASR和翻译）中多目标优化存在目标冲突，难以找到共同下降方向。
method: 独立优化每个目标再通过模型参数平均（目标汤）进行组合，避免梯度竞争。
result: 在多个语音翻译基准上超过联合训练和单任务模型，训练效率更高。
conclusion: 目标汤方法为多任务语音处理提供了一种实用且有效的训练策略。
---

## Abstract
The need for training multilingual multi-task speech processing (MSP) models that perform both automatic speech recognition and speech-to-text translation is increasingly evident. However, a significant challenge arises from the conflicts among multiple objectives when using a single model. Multi-objective optimization can address this challenge by facilitating the optimization of multiple conflicting objectives and aligning the gradient updates in a common descent direction. While multi-objective optimization helps avoid conflicting gradient updates, a critical issue is that when there are many objectives, such as in MSP, it is often {\em difficult to find} a common descent direction. This leads to an important question: Is it more effective to separate highly conflicting objectives into different optimization levels or to keep them in a single level? To address this question, this paper investigates three multi-objective MSP formulations, which we refer to as \textbf{objective soup recipes}. These formulations apply multi-objective optimization at different optimization levels to mitigate potential conflicts among all objectives. To keep computation and memory overhead low, we incorporate a lightweight layer‑selection strategy that detects the most conflicting layers and uses only their gradients when computing the conflict‑avoidance direction. We conduct an extensive investigation using the CoVoST v2 dataset for combined multilingual ASR and ST tasks, along with the LibriSpeech and AISHELL-1 datasets for multilingual ASR, to identify highly conflicting objectives and determine the most effective training recipe among the three proposed multi-objective optimization algorithms.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义（研究动机和背景）

- 当前多语言多任务语音处理（MSP）模型（如同时进行语音识别ASR和语音到文本翻译ST）面临严重的目标冲突问题：优化一个任务会损害另一个任务，导致训练困难。
- 传统的多目标优化（MOO）方法试图通过动态加权来对齐梯度方向，但随着任务数量增加，找到一个共同下降方向变得极为困难。
- 因此提出核心问题：是否应该将高度冲突的目标分离到不同的优化层级中，而不是放在同一平面内优化？本文围绕此问题提出三种“目标汤”配方，并系统评估其效果。

### 论文提出的方法论

#### 核心思想
- 将多目标优化与层级结构相结合，构建三种不同层次的优化配方：
  - **VS-MSP（向量化单层）**：将所有目标（包括自监督损失、多个语言的ASR和ST损失）放在同一层，使用动态加权（MoDo算法）求冲突避免方向。
  - **VC-MSP（双层）**：将自监督损失作为下层约束（惩罚项），上层优化监督目标（ASR+ST），通过惩罚参数η控制。
  - **VM-MSP（多层）**：进一步将ASR和ST分离到不同层级，形成三级结构（自监督→任务A→任务B），通过多层惩罚参数η₁, η₂控制。

#### 关键技术细节
- **冲突避免方向计算**：采用MoDo算法（随机多梯度下降），通过双采样估计无偏梯度，求解最小化梯度范数的加权组合。
- **层级间惩罚机制**：用惩罚项近似约束，惩罚参数从0开始线性增加（如每epoch增加0.02，上限1.5），实现逐步加强低层约束。
- **轻量级层选择机制**：仅对余弦相似度为负（冲突）的编码器层计算动态更新方向，减少17%训练时间和18%内存占用，且不损失性能。

#### 算法流程（文字说明）
- 每个epoch：从标注数据中采样两个独立批次，从无标注数据中采样两个批次。
- 计算各目标梯度，通过MoDo更新动态权重λ。
- 根据配方（VS/VC/VM）组合梯度：VS用所有梯度加权；VC加惩罚项η·∇ℓ_u；VM加多层惩罚项。
- 更新共享编码器参数θ和任务/语言特定头部参数ϕ。

### 实验设计

#### 数据集
- **CoVoST v2**：多语言ST数据集，选取5种语言做ASR（En, Fr, De, Es, Ca），4种语言对做ST（Fr→En, De→En, Es→En, Ca→En）。
- **LibriSpeech（英语）** 和 **AISHELL-1（中文）**：用于多语言ASR实验。

#### 模型与基准
- 模型：Conformer A (150M)、Conformer B (83M)、Whisper-medium (约300M)、Wav2Vec2-XLSR (300M)。
- 对比方法：
  - 两阶段训练（预训练+微调）
  - 两阶段+静态加权（网格搜索权重）
  - 联合训练（不包含MOO）
  - VS-MSP、VC-MSP、VM-MSP（提出方法）

#### 评测指标
- ASR: 词错误率（WER）
- ST: BLEU分数

### 资源与算力

- 使用 **2块NVIDIA A5000 GPU 和 2块NVIDIA A4500 GPU**，Intel i9-7920X CPU，128GB DDR4内存。
- 每epoch训练时间：
  - 两阶段基线：3.5小时
  - MSP动态加权：4.1小时（增加17%）
  - 高效MSP（层选择）：3.7小时
- 训练总epoch：200（自监督+监督联合训练），预训练模型另需200+100 epoch。
- GPU显存占用：基线12.5GB → MSP 14.7GB → 高效MSP 12.8GB。

### 实验数量与充分性

- 涵盖 **3种模型架构**（Conformer、Whisper、Wav2Vec2）、**2个模型大小**（83M、150M）、**5种语言**（ASR）、**4种语言对**（ST）。
- 进行 **多种消融实验**：
  - 优化顺序（UAS vs USA，任务级/语言级）
  - 惩罚参数增速（0.002 vs 0.02）
  - 预训练方法（CPC vs BEST-RQ）
  - 轻量级层选择有效性
- 实验设计 **公平客观**：超参数一致（学习率、优化器、batch size等），统计单次运行结果（未报告误差棒，但对比趋势清晰）。
- **充分性评价**：实验数量较多，覆盖主要变体，结论可靠。

### 论文的主要结论与发现

1. **MOO显著降低梯度冲突，提升性能**：VS-MSP优于两阶段基线（WER降低9.8%，BLEU提升8.6%）。
2. **层级结构进一步改进**：VM-MSP优于VC-MSP（WER额外降低4.2%，BLEU提升2.8%）。
3. **任务级层级优于语言级层级**：将ASR和ST分离到不同层级比按语言分离效果更好（WER改善7.4%，BLEU提升8.5%）。
4. **层级顺序影响性能**：自监督→ASR→ST（UAS）在ASR上最优；自监督→ST→ASR（USA）在ST上最优。
5. **轻量级层选择有效**：仅计算冲突层的动态方向，减少17%时间、18%内存，不损失精度。

### 优点

- **方法创新**：首次系统研究多层级多目标优化在MSP中的应用，提出三种可扩展的配方。
- **高效性**：引入层选择剪枝机制，显著降低额外开销，实用性强。
- **实验全面**：涵盖多种模型、语言、任务，消融实验深入，结论可靠。
- **分析透彻**：通过梯度余弦相似度热力图直观展示冲突分布，为层级设计提供依据。
- **开源代码**：代码已公开，可复现。

### 不足与局限

- **架构依赖**：方法基于共享编码器+独立任务头架构，对于更紧密耦合的架构（如统一解码器）可能不适用，冲突会更深层传播。
- **计算开销**：尽管轻量级层选择降低了开销，但动态加权仍比基线训练时间增加约6%（3.5→3.7小时），GPU内存增加约2.4%。
- **实验覆盖**：未在更大规模模型（如Whisper-large）或更多任务（如语言识别、意图分类）上验证；未报告多次运行的统计误差。
- **惩罚参数敏感**：惩罚增速需精细调优，不同任务优先级的平衡依赖经验设置。
- **理论分析缺失**：论文主要依赖实验，未提供层级MOO的收敛性保证。

（完）
