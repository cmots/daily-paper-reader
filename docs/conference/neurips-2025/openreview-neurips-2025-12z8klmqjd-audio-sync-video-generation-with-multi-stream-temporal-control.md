---
title: Audio-Sync Video Generation with Multi-Stream Temporal Control
title_zh: 基于多流时间控制的音频同步视频生成
authors: "Shuchen Weng, Haojie Zheng, Zheng Chang, Si Li, Boxin Shi, Xinlong Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=12z8KLMQJD"
tags: ["query:speech-model"]
score: 4.0
evidence: 语音驱动的音频同步视频生成，具有解耦控制
tldr: 针对复杂音频类型下视听同步视频生成质量低的问题，提出MTV框架。该框架将音频显式分解为语音、效果和音乐三个独立流，从而对口型运动、事件时序和视觉氛围进行解耦控制。实验证明，MTV在多种音频场景中均能生成高同步度与高质量的视频，拓展了音频驱动视频生成的应用边界。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-12z8klmqjd/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 1316, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-12z8klmqjd/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-12z8klmqjd/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 728, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-12z8klmqjd/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1447, \"height\": 737, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-12z8klmqjd/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1448, \"height\": 662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-12z8klmqjd/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1443, \"height\": 397, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-12z8klmqjd/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1452, \"height\": 435, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-12z8klmqjd/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1456, \"height\": 484, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-12z8klmqjd/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1453, \"height\": 214, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-12z8klmqjd/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1448, \"height\": 209, \"label\": \"Table\"}]"
motivation: 现有方法难以生成高质量音频-视频同步视频，尤其是复杂音频类型。
method: 提出MTV框架，将音频解耦为语音、效果和音乐三流，实现分别控制口型、事件和氛围。
result: 在多种音频类型上实现了精确的视听同步，生成视频质量显著提升。
conclusion: 为复杂音频驱动的视频生成提供了灵活且强大的控制方案。
---

## Abstract
Audio is inherently temporal and closely synchronized with the visual world, making it a naturally aligned and expressive control signal for controllable video generation (e.g., movies).
Beyond control, directly translating audio into video is essential for understanding and visualizing rich audio narratives (e.g., Podcasts or historical recordings).
However, existing approaches fall short in generating high-quality videos with precise audio-visual synchronization, especially across diverse and complex audio types.
In this work, we introduce MTV, a versatile framework for audio-sync video generation. MTV explicitly separates audios into speech, effects, and music tracks, enabling disentangled control over lip motion, event timing, and visual mood, respectively—resulting in fine-grained and semantically aligned video generation.
To support the framework, we additionally present DEMIX, a dataset comprising high-quality cinematic videos and demixed audio tracks. DEMIX is structured into five overlapped subsets, enabling scalable multi-stage training for diverse generation scenarios.
Extensive experiments demonstrate that MTV achieves state-of-the-art performance across six standard metrics spanning video quality, text-video consistency, and audio-video alignment.

---

## 论文详细总结（自动生成）

# 论文《Audio-Sync Video Generation with Multi-Stream Temporal Control》中文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：现有音频驱动视频生成方法难以在复杂音频类型（如同时包含语音、效果、音乐的影视音频）下生成高质量且精确视听同步的视频。主要存在两个挑战：
  - **音频-视觉映射不明确**：现有方法将整体音频直接映射到视频，导致映射泛化、缺乏特异性。
  - **时间对齐不精确**：难以在单个音频事件（如特定语音、音效）与其对应视觉特征（如口型、事件发生时刻）之间建立准确的时间对应关系。
- **整体含义**：音频天然具有时序性且与视觉世界紧密同步，可作为表达性强的控制信号。本文提出 MTV 框架，通过将音频显式分解为三个独立流（语音、效果、音乐），实现对口型运动、事件时序和视觉氛围的解耦控制，从而生成高同步度、高质量的电影级视频，并拓展音频驱动视频生成的应用边界（如播客可视化、历史录音复原等）。

## 2. 方法论：核心思想、关键技术细节与算法流程

### 核心思想
- 将复合音频分解为三个独立控制信号（语音、效果、音乐），通过**多流时间 ControlNet（MST-ControlNet）** 分别对口型、事件时序、视觉氛围进行精确控制。
- 提出**多阶段训练策略**，从具体局部控制（口型）逐步过渡到抽象全局影响（视觉氛围），逐步学习清晰的视听关系。
- 构建大规模数据集 **DEMIX**，包含高质量电影级视频及对应的分解音频轨道，支持多阶段训练。

### 关键技术细节

#### 整体框架（MTV）
- 基于预训练文本到视频模型（CogVideoX）的 DiT 骨干网络，使用 3D VAE 进行视频压缩，T5 编码文本描述。
- 将文本嵌入和加噪的潜在代码拼接后送入 Denoising Network，其中 Expert AdaLN 分别处理文本和视频特征，3D 全注意力进行语义交互。
- MST-ControlNet 提取音频特征后，通过间隔特征注入和全局风格注入整合到去噪网络中。

#### MST-ControlNet 结构
- **音频编码**：对分解的三个音频轨道使用 wav2vec 提取特征。
- **间隔流（Interval Stream）**：处理语音和效果特征。通过线性层和 N 个间隔交互块（包含独立处理和自注意力交互）建模两轨的 interplay，然后通过交叉注意力将特征注入对应时间间隔的视频潜在码，控制口型和事件时序。
- **整体流（Holistic Stream）**：处理音乐特征。通过整体上下文编码器（线性层 + 1D 卷积）提取特征，全局平均池化后生成风格嵌入，通过仿射变换（缩放+平移）统一调制所有帧的视频潜在码，控制视觉氛围。

#### 多阶段训练策略
- 文本结构模板：包含参与者数量、个人外观描述、当前说话者标识、场景描述。
- 训练阶段顺序：
  1. Basic Face（口型学习）
  2. Single Character（人体姿态、场景、相机运动）
  3. Multiple Characters（多说话人交互）
  4. Sound Event（事件时序、对象理解）
  5. Visual Mood（视觉氛围）
- 每阶段 40K 步，使用 Adam 优化器，学习率 1e-5。

#### 损失函数
- 标准扩散损失：\( \mathcal{L}_{dm} = \mathbb{E}_{t, z_0, \epsilon_t} [\| \epsilon_t - \epsilon_\theta(z_t, a, t, y) \|^2] \)

## 3. 实验设计

### 使用的数据集
- **DEMIX 数据集**（本文贡献）：从多个来源（CelebV-HQ, MovieBench, Condensed Movies, Short-Films 20K, YouTube）收集并经过严格过滤，共 392K 视频片段，1.2K 小时，包含五个重叠子集（basic face, single character, multiple characters, sound event, visual mood）。保留 1K 片段作为测试集。
- 对比方法使用的数据集：论文在 DEMIX 测试集上评估所有方法，并针对 MM-Diffusion 进行微调以适应此数据分布。

### Benchmark 与对比方法
- 对比方法：
  - MM-Diffusion（CVPR 2023）：基于扩散的多模态联合生成与零样本音频同步生成。
  - TempoTokens（AAAI 2024）：文本+音频条件，轻量适配器。
  - Xing et al.（CVPR 2024）：扩散潜在对齐器，开放领域音视频生成。
- 评估指标（6 个）：
  - 视频质量：**FVD**（Frechet Video Distance）
  - 时间一致性：**Temp-C**（CLIP 相邻帧相似度）
  - 文本-视频对齐：**Text-C**（VideoCLIP-XL）
  - 音频-视频对齐：**Audio-C**（ImageBind）
  - 口型同步：**Sync-C**（一致性）和 **Sync-D**（距离）
- 用户研究：3 项主观标准（语义一致性、运动流畅性、整体偏好），50 个描述，25 名志愿者。

### 额外实验
- **消融实验**：验证 MST-ControlNet 的关键组件（W/o SE: 不分离音乐特征提取；W/o SI: 共享交叉注意力注入；W/o TB: 冻结 DiT 骨干）。
- **预训练组件分析**：替换音频编码器为 BEATs、视频骨干为 Wan14B。
- **应用演示**：虚拟角色创建、关键帧驱动、长视频生成、场景过渡。
- **可控性展示**：改变文本描述、语音、效果、音乐分别独立控制不同方面。

## 4. 资源与算力

- **训练**：24 块 NVIDIA A800 GPU，每阶段训练 40K 步，共 5 个阶段，共 200K 步。
- **优化器**：Adam，学习率 1e-5。
- **可训练参数**：MST-ControlNet 和骨干网络的注意力层。
- **推理**：单张 NVIDIA A100 GPU 上生成 49 帧音频同步视频需 280 秒。
- **微调基线**：MM-Diffusion 使用 8 块 NVIDIA A100 GPU 微调 320K 步。

## 5. 实验数量与充分性

- 实验中包含：
  - 与 3 种 SOTA 方法的定量对比（6 个指标）。
  - 定性对比（可视化示例）。
  - 3 项消融实验。
  - 用户研究（3 个标准，50 个样本，25 人）。
  - 预训练组件替换实验（2 种替代方案）。
  - 可控性展示（4 个方面）。
  - 应用场景演示（4 种）。
- **充分性分析**：实验覆盖了多个维度（质量、对齐、人类偏好），指标全面，消融清晰，验证了各组件有效性。但缺失统计显著性检验（如误差线），仅报告单次结果。对比方法在 DEMIX 上重新微调或评估，确保公平。整体实验设计合理、充分。

## 6. 主要结论与发现

- MTV 在全部 6 个量化指标上优于所有对比方法，尤其在音频-视频对齐指标（Audio-C, Sync-C, Sync-D）上大幅领先。
- 消融实验表明：分离提取音乐特征（W/o SE）、分离注入特征（W/o SI）、训练骨干网络（W/o TB）对最终性能均有正向贡献，其中训练骨干对同步影响最大。
- 用户研究显示 MTV 在语义一致性、运动流畅性、整体偏好上均获最高票数（>74%），远超基线。
- 预训练组件实验表明框架可灵活替换更强的骨干（如 Wan14B）以提升视频质量，同时保持音频同步能力。
- MTV 支持多样化应用（角色创建、关键帧驱动、长视频、场景过渡），并展现出良好的可控性。

## 7. 优点

- **创新性**：首次将音频分解为三个独立控制流用于视频生成，实现精细解耦控制，解决了开放式音频映射不明确的问题。
- **方法论完整性**：提出配套数据集 DEMIX 和多阶段训练策略，系统支持从局部到全局的渐进学习。
- **架构设计**：MST-ControlNet 中的间隔流和整体流设计合理，间隔交互块和交叉注意力有效实现时序精确控制，全局风格注入实现整体氛围控制。
- **实验充分性**：多维度定量评估 + 用户研究 + 消融 + 组件分析，验证了方法的鲁棒性。
- **应用潜力**：框架可集成到更强骨干中，易于扩展，支持多种实际场景。

## 8. 不足与局限

- **上游依赖**：性能受限于音频分解方法的准确性（论文使用 MVSEP 和 Spleeter），若分解质量差（如音轨重叠严重），则控制效果下降。
- **领域覆盖**：DEMIX 数据集主要来自电影和访谈类视频，对极端噪声、非语言音频、高度重叠的复杂场景覆盖可能不足。
- **计算成本**：推理 49 帧需 280 秒（A100），实时性差；训练资源消耗大（24×A800，200K 步）。
- **验证局限**：
  - 未报告误差线或置信区间，无法判断结果的稳定性。
  - 对比方法中 MM-Diffusion 经过大量微调，但其他基线可能未完全优化，导致不公平。
  - 用户研究样本量较少（50 个测试，25 人），可能存在选择偏差。
- **理论分析缺乏**：论文未深入分析为什么分解三流控制有效或何时会失败。
- **生成时长限制**：目前仅支持 49 帧片段（<2 秒），长视频生成依赖于初始帧连接，可能累积误差。

（完）
