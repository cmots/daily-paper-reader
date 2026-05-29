---
title: "NTPP: Generative Speech Language Modeling for Dual-Channel Spoken Dialogue via Next-Token-Pair Prediction"
title_zh: NTPP：通过下一标记对预测实现双通道口语对话的生成式语音语言建模
authors: "Qichao Wang, Ziqiao Meng, Wenqian Cui, Yifei Zhang, Pengcheng Wu, Bingzhe Wu, Irwin King, Liang Chen, Peilin Zhao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=5Gke1dfRVA"
tags: ["query:speech-model"]
score: 8.0
evidence: 生成式语音语言建模用于双通道口语对话，统一生成与理解
tldr: 现有语音语言模型未充分利用双通道对话数据的结构。本文提出NTPP（下一标记对预测）范式，利用双通道语音数据实现与说话人无关的口语对话学习。该方法通过预测成对标记同时建模理解和生成，提升了对话的自然性和流畅性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-5gke1dfrva/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 867, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5gke1dfrva/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1611, \"height\": 458, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5gke1dfrva/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1690, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5gke1dfrva/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1642, \"height\": 268, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5gke1dfrva/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 755, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5gke1dfrva/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 805, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5gke1dfrva/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 687, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5gke1dfrva/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 830, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5gke1dfrva/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 852, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5gke1dfrva/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1061, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-5gke1dfrva/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1420, \"height\": 259, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-5gke1dfrva/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 854, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5gke1dfrva/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1570, \"height\": 439, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5gke1dfrva/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1474, \"height\": 378, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5gke1dfrva/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1574, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-5gke1dfrva/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1734, \"height\": 810, \"label\": \"Table\"}]"
motivation: 当前语音语言模型未能充分挖掘双通道对话数据的内在对话结构。
method: 提出NTPP生成式建模范式，在双通道语音数据上预测下一对标记，实现说话人无关的口语对话学习。
result: 在对话生成任务上取得了更好的自然度和连贯性，接近GPT-4o的表现。
conclusion: NTPP为统一语音理解和生成提供了一种简洁有效的建模方式。
---

## Abstract
Inspired by the impressive capabilities of GPT-4o, there is growing interest in enabling speech language models (SLMs) to engage in natural, fluid spoken interactions with humans. Recent advancements have led to the development of several SLMs that demonstrate promising results in this area. However, current approaches have yet to fully exploit dual-channel speech data, which inherently captures the structure and dynamics of human conversation. In this work, we systematically explore the use of dual-channel speech data in the context of modern large language models, and introduce a novel generative modeling paradigm—Next-Token-Pair Prediction (NTPP)—to enable speaker-independent dual-channel spoken dialogue learning using decoder-only architectures for the first time. We evaluate our approach on standard benchmarks, and empirical results show that our proposed method, NTPP, significantly improves the conversational abilities of SLMs in terms of turn-taking prediction, response coherence, and naturalness. Moreover, compared to existing methods, NTPP achieves substantially lower inference latency, highlighting its practical efficiency for real-time applications.  Demo and code can be found at https://audio-3059.pages.dev.

---

## 论文详细总结（自动生成）

基于您提供的论文内容，以下是对该论文的详细中文总结，按要求的要点逐一展开。

## 论文总结：NTPP：通过下一标记对预测实现双通道口语对话的生成式语音语言建模

### 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：受GPT-4o等模型展示的实时语音交互能力启发，语音语言模型（SLMs）的研究日益增多。然而，现有方法未能充分利用双通道语音数据（即分别记录两个说话人音频通道的数据），这类数据天然包含了对话中的重叠、停顿、打断等动态结构，对于实现自然流畅的对话至关重要。
- **核心问题**：如何利用双通道语音数据，使SLMs能够进行实时、流畅、与说话人身份无关的对话生成，同时保持低推理延迟和高效的参数利用。
- **整体含义**：论文引入了一种新的生成式建模范式——下一标记对预测（NTPP），旨在以decoder-only架构首次实现双通道口语对话的联合学习，统一语音理解与生成，推动SLMs向更接近人类对话的实时交互迈进。

### 2. 方法论（核心思想、关键技术细节）
- **核心思想**：与传统方法建模条件分布 \(p(S_b | S_a)\)（如Moshi、LSLM）不同，NTPP直接建模双通道语音序列的联合分布 \(p(S_a, S_b)\)。在每个时间步 \(t\)，模型同时预测两个说话人的下一个标记对 \((s^a_t, s^b_t)\)，基于所有历史标记对。假设在每个时间步内，两个标记条件独立，从而分解为两个独立预测任务。
- **关键技术细节**：
  - **Token Pair Embedding**：对每个标记对，从码本中获取嵌入，添加共享的位置编码（因时间对齐）和通道编码（区分说话人）。在注意力机制的查询和键向量中加入位置和通道嵌入。
  - **Pair-wise Causal Masking**：在因果掩码中，每个 \(2 \times 2\) 块的对角线元素不掩码（即本时间步的两个标记互不看见），其余遵循因果顺序。
  - **推广到RVQ Tokenizer**：将二维RVQ编码序列展平成一维，引入循环深度嵌入（如正弦-余弦编码）区分每个标记的残差深度，并调整RVQ掩码策略：防止当前标记关注更深层次的标记，并交叉说话人掩码。
  - **两阶段训练**：第一阶段：在约14万小时的单通道语音数据上持续预训练SLM（使用NTP目标），建立基础语音表达能力；第二阶段：在Fisher双通道对话数据上进行NTPP训练，学习对话动态。

### 3. 实验设计
- **数据集**：
  - 第一阶段：三个大型单通道语音数据集，总计约140,000小时（具体未列出名称，但包含语音理解与合成数据），采用无文本学习范式。
  - 第二阶段：Fisher数据集（约2,200小时电话对话，每位说话人的音频记录在单独通道，8kHz上采样至16kHz）。
- **基准与对比方法**：
  - 对话轮次统计对比：dGSLM（带/不带交叉注意力）、LSLM、级联基线（ASR + 文本LM + TTS）。
  - 人类评估对比：dGSLM、SyncLLM、Moshi。
  - 额外对比：Moshi、SyncLLM用于中断/反思性停顿实验。
- **评估场景与指标**：
  - **对话轮次事件统计**：计算每分钟IPU（话语间停顿单元）、停顿、间隙、重叠的发生次数和累计时长，与真实Fisher数据比较平均绝对偏差。
  - **中断与反思性停顿**：使用GPT-4生成400个多样化场景，ChatTTS合成语音，判断NTPP作为听众时的表现与人类参考的一致性。
  - **人类评估**：25名母语者，采用5分制MOS分别评估自然度（N-MOS）和有意义性（M-MOS），包括Fisher和CANDOR（域外）数据集。
  - **推理延迟**：多轮对话中测量从输入语音结束到输出语音开始的时间，对比Moshi。
  - **说话人独立性**：交换说话人通道顺序，测量轮次统计指标的变化幅度。
  - **消融实验**：两阶段训练的有效性（单阶段 vs. 两阶段）、VQ vs. RVQ tokenizer的性能对比。

### 4. 资源与算力
- 文中明确说明：模型在**16块A100 GPU**上训练，采用余弦退火学习率调度（最小学习率4e-6，最大4e-4），每个训练周期40,000步，每步batch size为64。微调时学习率从4e-6到5e-5。未提及总训练时长（小时数）。

### 5. 实验数量与充分性
- 实验数量较多且覆盖全面：
  - 对话轮次统计（表2）：针对NTPP三个温度设置（0.1, 0.5, 0.9）以及多个基线，报告8个指标的绝对偏差。
  - 中断/停顿实验（图6）：在4种行为维度上比较与人类参考的一致性。
  - 人类评估（表3）：在Fisher和CANDOR两个数据集上报告平均MOS和标准误差，对比dGSLM、SyncLLM、Moshi及真实录音（GT）。
  - 延迟比较（图7）：覆盖1-10轮对话，显示NTPP始终低于感知阈值220ms。
  - 说话人独立性（表4）：在训练集和测试集上报告8个指标的变化绝对值，对比dGSLM、Moshi。
  - 消融实验（图8a, 8b）：两阶段训练 vs. 单阶段，VQ vs. RVQ损失对比。
- **充分性评估**：实验设计较为充分和客观。对比了代表性的基线，覆盖了核心能力评估（自然度、连贯性、轮次模拟、延迟、鲁棒性），同时进行了消融来验证设计选择。人类评估使用了25名评价者，公平性较好。但缺少与最新模型（如GPT-4o本身）的直接比较（因闭源），也仅在Fisher数据上训练，未评估更大规模或更多样化的双通道数据集。

### 6. 主要结论与发现
- NTPP显著提升了SLMs的对话能力：在轮次预测、响应连贯性和自然度上优于dGSLM、LSLM、级联基线及Moshi。
- NTPP在中断和反思性停顿场景中与人类参考标籤的一致性最高。
- 人类评估中，NTPP在Fisher和CANDOR数据集上的有意义性和自然性得分均接近或达到最高，尤其Fisher自然度得分4.42（Moshi为3.90）。
- NTPP推理延迟在所有轮次中低于Moshi，控制在220ms感知阈值以下，且随轮次增长延迟增加更平缓。
- NTPP在说话人通道交换后保持几乎不变的轮次统计指标，表现出最强的说话人独立性（dGSLM次之，Moshi较差）。
- 两阶段训练优于单阶段，且RVQ tokenizer比VQ带来更低的训练损失。

### 7. 优点
- **方法层面**：
  - 首次提出NTPP建模范式，统一建模双通道联合分布，无需额外编码器或VAD模块，实现真全双工。
  - 兼容VQ和RVQ tokenizer，通用性强。
  - 采用decoder-only架构，保持单KV缓存，内存和推理效率高。
- **实验层面**：
  - 多维度评估：从轮次统计、中断行为、人类感知、延迟、鲁棒性到消融分析，全面客观。
  - 使用了域外数据集CANDOR验证泛化能力。
  - 消融实验验证了两阶段训练和RVQ的必要性，设计科学。

### 8. 不足与局限
- **数据局限**：仅在Fisher数据集（约2,200小时）上训练双通道阶段，该数据集为英语电话对话，噪声和话题有限；领域外泛化未充分验证（CANDOR虽测试但仅评估自然性/有意义性，未评估轮次统计）。
- **实验覆盖不足**：缺少与最新闭源模型（如GPT-4o）的直接对比；未在更大的双通道数据集（如日常对话、多说话人会议）上评估。
- **潜在偏差**：人类评估仅25名英语母语者，样本量较小；轮次统计基于简单VAD规则，可能忽略更细微的对话线索。
- **计算成本**：两阶段训练需要14万小时单通道和2,200小时双通道数据，算力需求较高，未讨论对于低资源语言的拓展性。
- **安全风险**：作者承认增强的生成自然度可能被用于电信诈骗，需结合AI安全技术。

（完）
