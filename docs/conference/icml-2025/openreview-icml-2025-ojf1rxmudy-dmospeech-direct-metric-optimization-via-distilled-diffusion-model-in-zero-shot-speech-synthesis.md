---
title: "DMOSpeech: Direct Metric Optimization via Distilled Diffusion Model in Zero-Shot Speech Synthesis"
title_zh: DMOSpeech：基于蒸馏扩散模型的直接度量优化零样本语音合成
authors: "Yinghao Aaron Li, Rithesh Kumar, Zeyu Jin"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ojF1rXmUdy"
tags: ["query:speech-model"]
score: 9.0
evidence: 通过蒸馏扩散模型进行直接度量优化的零样本语音合成
tldr: 本文提出DMOSpeech，一种蒸馏扩散文本到语音模型，通过端到端感知度量优化，首次在提升推理速度的同时超越教师模型质量。该方法解决了扩散模型迭代慢和蒸馏质量下降的问题，在零样本语音合成和声音克隆中取得优异表现，推动了高质量语音合成的发展。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ojf1rxmudy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 587, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ojf1rxmudy/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1695, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ojf1rxmudy/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 694, \"height\": 521, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ojf1rxmudy/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1684, \"height\": 1396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ojf1rxmudy/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1680, \"height\": 1319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ojf1rxmudy/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1620, \"height\": 651, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ojf1rxmudy/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1469, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ojf1rxmudy/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1460, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ojf1rxmudy/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 861, \"height\": 412, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ojf1rxmudy/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 863, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ojf1rxmudy/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1513, \"height\": 388, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ojf1rxmudy/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1446, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ojf1rxmudy/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1288, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ojf1rxmudy/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1286, \"height\": 460, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ojf1rxmudy/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 659, \"height\": 418, \"label\": \"Table\"}]"
motivation: 扩散模型语音合成计算量大，蒸馏导致质量下降，且无法端到端优化感知指标。
method: 设计可微蒸馏扩散模型，实现梯度流遍及所有组件，直接优化感知度量。
result: 推理速度更快，合成质量优于教师模型，零样本性能出色。
conclusion: 为高效高质量语音合成提供了新的蒸馏与优化范式。
---

## Abstract
Diffusion models have demonstrated significant potential in speech synthesis tasks, including text-to-speech (TTS) and voice cloning. However, their iterative denoising processes are computationally intensive, and previous distillation attempts have shown consistent quality degradation. Moreover, existing TTS approaches are limited by non-differentiable components or iterative sampling that prevent true end-to-end optimization with perceptual metrics. We introduce DMOSpeech, a distilled diffusion-based TTS model that uniquely achieves both faster inference and superior performance compared to its teacher model. By enabling direct gradient pathways to all model components, we demonstrate the first successful end-to-end optimization of differentiable metrics in TTS, incorporating Connectionist Temporal Classification (CTC) loss and Speaker Verification (SV) loss. Our comprehensive experiments, validated through extensive human evaluation, show significant improvements in naturalness, intelligibility, and speaker similarity while reducing inference time by orders of magnitude. This work establishes a new framework for aligning speech synthesis with human auditory preferences through direct metric optimization. The audio samples are available at https://dmospeech.github.io/demo

---

## 论文详细总结（自动生成）

# DMOSpeech: 基于蒸馏扩散模型的直接度量优化零样本语音合成

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：扩散模型在语音合成（TTS）和声音克隆中表现优异，但存在两大瓶颈：一是迭代去噪过程计算量巨大（需数十至上百步）；二是之前的蒸馏方法均导致质量下降；三是现有TTS模型存在不可微组件（如时长预测器）或依赖迭代采样，无法对感知指标（如词错误率WER、说话人相似度SIM）进行端到端优化。

- **整体意义**：本文首次在零样本语音合成中实现**直接对可微感知度量进行端到端优化**，同时通过分布匹配蒸馏将推理步数从128步降至4步，且蒸馏后质量**超越**教师模型，而非退化。该工作为对齐人类听觉偏好提供了新的框架，在速度、自然度、可懂度和说话人相似性上均显著提升。

## 2. 提出的方法论：核心思想、关键技术细节

- **核心思想**：通过**改进的分布匹配蒸馏（DMD2）** 将教师扩散模型蒸馏为少步（4步）学生生成器，同时构建从噪声输入到语音输出的完全可微路径，从而允许对CTC损失和说话人验证（SV）损失进行端到端梯度反传优化。

- **关键技术细节**：
  - **基础框架**：采用端到端潜在扩散模型（类似SimpleTTS/DiTTo-TTS），使用DAC变分自编码器将原始波形压缩为潜在表示，扩散Transformer（DiT）在潜在空间进行去噪。
  - **蒸馏中的多步采样**：学生生成器Gθ以噪声级别t为条件，在预定义时间步{1.0, 0.75, 0.50, 0.25}上逐步估计干净潜在表示xt0，然后重新加噪得到下一步输入（类似一致性模型），实现4步推理。
  - **分布匹配蒸馏损失（LDMD）**：最小化学生输出分布与数据分布之间的KL散度，梯度通过真实得分模型（教师fϕ）和学生得分模型（gψ）的得分差计算得出。
  - **多模态对抗训练**：改进DMD2中的判别器为条件多模态判别器（基于Conformer），输入学生得分模型的多层特征及文本、掩码、时间步等条件，使用LSGAN损失进行对抗训练，弥补单步学生模型的细节损失。
  - **直接度量优化**：在两个可微损失上反传梯度：
    - **CTC损失（LCTC）**：基于潜在CTC-ASR模型，直接优化字符级对齐概率，降低WER。
    - **说话人验证损失（LSV）**：基于潜在SV模型，最小化生成语音与提示语音的说话人嵌入余弦距离，提升相似度。
  - **训练策略**：交替训练，每更新一次Gθ更新五次gψ；屏蔽初始阶段CTC和SV损失（前5000/10000步），等主损失稳定后再加入；学习率设为教师最终学习率（1e-5）防止灾难性遗忘；批量大小需足够大（96）以保证得分估计准确性。

## 3. 实验设计

- **数据集**：
  - 主要预训练：**LibriLight**（57,706.4小时，7,439说话人），音频重采样至48kHz，文本转音素。
  - 额外实验（通用性验证）：**Emilia数据集**（多语言大规模），以F5-TTS为教师训练DMOSpeech，在**Seed-TTS评测集**（中英文）上评估。

- **评测基准**：
  - **主观评测**：在Prolific平台上进行由母语英语者参与的听感测试，含四项指标（MOS自然度、MOS音质、SMOS声音相似度、SMOS风格相似度），使用锚点（相同/不同说话人）进行质量控制。
  - **客观评测**：WER（基于HuBERT CTC ASR）、SIM（基于WavLM-TDCNN说话人嵌入）、RTF（实时因子）。

- **对比方法**：
  - **非端到端模型（含显式时长建模）**：NaturalSpeech 3、StyleTTS-ZS。
  - **端到端模型**：DiTTo-TTS、VoiceCraft、CLaM-TTS、XTTS，以及教师模型本身。

## 4. 资源与算力

- 文中明确说明：
  - 教师模型训练：24张 NVIDIA A100 40GB GPU，批量大小384，训练400,000步。
  - 学生训练（蒸馏与度量优化）：相同24张A100，批量大小96，Gθ和D训练40,000步，gψ训练200,000步。
  - 学习率调度、优化器（AdamW）等均有详细配置。
  - 未提及具体训练总耗时（天数/小时），但可大致推断在大量GPU资源下完成。

## 5. 实验数量与充分性

- **主观评测**：两轮大规模听测：第一轮（端到端对比+消融）80个平行样本/方法，501名工人；第二轮（非端到端对比）47个样本/方法，290名工人。经过严格的锚点验证（约30%-40%无效响应被剔除），结果具统计显著性。
- **客观评测**：在3,711个LibriSpeech test-clean样本上计算WER、SIM；在40个说话人上各合成50次计算基频变异系数（CV f0）以衡量多样性。
- **消融实验**：系统对比了教师模型、仅DMD2（1步/4步）、仅加CTC、仅加SV、完整DMOSpeech、以及降低批量大小（96→16）的效果，覆盖自然度、相似度、可懂度、多样性。
- **额外评测**：分析了情感相关声学特征（基频、能量、HNR、jitter、shimmer）的相关性；分析了条件/无条件情况下的Wasserstein距离以验证模式收缩现象。
- **充分性评价**：实验设计较为充分，覆盖了主客观、多方法、多维度、消融和通用性验证。但仅在英文（LibriLight/LibriSpeech）和有限中文（Seed-TTS）上测试，缺少更多语言和场景的评估。

## 6. 主要结论与发现

- DMOSpeech（4步）在主观自然度和声音相似度上**显著优于**教师模型（128步）及所有对比基线，且在音质上与NaturalSpeech 3相当，但推理速度快约13.7倍。
- **端到端度量优化有效**：仅加CTC损失大幅降低WER（5.67→1.79），仅加SV损失大幅提升SIM（0.53→0.70），二者联合取得最佳平衡，且优化后的度量与人类评分显著相关（SIM vs SMOS-V ρ=0.55；WER vs MOS-N ρ=-0.16）。
- **蒸馏诱导有益的模式收缩**：在强条件生成（相同文本和提示）下，学生分布集中在高概率区域，提升感知质量而不损害对不同输入的整体覆盖；同时自动修复了教师模型中的切音问题（10%左右句子末尾被切断）。
- **批量足够大对DMD训练至关重要**，从96降至16导致音质和相似度严重下降。

## 7. 优点

- **方法创新**：首次在TTS中实现可微感知度量端到端优化，通过蒸馏+对抗+可微损失的组合，在加速的同时提升质量（突破蒸馏必然降质的传统认知）。
- **高效性**：仅需4步推理，RTF低至0.07，远低于其他端到端模型（如VoiceCraft 1.12、NaturalSpeech 3 0.30）。
- **实验严谨性**：主观评测采用大规模众包、多重锚点验证、统计显著性检验；消融实验系统全面；开源音频演示。
- **通用性验证**：在F5-TTS + Emilia数据集上同样取得可比或更优结果，表明框架可移植。

## 8. 不足与局限

- **实验覆盖有限**：主要数据为英文LibriLight/LibriSpeech，中文实验仅十几小时数据规模（Seed-TTS评测集），缺乏多语言、多领域、低资源场景的评估。
- **多样性/模式收缩的双刃剑**：作者承认蒸馏降低了条件多样性（CV f0下降），虽然主观上偏好，但可能限制对稀有风格、情感或口音的覆盖。论文建议未来可探索控制多样性。
- **梯度稳定性与训练敏感度**：CTC和SV损失需要屏蔽初期阶段，批量大小需很大，训练对超参数敏感（学习率、损失权重），实际部署可能需复杂调参。
- **潜在滥用风险**：生成的语音比真实语音更接近提示说话人（SIM超过GT），可能被用于深度伪造，作者虽提及检测与伦理，但未提供具体缓解方案。

（完）
