---
title: "🎧MOSPA: Human Motion Generation Driven by Spatial Audio"
title_zh: 🎧MOSPA：空间音频驱动的人体运动生成
authors: "Shuyang Xu, Zhiyang Dou, Mingyi Shi, Liang Pan, Leo Ho, Jingbo Wang, Yuan Liu, Cheng Lin, Yuexin Ma, Wenping Wang, Taku Komura"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=X2r9D46kvI"
tags: ["query:wm-vla-sa"]
score: 8.0
evidence: 利用空间音频驱动人体运动生成，并构建首个空间音频-运动数据集
tldr: 本文针对空间音频驱动的人体运动生成问题，构建了首个大规模高质量空间音频-运动数据集SAM，并提出MOSPA方法。该方法能从空间音频信号中提取空间特征，生成与音频空间属性一致的人体运动。实验证明了空间特征对运动生成质量的关键作用，为虚拟人交互提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 770, \"height\": 225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1268, \"height\": 159, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1298, \"height\": 203, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1246, \"height\": 203, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1257, \"height\": 201, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1257, \"height\": 189, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 626, \"height\": 327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 782, \"height\": 460, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 204, \"height\": 239, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 823, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1338, \"height\": 1212, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 657, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1165, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-x2r9d46kvi/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1343, \"height\": 375, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-x2r9d46kvi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x2r9d46kvi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1209, \"height\": 404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x2r9d46kvi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1350, \"height\": 445, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-x2r9d46kvi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 954, \"height\": 227, \"label\": \"Table\"}]"
motivation: 现有研究忽略空间音频对运动的影响，缺乏空间音频-运动数据集和方法。
method: 构建SAM数据集，设计从空间音频提取空间特征并生成运动的模型。
result: MOSPA生成的运动在空间响应上明显优于忽略空间音频的基线方法。
conclusion: 空间音频是驱动虚拟人运动的重要模态，该工作填补了相关空白。
---

## Abstract
Enabling virtual humans to dynamically and realistically respond to diverse auditory stimuli remains a key challenge in character animation, demanding the integration of perceptual modeling and motion synthesis. Despite its significance, this task remains largely unexplored. Most previous works have primarily focused on mapping modalities like speech, audio, and music to generate human motion. As of yet, these models typically overlook the impact of spatial features encoded in spatial audio signals on human motion. To bridge this gap and enable high-quality modeling of human movements in response to spatial audio, we introduce the first comprehensive "Spatial Audio-Driven Human Motion" (SAM) dataset, which contains diverse and high-quality spatial audio and motion data. For benchmarking, we develop a simple yet effective diffusion-based generative framework for human "MOtion generation driven by SPatial Audio," termed MOSPA, which faithfully captures the relationship between body motion and spatial audio through an effective fusion mechanism. Once trained, MOSPA can generate diverse realistic human motions conditioned on varying spatial audio inputs. We perform a thorough investigation of the proposed dataset and conduct extensive experiments for benchmarking, where our method achieves state-of-the-art performance on this task. Our code and model are publicly available at https://github.com/xsy27/Mospa-Acoustic-driven-Motion-Generation.git

---

## 论文详细总结（自动生成）

## 论文中文总结

### 1. 核心问题与整体含义（研究动机和背景）

**研究动机**：  
使虚拟人能够根据环境中的听觉刺激动态、逼真地做出反应是角色动画中的一个关键挑战，涉及感知建模与运动合成。然而，现有工作大多聚焦于语音、音乐或一般音频驱动的人体运动生成，忽略了**空间音频**中蕴含的空间特征（如声源方向、距离、强度变化）对人体运动的显著影响。例如，尖锐声音使人远离声源，柔和声音可能吸引人靠近。这种空间音频驱动的运动生成任务目前尚属空白。

**整体含义**：  
本文旨在填补该空白，首次提出**空间音频驱动的人体运动生成**任务，并构建了第一个大规模、高质量的**空间音频-运动数据集（SAM）**，以及一个基于扩散模型的生成框架**MOSPA**，以捕捉身体运动与空间音频之间的复杂关系，生成与音频语义和空间属性一致的人体运动。

---

### 2. 方法论：核心思想、关键技术细节

**核心思想**：  
将空间音频（双耳音频）作为条件输入，利用扩散模型生成与音频的空间特征（方向、强度、时间动态）相匹配的人体运动。通过提取丰富的空间音频特征（MFCC、tempogram、RMS能量等），并结合声源位置（SSL）和动作类型（genre）作为条件，指导去噪过程。

**关键技术细节**：

- **音频特征提取**：使用Librosa提取每只耳朵的MFCC、MFCC delta、恒Q色度图、STFT色度图、起始强度、节奏图、节拍，以及RMS能量和活动帧。左右耳特征拼接得到2272维特征向量 `a`。
- **运动表示**：采用SMPL-X模型的25个身体关节（排除手指），每个运动序列 `T=240` 帧（30 FPS，8秒），包含全局位置、局部旋转（6d表示）和关节速度，共300维向量。
- **扩散模型**：采用编码器-Transformer架构，直接预测干净运动样本 `ˆx0`。条件包括音频特征 `a`、声源位置 `s`、动作类型 `g` 和时间步 `t`。所有条件与噪声运动拼接为 token 序列，输入Transformer。
- **损失函数**：  
  - 数据损失：MSE（预测与真实运动向量 + 帧间变化率）  
  - 几何损失：正向运动学计算的位置和速度的MSE  
  - 足部接触损失：足关节速度不一致性惩罚  
  - 轨迹损失和旋转损失（额外加权，加速收敛）  
  - 总损失为各项加权和，后5000个epoch增大轨迹和旋转权重。

**算法流程**（文字说明）：
1. 前向扩散：对干净运动 `x0` 逐步添加高斯噪声得到 `xt`。
2. 逆向去噪：噪声运动 `xt` 与条件（音频特征 `a`、SSL `s`、genre `g`、时间步 `t`）一起输入Transformer，输出预测的干净运动 `ˆx0`。
3. 训练：最小化上述损失函数，优化网络参数。

---

### 3. 实验设计

**数据集**：
- **SAM数据集**：包含9小时以上人体运动与对应双耳音频，共27种常见空间音频场景、20种反应类型（含49种细分动作），12个表演者（5女7男），总帧数超过400万。每个音频片段对应16个随机声源位置，每个位置有3种反应强度（迟钝、中性、敏感），后处理为SMPL-X格式。

**基准测试**：
- 对比方法：EDGE、POPDG、LODGE、Bailando（均改编为接受空间音频特征）。
- 评价指标：
  - **R-precision**（Top1/2/3）：运动与音频的匹配准确率
  - **FID**：生成运动分布与真实运动分布的距离
  - **Diversity**：生成运动的多样性（与真实运动对比）
  - **APD**：生成运动集合中两两序列的平均欧氏距离
- 训练/验证/测试集划分：8:1:1。

**消融实验**：
- 改变潜在维度（512 vs 256）、注意力头数（8 vs 4）、扩散步数（1000 vs 100 vs 4）、是否使用动作类型（genre）条件。
- 分析MFCC和tempogram特征的影响。

**用户研究**：25名参与者，比较MOSPA与四种基线在意图对齐、运动质量、与真实运动相似度三方面的表现。

---

### 4. 资源与算力

- **GPU**：单张Nvidia RTX 4090  
- **训练时长**：约18小时（6000个epoch，batch size=128）  
- 文中未明确提及训练数据量级对应的具体显存占用，但指出该配置足够。

---

### 5. 实验数量与充分性

**实验数量**：
- 主实验：在SAM测试集上与4种基线对比，报告4个指标的均值与95%置信区间。
- 消融实验：6组（潜在维度、头数、扩散步数、genre条件、MFCC/tempogram特征）。
- 用户研究：1组（5个模型+GT，3个问题）。
- 额外测试：测试模型在分布外（out-of-distribution）音频上的表现（定性）。

**充分性与客观性**：
- 对比方法均为近年代表性工作且经过改编，保证公平。
- 所有指标均附带置信区间，统计可靠。
- 用户研究采用盲选，参与者评价。
- 消融实验覆盖关键设计选择，揭示了每个组件的贡献。

**结论**：实验设计较为充分，结果客观，支持文中声称的SOTA性能。

---

### 6. 主要结论与发现

- **MOSPA在所有定量指标上显著优于现有基线**：R-precision最高（Top1 0.937）、FID最低（7.981）、Diversity和APD最接近真实运动。
- 空间音频特征（MFCC、tempogram）对生成质量至关重要，缺少任一都会导致FID和R-precision下降。
- 动作类型（genre）条件能有效引导运动强度，缺失会降低多样性并增加FID。
- 模型对分布外音频（新场景、未见声源位置）仍保持鲁棒性，生成的运动意图一致。
- 用户研究一致偏好MOSPA，认为其运动更自然、语义更符合。

---

### 7. 优点

- **任务新颖性**：首次提出空间音频驱动的运动生成，填补了领域空白。
- **数据集价值**：SAM数据集规模大（>9小时）、多样性高（27种场景、49种动作类型、12个演员），包含精确同步的双耳音频和3D运动，并标注声源位置，为后续研究奠定基础。
- **方法有效性**：MOSPA通过精心设计的音频特征（MFCC+tempogram+RMS）和扩散模型，有效融合空间信息与运动生成，设计简洁但性能领先。
- **实验严谨性**：多指标、多基线、带置信区间的定量对比，加上用户研究和消融实验，结论可靠。
- **可复现性**：代码和模型已开源，便于复现和应用。

---

### 8. 不足与局限

- **物理正确性不足**：生成的运动可能存在不自然的地面穿透或浮空等物理伪影，未集成物理仿真约束。
- **身体建模局限**：仅考虑身体关节，忽略了SMPL-X支持的手势、面部表情等精细动作，限制了全身体交互场景。
- **场景感知缺失**：模型未考虑周围环境几何信息，无法生成与环境物体交互（如避开障碍物）的运动，场景一致性受限。
- **数据覆盖有限**：虽然SAM包含27种场景，但日常生活中的空间音频多样性远超此范围，可能影响泛化到更复杂环境。
- **音频特征依赖**：特征提取基于传统信号处理（librosa），可能无法捕捉极细微的空间线索，深度特征或端到端学习可能提升性能。
- **用户研究样本量较小**（25人），可能对统计分析敏感。

---

（完）
