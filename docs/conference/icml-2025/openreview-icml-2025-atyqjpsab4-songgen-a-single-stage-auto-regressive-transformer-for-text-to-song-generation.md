---
title: "SongGen: A Single Stage Auto-regressive Transformer for Text-to-Song Generation"
title_zh: SongGen：用于文本到歌曲生成的单阶段自回归Transformer
authors: "Zihan Liu, Shuangrui Ding, Zhixiong Zhang, Xiaoyi Dong, Pan Zhang, Yuhang Zang, Yuhang Cao, Dahua Lin, Jiaqi Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=aTyQjpsaB4"
tags: ["query:speech-model"]
score: 7.0
evidence: 文本到歌曲生成，属于表现力语音合成
tldr: 针对文本到歌曲生成中的多阶段流水线导致的误差累积问题，本文提出单阶段自回归Transformer SongGen，从文本直接生成带伴奏的歌声，支持歌词、乐器、流派等细粒度控制。实验证明SongGen在生成质量和可控性上优于多阶段方法。为文本到歌曲生成提供了简化有效的单阶段解决方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-atyqjpsab4/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 829, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atyqjpsab4/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1612, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atyqjpsab4/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1688, \"height\": 817, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atyqjpsab4/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 858, \"height\": 233, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atyqjpsab4/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 856, \"height\": 580, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-atyqjpsab4/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 691, \"height\": 286, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-atyqjpsab4/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1618, \"height\": 582, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-atyqjpsab4/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 486, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-atyqjpsab4/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 852, \"height\": 155, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-atyqjpsab4/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 820, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-atyqjpsab4/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-atyqjpsab4/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 870, \"height\": 224, \"label\": \"Table\"}]"
motivation: 现有文本到歌曲生成方法多阶段训练推理，误差累积且效率低。
method: 提出单阶段自回归Transformer，直接生成歌声和伴奏。
result: 实验证明SongGen在生成质量和可控性上优于多阶段方法。
conclusion: 为文本到歌曲生成提供了简化且有效的单阶段解决方案。
---

## Abstract
Text-to-song generation, the task of creating vocals and accompaniment from textual inputs, poses significant challenges due to domain complexity and data scarcity. 
Existing approaches often employ multi-stage generation procedures, leading to cumbersome training and inference pipelines, as well as suboptimal overall generation quality due to error accumulation across stages.
In this paper, we propose **SongGen**, a fully open-source, single-stage auto-regressive transformer designed for controllable song generation. The proposed model facilitates fine-grained control over diverse musical attributes, including lyrics and textual descriptions of instrumentation, genre, mood, and timbre, while also offering an optional three-second reference clip for voice cloning. Within a unified auto-regressive framework, SongGen supports two output modes: **mixed mode**, which generates a mixture of vocals and accompaniment directly, and **dual-track mode**, which synthesizes them separately for greater flexibility in downstream applications. We explore diverse token pattern strategies for each mode, leading to notable improvements and valuable insights. Furthermore, we design an automated data preprocessing pipeline with effective quality control. To foster community engagement and future research, we will release our model weights, training code, annotated data, and preprocessing pipeline.
The code is available at https://github.com/LiuZH-19/SongGen.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：文本到歌曲生成任务（同时产生人声和伴奏）比纯语音或纯器乐生成更复杂，需要人声与伴奏的精确对齐和和谐。现有方法大多采用多阶段流水线（如先产生人声再产生伴奏，或相反），导致训练/推理流程繁琐，且各阶段误差累积，难以获得全局最优，尤其在人声与伴奏强耦合的流派（如rap）或表现力强的流派（如ballad）中问题突出。此外，开源数据极度匮乏。
- **整体含义**：论文提出 **SongGen**，一个完全开源的**单阶段自回归Transformer**，能够从歌词和文本描述直接生成带伴奏的歌声，并支持细粒度控制（乐器、风格、情绪、音色等），可选3秒参考片段进行零样本声音克隆。同时提供两种输出模式：**混合模式**（直接输出混音）和**双轨模式**（分别输出人声和伴奏），从而在简化流程的同时提升生成质量和可控性。

## 2. 方法论
- **核心架构**：基于自回归Transformer解码器，使用预训练音频编解码器（X-Codec，8个码本，帧率50Hz）将音频离散化为token序列，并采用MusicGen的codebook-delay pattern处理多码本。用户条件（歌词、文本描述、可选声音）通过各自的编码器和投影层，拼接后作为交叉注意力输入。
- **歌词编码**：使用VoiceBPE（基于字节对编码的音素级tokenizer）将歌词转为token序列，再通过一个小型Transformer编码器提取发音相关特征。
- **声音编码**：使用冻结的MERT（音乐表示模型）提取3秒参考片段的声学特征。
- **文本编码**：使用冻结的FLAN-T5编码器提取文本描述（涵盖乐器、情绪、流派等）的嵌入。
- **混合模式**：
  - 直接以混音音频的token为预测目标，训练时对各码本损失加权（早期码本权重更大）。
  - 提出 **Mixed Pro**：增加一个辅助的人声token预测损失（仅训练时使用，推理时去掉），以缓解模型偏向伴奏而忽略人声的问题。总损失函数为 \( L_{mixed-pro} = L_{mixed} + \lambda L_{vocal} \)。
- **双轨模式**：
  - **并行（Parallel）**：将人声和伴奏的token沿码本维度拼接，每步包含两组码本。在时间维度上尝试标准对齐、人声延迟一步（A-V）、伴奏延迟一步（V-A）三种变体。
  - **交错（Interleaving）**：时间维度上交替排列人声和伴奏token（先伴奏后人声A-V或先人声后伴奏V-A）。实验表明交错模式优于并行，且先伴奏后人声效果最佳。
- **训练方案**（分三步）：
  1. **模态对齐**：用全部数据进行全参数训练，对齐条件输入与音频输出。
  2. **无参考声音支持**：随机丢弃50%的声音参考输入，先冻结用户输入模块微调解码器，再全参数微调。
  3. **高质量微调**：使用过滤后的高质量子集（编辑距离≤5%，CLAP score≥25%，能量>1000，约100K片段）进行微调。
- **双轨模式训练**：先用混合模式预训练权重初始化，冻结用户输入模块微调解码器适配新token模式，再全参数微调，后续步骤与混合模式一致。
- **课程学习**：训练初期增大前三个码本的损失权重，后期逐渐平衡，使模型先学习主要成分再捕获细节。
- **数据预处理流水线**：从MSD、FMA、MTG-Jamendo收集8000小时音频 → Demucs分离人声/伴奏 → VAD检测人声段并切片（平均15秒） → 过滤低能量片段 → 两个Whisper模型做歌词识别，计算编辑距离（>20%丢弃） → 使用LP-MusicCaps生成caption，CLAP score过滤 → 最终获得约540K片段（约2000小时）。

## 3. 实验设计
- **数据集**：训练使用自建数据集（540K英文歌声片段）。测试从MusicCaps benchmark中筛选出326个英文歌声样本（保证与训练集不重叠）。
- **基线方法**：
  - 多阶段基线（自建）：两个与SongGen相同架构的Transformer，第一阶段从歌词+描述+参考声音生成人声，第二阶段以人声为额外条件生成伴奏，最后混合。
  - Parler-TTS（微调）：文本转语音模型，用相同训练数据微调。
  - Suno：商业产品（仅人类评估）。
- **评估指标**：
  - 自动指标：**FAD**（Frechet Audio Distance，分布匹配）、**KL**（Kullback-Leibler Divergence，概念相似性）、**CLAP Score**（音频-文本对齐）、**CLaMP3 Score**（更鲁棒的对齐）、**PER**（音素错误率，衡量歌词准确度，但ASR在唱歌上不准确所以偏高）、**SECS**（说话人嵌入余弦相似度，衡量声音克隆）、**内容美学指标**（CE内容享受、CU内容有用性、PC制作复杂度、PQ制作质量）。
  - 人类评估：MOS评分五项——**OVL**整体质量、**REL**文本相关性、**VQ**人声质量（清晰度、自然度）、**HAM**人声与伴奏和谐度、**SS**声音相似度。每个样本20个听者评估。

## 4. 资源与算力
- 论文附录A明确说明：
  - 使用 **16 张 Nvidia A100 (80GB) GPU**，每GPU batch size = 16。
  - 混合模式训练约 **400K 步**，优化器AdamW（β1=0.9, β2=0.99, weight decay=10⁻⁴）。
  - 第一步学习率10⁻⁴，后续微调步学习率5×10⁻⁵，余弦衰减。
  - 多阶段基线各训练约200K步，资源一致。
- 未提及具体训练总时长（小时数），但提供了足够细节。

## 5. 实验数量与充分性
- **主要实验组**：
  - 表1（自动评估）：对比混合模式（Mixed、Mixed Pro）、双轨模式所有变体（Parallel 3种、Interleaving 2种）以及基线。
  - 表2（人类评估）：同表1模式，另包含Suno和Ground Truth。
  - 表3：无参考声音测试（混合/双轨各一）。
  - 表4：消融训练策略（有无高质量微调、有无课程学习）。
  - 表5：消融歌词模块设计（tokenizer类型、是否用歌词编码器、prepend vs cross-attention）。
  - 表6：消融不同音频编解码器（Encodec, DAC, X-Codec）。
  - 额外可视化：注意力图分析、mel-spectrogram展示。
- **充分性评价**：实验设计较为全面，涵盖了主要变体、消融、与多种基线的对比，且进行了人类评估。虽然多阶段基线是自建的，但保证了架构和训练数据一致，比较公平。消融实验控制变量合理。尽管缺乏与现有其他开源模型（如Melodist、MelodyLM）的直接对比（因这些模型使用不同语言和封闭数据），但作者已说明情况。

## 6. 主要结论与发现
- **单阶段优于多阶段**：SongGen在自动和人类评估中均显著优于多阶段基线，尤其在和谐度（HAM增加1.04/5分）、整体质量（OVL增加0.57）和美学指标上。单阶段避免了误差累积，且推理速度更快（18.04s vs 42.85s生成30秒音频）。
- **Mixed Pro有效改善人声**：通过辅助人声token预测损失，显著提升了人声清晰度（PER从51.84降至40.58，VQ从3.55升至4.07）。
- **双轨模式最佳配置**：交错模式（Interleaving A-V）优于并行模式，且先伴奏后人声排列优于反序。其性能接近混合模式，并提供后处理灵活性。
- **训练策略有效**：高质量微调（HQFT）和课程学习（CL）均带来显著提升。
- **歌词编码设计**：VoiceBPE音素级tokenizer + 歌词编码器 + 交叉注意力效果最佳，优于T5 tokenizer或prepend方式。
- **音频编解码器选择**：X-Codec在本任务中比Encodec、DAC更稳定，训练收敛快，生成成功率更高（虽然采样率16kHz较低）。
- **无参考声音**：模型仍能生成可听歌曲，但性能略有下降。

## 7. 优点
- **开源全面**：模型权重、训练代码、标注数据、预处理流水线均开源，便于复现和社区发展。
- **单阶段简化流程**：相比多阶段方法，训练和推理更高效，且避免误差累积。
- **两种灵活模式**：混合模式直接输出混音，双轨模式便于后期编辑，统一框架下实现。
- **细粒度控制**：支持歌词、文本描述（乐器、风格、情绪、音色等）和可选声音克隆，可控性强。
- **数据预处理流水线**：自动化的清洗、过滤、标注流程，有效提高了训练数据质量，且公开。
- **深入的token模式探索**：在混合模式和双轨模式下系统比较了多种变体（并行/交错、顺序），并给出有价值见解（如声学偏置、交错模式注意力可视化），具有指导意义。
- **全面的消融实验**：对训练策略、歌词模块、音频编解码器均做了消融，验证了设计选择的有效性。

## 8. 不足与局限
- **数据规模与时长限制**：公开数据稀缺导致只能生成30秒片段，无法形成完整歌曲结构（如主歌-副歌循环）。
- **音频质量**：使用16kHz采样率X-Codec，保真度有限（低于24kHz或44.1kHz），论文提出未来可用渲染器上采样。
- **评估指标局限性**：PER因ASR在唱歌上不准确而偏高，可能无法真实反映歌词准确性；与Suno对比仅人类评估，且Suno数据规模远超，公平性有限。
- **多阶段基线自建**：并非现有开源模型，且未包含其他最新模型（如SongCreator、Yue）的对比，通用性受限。
- **无参考声音能力**：虽然支持，但性能略有下降，且未深入探索零样本泛化边界。
- **声音克隆风险**：论文指出存在版权和深度伪造滥用风险，但未提供具体约束机制。

（完）
