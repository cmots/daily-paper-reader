---
title: "Sortformer: A Novel Approach for Permutation-Resolved Speaker Supervision in Speech-to-Text Systems"
title_zh: "Sortformer: 一种解决语音到文本系统中说话人标签置换问题的新方法"
authors: "Taejin Park, Ivan Medennikov, Kunal Dhawan, Weiqing Wang, He Huang, Nithin Rao Koluguri, Krishna C Puvvada, Jagadeesh Balam, Boris Ginsburg"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=AyYjRvrbDx"
tags: ["query:speech-model"]
score: 6.0
evidence: 语音转文本中的说话人监督
tldr: 该论文针对多说话人语音转文本中的置换问题，提出Sortformer模型，引入Sort Loss解决说话人标签排序，通过正弦核函数嵌入说话人标签，有效桥接时间戳和标记，提升了多说话人语音识别的准确性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ayyjrvrbdx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 833, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ayyjrvrbdx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 755, \"height\": 1003, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ayyjrvrbdx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 785, \"height\": 1152, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ayyjrvrbdx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 837, \"height\": 431, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ayyjrvrbdx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 874, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ayyjrvrbdx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1192, \"height\": 580, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ayyjrvrbdx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1770, \"height\": 718, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ayyjrvrbdx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1780, \"height\": 435, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ayyjrvrbdx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 860, \"height\": 608, \"label\": \"Table\"}]"
motivation: 多说话人语音转文本中说话人标签置换问题。
method: 提出Sort Loss和正弦核函数嵌入说话人标签。
result: 实验表明Sort Loss有效解决了置换问题。
conclusion: Sortformer提升了多说话人语音识别系统的表现。
---

## Abstract
Sortformer is an encoder-based speaker diarization model designed for supervising speaker tagging in speech-to-text models. Instead of relying solely on permutation invariant loss (PIL), Sortformer introduces Sort Loss to resolve the permutation problem, either independently or in tandem with PIL. In addition, we propose a streamlined multi-speaker speech-to-text architecture that leverages Sortformer for speaker supervision, embedding speaker labels into the encoder using sinusoidal kernel functions. This design addresses the speaker permutation problem through sorted objectives, effectively bridging timestamps and tokens to supervise speaker labels in the output transcriptions. Experiments demonstrate that Sort Loss can boost speaker diarization performance, and incorporating the speaker supervision from Sortformer improves multi-speaker transcription accuracy. We anticipate that the proposed Sortformer and multi-speaker architecture will enable the seamless integration of speaker tagging capabilities into foundational speech-to-text systems and multimodal large language models (LLMs), offering an easily adoptable and user-friendly mechanism to enhance their versatility and performance in speaker-aware tasks. The code and trained models are made publicly available through the NVIDIA NeMo Framework.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：在多说话人语音转文本（STT）任务中，说话人标签的“置换问题”（permutation problem）长期存在。传统方法（如置换不变损失PIL）虽然能训练说话人分割模型，但难以与基于交叉熵的ASR模型无缝集成，导致多说话人ASR系统通常需要独立的级联模块或复杂的损失函数。
- **动机**：现有端到端说话人分割与ASR模型缺乏可微分的计算图级集成；级联系统（如TS-VAD、Transcribe-to-Diarize）需要大量领域定制，不易部署。作者希望提出一种统一框架，使多说话人ASR的训练与单说话人ASR一样简单，使用标准交叉熵损失，同时保持高精度。
- **整体含义**：Sortformer通过“按到达时间排序”的标签监督机制，实现了对说话人标签的置换解析，可无缝嵌入语音基础模型或多模态LLM，降低部署门槛并提升说话人感知任务性能。

## 2. 方法论核心思想与关键技术
- **核心思想**：将说话人分割建模为多标签二分类问题，训练模型按说话人首次出现的帧索引顺序（到达时间）输出说话人活动矩阵，从而自然解析置换。
- **关键技术细节**：
  - **Sort Loss**：定义到达时间函数Ψ(·) = 第一个非零帧索引，要求模型输出行向量按Ψ升序排列。损失函数为`L_Sort(Y,P)=L_BCE(Y_η,P)`，其中η为按到达时间排序的索引映射。
  - **混合损失**：`L_hybrid = α·L_Sort + (1-α)·L_PIL`，平衡排序约束与置换不变灵活性。
  - **说话人监督集成**：使用正弦核函数`Γ`生成说话人编码，与ASR编码器状态相加：`Ã = A/||A||₂ + Γᵀ·P`。其中P为Sortformer输出的说话人存在后验概率。
  - **排序序列化转录（SST）**：在文本标注中按到达时间插入排序后的说话人标记（如`<spk0>`, `<spk1>`），使得训练时解码器可直接使用标准交叉熵损失，无需PIL。
  - **词级与段级目标**：支持两种粒度——每词前加说话人标记（词级）或按说话人串行输出（段级，类似SOT风格但不使用`<cs>`）。
  - **适配器**：对1B大模型冻结主干，仅学习适配器参数，避免灾难性遗忘。
- **公式与算法流程**：
  - 模型输出`P = f_Θ(X)`，其中`P ∈ [0,1]^(K×T)`，K为最大说话人数。
  - 训练时，Sort Loss强制模型输出行索引顺序与说话人首次出现顺序一致。
  - 推理时，直接使用Sigmoid输出进行二值化，并通过后处理（阈值、填充、最小长度）获得最终分割。

## 3. 实验设计
- **数据集**：
  - **说话人分割任务**：训练：2,030小时真实数据（Fisher、AMI、DIHARD3-dev、VoxConverse、ICSI、AISHELL-4、CALLHOME Part1）+ 5,150小时模拟数据（LibriSpeech、SRE04-10）。测试：DIHARD3-eval（≤4说话人，0.0s collar）、CALLHOME Part2（2/3/4说话人，0.25s collar）、CH109（2说话人，0.25s collar）。
  - **多说话人ASR任务**：真实录音：AMI IHM、ICSI、DipCo、Fisher（子集30K段，共230小时）。合成数据：LibriSpeechMix（2-mix/3-mix，基于LibriSpeech生成）。
- **基准对比**：
  - 说话人分割：MSDD、EEND-EDA、WavLM+EEND-VC、EEND-GLA、AED-EEND等。
  - 多说话人ASR：Canary（单说话人基线）、SOT-ASR、DOM-SOT、MT-LLM、MS-Canary。
- **评价指标**：
  - 说话人分割：DER（含重叠语音）。
  - 多说话人ASR：cpWER（真实录音）、ORC WER（合成数据）。
- **实验充分性**：共约20余组实验，涵盖不同损失（纯PIL、纯Sort、混合）、是否微调Sortformer、是否使用适配器、词级/段级目标、不同模型规模（170M/1B）、不同数据集。消融设计系统，对比方法均为近年主流。

## 4. 资源与算力
- **Sortformer训练**：8节点 × 8×NVIDIA Tesla V100 GPU（共64卡）。使用AdamW优化器，lr=1e-4，weight decay=1e-3，批大小4，90秒样本。每epoch时间约1,020秒（纯PIL），混合损失增加2.26%（约1,043秒）。
- **多说话人ASR微调**：单卡NVIDIA RTX 6000 Ada（Canary-170M）或单卡RTX A6000 Ada（Canary-1B适配器实验）。训练步数：170M模型50K步，1B模型75K步。
- 文中未提及总训练GPU小时数，但提供了相对时间开销。

## 5. 实验数量与充分性
- **实验数量**：表1比较了多种说话人分割模型（含不同损失变体）；表2进行了6组系统级消融（基线、是否微调、是否适配器、不同目标、是否真实标签）；表3对比了多个ASR系统在LibriSpeechMix上的表现。此外附录有后处理优化（Optuna调参）和词级时间戳近似验证。
- **充分性**：实验覆盖了主要场景（模拟/真实、2/3/4说话人、不同重叠率）和关键消融点（损失函数、微调策略、适配器、目标粒度）。对比方法来自近年顶级会议（ICASSP、INTERSPEECH、CHiME），具有代表性。但未与最新的大型端到端多说话人ASR模型（如基于LLM的）直接比较，仅在LibriSpeechMix上与MT-LLM对比。
- **公平性**：Sortformer的DER评测中未对每个数据集单独微调（而许多对比方法有微调），这可能导致一定劣势，但实验结果仍显示了竞争力。多说话人ASR实验中对比了不同参数量级，且控制了训练数据来源。

## 6. 主要结论与发现
- Sort Loss可替代或补充PIL：单独使用纯Sort Loss时DER与PIL相当；混合损失（α=0.5）显著优于纯PIL，在DIHARD3-eval上DER降至14.76%（经后处理）。
- 集成Sortformer的多说话人ASR系统（Sortformer-MS-Canary）在LibriSpeechMix上相比无说话人监督的MS-Canary，2-mix相对WER降低30%，3-mix降低25%；同时保持了单说话人性能的轻微下降（1-mix WER 2.26% vs 2.19%）。
- 词级目标优于段级目标（表2系统6 vs 5，cpWER更低）。
- 使用适配器（Canary-1B）可有效利用大模型，但段级目标下性能不如全微调小模型。
- 运行时开销极小（仅0.78%），表明Sortformer可高效集成。

## 7. 优点（方法与实验设计亮点）
- **创新性**：首次将“到达时间排序”作为监督信号引入端到端说话人分割，避免PIL的复杂排列搜索，与交叉熵损失自然兼容。
- **可集成性**：通过正弦核函数将说话人后验概率嵌入ASR编码器，实现计算图级联合训练，无需词级时间戳。
- **资源高效**：1B大模型使用适配器，冻结主干，仅学习少量参数，避免遗忘单说话人能力。
- **实用性**：代码和模型开源（NVIDIA NeMo），提供完整训练和推理流程。
- **实验设计**：包含详细消融（损失函数组合、微调策略、目标粒度），并从运行时间角度证明了低开销。
- **公平性考量**：在DER评测中仅使用统一后处理，未逐个数据集微调，体现鲁棒性。

## 8. 不足与局限
- **说话人数量限制**：Sortformer当前固定最大4个输出通道，无法处理任意数量说话人（对比EEND-EDA可动态输出）。
- **纯Sort Loss的局限**：当说话人首次到达时间接近或重叠时，排序可能不准确，导致性能略低于PIL（表1中Sort-Loss在DH3上DER 17.88% vs PIL的18.33%，但后处理后反而略优）。
- **实验覆盖有限**：
  - 真实录音实验仅使用AMI、ICSI、DipCo、Fisher子集（共230小时），未在更大规模或更嘈杂场景（如CHiME-6）上测试。
  - 未探索流式推理场景，论文明确表示“未来工作”。
  - 未与最新的多说话人端到端ASR系统（如基于Conformer或Whisper的改造）在公平条件下对比。
- **偏差风险**：训练数据中Fisher为电话对话，AMI/ICSI为会议，可能无法泛化到自由场或远场场景。合成数据（LibriSpeechMix）的混合方式固定，可能与真实重叠模式有差距。
- **后处理依赖**：DER结果依赖Optuna调参的后处理，若部署到新领域需重新优化阈值。
- **未讨论与LLM的集成**：尽管在摘要中声称可集成LLM，但实验未涉及多模态LLM的联合训练或指令微调，实用性验证不足。

（完）
