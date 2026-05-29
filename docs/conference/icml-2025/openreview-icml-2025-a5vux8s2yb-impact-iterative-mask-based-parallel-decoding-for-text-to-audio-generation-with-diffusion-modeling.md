---
title: "IMPACT: Iterative Mask-based Parallel Decoding for Text-to-Audio Generation with Diffusion Modeling"
title_zh: IMPACT：基于迭代掩码并行解码的文本到音频生成
authors: "Kuan-Po Huang, Shu-wen Yang, HUY PHAN, Bo-Ru Lu, Byeonggeun Kim, Sashank Macha, Qingming Tang, Shalini Ghosh, Hung-yi Lee, Chieh-Chi Kao, Chao Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=A5vUx8S2yB"
tags: ["query:speech-model"]
score: 6.0
evidence: 基于迭代掩码的并行解码用于文本到音频生成
tldr: 该论文提出IMPACT，一个结合扩散模型高质量和掩码模型快速推理的文本到音频生成框架。利用迭代掩码并行解码，在保持音频质量的同时大幅降低推理延迟。实验表明在音质和速度上均优于现有方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-a5vux8s2yb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1753, \"height\": 688, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5vux8s2yb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1735, \"height\": 1294, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5vux8s2yb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 835, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5vux8s2yb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1763, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5vux8s2yb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1084, \"height\": 818, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5vux8s2yb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1007, \"height\": 512, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5vux8s2yb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 898, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5vux8s2yb/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 908, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5vux8s2yb/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 909, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-a5vux8s2yb/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 448, \"height\": 120, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-a5vux8s2yb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1702, \"height\": 788, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5vux8s2yb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1691, \"height\": 409, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5vux8s2yb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 797, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5vux8s2yb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 788, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5vux8s2yb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 813, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5vux8s2yb/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 859, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5vux8s2yb/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 728, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5vux8s2yb/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1479, \"height\": 727, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-a5vux8s2yb/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1663, \"height\": 715, \"label\": \"Table\"}]"
motivation: 扩散模型推理慢，掩码模型质量差，需折中。
method: 融合扩散建模和迭代掩码并行解码。
result: 在音频质量和推理速度上实现双赢。
conclusion: 混合框架可有效平衡生成质量和效率。
---

## Abstract
Text-to-audio generation synthesizes realistic sounds or music given a natural language prompt. Diffusion-based frameworks, including the Tango and the AudioLDM series, represent the state-of-the-art in text-to-audio generation. Despite achieving high audio fidelity, they incur significant inference latency due to the slow diffusion sampling process. MAGNET, a mask-based model operating on discrete tokens, addresses slow inference through iterative mask-based parallel decoding. However, its audio quality still lags behind that of diffusion-based models. In this work, we introduce IMPACT, a text-to-audio generation framework that achieves high performance in audio quality and fidelity while ensuring fast inference. IMPACT utilizes iterative mask-based parallel decoding in a continuous latent space powered by diffusion modeling. This approach eliminates the fidelity constraints of discrete tokens while maintaining competitive inference speed. Results on AudioCaps demonstrate that IMPACT achieves state-of-the-art performance on key metrics including Fréchet Distance (FD) and Fréchet Audio Distance (FAD) while significantly reducing latency compared to prior models. The project website is available at https://audio-impact.github.io/.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **任务背景**：文本到音频生成任务旨在根据自然语言提示合成逼真的声音或音乐，在音频内容创作、视频游戏、营销广告等领域有广泛应用前景。
- **现有方法瓶颈**：
  - **扩散模型**（如 Tango、AudioLDM 系列）能生成高保真音频，但推理延迟很大，因为需要多步扩散采样，且模型架构中包含计算量大的注意力层。
  - **掩码生成模型**（如 MAGNET）在离散音频 token 上使用迭代掩码并行解码，推理速度快，但音频质量仍落后于扩散模型。
- **核心问题**：如何在保持高音频质量和保真度的同时，大幅降低推理延迟？现有方法在质量与速度之间存在明显的权衡。

## 2. 方法论：核心思想、关键技术细节、公式/算法流程

### 2.1 核心思想
- **混合框架**：将**迭代掩码并行解码**（来自掩码生成模型）与**潜在扩散模型**（LDM）相结合，在连续潜在空间中操作，既保留 LDM 的高保真能力，又利用并行解码加速推理。
- **关键设计**：用轻量级 MLP 扩散头替代传统 LDM 中沉重的注意力层，避免扩散采样循环中的高计算开销。

### 2.2 训练阶段
#### 无条件预训练
- **目的**：首先在不使用文本条件下训练模型学会重建部分掩码的音频潜在表示。利用大规模无标签音频数据（如 AudioSet）学习音频生成基础。
- **方式**：与条件训练类似但移除文本条件向量，模型只根据未掩码的潜在表示预测被掩码位置。

#### 文本条件训练
- **输入处理**：
  - 音频经 VAE 编码为潜在序列 \( z = [z_1, ..., z_N] \)，长度为 N。
  - 随机生成二进制掩码 \( M \in \{0,1\}^N \)，掩码比例 \( q = 0.7 \)，即 \( q \cdot N \) 个位置被掩码。
  - 文本条件 \( c \)（由 CLAP 和 Flan-T5 嵌入拼接而成，长度 L=78）与未掩码的音频潜在 \( z \odot \bar{M} \) 拼接，送入 Transformer 编码器 \( Enc_{\phi} \) 得到隐藏表示 \( h \in \mathbb{R}^{(L+N)\times D} \)。
- **扩散头预测**：
  - 对被掩码的位置，添加噪声：\( \hat{z}_t^i = \sqrt{\bar{\alpha}_t} z_i + \sqrt{1-\bar{\alpha}_t} \epsilon \)，其中 \( \epsilon \sim \mathcal{N}(0,I) \)，\( \bar{\alpha}_t \) 为噪声调度，\( t \) 为扩散步（最大 1000）。
  - 轻量 MLP 扩散头 \( \epsilon_{\theta} \) 以 \( h_i \) 为条件，预测噪声 \( \epsilon \)，训练目标为均方误差：
    \[
    \arg\min_{\{\phi,\theta\}} \sum_{\{i|M[i]=1\}} \left\| \epsilon - \epsilon_{\theta}(\hat{z}_t^i | t, h_i) \right\|^2
    \]
- **编码器结构**：采用 MAE 风格的双编码器，先丢弃掩码位置以减少计算，再插入掩码嵌入后经第二个编码器得到完整 \( h \)。

### 2.3 推理阶段（迭代掩码并行解码）
- **初始化**：从完全空的序列 \( z^{(0)} \) 和全掩码 \( M^{(0)} = [1,...,1] \) 开始。
- **每步迭代步骤**：
  1. **随机位置选择**：由于连续表示无法计算置信度，随机选择当前掩码位置的一个子集作为本次预测位置 \( M_{\text{pred}}^{(t)} \)。
  2. **掩码调度**：根据余弦调度 \( \gamma(t) = \cos(\frac{\pi}{2} \cdot \frac{t}{T}) \) 计算剩余掩码数量，确保早期预测较少（因上下文不足），后期预测更多。
  3. **扩散采样**：对每个预测位置，使用轻量扩散头进行逆向扩散采样（式 (3)），一次性并行生成该位置所有潜在。
- **分类器自由引导（CFG）**：在每步扩散采样中，将无条件噪声预测 \( \epsilon_{\text{uncond}} \) 与有条件预测 \( \epsilon_{\text{cond}} \) 按可调度系数 \( \beta_{\text{cfg}}^{(t)} \) 融合，以平衡文本相关性和音频保真度。
- **默认配置**：总解码迭代 \( T=64 \)（可调），扩散步数 100（最佳），最大 CFG 缩放 5.0。

## 3. 实验设计

### 3.1 数据集
- **无标签预训练数据**：AudioSet (AS)，约 5500 小时音频，无文本描述。
- **文本条件训练数据**：
  - 主要实验：AudioCaps (AC, 145h) + WavCaps (WC)，总计约 1200 小时。
  - 消融实验：仅用 AC (145h) 进行条件训练。
- **评估基准**：AudioCaps 测试集，每个音频有 5 个文本描述，随机选一个作为条件。
- **预处理**：每段音频截取 10 秒，提取梅尔频谱。

### 3.2 对比方法
- **公开可推理模型**：AudioGen v2, Tango, Tango-full-ft, Tango-AF&AC-FT-AC, Tango 2, EzAudio-L/X, MAGNET-S/L, Make-an-Audio 2, AudioLDM2-full/large。
- **非公开模型**：AudioLDM2-AC-large（结果从原文引用）。

### 3.3 评估指标
- **客观指标**：FD, FAD, KL 散度, Inception Score (IS), CLAP 分数（使用不同模型避免偏袒）。
- **主观指标**：文本相关性 (REL) 和整体质量 (OVL)，1-5 分制，每样本至少 10 人评分，30 个样本。
- **推理速度**：在单张 Tesla V100 32GB GPU 上测量生成批量音频的延迟（秒）。

## 4. 资源与算力
- 论文未明确说明训练所需 GPU 数量、训练总时长等具体算力信息。
- 推理时使用的硬件为**单张 Tesla V100 32GB GPU**（用于延迟测量）。
- 训练数据规模：最高 5500 小时无标签 + 1200 小时有标签音频。
- 模型参数量：Base 约 193M，Large 约 427M（Transformer 编码器部分分别 24/32 层，嵌入维度 768/1024；扩散头相同，轻量 MLP）。

## 5. 实验数量与充分性
- **系统级对比（表1）**：与 9 种以上公开/非公开模型在 5 个客观指标 + 2 个主观指标 + 延迟上全面比较。
- **消融实验**：
  - **无条件预训练**（表2）：对比无预训练 vs 1200h vs 5500h 预训练，证明其必要性。
  - **文本条件训练数据量**（表2）：对比 145h vs 1200h，显示数据量增大提升指标。
  - **CLAP 模块移除**（表3）：证明去除 CLAP 嵌入后性能几乎不变，鲁棒性强。
  - **单次解码 vs 迭代解码**（表4）：32 次迭代远超单次。
  - **扩散步数**（表5）：50/100/150/200 步对比，100 步最优。
  - **解码迭代数量**（图2）：从 1 到 64 步，展示性能-延迟权衡。
  - **CFG 缩放系数**（附录表7）：1.0~5.0 的影响。
- **推理速度与吞吐量对比（图4）**：与 MAGNET-S 在不同批量下的延迟和吞吐量对比。
- **充分性**：实验设计系统、覆盖了核心模块（预训练、条件训练、迭代解码、CFG）及关键超参数。主观评估样本量（30 样本）略小但可接受。对比方法全面且尽量保持公平（对公开模型调整参数至最优）。总体实验充分、客观。

## 6. 主要结论与发现
1. **性能领先**：IMPACT 在 FD 和 FAD 上达到最佳（例如 FD 14.72，FAD 1.07~1.13），显著优于所有现有公开模型（如 Tango 2、EzAudio、MAGNET 等）。
2. **主观评价高**：REL 和 OVL 得分最高（分别为 4.39 和 3.51），超过 Tango 2 和 EzAudio-XL。
3. **推理速度极快**：Base 模型 32 次迭代 + 100 扩散步，延迟仅 11.2 秒（批大小 8），仅次于 MAGNET-S（6.9 秒），但性能远超后者。甚至 4 次迭代即可达到比 MAGNET-S 更好的客观指标。
4. **无条件预训练至关重要**：无预训练则性能显著下降；增加预训练数据量（5500h 比 1200h）进一步提升主观评分。
5. **迭代解码的优势**：单次解码性能极差，多次迭代逐步增加上下文信息显著提升所有指标。
6. **扩散步数影响**：100 步为最优折中；更多步数延迟增加但收益甚微。

## 7. 优点
- **创新性结合**：首次将迭代掩码并行解码应用于连续潜在空间联合 LDM，有效弥合质量与速度的鸿沟。
- **设计巧妙**：采用轻量 MLP 扩散头，避免推理时重复计算注意力；通过 MAE 风格编码器降低训练复杂度。
- **预训练策略**：引入无条件预训练，可利用海量未标注数据（如 AudioSet），提升生成质量和稳定性。
- **灵活的推理调节**：可通过调节解码迭代数和扩散步数灵活平衡性能与速度；CFG 调度器进一步优化文本相关性。
- **全面实验**：涵盖客观/主观指标、多对比方法、详尽的消融和参数分析，结果可信度高。
- **开源友好**：项目网站提供代码和模型，便于复现。

## 8. 不足与局限
- **算力信息缺失**：未报告训练所需的具体 GPU 数量、训练时长，不利于他人复现能耗评估。
- **主观评估样本量有限**：仅 30 个音频样本，虽常见但可能不足以完全代表整体表现。
- **CLAP 分数略低**：虽主观 REL 领先，但客观 CLAP 分数略低于 Tango 2（0.364 vs 0.375），可能与 DPO 微调方法有关，但论文未深入讨论原因。
- **依赖预训练权重**：Transformer 编码器需从 MAR 预训练权重初始化，否则性能差，增加了使用门槛。
- **音频长度固定**：均为 10 秒，未探索更长或可变长度生成。
- **可控性有限**：缺乏细粒度控制（如音频事件的时序、音量等），仅依赖于文本条件。
- **潜在偏差**：训练数据主要来自 AudioCaps、WavCaps、AudioSet，可能偏向特定场景（如环境音、乐器），对工业级或对话式音频生成覆盖不足。

（完）
