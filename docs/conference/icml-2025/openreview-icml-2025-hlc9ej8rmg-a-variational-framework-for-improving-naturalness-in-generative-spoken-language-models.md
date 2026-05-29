---
title: A Variational Framework for Improving Naturalness in Generative Spoken Language Models
title_zh: 改进生成式口语模型自然度的变分框架
authors: "Li-Wei Chen, Takuya Higuchi, Zakaria Aldeneh, Ahmed Hussen Abdelaziz, Alexander Rudnicky"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=HLC9eJ8RMg"
tags: ["query:speech-model"]
score: 9.0
evidence: 变分框架提升生成式口语模型自然度，处理韵律和副语言特征
tldr: 该论文提出端到端变分框架，通过潜在变量模型自动学习语音中的韵律和副语言信息，无需手工特征工程，从而显著提升生成口语的自然度，解决了现有语义令牌丢失韵律信息导致自然度下降的问题。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-hlc9ej8rmg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1761, \"height\": 668, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hlc9ej8rmg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1713, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hlc9ej8rmg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1714, \"height\": 65, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hlc9ej8rmg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 618, \"height\": 61, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hlc9ej8rmg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1706, \"height\": 68, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-hlc9ej8rmg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 821, \"height\": 357, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlc9ej8rmg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1435, \"height\": 356, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlc9ej8rmg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1475, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlc9ej8rmg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1542, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlc9ej8rmg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 805, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlc9ej8rmg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1134, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlc9ej8rmg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1107, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlc9ej8rmg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1147, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlc9ej8rmg/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1007, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hlc9ej8rmg/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1017, \"height\": 279, \"label\": \"Table\"}]"
motivation: 现有语义令牌丢失韵律信息，导致语音生成不自然。
method: 提出端到端变分框架，自动学习语音中的多样化副语言属性。
result: 生成的语音自然度显著优于先前方法。
conclusion: 为生成式语音模型提供了更全面的表现力建模方法。
---

## Abstract
The success of large language models in text processing has inspired their adaptation to speech modeling.
However, since speech is continuous and complex, it is often discretized for autoregressive modeling.
Speech tokens derived from self-supervised models (known as semantic tokens) typically focus on the linguistic aspects of speech but neglect prosodic information.
As a result, models trained on these tokens can generate speech with reduced naturalness.
Existing approaches try to fix this by adding pitch features to the semantic tokens.
However, pitch alone cannot fully represent the range of paralinguistic attributes, and selecting the right features requires careful hand-engineering.
To overcome this, we propose an end-to-end variational approach that automatically learns to encode these continuous speech attributes to enhance the semantic tokens.
Our approach eliminates the need for manual extraction and selection of paralinguistic features.
Moreover, it produces preferred speech continuations according to human raters.
Code, samples and models are available at https://github.com/b04901014/vae-gslm.

---

## 论文详细总结（自动生成）

# 详细中文总结：改进生成式口语模型自然度的变分框架

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **问题**：现有生成式口语语言模型（如 GSLM）通常使用自监督模型（如 HuBERT）提取“语义令牌”进行自回归建模。这些令牌主要捕捉语音中的语言内容（如音素），但忽略了韵律、情感、响度等副语言信息，导致生成的语音**自然度不足**。
- **现有尝试的局限**：Kharitonov 等（2022）通过手工提取基频（pitch）特征来补充语义令牌，但仅靠 pitch 无法覆盖全部副语言属性，且特征选择依赖手工工程，存在子最优问题。
- **本文目标**：提出一种**端到端变分框架**，自动学习语音中连续的副语言属性（称为“变分特征”），用以增强语义令牌，从而提升生成语音的自然度，同时避免手工特征工程。

## 2. 论文提出的方法论
### 核心思想
- 结合变分自编码器（VAE）与自回归模型，学习一组连续的潜变量 Zc（变分特征），作为离散语义令牌 Zd 的补充。
- 变分特征通过 VAE 编码器从原始语音中提取，并同时被优化以：（1）辅助解码器重构语音；（2）易于被自回归模型预测；（3）帮助预测下一个语义令牌。
- 整体目标为最大化变分下界（ELBO），包含三项损失：重构损失、变分特征预测损失、语义令牌预测损失，通过超参数 β 和 γ 平衡。

### 关键技术细节
- **模型架构**：
  - 输入：mel谱图 X。
  - 语音分词器（固定）：将 X 映射为离散语义令牌序列 Zd（来自 HuBERT + k-means）。
  - 变分编码器 φ：输出高斯分布参数（μ, σ），采样得到连续变分特征 Zc = (zᶜ₁,...,zᶜ_T)，维度 dcz。
  - 自回归模型 ψ：预测下一个 zᶜ_t 和 zᵈ_t，基于过去的 Zc 和 Zd。使用 Transformer 架构。
  - 解码器 θ：条件扩散模型（DDPM），根据 Zc 和 Zd 重构 mel 谱图。
  - 时序正则化流：使用仿射耦合层（affine coupling layers）增强自回归先验的表达力。
  - 话语编码器：从随机片段中提取话语级嵌入，捕获说话人、环境等静态信息。

- **损失函数**（公式 5）：
  \[
  \mathcal{O}_{\text{ELBO}} = \mathcal{O}_{\text{rec}} - \beta (\mathcal{L}_{\text{ckl}} + \gamma \cdot \mathcal{L}_{\text{dkl}})
  \]
  - \(\mathcal{O}_{\text{rec}}\)：重构损失（扩散 L1 损失）。
  - \(\mathcal{L}_{\text{ckl}}\)：变分特征预测的 KL 散度。
  - \(\mathcal{L}_{\text{dkl}}\)：语义令牌交叉熵损失。
- **训练策略**：β 从 0 线性预热到目标值，防止后验崩塌。

## 3. 实验设计
### 数据集
- **训练**：LibriSpeech（960 小时英文有声书）和 Libri-light（60,000 小时）。
- **评估**：LibriSpeech dev-clean 和 dev-other 用于重建和继续生成。
- **语义令牌**：HuBERT 最后一层特征 + k-means（k=200）。另测试 SpeechTokenizer 第一级 RVQ 令牌。

### 对比方法
- **Token-LM**：仅使用语义令牌的自回归模型（类似 Lakhotia et al. 2021）。
- **Token-LM + Pitch**：在令牌基础上拼接手工提取的 log-pitch 特征（使用 CREPE），并增加 pitch 回归任务。
- **Token-LM + Acoustic**：使用声学令牌（4 级 RVQ）作为额外输入，类似 Défossez et al. 2024。
- **Proposed**：本文提出的变分框架。

### 评估指标
- **客观**：
  - 重构质量：F0-RMSE（pitch 误差）、MCD（mel-cepstral 失真）、CER（字符错误率）。
  - 语言能力：sWUGGY（单词级别）、sBLIMP（语法级别）。
- **主观**：平均意见评分（MOS）——自然度（N-MOS）和有意义度（M-MOS），由 7 位标注者评分，100 个 3 秒提示生成 10 秒延续。

## 4. 资源与算力
- **Libri-light 模型**：使用 2 块 L40S GPU，梯度累积步长 2，有效 batch size 192，训练 600k 步，约 **14 天**。
- **LibriSpeech 模型**：类似配置（2 块 L40S），无梯度累积，训练 100k~400k 步，约 **2 天**。
- **其他**：混合精度训练，AdamW 优化器，初始学习率 5e-4。

## 5. 实验数量与充分性
- **主要对比**：表 1（重构）和表 2（继续生成）展示了三种基线方法与本文方法的客观/主观结果。
- **消融实验**：
  - 超参数 β 和 γ 的影响（表 3、表 4）。
  - 移除语义令牌（仅用 Zc）（表 3）。
  - 变分特征维度 dcz 的选择（表 7）。
  - 不同语义令牌（SpeechTokenizer）（表 5）。
  - 语义令牌词汇量 k 的选择（表 8）。
- **额外分析**：副语言能力检测——情感识别（EmoV-DB）和说话人识别（VCTK）（表 9、表 10）。
- **充分性评价**：实验设计较全面，覆盖客观和主观评估，对比方法代表当前主流，消融实验验证了关键设计。主观评估采用 7 位标注者，有一定可靠性，但样本量（100 条）中等。

## 6. 论文的主要结论与发现
- **自然度显著提升**：本文方法在 N-MOS 上达到 **3.60**，远超 Token-LM（3.19）、Token-LM+Pitch（3.08）、Token-LM+Acoustic（3.03），接近真实语音（3.89）。
- **有意义度保持**：M-MOS（3.45）高于基线，尽管 sWUGGY/sBLIMP 略低于 Token-LM，但人类标注者认为本文生成语音更易理解（自然韵律改善可懂度）。
- **重构质量**：本文优于 Token-LM 和 Token-LM+Pitch，但低于 Token-LM+Acoustic（因变分特征受自回归损失正则化）。
- **超参数作用**：β 控制变分特征编码信息量（低 β → 更丰富，但自回归更难）；γ 控制信息类型（高 γ → 侧重语义，低 γ → 侧重韵律）。
- **无需手工特征**：自动学习到的变分特征能有效捕获情感（情感识别准确率 91.6% vs. 令牌仅 57.5%）和韵律信息。

## 7. 优点
- **端到端学习副语言特征**：省去手工特征工程，自动适应不同语音属性。
- **灵活可扩展**：不依赖特定分词器或解码器（可替换为 SpeechTokenizer + RVQ 解码）。
- **自然度改善显著**：主观评分明显高于所有基线，且足以与真实语音竞争。
- **对语言内容影响小**：相比直接加声学令牌，本文方法在保持语言能力（sWUGGY/sBLIMP 下降较小）的同时大幅提升自然度。
- **分析全面**：不仅评估合成质量，还通过情感/说话人任务验证了学到特征的有效性。

## 8. 不足与局限
- **超参数敏感**：β 和 γ 需要仔细调优，未探索自动调节方法。
- **语言泛化性未知**：仅测试英语，未验证其他语言（如韵律差异大的语言）。
- **模型规模较小**：仅 221M 参数，训练数据为 Libri-light（6 万小时），与商业模型（百亿参数、数百万小时）有差距，结论可扩展性需验证。
- **主观评估范围有限**：100 条提示，7 位标注者，统计显著性可接受但样本量不大；未包含更细粒度的感知任务（如自然度-韵律分离）。
- **计算资源需求**：Libri-light 模型需要 14 天 2×L40S，对资源有限的研究组不友好。
- **未解决端到端问题**：仍依赖外部神经声码器（HiFi-GAN），生成流程未完全统一。

（完）
