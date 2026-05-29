---
title: Shallow Flow Matching for Coarse-to-Fine Text-to-Speech Synthesis
title_zh: 浅层流匹配用于粗到细文本到语音合成
authors: "Dong Yang, YIYI CAI, Yuki Saito, Lixu Wang, Hiroshi Saruwatari"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=SoRe80Tg48"
tags: ["query:speech-model"]
score: 9.0
evidence: 基于流匹配的文本到语音合成
tldr: 现有流匹配TTS模型从纯噪声生成，计算开销大。本文提出浅层流匹配（SFM），在粗到细生成范式中从粗表示构造中间状态开始推理，聚焦后期精化阶段，显著提升计算效率。集成到多个TTS模型后，在保持高质量的同时加速了推理。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-sore80tg48/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1421, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sore80tg48/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 641, \"height\": 1012, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-sore80tg48/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sore80tg48/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 911, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sore80tg48/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1159, \"height\": 539, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sore80tg48/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1271, \"height\": 1467, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sore80tg48/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1298, \"height\": 403, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sore80tg48/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1297, \"height\": 1128, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sore80tg48/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1289, \"height\": 1120, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sore80tg48/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1289, \"height\": 1121, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sore80tg48/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1298, \"height\": 1125, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sore80tg48/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1435, \"height\": 1592, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sore80tg48/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1038, \"height\": 1633, \"label\": \"Table\"}]"
motivation: 传统流匹配TTS从纯噪声开始，计算成本高，需要更高效的生成路径。
method: 提出SFM机制，从弱生成器的粗表示中构造流路径中间状态，推理从中间状态开始。
result: 集成到多个TTS模型后，在保持音质的同时显著减少了推理步骤和计算量。
conclusion: 粗到细的流匹配策略能够有效加速TTS推理，适用于多种模型架构。
---

## Abstract
We propose Shallow Flow Matching (SFM), a novel mechanism that enhances flow matching (FM)-based text-to-speech (TTS) models within a coarse-to-fine generation paradigm. Unlike conventional FM modules, which use the coarse representations from the weak generator as conditions, SFM constructs intermediate states along the FM paths from these representations. During training, we introduce an orthogonal projection method to adaptively determine the temporal position of these states, and apply a principled construction strategy based on a single-segment piecewise flow. The SFM inference starts from the intermediate state rather than pure noise, thereby focusing computation on the latter stages of the FM paths. We integrate SFM into multiple TTS models with a lightweight SFM head. Experiments demonstrate that SFM yields consistent gains in speech naturalness across both objective and subjective evaluations, and significantly accelerates inference when using adaptive-step ODE solvers. Demo and codes are available at https://ydqmkkx.github.io/SFMDemo/.

---

## 论文详细总结（自动生成）

# Shallow Flow Matching for Coarse-to-Fine Text-to-Speech Synthesis 中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **任务**：文本到语音合成（TTS），特别是基于流匹配（Flow Matching, FM）的粗到细（coarse-to-fine）生成范式。
- **现有痛点**：传统FM模块在推理时仍从纯噪声出发，尽管弱生成器（如编码器）已提供包含大量语义和声学结构的粗表示，但早期计算阶段冗余且贡献有限，导致建模能力次优分配。
- **核心动机**：借鉴浅层扩散机制（shallow diffusion）的思想，将其扩展到流匹配中，使推理从粗表示构造的中间状态开始，跳过噪声早期阶段，聚焦于后期精化，从而提升生成质量与推理效率。

## 2. 方法论
- **核心思想**：利用弱生成器（gω）的输出粗表示，通过轻量级SFM head（hψ）预测缩放后的粗表示X̂h、时间t̂h和方差σ̂²h。训练时通过正交投影将X̂h映射到最优传输（CondOT）路径上的中间状态，并采用单段分段流（piecewise flow）仅保留后半段。推理时从该中间状态开始ODE求解。
- **关键技术细节**：
  - **正交投影**：计算投影系数th = E[sg[X̂h]·X1 / X1·X1] 和方差σ²h，再通过缩放因子Δ = max((1-σmin)th + σh, 1)将X̂h校正到CondOT路径上。
  - **单段分段流**：根据定理2，将路径在t=th处分为两段，仅训练第二段（t ≥ th），对应损失LCFM。
  - **损失函数**：LSFM = Lcoarse + Lt + Lσ + Lμ + LCFM，其中Lcoarse是粗输出与目标MEL的L2损失，Lt/Lσ是时间/方差预测损失，Lμ是中间状态与thX1的匹配损失。
  - **推理加速**：引入超参数SFM强度α（≥1）缩放中间状态，提高信号噪声比，使自适应步ODE求解器步数减少，显著降低RTF。
- **算法流程**（以文字说明）：
  - 训练：前向生成粗表示→SFM head预测X̂h, t̂h, logσ̂²h→正交投影得到中间状态→按分段流采样t→计算CFM损失→联合优化。
  - 推理：用SFM head预测参数，乘以α缩放后构造中间状态→从该状态开始ODE积分到t=1。

## 3. 实验设计
- **数据集**：
  - 单说话人：LJ Speech。
  - 多说话人：VCTK（阅读风格）、LibriTTS（有声书风格，用于跨句子评估）。
- **基准模型（Backbone）**：
  - Matcha-TTS（U-Net FM decoder + MAS alignment）
  - StableTTS（DiT blocks + MAS alignment）
  - CosyVoice（LLM + U-Net FM decoder，使用预训练tokenizer和LLM）
  - CosyVoice-DiT（将StableTTS的DiT模块作为CosyVoice的FM decoder）
- **对比方法**：
  - 原始模型（Baseline）
  - 消融模型（Ablated）：加入粗损失和SFM head，但不应用SFM机制，仅将X̂h作为FM条件。
  - SFM-c：既应用SFM方法又使用粗MEL作为FM条件。
  - SFM-t：仅语音token作为encoder输入（消融特征融合方式）。
- **评估指标**：
  - 客观：UTMOS、UTMOSv2、Distill-MOS（取平均得PMOS）、WER（Whisper-large-v3）、SIM（WavLM-base-plus-sv）。
  - 主观：CMOS（自然度对比）、SMOS（相似度对比），招募20名英语母语者（Prolific平台，£9/小时）。

## 4. 资源与算力
- 所有训练、推理和客观评估在 **96GB Nvidia H100 GPU** 上进行，采用半精度（FP16）。
- 各模型配置（epochs, batch size, learning rate, GPU数等）详见论文表1，但 **未明确总训练时长**（如具体GPU小时数）。

## 5. 实验数量与充分性
- **实验组数**：覆盖4种主干模型×多数据集（LJ Speech, VCTK, LibriTTS），包括α搜索（从1.0到10.0，步长0.5~1.0）、消融实验（Ablated、SFM-c、SFM-t）、自适应步求解器加速评估（4种求解器×5次运行）。
- **充分性评估**：
  - 客观指标全面（伪MOS、WER、SIM），主观测试（CMOS、SMOS）统计显著标记。
  - 消融实验设计合理，对比了是否使用SFM、是否使用粗条件、不同特征融合方式。
  - α选择基于验证集PMOS，避免过拟合。
- **潜在不足**：未在更多样化场景（如噪声、多语言、低资源）验证，主观测试仅各20名听者，样本量中等。

## 6. 主要结论与发现
- SFM在所有骨干模型上 **一致提升语音自然度**（PMOS、CMOS显著优于基线/消融），在WER和SIM上部分提升但不稳定。
- 推理加速显著：使用自适应步求解器时，RTF可降低 **40%~60%**（如Matcha-TTS在LJ Speech上Heun(2)从0.401降至0.249）。
- SFM强度α通常取较小值（2.0~3.5），过大导致质量下降。
- SFM-c（同时使用粗MEL作为条件）在U-Net模型中不可用（收敛至0），在DiT模型中性能劣于纯SFM，说明粗条件可能干扰。
- CosyVoice-SFM-t（仅语音token输入）相似度显著下降，凸显早期阶段对保持说话人特征的重要性。

## 7. 优点
- **理论创新**：将浅层扩散思想首次扩展到流匹配，提出正交投影和单段分段流，理论证明连续性和可操作性。
- **通用性强**：适用于U-Net和DiT两种主流FM架构，且仅需轻量SFM head（约4层Conv1d），修改量小。
- **实验设计严谨**：多骨干、多数据集、多指标评估，包含统计显著性检验和消融实验，结果可靠。
- **实际价值**：在保证或提升生成质量的同时显著加速推理（尤其自适应步求解器），有利于实时或低延迟TTS应用。

## 8. 不足与局限
- **SFM head容量有限**：当弱生成器不稳定时可能预测不准，需更强大的中间状态构造模块。
- **语义条件缺失**：粗表示虽基于文本/语义token，但未显式作为FM条件，可能影响最终对齐。
- **特征融合简单**：在CosyVoice中直接拼接语音token、说话人嵌入和masked MEL，可能损害跨模态对齐，需更精细融合策略。
- **α调参依赖**：需在验证集上搜索最佳α，增加部署成本。
- **适用范围有限**：仅验证于TTS任务，虽声称可推广到语音增强、图像去噪等，但无实验支撑。
- **实验覆盖不足**：未在低资源、多语言、嘈杂环境等场景测试；主观测试样本量中等且限于英语母语者，存在文化偏差风险。
- **加速仅限自适应步求解器**：固定步求解器无法享受加速收益。

（完）
