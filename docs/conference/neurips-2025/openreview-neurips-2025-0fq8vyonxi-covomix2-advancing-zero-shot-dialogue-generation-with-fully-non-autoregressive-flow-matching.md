---
title: "CoVoMix2: Advancing Zero-Shot Dialogue Generation with Fully Non-Autoregressive Flow Matching"
title_zh: CoVoMix2：基于全非自回归流匹配推动零样本对话生成
authors: "leying zhang, Yao Qian, Xiaofei Wang, Manthan Thakker, Dongmei Wang, Jianwei Yu, Haibin Wu, Yuxuan Hu, Jinyu Li, Yanmin Qian, sheng zhao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=0fq8vYOnxi"
tags: ["query:speech-model"]
score: 8.0
evidence: 表现力语音合成
tldr: 针对多说话人对话生成中说话人一致性、重叠建模和合成效率低的问题，本文提出CoVoMix2框架，采用全非自回归流匹配直接预测梅尔谱图，无需中间token表示。通过转录级说话人解耦和句子级对齐，实现了零样本多说话人高质量对话生成，比自回归方法速度更快且保持自然流畅。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-0fq8vyonxi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 1237, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0fq8vyonxi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0fq8vyonxi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 234, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0fq8vyonxi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 436, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0fq8vyonxi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1421, \"height\": 268, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0fq8vyonxi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1423, \"height\": 615, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-0fq8vyonxi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1424, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0fq8vyonxi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 880, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0fq8vyonxi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0fq8vyonxi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1081, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0fq8vyonxi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 745, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0fq8vyonxi/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1093, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0fq8vyonxi/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1461, \"height\": 377, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0fq8vyonxi/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1441, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0fq8vyonxi/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1429, \"height\": 907, \"label\": \"Table\"}]"
motivation: 现有系统难以保持说话人一致性、建模重叠语音并高效合成连贯对话。
method: 提出CoVoMix2，使用流匹配直接预测多流转录对应的梅尔谱图，实现非自回归对话生成。
result: 在多个对话数据集上实现了高质量的零样本多说话人生成，效率显著提升。
conclusion: 全非自回归流匹配为零样本对话生成提供了高效且一致的解决方案。
---

## Abstract
Generating natural-sounding, multi-speaker dialogue is crucial for applications such as podcast creation, virtual agents, and multimedia content generation. However, existing systems struggle to maintain speaker consistency, model overlapping speech, and synthesize coherent conversations efficiently. In this paper, we introduce CoVoMix2, a fully non-autoregressive framework for zero-shot multi-talker dialogue generation. CoVoMix2 directly predicts mel-spectrograms from multi-stream transcriptions using a flow-matching-based generative model, eliminating the reliance on intermediate token representations. To better capture realistic conversational dynamics,  we propose transcription-level speaker disentanglement, sentence-level alignment, and prompt-level random masking strategies.  Our approach achieves state-of-the-art performance, outperforming strong baselines like MoonCast and Sesame in speech quality, speaker consistency, and inference speed. Notably, CoVoMix2 operates without requiring transcriptions for the prompt and supports controllable dialogue generation, including overlapping speech and precise timing control, demonstrating strong generalizability to real-world speech generation scenarios. Audio samples are available at https://www.microsoft.com/en-us/research/project/covomix/covomix2.

---

## 论文详细总结（自动生成）

# CoVoMix2 论文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：多说话人对话生成（如播客、虚拟助手、多媒体内容）需要合成自然、动态、多轮交互的语音。现有系统在说话人一致性、重叠语音建模和合成效率方面存在严重不足。
- **现有方法的局限**：
  - 自回归（AR）或混合AR+NAR架构依赖中间表示（语义/音频token），推理解码慢（串行生成）。
  - 缺乏对语速、停顿、重叠时长等韵律特征的细粒度控制，对话流不自然。
  - 说话人身份偶发混淆，尤其在长对话中。
  - 许多方法需要立体声音频训练和配对文本-音频提示，扩展性差。
- **整体目标**：提出**CoVoMix2**，一个**全非自回归（fully NAR）** 的零样本多说话人对话生成框架，直接预测梅尔谱图，无需中间表示。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：基于**流匹配（Flow Matching）** 的生成模型，将多流转录（每个说话人独立一个文本流）作为条件，直接生成混合梅尔谱图。训练时学习从噪声到数据的连续映射，推理时通过求解ODE并行生成。
- **关键技术细节**：
  - **转录级说话人解耦（Transcription-Level Speaker Disentanglement）**：将对话转录拆分为每个说话人独立的平行文本流，包含活动语音段（带时间戳）和静音段（特殊token [S]）。允许精确控制重叠和静音时段。
  - **句子级对齐（Sentence-Level Alignment）**：每个活动语音段转换为字符序列 + 填充token [P]（延续标记），根据起止时间对齐到梅尔帧。不依赖音素或帧级对齐。
  - **提示级随机掩码（Prompt-Level Random Masking）**：训练时随机选择每个说话人的提示片段拼接至输入开头，并用 [Spk1]/[Spk2] 替换提示区文字。在损失计算中排除提示区域，防止模型直接复制提示，鼓励泛化说话人特征。
  - **流匹配训练目标**（公式1）：
    \[
    \mathcal{L} = \mathbb{E} \| M( (m - (1-\sigma_{\min})m_0) - v_t(w, m_{ctx}, z; \theta) ) \|^2
    \]
    其中 \(m_0\) 高斯噪声，\(w = (1-(1-\sigma_{\min})t)m_0 + tm\) 是插值样本，\(M(\cdot)\) 为掩码（排除提示区域）。
  - **分类器自由引导（CFG）**：训练时以概率 \(p_{\text{uncond}}\) 丢弃条件；推理时使用引导强度 \(\alpha=1.0\)。
  - **训练策略**：两阶段课程学习：
    1. **第一阶段**：在60k小时单说话人LibriHeavy上预训练（200k步），学习准确的发音和声学建模。
    2. **第二阶段**：混合播客对话、有声书单说话人、模拟重叠对话等数据继续训练（200k步）。
  - **推理时控制**：用户可指定每个话语的语速、持续时间和停顿时长（通过音节数和预设语速计算），构建文本流后采样噪声并求解ODE。

## 3. 实验设计：数据集、基准与对比方法

- **训练数据集**：
  - 单说话人：LibriHeavy（60k小时）、LibriTTS。
  - 多说话人对话：内部3000小时英语播客数据（经降噪、ASR + 说话人日志处理、剪辑为2-3人片段）。
  - 模拟对话：从单说话人数据配对生成，支持0-100%重叠率。
- **测试数据集**：
  - 对话测试集：从DailyDialog取样1000个转录，提示音频来自LibriSpeech test-clean（20个不同说话人，时长3-18秒不等）。另有真实场景测试（来自NCSSD数据集）。
  - 单说话人测试：LibriSpeech或LibriHeavy单说话人片段。
- **对比方法**：
  - **MoonCast**：混合AR+NAR，基于语言模型的长上下文对话生成。
  - **Sesame**：纯AR的对话式语音合成（CSS），按序生成每个话语。
- **评估指标**：
  - **客观**：实时因子（RTF）、词错误率（WER）、说话人感知WER（SA-WER）、说话人感知相似度（SA-SIM）、UTMOS（自然度）。
  - **主观**：CMOS（15名专业评审，从-3到+3比较对话交互性、流畅性、一致性等）。

## 4. 资源与算力

- **训练硬件**：32块 NVIDIA Tesla V100 32GB GPU，梯度累积4。
- **训练步数**：第一阶段200k步（峰值学习率7.5e-5），第二阶段200k步（峰值学习率5e-5），均为线性衰减。Adam优化器。
- **推理测试**：在单张NVIDIA A100上测量RTF。
- **其他**：模型参数量约0.3B（Transformer 24层，16头，1024维）。BigVGAN声码器将梅尔谱图转波形（24kHz采样率）。

## 5. 实验数量与充分性

- **核心对比实验**（表1）：在对话测试集上对比CoVoMix2与MoonCast、Sesame的RTF、WER、SA-WER、SA-SIM、UTMOS、CMOS。结果全面显示CoVoMix2优势。
- **说话人一致性分析**（图4）：选取长对话（12个话语），计算每轮与提示的相似度及内部对相似度，可视化显示CoVoMix2最稳定。
- **重叠语音分析**（图5）：与NotebookLM、CoVoMix的梅尔谱图视觉比较，CoVoMix2更自然。
- **消融实验**（附录D）：
  - 数据混合策略（6组，表6）：比较不同数据组合（播客单/对话、LibriTTS、LibriHeavy、模拟数据）的影响。
  - 训练阶段（表7）：验证预训练与微调（20分钟人工标注数据）的效果。
  - 静音token表示（表8）：对比[P]、[S]、[S1][S2]三种方案。
- **额外实验**（附录C）：
  - 不同提示长度（图6）：3-18秒提示，SA-WER/SA-SIM稳定性。
  - 不同生成长度（表4）：对话长度30s/60s/90s/120s，CoVoMix2在90s后略有退化但仍优于基线。
  - 真实场景（表5）：来自NCSSD的现实提示，CoVoMix2依然领先。
  - 单说话人性能（表3）：对比LibriSpeech单说话人WER/SIM/UTMOS，CoVoMix2最优。
- **充分性判断**：实验设计全面，覆盖主要基线、多种场景、消融分析，且提供标准误差。实验公平（统一测试集、指标、主观评审）。

## 6. 主要结论与发现

- CoVoMix2在**所有客观指标**（RTF 0.30，SA-WER 6.31%，SA-SIM 0.56，UTMOS 3.10）上均**显著优于** MoonCast和Sesame。
- 在**主观评估CMOS**中，CoVoMix2被评审评为更好（对比月播0.25，Sesame 0.39）。
- **全非自回归架构**实现快速并行生成（RTF比基线快4-7倍），无需中间表示。
- **说话人一致性**极强：即使在长对话中也能稳定保持身份，无漂移。
- **支持精细控制**：可精确控制重叠、停顿和语速，生成自然对话流。
- 无需提示转录，支持跨语言声音克隆。
- 仅需20分钟干净人工标注数据微调即可进一步提升性能。

## 7. 优点

- **方法论创新**：首次将全非自回归流匹配应用于零样本多说话人对话生成，简化流水线。
- **高效性**：推理速度远超AR方法，适合实时应用。
- **可控性**：转录解耦支持自由指定话语时序、重叠比例，实用性高。
- **鲁棒性**：提示掩码和句子级对齐减少对标注质量依赖，对短提示（<10s）和长提示均稳定。
- **数据高效**：即使训练数据为自动转写的含噪数据，仍能生成高质量语音；用少量干净数据微调即可提升。
- **开源诚意**：提供了数据处理流水线代码和测试集链接，促进复现。

## 8. 不足与局限

- **训练数据限制**：
  - ASR自动转写引入小错误（尤其重复、口头禅等非流畅现象）。
  - 重叠语音缺少字级时间戳，需用模拟数据训练，导致轻微自然度偏差和音频质量退化。
- **说话人数量**：当前仅支持两个说话人，扩展至更多说话人需未来工作。
- **长对话退化**：模型在90秒以上对话中性能下降（SA-WER升高），尽管优于基线，但仍有改进空间。
- **模拟数据噪声**：表6显示模拟对话数据可能引入分布不匹配，未能持续改善性能，但其对重叠能力是必要的。
- **公平性考量**：论文未讨论种族、口音等偏差；模型可能对训练数据中的常见口音/性别偏好。
- **潜在滥用风险**：能合成保持说话人身份的语音，可能被用于欺诈或冒充。作者建议构建检测模型，但未提供具体方案。

（完）
