---
title: Word-Level Emotional Expression Control in Zero-Shot Text-to-Speech Synthesis
title_zh: 零样本文本到语音合成中的词级情感表达控制
authors: "Tianrui Wang, Haoyu Wang, Meng Ge, Cheng Gong, Chunyu Qiang, Ziyang Ma, Zikang Huang, Guanrou Yang, Xiaobao Wang, EngSiong Chng, Xie Chen, Longbiao Wang, Jianwu Dang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=SYcggdxX6W"
tags: ["query:speech-model"]
score: 9.0
evidence: 文本到语音合成中的词级情感控制
tldr: WeSCon提出了首个无需句子内情感标注的自训练框架，实现了零样本TTS中词级别的情感和语速控制。通过过渡平滑策略和动态速度建模，在保持语音自然度的同时实现了精细的表达力调节，填补了表现力语音合成中词级控制的空白。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 923, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1212, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1407, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1390, \"height\": 673, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 745, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1090, \"height\": 733, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 696, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1159, \"height\": 607, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1393, \"height\": 1045, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1361, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sycggdxx6w/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1372, \"height\": 517, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-sycggdxx6w/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1341, \"height\": 581, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sycggdxx6w/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 847, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sycggdxx6w/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 600, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sycggdxx6w/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 884, \"height\": 441, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sycggdxx6w/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1173, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sycggdxx6w/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1208, \"height\": 351, \"label\": \"Table\"}]"
motivation: 现存情感TTS仅支持语句级情感，无法对词级情感过渡进行精细控制，且缺乏标注数据。
method: 提出自训练框架WeSCon，基于预训练零样本TTS模型，通过过渡平滑和动态速度控制实现词级情感与语速调节。
result: 在客观和主观评测中，WeSCon在表达力控制和自然度上均达到先进水平。
conclusion: 该工作首次实现了词级情感控制，为人机交互中更细腻的语音生成提供了新思路。
---

## Abstract
While emotional text-to-speech (TTS) has made significant progress, most existing research remains limited to utterance-level emotional expression and fails to support word-level control. Achieving word-level expressive control poses fundamental challenges, primarily due to the complexity of modeling multi-emotion transitions and the scarcity of annotated datasets that capture intra-sentence emotional and prosodic variation. In this paper, we propose WeSCon, the first self-training framework that enables word-level control of both emotion and speaking rate in a pretrained zero-shot TTS model, without relying on datasets containing intra-sentence emotion or speed transitions.
Our method introduces a transition-smoothing strategy and a dynamic speed control mechanism to guide the pretrained TTS model in performing word-level expressive synthesis through a multi-round inference process. To further simplify the inference, we incorporate a dynamic emotional attention bias mechanism and fine-tune the model via self-training, thereby activating its ability for word-level expressive control in an end-to-end manner. Experimental results show that WeSCon effectively overcomes data scarcity, achieving state-of-the-art performance in word-level emotional expression control while preserving the strong zero-shot synthesis capabilities of the original TTS model.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：现有情感文本到语音合成（TTS）大多仅支持**语句级**（utterance-level）的情感表达，无法实现**词级**（word-level）的情感与语速控制。人类语音中情感和语速是动态变化的，词级控制在人机交互中具有重要意义。
- **背景**：已有研究如 ELaTE 和 EmoCtrl-TTS 尝试通过情感参考语音实现句子内情感过渡，但它们依赖**包含句子内情感转换标注的大规模数据集**，这类数据集极为稀缺且多为私有，难以获取。因此，如何在不依赖此类数据集的前提下实现词级情感与语速控制成为一个重大挑战。

## 2. 方法论：核心思想、关键技术细节
### 2.1 总体框架：WeSCon（两阶段自训练）
- **阶段一（教师模型）**：基于预训练零样本TTS模型（CosyVoice2），设计**多轮推理框架**，结合**过渡平滑（Transition Smoothing）** 和**动态速度控制（Dynamic Speed Control）**，无需情感训练数据即实现词级情感与语速变化。
- **阶段二（自训练学生模型）**：使用教师模型生成的带词级情感与语速变化的语音作为监督信号，对学生模型（原始TTS模型）进行微调。学生模型引入**动态情感注意力偏置（Dynamic Emotional Attention Bias, DEAB）**，实现端到端的简化推理。

### 2.2 关键技术细节
- **过渡平滑**：在每轮推理时，将上一轮生成的尾部文本和语音token附加到当前提示中，形成明确的“尾-头”连接，利用CosyVoice2的续写生成能力保证过渡自然。一个轻量级内容对齐器（非因果Transformer+卷积层，在ASR数据上训练）预测每帧对应的文本token，实现精准对齐。
- **动态速度控制**：对提示语音token进行最近邻插值（放慢语速）或降采样（加快语速），从而调节生成语音的全局语速。通过多轮推理可对不同词段独立调节。
- **说话人一致性**：在LM部分尽量使用同一说话人的不同情感提示，并通过流匹配使用目标说话人参考音频进行语音转换，确保最终输出说话人一致。
- **动态情感注意力偏置**：
  - 在学生模型中，输入格式扩展为：`{S, E_I, C_prompt_I, E_II, C_prompt_II, ..., C_tgt, B, S_prompt_I, ..., S_tgt}`，其中`E_i`为情感指示符。
  - 每个生成步预测当前帧情感标签，并据此生成**7个预定义的注意力偏置模板**的加权组合（通过MLP和softmax输出权重ω∈R^{1×7}）。
  - 偏置与softmax后的注意力权重逐元素相乘并重新归一化，使模型仅关注与当前情感一致的提示区域，避免跨情感干扰。

## 3. 实验设计
### 3.1 数据集
- **阶段一**：内容对齐器在200小时非情感语音上训练（LibriSpeech-100-Clean英文 + AISHELL-1中文）。
- **阶段二**：教师模型使用ESD数据集（20个说话人，中英文各半，5种情感：开心、悲伤、中性、愤怒、惊讶）的非转换情感样本作为提示。通过GPT-4o生成包含情感转换的文本（500条中文+500条英文用于测试；训练时使用类似方法生成大量文本）。
- **自训练数据**：教师模型按情感转换文本和对应情感提示合成语音，经数据筛选（ASR准确率、说话人相似度、情感相似度取top 50%），最终得到约500小时高质量训练数据。
- **评估基准**：ESD测试集；零样本TTS评估使用SEED测试集（test-zh）；领域外评估使用CASIA中文情感语音库（包含未见情感类别如恐惧）。

### 3.2 对比方法
- **Index-TTS**、**F5-TTS**、**Spark-TTS**、**CosyVoice2**（四种强零样本TTS系统）。所有基线采用相同策略：将句子按词级情感计划分割，分别合成后拼接。

### 3.3 评估指标
- **客观指标**：WER/CER（语音识别）、DNSV（DNSMOS-PRO分数的方差，衡量过渡平滑度）、S-SIM（说话人相似性，WavLM-Large余弦相似度）、AutoPCP（韵律相似度）、情感相似度（Emotion2vec-Large和wav2vec 2.0模型）。
- **主观指标**：4类MOS（EMOS情感匹配、SPMOS语速匹配、SMOS说话人相似性、NMOS过渡自然度），15名受试者，5分制，报告均值和95%置信区间。

## 4. 资源与算力
- **第一阶段**：2块NVIDIA 3090 GPU，训练400k步，每批90秒语音。优化器Adam，学习率线性warmup至2.5e-4，后线性衰减至0。
- **第二阶段**：4块NVIDIA 3090 GPU，训练600k步（前20k步冻结TTS模型只训练情感对齐器），每批40秒语音。学习率固定为5e-7。
- **消融实验及推理**：未单独说明额外算力，但应在上述条件下完成。

## 5. 实验数量与充分性
- **主实验**：中英文各500句测试，客观结果（表1）和主观结果（表2）均涵盖。
- **零样本TTS能力评估**：在SEED测试集上验证（表3），显示学生模型保持原始CosyVoice2性能。
- **消融实验**（表4）：
  - 教师模型：去除平滑、去除速度控制。
  - 学生模型：去除注意力偏置、去除情感标志、去除数据筛选、替换数据格式。
- **数据规模影响**（图5）：训练4种数据量（125h、250h、500h、1000h、2000h），以500h最优。
- **领域外泛化**（表6）：在CASIA数据集上复现主实验，结果与表1一致。
- **速度-情感交互分析**（表5、图7）：系统性地变化重采样比例（0.5~2.0）并测量情感相似度，验证速度控制对情感感知的影响。
- **训练进展**（图10、11）：展示两阶段中内容对齐器和情感对齐器的帧级准确率上升曲线。
- **结论**：实验覆盖消融、规模、领域外、速度-情感耦合等多个维度，充分验证了各组件有效性，对比基线公平（相同推理策略）。

## 6. 论文的主要结论与发现
- WeSCon在词级情感和语速控制上达到**SOTA**，客观指标（Emo2v., Aro., DNSV）和主观MOS均显著优于基线。
- **过渡平滑**和**动态速度控制**对保持自然度和表达力至关重要（消融后DNSV大幅上升）。
- **自训练+动态情感注意力偏置**使学生模型以端到端方式实现词级控制，且不损害原始零样本TTS能力（CER与S-SIM几乎不变）。
- 数据规模在500h附近最优，过大规模因情感和说话人种类有限导致过拟合。
- 方法在**中文和英文**上均有效，且对**未见情感和说话人**具有良好泛化能力（CASIA测试结果稳定）。

## 7. 优点
- **首次实现**：无需句子内情感转换标注数据集即完成词级情感与语速控制，克服了关键数据瓶颈。
- **自训练框架创新**：教师模型通过多轮推理产生高质量伪标签，学生模型通过动态注意力偏置简化推理，两阶段配合巧妙。
- **模型无关性**：以CosyVoice2为骨干，但框架可推广至其他自回归/零样本TTS模型。
- **控制精细**：支持词级情感类别和语速连续调节（通过重采样比例），且过渡平滑度高（DNSV降低近一半）。
- **保持零样本能力**：学生模型经过微调后，在标准零样本TTS任务上性能与原始模型相当（表3）。

## 8. 不足与局限
- **缺乏语义级情感演变建模**：当前仅实现信号级平滑过渡，无法模拟情感渐变（如从愤怒到悲伤的中间状态）。
- **离散情感集受限**：仅支持5种固定情感，不支持复合或混合情感（如“愤怒+悲伤”表达绝望）。
- **控制策略不灵活**：情感转换计划由GPT-4o预定义，缺乏动态上下文感知能力。未来需探索更自然、交互式的控制。
- **潜在过拟合风险**：数据规模超过500h后性能下降，因训练数据的情感类别和说话人多样性不足（仅ESD），限制了泛化性。
- **安全与伦理**：可能被用于说话人冒充或生成不当内容，需谨慎部署。虽然在测试中未发现偏见，但未做系统性公平性评估。

（完）
