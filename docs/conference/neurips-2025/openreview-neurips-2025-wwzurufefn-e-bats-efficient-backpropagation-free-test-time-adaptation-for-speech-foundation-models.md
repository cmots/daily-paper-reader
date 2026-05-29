---
title: "E-BATS: Efficient Backpropagation-Free Test-Time Adaptation for Speech Foundation Models"
title_zh: E-BATS：语音基础模型的高效无反向传播测试时自适应
authors: "Jiaheng Dong, Hong Jia, Soumyajit Chatterjee, Abhirup Ghosh, James Bailey, Ting Dang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=WwzurufeFN"
tags: ["query:speech-model"]
score: 6.0
evidence: 语音基础模型的测试时自适应
tldr: 针对语音基础模型在噪声和口音等声学域偏移下性能下降的问题，提出E-BATS高效无反向传播测试时自适应方法。该方法针对语音任务的特点设计，避免了传统反向传播的高内存开销，同时保持了高精度。实验表明，E-BATS在多种域偏移场景中均能有效恢复模型性能，且计算成本远低于现有方法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-wwzurufefn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 593, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wwzurufefn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1431, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wwzurufefn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 729, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wwzurufefn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 555, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wwzurufefn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 548, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-wwzurufefn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1010, \"height\": 744, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-wwzurufefn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1457, \"height\": 748, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wwzurufefn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1456, \"height\": 749, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wwzurufefn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1454, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wwzurufefn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1427, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wwzurufefn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1429, \"height\": 612, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wwzurufefn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1452, \"height\": 952, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wwzurufefn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1452, \"height\": 949, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wwzurufefn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1454, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wwzurufefn/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 962, \"height\": 137, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wwzurufefn/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1217, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wwzurufefn/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1367, \"height\": 140, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wwzurufefn/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1361, \"height\": 142, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wwzurufefn/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1454, \"height\": 259, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wwzurufefn/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1386, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wwzurufefn/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1212, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wwzurufefn/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1283, \"height\": 140, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-wwzurufefn/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 888, \"height\": 221, \"label\": \"Table\"}]"
motivation: 语音基础模型在声学域偏移下性能下降，现有TTA方法计算开销大或精度低。
method: 提出无反向传播的测试时自适应方法，专为语音模型设计，兼顾效率与精度。
result: 在多种语音域偏移场景下保持了高精度且计算开销极小。
conclusion: 为语音模型在现实场景中的自适应部署提供了实用方案。
---

## Abstract
Speech Foundation Models encounter significant performance degradation when deployed in real-world scenarios involving acoustic domain shifts, such as background noise and speaker accents. Test-time adaptation (TTA) has recently emerged as a viable strategy to address such domain shifts at inference time without requiring access to source data or labels. However, existing TTA approaches, particularly those relying on backpropagation, are memory-intensive, limiting their applicability in speech tasks and resource-constrained settings. Although backpropagation-free methods offer improved efficiency, existing ones exhibit poor accuracy. This is because they are predominantly developed for vision tasks, which fundamentally differ from speech task formulations, noise characteristics, and model architecture, posing unique transferability challenges.
In this paper, we introduce E-BAT, first Efficient BAckpropagation-free TTA framework designed explicitly for speech foundation models. E-BAT achieves a balance between adaptation effectiveness and memory efficiency through three key components: (i) lightweight prompt adaptation for a forward-pass-based feature alignment, (ii) a multi-scale loss to capture both global (utterance-level) and local distribution shifts (token-level) and (iii) a test-time exponential moving average mechanism for stable adaptation across utterances. Experiments conducted on four noisy speech datasets spanning sixteen acoustic conditions demonstrate consistent improvements, with 4.1\%--13.5% accuracy gains over backpropogation-free baselines and 2.0$\times$–6.4$\times$ GPU memory savings compared to backpropogation-based methods. By enabling scalable and robust adaptation under acoustic variability, this work paves the way for developing more efficient adaptation approaches for practical speech processing systems in real-world environments.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：语音基础模型（Speech Foundation Models, SFMs）在真实部署中会面临声学域偏移（如背景噪声、说话人口音、麦克风差异），导致性能显著下降。尽管测试时自适应（TTA）是一种无需源数据或标签的可行策略，但现有基于反向传播的 TTA 方法内存占用极大，限制了在资源受限设备上的应用；而现有的无反向传播方法主要针对视觉任务设计，在语音任务上精度较差，因为语音任务的模型架构（CNN+Transformer 顺序流水线）、序列到序列映射、单 utterance 处理等特性与视觉任务有根本不同。
- **整体含义**：论文首次提出专为语音基础模型设计的无反向传播测试时自适应框架 E-BATS，旨在平衡自适应效果与内存效率，从而在现实声学变化中实现可扩展且鲁棒的适应。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：通过轻量级 prompt 调优、多尺度损失函数和测试时指数移动平均（T-EMA），仅利用前向传播（无反向传播）完成域偏移的自适应。
- **关键技术细节**：
  - **Lightweight Prompt Adaptation (LPA)**：
    - 分析源域与目标域潜在特征分布的偏移，发现均值偏移远大于协方差偏移（可达 7.8 倍），因此假设可以通过简单的几何平移操作对齐特征。
    - 在 CNN 特征编码器输出的潜在表示 Z_t 上添加可学习 prompt 向量 s_t：$\hat{Z}_t = Z_t + s_t \cdot \mathbf{1}^\top_N$。
    - 使用无导数优化算法 CMA-ES 采样 J 个候选 prompt，依据损失函数排序并迭代更新分布参数（均值 m_t、协方差 C_t、步长 σ_t）。
  - **Multi-scale Loss Function**：
    - **熵最小化损失（L_ent）**：对非空白帧（剔除空白符 ∅ 预测）计算 Shannon 熵。
    - **Utterance-level 对齐损失（L_utt）**：计算源域（预收集）与目标域 utterance 级特征质心的平方欧氏距离，平均所有 transformer 层。
    - **Token-level 对齐损失（L_token）**：对每个 token 类 v，计算源域与目标域在每层的均值差平方和与标准差差平方和，并引入自适应置信系数 c（基于 L_ent 和 L_utt 的归一化值），降低不可靠伪标签的影响。
    - 总损失：$L_{adapt} = \alpha L_{ent} + \beta L_{utt} + c L_{token}$。
  - **Test-time Exponential Moving Average (T-EMA)**：
    - 跨 utterance 平滑 CMA-ES 统计参数（均值、协方差、步长），避免过拟合和模型漂移。
    - 更新公式：$m_{ema} = \gamma m_{ema} + (1 - \gamma) m_t^{(K)}$，γ ∈ [0,1)，用于初始化下个 utterance 的搜索分布。
- **算法流程**（文字说明）：
  - 对每个测试 utterance X_t，从 CMA-ES 分布中采样 J 个 prompt 候选。
  - 并行注入 prompt 到 CNN 特征，前向传播计算多尺度损失。
  - 根据损失排序，更新 CMA-ES 参数，迭代 K 次直到收敛。
  - 选择最优 prompt 进行最终解码。
  - 使用 T-EMA 更新全局统计量，用于下一个 utterance。

## 3. 实验设计：数据集、场景、benchmark、对比方法
- **数据集与场景**（16 种声学条件）：
  - **合成噪声**：LibriSpeech test-other 添加高斯噪声（σ ∈ {0.0, 0.005, 0.01, 0.015, 0.02}）。
  - **单域偏移**：CHiME-3 数据集，包含 4 种真实/模拟环境（公交、咖啡馆、人行道、街角）。
  - **多域动态流**：CHiME-3-Mix（拼接各环境模拟非平稳变化）。
  - **真实多样偏移**：CommonVoice（口音、设备差异）、TEDLIUM-v2（演讲风格、句法结构）。
- **Benchmark**：以 Word Error Rate (WER) 为评价指标。
- **对比方法**（13 种 SOTA TTA）：
  - **基于反向传播（BP）**：TENT、EATA、SAR、CoTTA、SUTA、CEA、SGEM、DSUTA、CSUTA、AWMC。
  - **无反向传播（BP-free）**：T3A、LAME、FOA。
- **骨干模型**：Wav2Vec2ForCTC-Base 和 HuBERTForCTC-Large。

## 4. 资源与算力
- **明确说明**：所有实验在单张 NVIDIA A100 GPU 上完成。未提供具体训练时长或总 GPU 小时数。
- **额外信息**：论文提供了峰值 GPU 内存对比图（Figure 4），E-BATS 在 HuBERT-Large 上峰值内存约 2GB，而 BP 方法可达 6-12 GB。并给出了随 utterance 时长增加的内存增长曲线（Figure 5），E-BATS 近乎线性增长（1.1GB→1.9GB），BP 方法增速极快。

## 5. 实验数量与充分性
- **实验数量**：覆盖 4 个主要数据集（LibriSpeech 噪声、CHiME-3 单域、CHiME-3-Mix 混合域、CommonVoice + TED）共 16 种声学条件。两个骨干模型（Base 和 Large）。
- **消融实验**（Section 5.5）：
  - 验证 prompt 插入位置（CNN vs. Transformer 输入）。
  - 验证损失函数各组件（L_ent、L_utt、L_token）的贡献（含 T-EMA 和不含 T-EMA 两种场景）。
  - 验证 T-EMA 与 Reset 策略的比较。
- **敏感性分析**（Appendix C.3）：对 CMA-ES 候选数、迭代步数、损失权重 α/β、T-EMA 衰减因子 γ 进行了网格搜索。
- **额外实验**（Appendix C.8）：在语音情感识别任务（IEMOCAP）上测试，准确率从 38.8% 提升至 43.4%。
- **充分性评价**：实验设计较为全面，对比方法多，涵盖多种域偏移类型，消融和敏感性分析完整。但缺少与更多近期 BP-free 方法的对比（当前仅三个），且未在更多规模更大的 SFM（如 Whisper）上验证。

## 6. 论文的主要结论与发现
- E-BATS 在所有 BP-free 方法中取得最优 WER，在多数数据集上甚至优于 BP 方法，WER 降低 4.1%–13.5%（相对）。
- 峰值 GPU 内存相比 BP 方法减少 2.0×–6.4×，且随模型规模增大优势更明显。
- 在动态多域流（CHiME-3-Mix）和真实多样数据（CommonVoice）上均表现稳定，证明 T-EMA 有效防止灾难性遗忘和过拟合。
- 消融表明：CNN 层 prompt 优于 Transformer 层；多尺度损失相比纯熵损失显著减少空白/单字符琐碎预测；T-EMA 比完全重置或全继承更优。

## 7. 优点：方法或实验设计上的亮点
- **方法创新**：
  - 首个专为 SFM 设计的无反向传播 TTA，针对 CNN+Transformer 混合架构修改 prompt 插入位置。
  - 基于平均偏移主导的观察，设计简单的加法 prompt，降低优化难度。
  - 多尺度损失同时捕捉全局和局部分布偏移，并自适应加权 token 级损失，避免不可靠伪标签。
  - T-EMA 实现跨 utterance 的稳定演化和持续学习。
- **实验设计**：覆盖从合成到真实、从静态到动态、从单域到多域的全面声学场景；两个骨干模型验证泛化性；消融和敏感性分析详尽。
- **代码开源**：提供 GitHub 仓库，可复现。

## 8. 不足与局限
- **延迟问题**：CMA-ES 的迭代优化引入额外推理延迟，当前未充分利用 GPU 并行化，在实时性要求高的场景可能受限（论文在 Limitations 中明确提及）。
- **骨干模型范围**：仅验证了 Wav2Vec2 和 HuBERT，未涉及 Whisper 等更现代架构，通用性待验证。
- **BP-free 对比方法少**：仅比较了三个 BP-free 基线（T3A、LAME、FOA），缺少近期更先进的 BP-free TTA（如 SHOT、TTT++ 等，尽管它们主要针对视觉）。
- **隐私保护局限**：虽然源域统计量（质心、协方差）是样本无关的，但仍需在适应前预先计算并存储，可能存在隐私风险（论文已声明隐私保护，但实际部署中仍需谨慎）。
- **实验覆盖偏重噪声和口音**：未测试其他类型域偏移（如不同采样率、压缩伪影、说话人变化等）。

（完）
