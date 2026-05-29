---
title: Emotional Face-to-Speech
title_zh: 情感人脸到语音
authors: "Jiaxin Ye, Boyuan Cao, Hongming Shan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=EuDlvBqcSm"
tags: ["query:speech-model"]
score: 10.0
evidence: 从表情合成情感语音
tldr: 该论文探索了从表情人脸直接合成情感语音的新任务——情感人脸到语音。现有方法难以生成多样化的情感语音风格，为此提出了DEmoFace框架，基于多级神经音频编解码器和离散扩散Transformer（DiT），结合课程学习和多模态DiT块来动态对齐面部特征与语音特征。实验表明该方法能生成自然、富有表现力的情感语音，在虚拟角色配音和辅助表达障碍者等场景具有重要应用。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1669, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1674, \"height\": 840, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1762, \"height\": 760, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1747, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1767, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 843, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eudlvbqcsm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1655, \"height\": 708, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-eudlvbqcsm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1714, \"height\": 629, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eudlvbqcsm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 826, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eudlvbqcsm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 842, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eudlvbqcsm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1839, \"height\": 899, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eudlvbqcsm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1544, \"height\": 1329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eudlvbqcsm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1681, \"height\": 676, \"label\": \"Table\"}]"
motivation: 现有方法无法从人脸表情生成具有情感多样性的语音。
method: 提出DEmoFace框架，采用离散扩散Transformer和多级音频编解码器，结合课程学习进行多模态对齐。
result: 生成的情感语音在自然度和情感表达丰富度上显著优于现有方法。
conclusion: 人脸表情可作为语音情感表达的可靠信号，为表现力语音合成开辟了新途径。
---

## Abstract
How much can we infer about an emotional voice solely from an expressive face? This intriguing question holds great potential for applications such as virtual character dubbing and aiding individuals with expressive language disorders. Existing face-to-speech methods offer great promise in capturing identity characteristics but struggle to generate diverse vocal styles with emotional expression. In this paper, we explore a new task, termed *emotional face-to-speech*, aiming to synthesize emotional speech directly from expressive facial cues. To that end, we introduce  **DEmoFace**, a novel generative framework that leverages a discrete diffusion transformer (DiT) with curriculum learning, built upon a multi-level neural audio codec. Specifically, we propose multimodal DiT blocks to dynamically align text and speech while tailoring vocal styles based on facial emotion and identity. To enhance training efficiency and generation quality, we further introduce a coarse-to-fine curriculum learning algorithm for multi-level token processing. In addition, we develop an enhanced predictor-free guidance to handle diverse conditioning scenarios, enabling multi-conditional generation and disentangling complex attributes effectively. Extensive experimental results demonstrate that DEmoFace generates more natural and consistent speech compared to baselines, even surpassing speech-driven methods. Demos of DEmoFace are shown at our project https://demoface.github.io.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：现有的人脸到语音（Face-to-Speech, F2S）任务主要关注从人脸图像提取身份特征来合成语音，但忽略了人脸表情中包含的丰富情感信息。用户期望合成的语音不仅保留说话人身份，还能传达符合面部表情的情感韵律，以提升人机交互体验。
- **新任务定义**：论文提出了 **情感人脸到语音（Emotional Face-to-Speech, eF2S）** 任务——仅从人脸视觉线索（包括身份和表情）合成具有对应情感的语音，而不依赖任何语音提示。此任务在虚拟角色配音、辅助表达障碍者等场景具有重要价值。
- **核心挑战**：传统F2S方法无法建模情感；现有的情感TTS方法需语音提示或情感标签，且难以同时定制身份和情感；跨模态（人脸→语音）的异质性导致对齐困难。

## 2. 论文提出的方法论

- **核心思想**：提出 **DEmoFace** 框架，基于离散扩散Transformer（DiT）和多级神经音频编解码器，实现从人脸条件（身份+表情）和文本到情感语音的生成。通过课程学习逐步处理多级RVQ token，并通过增强的无预测器引导（EPFG）实现多条件解耦。
- **关键技术细节**：
  - **语音Token化**：使用RVQ-based神经音频编解码器（12层、码本大小1024）将语音离散化为12级token序列（低层保留语义，高层保留声学细节）。
  - **离散扩散过程**：定义连续时间马尔可夫链，每个token独立向[MASK]状态扩散。前向过程可并行采样，反向过程通过得分网络估计混凝土分数（concrete score）。
  - **多模态DiT (MM-DiT)**：输入为掩码token序列，融合三组条件：
    - **身份条件 \(c_{id}\)**：通过ArcFace+FaceNet提取人脸特征，经MLP转换，并与GE2E语音嵌入进行余弦、L1、L2对齐损失训练。
    - **情感条件 \(c_{emo}\)**：使用Poster2提取表情嵌入，通过预测标签和学习嵌入层得到身份无关的情感向量。
    - **文本条件 \(c_{text}\)**：通过SpeechT5编码器和IPA音素序列获得文本嵌入。
    - 条件和时间步嵌入通过AdaLN注入，文本条件通过交叉注意力（含旋转位置编码）动态对齐。
  - **课程学习**：基于不同RVQ层的频率分布（低层低频），每3个epoch逐步引入更高层token进行训练（从x^{r1}到x^{r12}），提升训练效率和生成质量。
  - **增强无预测器引导 (EPFG)**：将条件得分分解为组合项（各独立条件）和联合项（所有条件整体），通过加权乘积实现多条件灵活控制，公式为：
    \[
    \hat{s}^{(w)}_\theta(x,t)_{\hat{x}} = s_\theta(x,t)_{\hat{x}} \prod_{k=1}^K \frac{s^{w_k}_\theta(x,t,c_k)_{\hat{x}}}{s^{w_k}_\theta(x,t)_{\hat{x}}} \cdot \frac{s^{w_0}_\theta(x,t,c)_{\hat{x}}}{s^{w_0-1}_\theta(x,t)_{\hat{x}}}
    \]
    其中 \(w_0\) 控制联合强度，\(w_k\) 控制各个局部条件强度。
- **训练与推理流程**：
  - 训练：随机掩码token，计算多级DSE损失；同时训练身份对齐损失。
  - 推理：先通过帧级时长预测器估算语音长度，然后从全[MASK]开始，使用欧拉采样器（96步）和EPFG逐步去噪，最后用编解码器解码波形。

## 3. 实验设计

- **数据集**：
  - 预训练：RAVDESS、MEAD、MELD-FAIR，共31.33小时、26,767条语音、953个说话人、7种基本情感。另加入10小时LRS3子集进行预训练（使模型可与Face-TTS相比）。
  - 训练/验证/测试划分：RAVDESS和MEAD按说话人无重叠划分；MELD-FAIR按原始划分（有说话人重叠）。
- **Benchmark与对比方法**：
  - **声学引导方法**（需语音提示）：EmoSpeech、FastSpeech2、V2C-Net、HPM、StyleDubber。
  - **视觉引导方法**（仅视觉）：Face-TTS。
  - 对比维度：客观（EmoSim、SpkSim、RMSE、MCD、WER）和主观（MOS_nat、MOS_id、MOS_emo，50名参与者，5分制）。
- **评价指标**：
  - 自然度：MCD（频谱失真）、WER（字错误率，智能度）。
  - 表现力：EmoSim（情感相似度）、SpkSim（说话人相似度）、RMSE（基频误差）。

## 4. 资源与算力

- **硬件**：使用一块 **24GB NVIDIA RTX 4090 GPU** 进行训练。
- **训练配置**：
  - MM-DiT：AdamW优化器，学习率1e-4，batch size 32，总迭代300k。
  - 身份编码器：batch size 12，80k steps。
  - 时长预测器：batch size 32，至少100k steps。
- **推理效率**：batch size=1时RTF=0.49（接近实时），batch size=32时RTF=0.13。

## 5. 实验数量与充分性

- **实验数量**：
  - 主对比实验：与6种基线方法进行客观（5项指标）和主观（3项MOS）对比。
  - 消融实验：5组（移除身份条件、移除情感条件、移除课程学习、移除身份对齐、移除EPFG），在5项指标上验证。
  - 参数搜索：对EPFG的 \(w_0\)、\(w_1\)、\(w_2\) 进行网格搜索（图6a）。
  - 推理步数消融：对比不同NFE步数（图6b）。
  - 可视化分析：t-SNE分布对比（图4）和mel谱图/F0曲线（图3）。
- **充分性与公平性**：
  - 客观指标全面覆盖自然度、情感、身份、基频、可懂度。
  - 主观评估有50名参与者，95%置信区间，符合领域惯例。
  - 对比方法均按原论文复现或使用官方预训练模型，训练数据一致（Face-TTS使用更大数据集但论文已指出）。
  - 消融实验逻辑清晰，验证了各组件必要性。
  - 实验设计较为充分，但数据集规模较小（31小时），可能影响泛化性结论。

## 6. 论文的主要结论与发现

- DEmoFace在情感语音合成上显著优于现有F2S方法，在EmoSim、SpkSim、MCD、RMSE等指标上甚至超过部分声学引导方法。
- 课程学习有效提升训练效率和生成质量，低层语义先学习保证了WER和EmoSim，高层声学细节后学习提升了SpkSim。
- EPFG实现了多条件解耦和联合控制，网格搜索验证了参数敏感性。
- 仅需32步即可达到满意效果，推理速度接近实时。
- 人脸表情可以作为语音情感表达的有效信号，无需语音提示即可生成具有一致身份和情感的语音。

## 7. 优点

- **任务创新**：首次提出eF2S任务，拓宽了人脸到语音的研究边界。
- **方法融合巧妙**：将离散扩散模型、多模态DiT、课程学习、增强引导相结合，解决了多条件生成中的对齐与解耦难题。
- **性能优越**：在多个指标上击败了依赖语音输入的声学引导方法，证明了仅靠视觉线索生成高质量情感语音的可行性。
- **训练高效**：课程学习减少了高层token早期干扰，加速收敛；推理步数少，RTF接近实时。
- **可解释性**：通过t-SNE和谱图可视化展示了情感和身份的聚类效果，验证了条件解耦有效性。

## 8. 不足与局限

- **数据集局限**：训练数据仅31小时，且存在视觉-语音偏差（如说话人表情和语音情感不完全匹配），导致合成语音倾向于“平均”音质，无法精确重建真实个体声音。
- **发音准确性问题**：数据集语义单元不足，语音智能度（WER）仍有提升空间（尽管已优于多数基线）。
- **视觉条件依赖**：仅使用人脸图像，未考虑背景、姿态等信息，当人脸部分遮挡或表情不显著时可能失效。
- **实验规模**：尽管对比全面，但未在更大规模数据集（如LRS3全量）上评估，泛化性有待验证。
- **计算资源**：仅单GPU训练，大规模部署可能需要更多算力。

（完）
