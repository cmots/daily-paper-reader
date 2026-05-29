---
title: "MoonCast: High-Quality Zero-Shot Podcast Generation"
title_zh: MoonCast：高质量零样本播客生成
authors: "Zeqian Ju, Dongchao Yang, Kai Shen, Yichong Leng, Zhengtao Wang, Songxiang Liu, Xinyu Zhou, Tao Qin, Xiangyang Li, Jianwei Yu, Xu Tan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=MVlKSYR7HX"
tags: ["query:speech-model"]
score: 8.0
evidence: 零样本播客生成，表现力语音合成
tldr: MoonCast针对长语音和自发对话场景提出解决方案，实现零样本高质量播客生成。它通过分段建模和口语化风格迁移，生成长达数分钟的多说话人自然对话，在自然度和表现力上显著优于现有TTS系统，拓展了表现力语音合成的应用边界。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvlksyr7hx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1022, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvlksyr7hx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1240, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-mvlksyr7hx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 489, \"height\": 465, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-mvlksyr7hx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1501, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mvlksyr7hx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1501, \"height\": 226, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mvlksyr7hx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1408, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mvlksyr7hx/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 552, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-mvlksyr7hx/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1417, \"height\": 191, \"label\": \"Table\"}]"
motivation: 现有TTS无法生成长时间、多说话人、自发对话风格的播客内容。
method: 通过分段生成和口语风格建模，结合零样本说话人适应，实现长篇多说话人播客合成。
result: 在客观指标和主观听感评测中均达到当前最优，特别是在自然度和表现力上。
conclusion: MoonCast将TTS能力扩展到播客等实际场景，为表达性语音生成提供了新范式。
---

## Abstract
Recent advances in text-to-speech synthesis have achieved notable success in generating high-quality short utterances for individual speakers. However, these systems still face challenges when extending their capabilities to long, multi-speaker, and spontaneous dialogues, typical of real-world scenarios such as podcasts. These limitations arise from two primary challenges: 1) long speech: podcasts typically span several minutes, exceeding the upper limit of most existing work; 2) spontaneity: podcasts are marked by their spontaneous, oral nature, which sharply contrasts with formal, written contexts; existing works often fall short in capturing this spontaneity. In this paper, we propose MoonCast, a solution for high-quality zero-shot podcast generation, aiming to synthesize spontaneous podcast-style speech from text-only sources (e.g., stories, technical reports, news in TXT, PDF, or Web URL formats) using the voices of unseen speakers.   To enable long audio generation, we employ a language model with parameter, data, and context scaling to process sequences in an innovative format designed for modeling entire multi-speaker, multi-turn speech interactions. To enhance spontaneity, we observe that ASR transcripts capture spontaneous speech details (e.g., filler words indicating hesitations, and specific punctuation and spaces reflecting breathing pauses), suggesting that these transcripts can serve as a partial indicator of speech spontaneity. Building upon this assumption, we utilize a script generation module to generate scripts incorporating these spontaneous elements. Experiments show MoonCast outperforms baselines, with notable improvements in contextual coherence and spontaneity.

---

## 论文详细总结（自动生成）

好的，以下是对论文《MoonCast: High-Quality Zero-Shot Podcast Generation》的深入分析与总结。

### 1. 论文的核心问题与整体含义（研究动机和背景）

*   **核心问题**：现有文本转语音系统在生成高质量短句方面表现出色，但在应对**长时间、多说话人、自发性强**的真实场景（如播客）时面临巨大挑战。具体挑战包括：
    *   **长语音建模**：播客通常持续数分钟，其音频令牌序列长度远超大多数现有模型的处理上限。
    *   **自发性缺失**：播客口语化、自然、带有填充词和犹豫等特征，与正式书面语截然不同，现有TTS系统难以捕捉和生成这种“自发性”。
*   **研究动机**：TTS技术需要从短句生成向更长、更复杂的对话场景扩展，以满足日益增长的播客内容生成需求。现有工业解决方案技术细节不透明，学术研究又难以处理长篇和多说话人交互。
*   **整体含义**：论文提出MoonCast，旨在实现**零样本播客生成**，即仅从文本源（如PDF、网页链接）出发，使用未见过的说话人声音，合成高质量的、具有自发性的播客体语音。这标志着TTS技术向更真实、更动态的语音交互场景迈出了重要一步。

### 2. 论文提出的方法论：核心思想、关键技术细节

*   **核心思想**：采用“**分而治之**”的**管道式架构**，将播客生成分解为**自发脚本生成**和**自发语音生成**两个阶段。
*   **关键技术细节**：
    1.  **音频建模模块**：
        *   **模型架构**：基于**大语言模型的文本到语义建模**。将语音编码为单一的离散语义码（50Hz），将任务分解为“文本→语义码”和“语义码→音频”两个子任务。
        *   **序列设计**：提出创新的**全文本到全音频交错序列格式**，能够整体建模多说话人多轮对话，确保上下文连贯性。序列包含提示文本、播客文本、提示语音和播客语音，并引入特殊的说话人切换令牌。
        *   **课程学习**：采用**三阶段课程学习**逐步提升模型能力：
            *   第一阶段：在单人单句数据上训练，建立零样本TTS基础能力。
            *   第二阶段：在双人多轮数据（如有声书，相对简单）上训练，扩展上下文长度至4万个令牌，学习长上下文和双说话人一致性。
            *   第三阶段：在自发对话数据（如真实播客）上微调，学习自发性特征。
        *   **分块自回归语音解码器**：为了处理长序列，提出基于**流匹配**和**分块因果掩码**的解码器。它将长语音序列切分为小段（如3秒），在生成当前段时可以关注历史已生成段，从而在降低计算量和内存占用的同时，保证了段间边界的一致性和流畅性。
    2.  **LLM驱动的脚本生成模块**：
        *   **核心假设**：ASR转录文本反映了口语的许多自发特征（如填充词、停顿），因此可以作为生成自发语音的“代理”输入。
        *   **生成流程**：接收知识源（文本/PDF/URL）后，先由LLM生成“简报文档”以提炼关键信息；再由LLM基于此简报，按照特定的结构、格式和内容要求，生成**包含自发性元素的播客脚本**，要求脚本模仿ASR转录的风格，包含填充词、响应词、口语化表达等。

### 3. 实验设计：数据集、Benchmark、对比方法

*   **数据集**：使用一个包含约**100万小时**的大规模内部多源音频数据集，经数据清洗和预处理后，最终使用**51.5万小时**的数据：30万小时中文有声书、1.5万小时中文对话、20万小时英文对话。
*   **来演化Benchmark**：由于任务新颖，论文构建了专有的评测数据集：
    *   **播客生成评测**：包含4个知识源（2个PDF，2个网页URL），涵盖计算机科学论文、经济学论文、技术博客和新闻文章。
    *   **脚本影响评测**：从7个不可见说话人的中文播客中选用125轮对话，用于测试脚本自发性对生成质量的影响。
*   **对比方法**：
    *   **拼接基线**：使用与MoonCast相同的TTS模型，但仅用单说话人、单回合数据训练。生成时，对每一回合单独零样本生成，然后拼接成完整播客。
    *   **Cosyvoice2**：一个强大的开源多语言单说话人零样本TTS模型，同样采用逐回合生成后拼接的策略。
    *   **对话基线**（仅在英文上评估）：与Sesame和Dia这两个对话生成模型进行比较。
*   **评测指标**：
    *   **主观评测**：由10位评估者对5个维度评分（95%置信区间）：自发性、连贯性、可懂度、语音质量、说话人相似度。
    *   **客观评测**：SIM-O（说话人相似度）和WER（词错误率）。

### 4. 资源与算力

*   论文明确提供了算力信息。**音频建模模块**（文本到语义模型）为一个**25亿参数**、16层的Llama风格Transformer，在**64块A100 80GB GPU**上使用Megatron框架训练，**张量并行度为8**，每个课程学习阶段训练**2000步**。
*   语音解码器（流匹配模型）为一个**8亿参数**、10层的DiT风格Transformer。
*   论文未提及具体的总训练时长，但最大序列长度、批量大小等信息已给出。

### 5. 实验数量与充分性

*   **实验数量**：共进行了**4类主要实验**，包括与拼接基线和Cosyvoice2的主观/客观对比（中英文）、对话基线对比、脚本自发性影响的消融实验（表3）、以及数据规模的消融实验（附录D）。
*   **充分性与公平性**：
    *   实验设计**相对充分**，涵盖了核心假设验证（脚本自发性影响）、组件有效性验证（课程学习、长上下文建模）、以及多种场景（中英文）和多种基线方法的对比。
    *   实验**较为客观公平**：主观评测使用了95%置信区间，对比方法的评估在相同输入下进行。
    *   不足之处：仅在7个中文播客上验证了脚本自发性假设，样本量较小；主要内部数据集构成复杂，可能影响结果的可泛化性。

### 6. 论文的主要结论与发现

1.  **性能超越现有方法**：MoonCast在**中、英文播客生成**任务上，在自发性、连贯性、可懂度和质量等主观指标上**显著优于**两个拼接基线方法（Cosyvoice2和拼接基线），验证了整体建模多说话人长对话的有效性。
2.  **脚本自发性至关重要**：实验（表3）明确证实，**脚本的自发性直接影响生成语音的自发性**。使用最自发的真实ASR转录脚本（GT script）生成的语音自发性最高，而移除自发元素后（written script）的自发性评分显著下降。这一发现验证了论文的核心假设。
3.  **长上下文建模和价值**：直接采用逐句生成后拼接的方式（两个基线方法）效果较差，证明了整体建模多说话人多轮对话对于维持**上下文连贯性和语音自然性**的重要性。
4.  **大模型训练的有效性**：在更大数据集上训练（附录D）能显著提升播客生成的整体质量（尤其是主观评分），表明数据规模对学习复杂的自发对话模式至关重要。

### 7. 优点：方法或实验设计上的亮点

*   **任务定义新颖且实际**：将TTS从短句扩展到零样本长篇播客生成，解决了实际应用中的关键痛点。
*   **方法论整体性**：提出了一个**完整的端到端管道**（脚本生成 → 语音生成），两个模块设计巧妙且相互支撑，逻辑自洽。
*   **算法设计精巧**：序列格式（全文本到全音频交错）和分块自回归解码器设计，有效解决了长上下文建模和推理的效率/稳定问题。课程学习策略也有效利用了不同数据源的特点。
*   **假设验证明确**：不满足于系统性能报告，专门设计了实验验证“脚本自发性是关键影响因素”这一核心假设，使工作更具说服力和科学性。
*   **开源贡献**：开源了脚本生成的提示词和音频建模模块（推理代码和模型权重），显著提升了可复现性，对领域发展有重要价值。

### 8. 不足与局限

*   **语言与场景覆盖有限**：系统目前仅支持**中文和英文**，且局限于**双人对话**。扩展到更多语言和多人交互场景是未来的工作。
*   **数据质量依赖**：整个系统严重依赖于**自动数据处理管道**生成的ASR和说话人分离标注。这些标注中的误差（如ASR错误、说话人识别错误）会直接传递给模型，成为性能的天花板。
*   **内容幻觉问题**：模型有时会混淆说话人，即“内容幻觉”。论文分析了可能的原因（语义令牌携带音色信息、数据标注错误、文本解读歧义等），但未能完全解决。
*   **计算开销**：虽然提出了分块推理降低峰值内存，但整个系统（25B+0.8B参数）仍然需要相当大的计算资源进行训练和推理。
*   **主观评测规模**：10名评估者的样本量在统计上可能不够稳健，虽然报告了置信区间。

（完）
