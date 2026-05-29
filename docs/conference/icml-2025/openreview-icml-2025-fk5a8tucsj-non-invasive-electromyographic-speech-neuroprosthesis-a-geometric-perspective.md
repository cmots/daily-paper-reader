---
title: "Non-invasive electromyographic speech neuroprosthesis: a geometric perspective"
title_zh: 非侵入性肌电言语神经假体：一种几何视角
authors: "Harshavardhana T Gowda, Ferdous Rahimi, Lee M. Miller"
date: 2025-01-19
pdf: "https://openreview.net/pdf?id=fk5a8tUCSJ"
tags: ["query:speech-model"]
score: 8.0
evidence: 用于无声语音的肌电到语音翻译
tldr: 本文提出一种基于肌电信号的非侵入式言语神经假体，将无声的语音意图翻译为文本或音频，旨在帮助失去清晰发音能力的患者恢复言语交流。系统收集面部和颈部的肌电信号，通过几何视角实现高带宽翻译，为言语康复提供新方案。
source: ICML-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-fk5a8tucsj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 608, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fk5a8tucsj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 670, \"height\": 931, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fk5a8tucsj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 623, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fk5a8tucsj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 622, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fk5a8tucsj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1763, \"height\": 943, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fk5a8tucsj/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1766, \"height\": 937, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fk5a8tucsj/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 834, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fk5a8tucsj/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 708, \"height\": 504, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-fk5a8tucsj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 914, \"height\": 375, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fk5a8tucsj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 710, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fk5a8tucsj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 916, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fk5a8tucsj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 473, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fk5a8tucsj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1911, \"height\": 1467, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fk5a8tucsj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 814, \"height\": 718, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fk5a8tucsj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 797, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fk5a8tucsj/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 682, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fk5a8tucsj/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 684, \"height\": 208, \"label\": \"Table\"}]"
motivation: 帮助因喉切除等丧失清晰发音能力的患者恢复言语交流。
method: 采集面部和颈部多个发音部位的肌电信号，实现肌电到文本或音频的翻译。
result: 实现了无声语音的高带宽翻译，有望辅助言语恢复。
conclusion: 该神经接口为言语恢复提供了一种非侵入性且高带宽的有效方法。
---

## Abstract
In this article, we present a high-bandwidth *egocentric* neuromuscular speech interface for translating silently voiced speech articulations into text and audio. Specifically, we collect electromyogram (EMG) signals from multiple articulatory sites on the face and neck as individuals articulate speech in an alaryngeal manner to perform EMG-to-text or EMG-to-audio translation. Such an interface is useful for restoring audible speech in individuals who have lost the ability to speak intelligibly due to laryngectomy, neuromuscular disease, stroke, or trauma-induced damage (e.g., radiotherapy toxicity) to speech articulators. Previous works have focused on training text or speech synthesis models using EMG collected during *audible* speech articulations or by transferring audio targets from EMG collected during *audible* articulation to EMG collected during *silent* articulation. However, such paradigms are not suited for individuals who have already lost the ability to *audibly* articulate speech. We are the first to present an alignment-free EMG-to-text and EMG-to-audio conversion using only EMG collected during *silently* articulated speech in an open-sourced manner. On a limited vocabulary corpora, our approach achieves almost $2.4\times$ improvement in word error rate with a model that is $25\times$ smaller by leveraging the inherent geometry of EMG.

---

## 论文详细总结（自动生成）

以下是根据论文内容生成的中文总结：

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：因喉切除、神经肌肉疾病、中风或放疗毒性等导致失去清晰发音能力的患者，需要一种非侵入性的无声语音接口，将无声的语音意图转化为可听语音或文本。
- **背景**：现有方法多依赖有声发音时的EMG（`EA`）和音频（`A`）进行训练，不适合已丧失有声发音能力的个体；且需要精确的时间对齐，计算成本高。
- **本文贡献**：首次提出仅利用无声发音时采集的EMG（`ES`），无需对齐、无需`EA`和`A`，实现端到端的EMG到文本/音频翻译；利用EMG的几何结构（对称正定矩阵流形）实现高带宽、低参数量的解码。

## 2. 方法论

### 核心思想
- 将EMG信号建模为图连通性学习问题，在对称正定（SPD）矩阵流形上使用单层循环网络（GRU）结合连接主义时间分类（CTC）损失进行序列到序列翻译。

### 关键技术细节
1. **数据表示**：
   - 对每个时间窗口 `τ`，构建完全图，边权重为两通道信号的协方差，得到SPD邻接矩阵 `E(τ)`。
   - 通过Cholesky分解计算所有 `E(τ)` 的Fréchet均值 `F`，并对其特征分解得到公共特征基 `Q`。
   - 用 `Q` 近似对角化每个 `E(τ)`，得到稀疏矩阵 `σ(τ) = Q^T E(τ) Q`，作为后续输入。
2. **序列建模**：
   - 设计三种GRU变体：
     - `GRU A`：标准欧几里得GRU（输入向量化的 `σ`）。
     - `GRU B`：在SPD流形上定义的GRU（基于Cholesky空间操作，见附录C公式1-4）。
     - `GRU C`：在 `GRU B` 基础上增加隐层神经ODE，模拟流形上的动力学。
   - 输出40个音素的概率分布，CTC损失训练，推理时用Beam Search解码。
3. **音频合成**：利用少样本学习（Choi et al., 2021）将预测的音素序列转化为个性化音频（需3-5分钟参考音频）。

## 3. 实验设计

### 数据集
- **Data SMALL-VOCAB**：67词（星期、月份、年份等），500个无声句子，31通道EMG，5000Hz采样。
- **Data LARGE-VOCAB**：约6500词、11000句，仅无声EMG，无时间戳词边界，31通道。
- **Data NATO-WORDS**：4个受试者用北约音标码拼读句子，22通道。

### Benchmark与对比方法
- **主要对比**：Gaddy & Klein (2020, 2021) 的方法（需EA和A，模型约40M参数，WER 64%）。
- **本文**：仅用ES，模型约1.4M参数，WER 27%，实现2.4倍提升、25倍参数减少。
- 另外与Willett等（侵入式BCI，128电极）和Metzger等（侵入式ECoG）定性比较。

### 对比方法
- 三种GRU变体（A、B、C）在不同模型大小（隐藏单元数）下对比。
- 在Data SMALL-VOCAB上对8电极、1000Hz下重做对比实验。

## 4. 资源与算力

- **论文未明确说明GPU型号、数量**。
- 仅提到：“Model training is completed in just a few minutes, whether using a GPU or CPU.”（训练只需几分钟，无论GPU还是CPU均可完成）。
- 未提供具体算力消耗细节（如浮点运算数、内存使用等）。

## 5. 实验数量与充分性

- **实验组数**：
  - 三个数据集（SMALL、LARGE、NATO）各自进行了多种模型规模（隐藏单元维度变化）和10个随机种子的重复实验。
  - 在Data SMALL上还做了电极配置消融（31 vs 8电极、不同子集）、训练数据量对精度的影响。
  - 在NATO-WORDS上对4个受试者分别评测。
- **充分性评价**：
  - 实验较全面，覆盖了不同词汇量、不同受试者、不同模型架构、不同电极数。
  - 对比了欧几里得与流形方法，并报告了均值与分布（图3、4、5、6）。
  - 但缺乏在真实患者上的验证，且NATO-WORDS的WER较高（平均40.61% vs Gowda et al.的43.56%），作者解释因序列模型上下文较短。
  - 总体公平客观，但缺少与更多近期非侵入式方法（如基于脑电图/脑磁图的解码）的直接更强对比。

## 6. 主要结论

- 利用EMG的几何结构（SPD流形）和公共特征基近似对角化，可以用极小模型（单层GRU）实现有效的无声语音到文本/语音翻译。
- 在67词词汇上达到88%解码准确率（WER 12%），对比方法WER 64%。
- 在大词汇语料（6500词）上达到音素错误率（PER）56%。
- 通过北约音标码拼读可实现少量数据泛化（训练10分钟，测试近5倍数据）。
- 该方法为非侵入式言语神经假体提供了可行路径，尤其适合不能植入电极的患者。

## 7. 优点

- **数据效率高**：仅需无声EMG，无需对齐，无需有声数据。
- **模型极度轻量**：单层GRU，参数仅约1.4M（对比40M），训练快（几分钟）。
- **几何洞察**：将信号分布漂移解释为基变换，为跨个体适应提供理论视角。
- **系统完整**：从EMG到文本再到个性化音频合成，有开源数据和代码（待发表）。
- **实验设计清晰**：多种数据集、多受试者、多模型变体，对比公平。

## 8. 不足与局限

- **词汇规模有限**：大词汇PER仍达56%，远不如侵入式BCI（21%），且测试为单受试者。
- **未在真实患者群体验证**：所有数据来自健康受试者无声发音，临床有效性待确认。
- **模型仅针对特定个体**：不同个体需不同特征基 `Q` 和微调，未展示跨个体零样本泛化。
- **音频合成依赖外部库**：gTTS+Choi模型，实际实时性未知。
- **NATO-WORDS结果低于分类基线**：序列模型在此任务上不如分类模型，作者归因于上下文窗口过短，可能非最优设计。
- **算力报告缺失**：未提供具体GPU型号、训练时长、能耗等，可重复性受影响。
- **未比较语言模型后处理**：可结合语言模型进一步提升准确率（作者已提及未来工作）。

（完）
