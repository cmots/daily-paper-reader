---
title: "OmniTalker: One-shot Real-time Text-Driven Talking Audio-Video Generation With Multimodal Style Mimicking"
title_zh: OmniTalker：一种基于多模态风格模仿的实时文本驱动说话音频-视频生成方法
authors: "Zhongjian Wang, Peng Zhang, Jinwei Qi, wang guang yuan, Sheng Xu, Bang Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=eK31JidsTN"
tags: ["query:speech-model"]
score: 8.0
evidence: 文本驱动的人脸说话视频生成，模仿说话风格
tldr: 本文提出OmniTalker，一个统一框架，可从输入文本实时生成同步的说话音频和视频，并模仿目标身份的语言和面部运动风格。采用双分支扩散Transformer结构，分别处理音频和视频生成，通过跨模态融合模块在浅层整合信息。实验证明该方法在生成质量和风格模仿上优于现有方法，为文本驱动的人脸动画提供了高效解决方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1416, \"height\": 904, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 851, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1395, \"height\": 1152, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1448, \"height\": 601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1434, \"height\": 612, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 775, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1195, \"height\": 596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1432, \"height\": 947, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1430, \"height\": 1344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1434, \"height\": 1326, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ek31jidstn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1431, \"height\": 1174, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ek31jidstn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1331, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ek31jidstn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ek31jidstn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1100, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ek31jidstn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1433, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ek31jidstn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1311, \"height\": 457, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ek31jidstn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1163, \"height\": 981, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ek31jidstn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1390, \"height\": 388, \"label\": \"Table\"}]"
motivation: 音频驱动的人脸生成已取得进展，但文本驱动方法尚未充分探索，特别是同步生成音频和视频并模仿风格。
method: 采用双分支扩散Transformer架构，一个分支生成音频，另一个生成视频，浅层引入跨模态融合模块整合信息。
result: 实验表明，OmniTalker在文本驱动的说话视频生成中实现了高质量同步输出和风格模仿。
conclusion: 本文为文本驱动的人脸动画提供了一种统一的高效解决方案，有望推动虚拟人实时交互应用。
---

## Abstract
Although significant progress has been made in audio-driven talking head generation, text-driven methods remain underexplored. In this work, we present OmniTalker, a unified framework that jointly generates synchronized talking audio-video content from input text while emulating the target identity's speaking and facial movement styles, including speech characteristics, head motion, and facial dynamics. Our framework adopts a dual-branch diffusion transformer (DiT) architecture, with one branch dedicated to audio generation and the other to video synthesis.
At the shallow layers, cross-modal fusion modules are introduced to integrate information between the two modalities. In deeper layers, each modality is processed independently, with the generated audio decoded by a vocoder and the video rendered using a GAN-based high-quality visual renderer. Leveraging DiT’s in-context learning capability through a masked-infilling strategy, our model can simultaneously capture both audio and visual styles without requiring explicit style extraction modules.  Thanks to the efficiency of the DiT backbone and the optimized visual renderer, OmniTalker achieves real-time inference at 25 FPS.
To the best of our knowledge, OmniTalker is the first one-shot framework capable of jointly modeling speech and facial styles in real time. Extensive experiments demonstrate its superiority over existing methods in terms of generation quality, particularly in preserving style consistency and ensuring precise audio-video synchronization, all while maintaining efficient inference.

---

## 论文详细总结（自动生成）

### 论文总结：OmniTalker: One-shot Real-time Text-Driven Talking Audio-Video Generation With Multimodal Style Mimicking

#### 1. 核心问题与整体含义（研究动机和背景）
- **问题**：音频驱动的说话头生成（THG）已取得显著进展，但文本驱动的THG仍较少探索。现有文本驱动方法多采用级联架构（TTS + 音频驱动THG），存在**计算冗余、错误传播、音视频风格不匹配**等问题。此外，风格建模通常简化为离散情感标签或帧级表情控制，未能同时捕捉语音特征、头部运动与面部动态之间的复杂关联。
- **意义**：OmniTalker旨在实现**端到端、一次学习（one-shot）、实时**的文本驱动说话头生成，同时模仿目标身份的完整说话风格（语音、头部姿势、面部表情），推动人机交互、虚拟数字人等应用的发展。

#### 2. 方法论：核心思想、关键技术细节
- **核心思想**：采用**双分支扩散Transformer（DiT）架构**，一条分支生成音频（梅尔谱），另一条生成视频（头部运动参数）。通过**跨模态融合**（MM-Attention）在浅层整合音频与视觉信息，深层分别独立细化。利用DiT的**上下文学习能力**，采用**掩码填充策略**（masked-infilling）隐式学习风格，无需显式风格提取模块。
- **关键技术细节**：
  - **多模态特征对齐**：从参考视频提取音频特征（梅尔谱）和视觉特征（面部blendshape、头部姿态、眼部运动系数）。驱动文本通过ConvNeXt-V2编码。
  - **融合模块**：经过实验比较，选择**多模态联合注意力（MM-Attention）**作为融合方式，将音频和视觉特征拼接后计算自注意力，应用RoPE位置编码。
  - **训练**：使用**流匹配（Flow Matching）**，优化条件流匹配损失，分别对梅尔谱、头部姿态、面部表情、眼部运动使用不同权重（λₘ=0.1, λ_f=3.0, λ_h=0.5, λ_e=0.5）。采用**分类器无指导（CFG）**增强风格复制（α_Mr=2.0, α_Cr=2.5, α_ST=2.0）。
  - **解码**：音频由Vocos解码；视频由基于GAN的warping渲染器生成（参考VASA-1、LivePortrait），输出512×512@50fps。
  - **推理**：通过任意ODE求解器从高斯噪声采样，总步数16步，达到25 FPS实时。

#### 3. 实验设计
- **数据集**：
  - **预训练**：开源的TalkingHead-1KH、VoxCeleb、CelebV-HQ（总计约690小时高质量自定义数据集）。
  - **测试**：音频：SEED（中英文）、Custom（真实场景100个中文视频）；视频：VoxCeleb2（500个片段）、Custom（100个中文视频）。
- **基准方法**：
  - TTS对比：MaskGCT、F5TTS、CosyVoice。
  - 音频驱动THG对比：SadTalker、AniTalker、StyleTalk、EchoMimic、Hallo（全部使用OmniTalker生成的音频作为驱动，保证公平）。
- **评估指标**：
  - 音频：词错误率（WER）、说话人相似度（SIM-A）。
  - 视频：FVD（视频质量）、CSIM（身份保持）、Sync-C（唇形同步）、E-FID（表情FID）、P-FID（姿态FID）。
  - 用户研究：MOS评分（1-5分），包含语音相似度、节奏、视觉质量、说话风格、唇形同步、姿势同步六项。

#### 4. 资源与算力
- 模型参数：**0.8B**（22个音视频融合块，每个分支4个单模态DiT块，嵌入维度512）。
- 训练硬件：**8×NVIDIA A100 GPU**，每GPU batch size为12,800帧，训练总计**750,000次迭代**，学习率1e-4。
- 推理硬件：单张NVIDIA RTX 4090，实时运行**25 FPS**（包括音频和视频生成）。

#### 5. 实验数量与充分性
- **实验组数**：
  - 定量对比：两个数据集（VoxCeleb2和Custom）上，针对THG方法报告5项指标（表2）；TTS方法在SEED和Custom上报告2项指标（表1）。
  - 消融实验：融合策略（Add/Linear/Cross-Attention/MM-Attention）在Custom数据集上的对比（表4）；模态消融（文本、音频、视频缺失）在Custom上的对比（表7）。
  - 用户研究：50名志愿者，25个参考视频×2个数据集，共50份结果，六维度MOS（表3）。
  - 定性可视化：头部姿态时序图、运动热力图、眼部运动、情感生成（图2-3、图7-10）。
- **充分性评价**：实验设计较为全面，覆盖了音频、视频、风格、同步等多个维度；对比方法采用统一音频输入，避免不公平；消融实验验证了核心设计选择；但未测试跨语言（仅中英文）、未报告多次运行的标准差或置信区间。

#### 6. 主要结论与发现
- OmniTalker在**所有视频指标上达到SOTA**（FVD最低、CSIM最高、E-FID和P-FID显著优于其他方法），在音频指标上WER最低（或接近最低），SIM-A排名第二（接近MaskGCT）。
- 在**说话风格保持**（头部姿态、面部动态）上取得极大提升（E-FID降低至0.08，P-FID降低至0.12），用户研究中说话风格和姿势同步评分大幅领先。
- **实时性能**：25 FPS，且无需TTS前置步骤（端到端），实际推理速度快于所有对比方法（它们需先用TTS生成音频）。
- 消融表明**MM-Attention融合**显著优于其他策略；引入视觉条件（αCr=2.5）能进一步降低WER，验证多任务学习的增益。

#### 7. 优点
- **创新性**：首个统一框架同时实现**文本→音频+视频**的实时生成，并**一次学习模仿完整说话风格**（语音+头部+表情）。
- **端到端设计**：避免级联误差，消除计算冗余。
- **双分支DiT + 跨模态融合**：符合多模态生成规律，浅层融合、深层独立处理，平衡同步与质量。
- **上下文学习**：通过掩码填充隐式学习风格，无需复杂风格提取模块，简洁高效。
- **高效推理**：流匹配训练、轻量模型（0.8B）、优化的GAN渲染器，在单卡4090上可达25FPS。
- **消融实验全面**：对比四种融合策略和三种条件组合，验证设计有效性。

#### 8. 不足与局限
- **生成范围受限**：仅生成头部区域，不含手部或身体动作，无法实现全身交互。
- **GAN渲染器限制**：大幅度运动时可能出现纹理模糊、边界伪影（如张嘴过大），视觉质量仍有提升空间。
- **实验覆盖**：未在更多样化的语言（如阿拉伯语、日语）或复杂场景（多人对话）上测试；未报告多次实验的方差，统计显著性不足。
- **潜在偏差风险**：训练数据主要来自开源英文/中文数据集，风格覆盖可能偏向年轻、正脸、高音质样本；少量测试集（Custom仅100个视频）可能不代表真实世界分布。
- **应用安全**：生成高保真假视频可能被滥用，论文虽提到水印等缓解措施，但未具体评估其鲁棒性。

---

（完）
