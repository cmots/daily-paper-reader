---
title: "SING: Spatial Context in Large Language Model for Next-Gen Wearables"
title_zh: SING：大语言模型中的空间上下文用于下一代可穿戴设备
authors: "Ayushi Mishra, Yang Bai, Priyadarshan Narayanasamy, Nakul Garg, Nirupam Roy"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=lZ4HiOwpBO"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 通过到达角提取和LLM集成实现空间音频处理
tldr: 该论文致力于将空间上下文融入大语言模型以赋能可穿戴设备。提出基于微型麦克风阵列的空间传感系统，从单声道麦克风中提取精确的到达方向（DoA）信息，并与Whisper语音模型融合，使LLM具备空间音频感知能力。合成数据集上的实验验证了该方法在空间语音理解任务上的有效性，为空间音频渲染与上下文感知应用提供了新方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-lz4hiowpbo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 866, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lz4hiowpbo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1751, \"height\": 764, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lz4hiowpbo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1298, \"height\": 1035, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lz4hiowpbo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 774, \"height\": 662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lz4hiowpbo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 760, \"height\": 652, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lz4hiowpbo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 763, \"height\": 651, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lz4hiowpbo/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 763, \"height\": 651, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lz4hiowpbo/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 761, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lz4hiowpbo/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 769, \"height\": 649, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lz4hiowpbo/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 976, \"height\": 811, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lz4hiowpbo/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1796, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lz4hiowpbo/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 791, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lz4hiowpbo/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 800, \"height\": 633, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-lz4hiowpbo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1587, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lz4hiowpbo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1480, \"height\": 529, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lz4hiowpbo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1736, \"height\": 719, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lz4hiowpbo/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1734, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lz4hiowpbo/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1742, \"height\": 657, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lz4hiowpbo/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 948, \"height\": 404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lz4hiowpbo/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 955, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lz4hiowpbo/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1775, \"height\": 1346, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lz4hiowpbo/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 843, \"height\": 175, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lz4hiowpbo/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1780, \"height\": 264, \"label\": \"Table\"}]"
motivation: 可穿戴设备需要空间感知能力以实现上下文智能交互，但缺乏将空间音频与语言模型结合的有效方法。
method: 利用微型麦克风提取到达角信息，将其与Whisper的语音嵌入融合，使LLM理解空间语音。
result: 在合成空间语音数据集上，模型能够准确识别语音的方位信息，并提升上下文相关任务的性能。
conclusion: 空间音频与语言模型的融合是实现可穿戴环境理解的关键，为自主智能体提供空间线索。
---

## Abstract
Integrating spatial context into large language models (LLMs) has the potential to revolutionize human-computer interaction, particularly in wearable devices. In this work, we present a novel system architecture that incorporates spatial speech understanding into LLMs, enabling contextually aware and adaptive applications for wearable technologies. Our approach leverages microstructure-based spatial sensing to extract precise Direction of Arrival (DoA) information using a monaural microphone. To address the lack of existing dataset for microstructure-assisted speech recordings, we synthetically create a dataset by using the LibriSpeech dataset. This spatial information is fused with linguistic embeddings from OpenAI’s Whisper model, allowing each modality to learn complementary contextual representations. The fused embeddings are aligned with the input space of LLaMA-3.2 3B model and fine-tuned with lightweight adaptation technique LoRA to optimize for on-device processing. SING supports spatially-aware automatic speech recognition (ASR), achieving a mean error of 25.72°—a substantial improvement compared to the 88.52° median error in existing work—with a word error rate (WER) of 5.3. SING also supports soundscaping, for example, inference how many people were talking and their directions, with up to 5 people and a median DoA error of 16°. Our system demonstrates superior performance in spatial speech understanding while addressing the challenges of power efficiency, privacy, and hardware constraints, paving the way for advanced applications in augmented reality, accessibility, and immersive experiences.

---

## 论文详细总结（自动生成）

# 论文总结：SING: Spatial Context in Large Language Model for Next-Gen Wearables

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：现有的大语言模型（LLM）缺乏对空间音频（尤其是语音）的感知能力，无法处理“谁在哪个方向说话”这类空间上下文信息。特别是在可穿戴设备（如智能耳机、AR眼镜）上，传统的基于麦克风阵列的空间感知方案体积大、功耗高、不实用。
- **整体含义**：该论文首次实现了将**单通道微型麦克风采集的空间语音信号**与LLM深度融合，使LLM能够同时理解语音内容（ASR）和声源方向（DoA），从而支持空间感知的自动语音识别、多说话人方向检测、声音场景描绘等高级应用，为可穿戴设备带来上下文智能交互。

## 2. 方法论：核心思想与关键技术

- **核心思想**：利用一种名为“Owlet”的**微结构辅助空间传感**技术，通过在单声道麦克风上加装微型物理结构（衍射、毛细效应、结构共振），使单通道录音自然地包含方向依赖的频率响应，从而用极简硬件提取到达角（DoA）信息。随后将DoA特征与Whisper的语音嵌入融合，通过线性投影层对齐到LLaMA-3.2 3B模型的输入空间，并使用LoRA进行轻量级微调。
- **关键技术细节**：
  - **空间编码**：使用Owlet硬件（原设计含两个麦克风但输出为单声道）记录语音信号；利用预先标定的360°方向的频域冲激响应H(ω,θ)与干净语音卷积生成合成空间语音数据。
  - **DoA编码器**：轻量级3层CNN（2D卷积+BN+ReLU+MaxPool）将Mel谱图映射为512维嵌入，最终输出DoA预测。
  - **语音编码器**：使用Whisper-large-v3的编码器，提取1024维隐藏状态，经自适应平均池化为固定尺寸。
  - **融合与对齐**：DoA嵌入和Whisper嵌入通过一个线性层（投影矩阵W）映射到LLM的输入空间，与LLaMA-3.2 3B的嵌入对齐。
  - **微调**：使用LoRA（r=8, alpha=16, dropout=0.1）在空间ASR任务上对LLM进行指令微调。
- **公式**：空间语音生成采用卷积 y_conv,θ(n) = (y * h_θ)(n)；STFT与Mel谱图采用标准变换。

## 3. 实验设计

- **数据集**：
  - **训练/测试数据**：基于LibriSpeech和Owlet的360°冲激响应合成400小时空间ASR数据集（单说话人）；以及2000小时多说话人（1-5人）数据集用于声音场景描绘。
  - **其他评估数据集**：Common Voice、VoxCeleb、LJ Speech（语音），以及ESC-50（环境音频）。
  - **噪声与混响**：使用GTU-RIR数据集添加不同SNR和混响条件。
- **Benchmark**：与三个现有工作对比：
  - **BAT**（Zheng et al., 2024）：支持非语音音频的DoA估计（MAE 88.52°）。
  - **SELDNet**（Adavanne et al., 2018）：使用4麦克风进行声音事件定位与检测。
  - **AudioMAE**（Huang et al., 2022）：单麦克风的音频掩码自编码模型。
  - **SALMONN**（Tang et al., 2023）：通用音频语言模型（无空间意识）。
- **对比方法**：在DoA任务上对比BAT（单声道）、SELDNet（4 mic）、AudioMAE（单mic）；在ASR任务上对比SALMONN。
- **评估指标**：MAE（平均绝对角度误差）、MEEM（修正效率度量，=MSE × 麦克风数量）、中位误差、WER（词错误率）。

## 4. 资源与算力

- **训练资源**：
  - DoA编码器：单张A100 GPU，每个epoch约20分钟，共20个epoch。
  - LLM预训练与微调：3张H100 80GB GPU，预训练5个epoch，微调10个epoch。
  - 混合精度（FP16）训练，梯度检查点启用。
- **推理资源**（附录O）：DoA编码器平均延迟62.93 ms/文件，内存50 MB（全精度）/16 MB（量化），总推理内存741.42 MB，适合端侧部署。

## 5. 实验数量与充分性

- **实验组数**：论文进行了以下多组实验：
  1. **主实验**：单说话人空间ASR，报告MAE=25.72°，WER=5.3（含DoA）/1.8（不含DoA）。
  2. **多说话人DoA估计**：1-5个说话人，MAE在17.08°-28.11°之间。
  3. **跨数据集泛化**：在Common Voice、VoxCeleb、LJ Speech、ESC-50上测试DoA，MAE为41°-80°。
  4. **噪声与混响鲁棒性**：在8种噪声/混响组合下测试，MAE从25.72°升至54.43°。
  5. **消融研究**：比较3层CNN vs. Audio Spectrogram Transformer作为DoA编码器（CNN更优）。
  6. **与Owlet模型比较**（附录M）：SING与Owlet原始CNN模型的CDF对比。
  7. **与现有方法全面对比**（表1、表2）。
- **充分性判断**：实验覆盖单/多说话人、多种数据集、噪声、混响、消融，较为充分。但缺乏真实场景（非合成数据）的实验；与其他方法对比时部分基线只报告了单源结果，多源对比不够全面。

## 6. 主要结论与发现

- **主要结论**：使用微结构辅助的单声道麦克风可以高精度提取DoA信息，并与LLM有效集成。SING在空间ASR任务上比BAT的DoA误差降低约70%（88.52°→25.72°），同时保持了可接受的WER（5.3%）。在多达5人的多说话人场景下，中位DoA误差仅16°。
- **方法有效性**：融合空间编码与Whisper嵌入，并利用LoRA轻量微调，实现了在极简硬件上的空间语音理解，且能满足可穿戴设备的功耗、隐私和尺寸约束。

## 7. 优点

1. **硬件创新**：利用微结构实现单声道空间感知，无需麦克风阵列，体积小、功耗低，适合可穿戴设备。
2. **方法简洁高效**：采用轻量CNN编码器（16.3M参数）+线性投影层+LoRA，避免复杂多模态对齐模块。
3. **性能显著提升**：DoA估计MAE 25.72°，大幅优于BAT（88.52°）。
4. **功能扩展**：支持多说话人数目估计与DoA联合估计（声音场景描绘）。
5. **隐私友好**：可在端侧完成特征提取，仅传输低维嵌入至云端。
6. **系统评估全面**：包含噪声、混响、跨数据集测试及消融分析。

## 8. 不足与局限

1. **依赖合成数据**：所有实验均基于Owlet冲激响应与LibriSpeech的卷积合成数据，缺乏真实录音标定，存在S2S（sim-to-real）差距。
2. **缺少真实场景验证**：未在真实会议室、户外等环境下部署测试，泛化能力未经充分验证。
3. **基线对比不够完整**：多说话人DoA任务中，SELDNet仅报告1源结果（且MAE=90.03°），未提供多源性能；BAT仅对比了平均误差而非中位误差；SALMONN无空间能力，可比性有限。
4. **ASR性能退化**：加入DoA后WER从1.8%升至5.3%，说明空间特征与语音内容存在竞争，尚未实现无损融合。
5. **仅支持水平方位角**（1-360°），未支持俯仰角，不是完全3D空间理解。
6. **可重复性**：Owlet硬件细节和冲激响应标定过程未公开，复现有难度。

（完）
