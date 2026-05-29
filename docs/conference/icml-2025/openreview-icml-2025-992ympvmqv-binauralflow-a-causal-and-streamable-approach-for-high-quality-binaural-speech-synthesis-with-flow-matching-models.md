---
title: "BinauralFlow: A Causal and Streamable Approach for High-Quality Binaural Speech Synthesis with Flow Matching Models"
title_zh: "BinauralFlow: 基于流匹配模型的高质量流式双耳语音合成"
authors: "Susan Liang, Dejan Markovic, Israel D. Gebru, Steven Krenn, Todd Keebler, Jacob Sandakly, Frank Yu, Samuel Hassel, Chenliang Xu, Alexander Richard"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=992yMPvMqV"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 使用流匹配的双耳语音合成，实现高质量空间音频渲染
tldr: 双耳音频渲染需建模双耳线索、房间混响与环境声，现有方法质量有限且不支持流式推理。本文提出BinauralFlow，将双耳渲染视为生成问题，采用流匹配模型实现因果、流式的高质量双耳语音合成。实验表明，该方法生成的音频在感知质量上接近真实录音，且支持实时流式处理，适用于VR/AR等应用。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-992ympvmqv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1751, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-992ympvmqv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1758, \"height\": 567, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-992ympvmqv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 832, \"height\": 759, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-992ympvmqv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 845, \"height\": 635, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-992ympvmqv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 785, \"height\": 574, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-992ympvmqv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 839, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-992ympvmqv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1675, \"height\": 774, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-992ympvmqv/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 895, \"height\": 678, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-992ympvmqv/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1427, \"height\": 1065, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-992ympvmqv/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1426, \"height\": 1065, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-992ympvmqv/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1426, \"height\": 1071, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-992ympvmqv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1767, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-992ympvmqv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 853, \"height\": 144, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-992ympvmqv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1771, \"height\": 734, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-992ympvmqv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1021, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-992ympvmqv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 633, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-992ympvmqv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1518, \"height\": 328, \"label\": \"Table\"}]"
motivation: 现有双耳渲染方法在质量和流式推理能力上不足，难以满足实时应用需求。
method: 提出流匹配框架BinauralFlow，将双耳合成作为生成任务，融合双耳线索和空间信息。
result: 主观和客观评估表明，合成音频质量接近真实录音，且支持因果流式推理。
conclusion: 流匹配模型为高质量双耳语音合成提供了高效解决方案，推动空间音频在实时系统中的应用。
---

## Abstract
Binaural rendering aims to synthesize binaural audio that mimics natural hearing based on a mono audio and the locations of the speaker and listener.  Although many methods have been proposed to solve this problem, they struggle with rendering quality and streamable inference. Synthesizing high-quality binaural audio that is indistinguishable from real-world recordings requires precise modeling of binaural cues, room reverb, and ambient sounds. Additionally, real-world applications demand streaming inference. To address these challenges, we propose a flow matching based streaming binaural speech synthesis framework called BinauralFlow. We consider binaural rendering to be a generation problem rather than a regression problem and design a conditional flow matching model to render high-quality audio. Moreover, we design a causal U-Net architecture that estimates the current audio frame solely based on past information to tailor generative models for streaming inference. Finally, we introduce a continuous inference pipeline incorporating streaming STFT/ISTFT operations, a buffer bank, a midpoint solver, and an early skip schedule to improve rendering continuity and speed. Quantitative and qualitative evaluations demonstrate the superiority of our method over SOTA approaches. A perceptual study further reveals that our model is nearly indistinguishable from real-world recordings, with a 42% confusion rate.

---

## 论文详细总结（自动生成）

## BinauralFlow 论文详细总结

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：双耳语音合成旨在基于单声道音频和说话者/听者位置，生成模拟自然听觉的双耳音频。现有方法在渲染质量和流式推理能力上均存在不足，难以满足沉浸式应用（如VR/AR）对高保真度和实时性的需求。
- **背景挑战**：
  - 高质量双耳音频需要精确建模双耳线索、房间混响和背景噪声，这些元素在输入单声道信号中缺失且具有随机性，传统回归方法难以生成。
  - 实际应用要求连续、低延迟的流式推理，但现有神经网络渲染方法大多采用非因果架构（如非因果卷积、全局注意力），不支持实时流式生成。

### 2. 论文提出的方法论

- **核心思想**：将双耳渲染视为生成任务而非回归任务，采用条件流匹配（Conditional Flow Matching）模型，结合因果关系设计，实现高质量、可流式推理的双耳语音合成。
- **关键技术细节**：
  - **条件流匹配模型**：
    - 将单声道音频 `x` 和双耳音频 `y` 转换到STFT谱域（复数谱）。
    - 定义概率路径 `ϕ_t(z) = t y + (1-t) z`，其中 `z = x + σϵ`，`ϵ` 为标准高斯噪声。
    - 学习向量场 `v_t(ϕ_t(z)) = y - z`，通过神经网络 `u_t` 以条件流匹配损失 `LCFM = E[||u_t - (y-z)||]` 进行训练。
    - 模型条件包括：说话者姿势 `p_tx`、听者姿势 `p_rx`、单声道谱 `x` 以及时间步 `t`。
  - **因果 U-Net 架构**：
    - 使用全因果的2D卷积、归一化、下/上采样层，确保当前帧的预测仅依赖历史信息。
    - 每层包含GroupNorm + SiLU激活 + 3x3因果卷积（一侧padding=2），支持流式处理。
    - 采用随机高斯傅里叶嵌入（RGFE）和MLP编码时间步和姿态条件，并注入U-Net隐藏特征。
  - **连续推理流水线**：
    - 流式STFT/ISTFT：为每个音频块维护缓冲区，实现帧级连续处理。
    - 缓冲库（Buffer Bank）：为不同时间步的模型推理步骤分别存储网络中间缓冲区，避免信息覆盖。
    - 中点求解器（Midpoint Solver）：使用二阶ODE求解方法，在6步内完成推理，平衡精度与效率。
    - 早期跳过调度（Early Skip Schedule）：跳过前一半推理步骤，经实验验证不降低渲染质量，可将NFE降至6（对比SGMSE需要30步）。

### 3. 实验设计

- **数据集与场景**：
  - **主数据集**：自建10小时真实录音（48kHz），在标准房间中采集，包含说话者自由走动、听者坐姿转头，背景有空调/电子设备噪声。训练/验证/测试分别8.47/0.86/1.33小时，测试集包含两位未见说话者（男女各一）。
  - **公共数据集**：使用Richard et al. (2021) 发布的公开双耳语音数据集进行补充验证。
  - **大规模预训练数据集**：利用人工双耳头（3Dio）和扬声器在非消声室采集超过7700小时双耳数据，涵盖97个VCTK说话者身份。
- **基准方法**：
  - 数字信号处理：SoundSpaces 2.0
  - 回归神经网络：2.5D Visual Sound、WaveNet、WarpNet
  - 生成模型：BinauralGrad（两阶段扩散）、SGMSE（扩散模型）
- **评估指标**：
  - 客观指标：波形L2误差（L2）、幅度L2误差（Mag）、相位角误差（Phase）。
  - 感知指标：ABX测试正确识别率（混淆率越高越好）、A-B测试混淆率、MUSHRA评分（环境和空间化两个维度，0-100分）。

### 4. 资源与算力

- 论文明确提到：在单张NVIDIA 4090 GPU上测试推理速度，音频采样率48kHz，单段音频长度683ms。BinauralFlow在NFE=6时推理耗时163ms（实时因子0.239）。
- 训练配置：使用PyTorch框架，Adam优化器，学习率1e-4，权重衰减1e-5，窗口长度512，hop 128，输入长度32768。未报告训练总时长和使用的GPU数量。
- 预训练阶段使用了大规模数据（7700小时+135个人工头+33个扬声器操作员），但未给出预训练的具体算力消耗。

### 5. 实验数量与充分性

- **定量对比**：主表1展示了与5种基线（DSP、3种回归、2种生成）在L2、Mag、Phase上的比较，并报告NFE和推理速度。图4进一步控制在相同NFE（6/30/60）下对比，证明BinauralFlow全面领先。
- **消融实验**：
  - 流匹配方法对比（表3）：验证提出的条件流匹配优于简化流匹配（Tong et al. 2023）。
  - 连续推理 vs. 非流式推理（图6）：显示流水线消除块间伪影。
  - 数据规模影响（图7）：分析训练数据量1%-100%的性能变化，以及预训练策略的效果。
  - 不同数值求解器对比（表5）：Euler、Midpoint、Heun在6步和30步下的质量/效率权衡。
  - Sway采样系数影响（表6）：说明早期跳过策略的合理性。
- **感知实验**：ABX、A-B和MUSHRA三项测试共23名受试者，结果具有统计显著性。
- **公共数据集验证**（表7）：在Richard et al. (2021) 数据集上对比，BinauralFlow多数指标优于BinauralGrad。
- **充分性评价**：覆盖了主流基线、多种消融、感知评估和跨数据集验证，实验设计较为全面。感知实验在受控声学环境中进行，校准了播放水平，降低了偏差。

### 6. 论文的主要结论与发现

- BinauralFlow在所有定量指标上显著优于现有方法（包括SOTA BinauralGrad和SGMSE），以更少的函数评估（6步）实现更高质量。
- 感知测试中，A-B测试混淆率达到42%（上限50%），MUSHRA环境评分68.4、空间化评分83.1，接近真实录音（87.4/89.9），表明合成音频几乎无法与真实录音区分。
- 大规模预训练策略可有效提升小数据量下的性能，零样本泛化能力较强。
- 因果架构和连续推理流水线使得生成模型首次支持实时流式双耳渲染，实时因子0.239具有实际应用潜力。

### 7. 优点

- **创新性**：首次将流匹配模型引入双耳语音合成，并严格设计为因果可流式网络，解决生成模型无法流式推理的瓶颈。
- **工程完整性**：包括完整的连续推理流水线（缓冲库、中点求解器、早期跳过），兼顾质量和实时性。
- **实验严谨**：同时进行客观指标和主观感知评估，并且控制感知实验环境（隔音室、校准耳机、均衡化），数据量充足（10小时+7700小时预训练）。
- **跨数据集验证**：在自建数据集和公共数据集上均验证有效性，增强结论可靠性。
- **消融深度**：对数值求解器、时间调度、数据规模、预训练等多个维度进行系统分析，支撑设计选择。

### 8. 不足与局限

- **实验覆盖**：仅测试了语音信号，未涉及非语音环境（如音乐、环境声）。房间类型单一（标准办公室环境），缺乏对多种声学场景的泛化验证。
- **偏差风险**：
  - 自建数据集使用有限数量的说话者和听者（训练集3人，测试集2人），可能带来说话者偏置。
  - 感知实验中的受试者数量（23人）虽满足统计要求，但样本量仍有限，且未报告受试者听力经验。
- **应用限制**：
  - 模型参数较大（314.5 MB），在移动或嵌入式设备上部署可能受限。
  - 实时因子0.239尚不能达到完全实时（<0.1），在低延迟要求严苛的场景（如AR）需更高优化。
  - 未讨论系统延迟（输入到输出端到端延迟）及对断网/丢块的鲁棒性。
- **预训练数据质量问题**：预训练使用人工头和扬声器采集，与真实人类双耳数据存在域差距，微调后虽提升效果但可能引入偏差。

（完）
