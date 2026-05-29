---
title: "OTTER: A Vision-Language-Action Model with Text-Aware Visual Feature Extraction"
title_zh: OTTER：具有文本感知视觉特征提取的视觉-语言-动作模型
authors: "Huang Huang, Fangchen Liu, Letian Fu, Tingfan Wu, Mustafa Mukadam, Jitendra Malik, Ken Goldberg, Pieter Abbeel"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=UHF0km7R5M"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 面向机器人学的VLA模型，具有文本感知视觉特征提取
tldr: 现有VLA模型微调预训练视觉语言模型时破坏语义对齐。本文提出OTTER，通过文本感知的视觉特征提取，只传递与语言指令相关的视觉特征给策略Transformer，从而冻结编码器。在多个机器人操作任务中，OTTER优于基准方法，且无需微调视觉语言编码器。OTTER为VLA模型提供了一种高效的特征提取范式。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-uhf0km7r5m/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 836, \"height\": 670, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uhf0km7r5m/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 798, \"height\": 700, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uhf0km7r5m/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 808, \"height\": 611, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uhf0km7r5m/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 828, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uhf0km7r5m/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 773, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uhf0km7r5m/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1603, \"height\": 920, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-uhf0km7r5m/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1751, \"height\": 492, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-uhf0km7r5m/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 862, \"height\": 513, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uhf0km7r5m/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1412, \"height\": 474, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uhf0km7r5m/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1582, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uhf0km7r5m/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 881, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uhf0km7r5m/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1106, \"height\": 536, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uhf0km7r5m/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1414, \"height\": 935, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uhf0km7r5m/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 998, \"height\": 836, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uhf0km7r5m/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 695, \"height\": 665, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-uhf0km7r5m/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1087, \"height\": 147, \"label\": \"Table\"}]"
motivation: 现有VLA模型独立处理视觉和语言特征，损害了预训练的语义对齐。
method: 提出文本感知视觉特征提取，选择性传递与指令语义对齐的特征。
result: 在多个机器人操作任务中，OTTER优于基准方法，且无需微调视觉语言编码器。
conclusion: OTTER为VLA模型提供了一种高效的特征提取范式。
---

## Abstract
Vision-Language-Action (VLA) models aim to predict robotic actions based on visual observations and language instructions. Existing approaches require fine-tuning pre-trained vision-language models (VLMs) as visual and language features are independently fed into downstream policies, degrading the pre-trained semantic alignments. We propose OTTER, a novel VLA architecture that leverages these existing alignments through explicit, text-aware visual feature extraction. Instead of processing all visual features, OTTER selectively extracts and passes only task-relevant visual features that are semantically aligned with the language instruction to the policy transformer. This allows OTTER to keep the pre-trained vision-language encoders frozen. Thereby, OTTER preserves and utilizes the rich semantic understanding learned from large-scale pre-training, enabling strong zero-shot generalization capabilities. In simulation and real-world experiments, OTTER significantly outperforms existing VLA models, demonstrating strong zero-shot generalization to novel objects and environments. Video, code, checkpoints, and dataset: https://ottervla.github.io/.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：现有的视觉-语言-动作（VLA）模型通常独立提取视觉和语言特征，然后直接馈入策略网络，这要求策略网络从零开始学习视觉与语言的关联。由于机器人数据集在语义多样性上远不如大规模视觉-语言预训练数据，微调预训练视觉-语言模型（VLM）会破坏其已学到的语义对齐，导致在未见物体/环境上的泛化能力大幅下降。
- **动机**：作者观察到，预训练的VLM（如CLIP）本身已具备强大的零样本视觉-语言对齐能力。因此，更有效的策略应当是**保留并利用**这种预训练对齐，而非通过微调削弱它。

## 2. 方法论：核心思想、技术细节
- **核心思想**：OTTER提出**文本感知的视觉特征提取（Text-Aware Visual Feature Extraction）**：在冻结预训练CLIP编码器的前提下，根据语言指令动态选择与之语义对齐的视觉补丁特征，仅将这些任务相关的视觉特征传递给下游策略网络。
- **关键技术细节**：
  - 使用CLIP的**注意力输出特征** \(X_{\text{attn}}\)（而非最终输出 \(X_{\text{out}}\)）作为视觉特征 \(f_v\)，因为前者包含更干净的语义信息。
  - 计算每个语言标记（text token）特征 \(\hat{f}_l\) 与每个视觉补丁特征 \(\hat{f}_v\) 的余弦相似度，经温度权重柔最大化后得到加权平均的视觉特征 \(f_{vl} = \text{softmax}(\hat{f}_l \hat{f}_v^\top / \tau)(\hat{f}_v + PE)\)，其中 \(PE\) 为2D位置编码，\(\tau\) 为可学习的温度参数。
  - 将提取的文本感知视觉特征 \(f_{vl}\) 通过可学习的交叉注意力池化压缩为单个令牌 \(f'_{vl}\)，语言特征 \(f_l\) 也池化为单个令牌 \(f'_l\)，机器人本体感（proprioception）编码为 \(f_e\)，三者拼接后输入因果Transformer策略网络。
  - 整个CLIP编码器**完全冻结**，仅训练温度参数 \(\tau\)、池化层、MLP编码器及策略Transformer。
- **公式/算法流程**（文字说明）：
  1. 对每个时间步，输入多视角图像和语言指令。
  2. 使用冻结CLIP提取视觉补丁特征 \(f_v\)（来自最后自注意力层输出）和文本标记特征 \(f_l\)。
  3. 计算 \(f_l\) 与 \(f_v\) 的余弦相似度，经softmax生成注意力权重，加权平均得到文本感知视觉特征 \(f_{vl}\)。
  4. 分别对 \(f_{vl}\) 和 \(f_l\) 进行交叉注意力池化，得到压缩令牌 \(f'_{vl}\) 和 \(f'_l\)。
  5. 本体感状态经MLP编码为 \(f_e\)。
  6. 拼接 \(f'_l, f'_{vl}, f_e\) 作为单令牌输入因果Transformer，自回归预测未来12步的相对位姿动作。

## 3. 实验设计：数据集/场景、Benchmark、对比方法
- **模拟环境**：使用**LIBERO基准**（LIBERO-Spatial/Object/Goal及LIBERO-90），共30个训练任务（可多任务学习）和10个自行构造的未见任务（更改物体或指令）。每个任务50条演示。
- **真实机器人环境**：使用**Franka机器人**，包含4种操作原语：拾取放置、戳、倒水、开/关抽屉。收集了：
  - DS-PnP：10个拾取放置任务，共724条演示。
  - DS-ALL：4种原语共1185条演示。
  - 评估：19个训练任务（in-distribution）和15个未见任务（out-of-distribution），每个任务10次试验，场景随机化（物体位置、干扰物）。
- **对比方法**：
  - Octo（开源策略，从头训练）
  - OpenVLA（微调7B VLM）
  - π0-Fast-Droid（基于PaliGemma和Fast tokenizer，预训练后评估/微调）
  - DFP-OTTER（直接传递所有视觉/语言特征，无文本感知提取）
  - 多种消融变体（去掉本体感、去掉文本令牌、去掉CLIP视觉、微调CLIP等）

## 4. 资源与算力
- 论文明确提到：所有模型在**4块NVIDIA A100 80GB GPU**上训练。
- 训练总步数：物理实验40,000步（预训练时60,000步），模拟实验采用相同超参数。
- 推理速度：OTTER（ViT-L/14）在单张NVIDIA 3090Ti上可达**50 Hz**，满足实时控制要求。

## 5. 实验数量与充分性
- **实验数量**：涵盖**模拟**（LIBERO三大套件+10个未见任务）和**真实**（4种原语、多组任务）共上百次试验，每任务10次。
- **消融实验**：共7种消融（表1、表4、表9），系统分析了文本感知提取、冻结CLIP、本体感、文本令牌等组件的重要性。
- **公平性**：与Octo、OpenVLA、π0-Fast-Droid在同一数据上微调/评估；超参数一致；OpenVLA允许更长推理时间（60秒）以弥补速度劣势。
- **充分性评估**：实验设计较为全面，覆盖多种原语、分布内外任务，并进行了缩放分析（不同CLIP模型规模、不同策略网络容量），结论稳健。但缺少对长时域任务（long-horizon）和不同机器人形态（如多指手）的测试。

## 6. 主要结论与发现
- OTTER在**训练任务和未见任务**上均显著优于所有现有VLA模型，且性能下降幅度极小（模拟任务：训练84% vs 未见61%；真实拾取放置：训练68% vs 未见62%）。
- 冻结预训练VLM并提取文本感知视觉特征，比微调VLM或直接传递所有特征更能保留泛化能力。
- 性能可沿多个尺度**缩放**：更大的CLIP编码器（ViT-L/14优于ViT-B/32）、更大的策略Transformer、在更大机器人数据集（OXE）上预训练均可提升OTTER性能。
- 消融实验表明：本体感编码、文本令牌、CLIP预训练均缺一不可；微调CLIP会导致泛化大幅下降。

## 7. 优点（方法与实验设计的亮点）
- **方法层面**：
  - 提出**冻结VLM+文本感知视觉特征提取**的新范式，有效解耦“任务规划”（选择相关特征）与“动作规划”（预测动作）。
  - 利用CLIP自注意力层输出（\(X_{\text{attn}}\)）而非最终输出，保留更干净的语义对齐，避免微调带来的过拟合。
  - 参数效率高（仅数千万参数），推理速度达到50Hz，适合实时控制。
- **实验层面**：
  - 同时涵盖**模拟和真实**环境，验证了跨领域泛化。
  - 设计**未见任务**测试零样本泛化，且严格区分分布内外性能。
  - 进行了**系统消融**（7种变体）和**缩放分析**（3种CLIP规模、2种策略容量、OXE预训练），充分论证了各组件的作用。

## 8. 不足与局限
- **形态限制**：当前模型仅支持SE(3)参数化的末端执行器（如两指夹爪），难以推广到多指灵巧手等复杂形态。
- **场景复杂度**：未深入评估长时域任务、密集操作或高动态环境。
- **数据集规模**：真实机器人数据仅千余条，虽然展现了数据效率，但更大规模数据集的验证（如OXE）仅在模拟中部分体现。
- **潜在偏差**：CLIP本身存在视觉-语言偏差（如对常见物体有偏），可能影响长尾物体识别；实验未专门测试对抗性干扰。
- **论文未明确讨论**：对语言指令的歧义鲁棒性、多模态融合的公平比较（如与RT-2等闭源模型对比缺失）。

（完）
