---
title: "DeepASA: An Object-Oriented Multi-Purpose Network for Auditory Scene Analysis"
title_zh: DeepASA：面向对象的多用途听觉场景分析网络
authors: "Dongheon Lee, Younghoo Kwon, Jung-Woo Choi"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=cnG7h8ucip"
tags: ["query:wm-vla-sa"]
score: 8.0
evidence: 听觉场景分析，包含方向到达估计（空间音频）
tldr: 针对复杂听觉场景中多声源重叠和动态移动带来的分析挑战，提出DeepASA多用途网络。它采用面向对象处理策略，将听觉特征封装为对象中心表示，并通过链式推理机制逐步精化。该网络统一了源分离、去混响、事件检测、分类和方向到达估计等任务。实验结果表明DeepASA在多个基准上取得最优结果，尤其擅长处理大规模多源场景。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-cng7h8ucip/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1377, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cng7h8ucip/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cng7h8ucip/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 798, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cng7h8ucip/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cng7h8ucip/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1363, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cng7h8ucip/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 985, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cng7h8ucip/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1447, \"height\": 314, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cng7h8ucip/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1438, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cng7h8ucip/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1424, \"height\": 307, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cng7h8ucip/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1441, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cng7h8ucip/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 989, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cng7h8ucip/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1048, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cng7h8ucip/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1136, \"height\": 1208, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-cng7h8ucip/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1460, \"height\": 567, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cng7h8ucip/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cng7h8ucip/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1238, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cng7h8ucip/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1465, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cng7h8ucip/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 976, \"height\": 691, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cng7h8ucip/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 684, \"height\": 98, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cng7h8ucip/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1132, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cng7h8ucip/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1122, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cng7h8ucip/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1335, \"height\": 438, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cng7h8ucip/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 877, \"height\": 406, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cng7h8ucip/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 835, \"height\": 153, \"label\": \"Table\"}]"
motivation: 复杂听觉场景中多个相似声源重叠且动态移动，现有模型难以统一处理。
method: 提出面向对象处理策略，将听觉特征封装为对象中心表示，并通过链式推理机制精化，统一进行源分离、去混响、事件检测和方向估计。
result: 在多个听觉场景分析基准上达到最优性能，尤其在大规模多输入多输出场景。
conclusion: 为复杂听觉场景提供了一体化的高效分析框架。
---

## Abstract
We propose DeepASA, a multi-purpose model for auditory scene analysis that performs multi-input multi-output (MIMO) source separation, dereverberation, sound event detection (SED), audio classification, and direction-of-arrival estimation (DoAE) within a unified framework. DeepASA is designed for complex auditory scenes where multiple, often similar, sound sources overlap in time and move dynamically in space. To achieve robust and consistent inference across tasks, we introduce an object-oriented processing (OOP) strategy. This approach encapsulates diverse auditory features into object-centric representations and refines them through a chain-of-inference (CoI) mechanism. The pipeline comprises a dynamic temporal kernel-based feature extractor, a transformer-based aggregator, and an object separator that yields per-object features. These features feed into multiple task-specific decoders. Our object-centric representations naturally resolve the parameter association ambiguity inherent in traditional track-wise processing. However, early-stage object separation can lead to failure in downstream ASA tasks. To address this, we implement temporal coherence matching (TCM) within the chain-of-inference, enabling multi-task fusion and iterative refinement of object features using estimated auditory parameters. We evaluate DeepASA on representative spatial audio benchmark datasets, including ASA2, MC-FUSS, and STARSS23. Experimental results show that our model achieves state-of-the-art performance across all evaluated tasks, demonstrating its effectiveness in both source separation and auditory parameter estimation under diverse spatial auditory scenes. The demo video, samples and code are available at https://huggingface.co/spaces/donghoney22/DeepASA.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：复杂听觉场景中，多个相似声源在时间上重叠、在空间中动态移动，传统的单一任务模型（如仅做源分离、或仅做事件检测）缺乏跨任务、跨线索的关系推理能力，导致在关键听觉线索缺失或退化时性能急剧下降。
- **研究动机**：人类听觉系统能够通过整合音高、时序、空间位置等多种互补线索实现场景分析（如鸡尾酒会效应）。受此启发，本文提出一个通用型计算听觉场景分析（CASA）模型，模拟人类的线索整合过程，统一处理源分离、去混响、声音事件检测（SED）、音频分类、到达方向估计（DoAE）等多任务。
- **整体含义**：DeepASA实现了从多通道混音到所有下游任务的端到端统一框架，消除了传统轨道式处理中参数关联歧义，并通过链式推理机制相互增强各任务估计，在多个空间音频基准上取得最优结果。

## 2. 方法论

### 2.1 核心思想

- **面向对象处理**：将多通道混音编码为对象级特征，每个对象封装一个声源的完整听觉信息（波形、类别、起止时间、方向）。对象特征在所有子解码器间自然保持一致，无需手动关联或置换不变训练。
- **链式推理**：通过时间相干性匹配（TCM）和特征融合（FF）构成的迭代精化过程，利用已估计的听觉参数（如DoA、SED）互相补充和修正不完整或模糊的估计，模拟人类利用多线索推理的能力。

### 2.2 关键技术细节

- **音频编码器（Dynamic STFT）**：提出时变可学习高斯窗，其均值μ<sub>t</sub>和标准差σ<sub>t</sub>由输入波形通过1D卷积和线性层预测，实现每帧自适应调整分析窗口的位置和宽度，以捕捉不同时间尺度的信息。
- **特征聚合模块**：基于DeFT-Mamba改进，使用混合Mamba和Transformer层捕获时域、频域、通道间关系，并采用轻量化设计（仅T-Hybrid Mamba使用Mamba-FFN，F-Hybrid Mamba使用传统FFN）。
- **对象分割器**：通过2D卷积核将聚合特征分割为J+1个对象特征（J个前景声源+1个背景噪声）。
- **子解码器**：
  - **MIMO音频解码器**：输出每个对象的多通道直达声、混响声、噪声波形，保留空间信息以辅助DoAE。
  - **SED解码器**：结合预训练ATST（音频教师-学生Transformer）、T-CRNN和F-CRNN，输出类别概率、激活曲线、SED图。推理时通过乘积合并避免多类映射。
  - **DoA解码器**：CRNN结构，输出每个时间帧的笛卡尔坐标DoA向量（x,y,z），源存在时模为1，无源时为0。
- **链式推理（CoI）**：
  - **TCM**：通过多头交叉注意力对齐SED和DoA的时间维度，SED作为查询、DoA作为键/值，反之亦然，输出融合线索。
  - **FF**：使用FiLM层对融合线索进行调制，结合原始聚合特征，通过第二个对象分割器重新生成精化对象特征，再送入第二组子解码器。
- **训练策略**：采用多阶段训练，先训练Net1，固定Net1的前三个DeFT-Mamba块后训练Net2。

## 3. 实验设计

### 3.1 数据集与基准

| 数据集 | 来源 | 用途 | 特点 |
|--------|------|------|------|
| **ASA2** | 基于ASA数据集扩展 | 全面评估（USS、SED、DoAE） | 支持直达/混响分离、MIMO、最多5个前景源、噪声混响环境 |
| **MC-FUSS** | 多通道自由通用源分离基准 | USS任务 | 混合1-4个源（含1背景），用于通用源分离 |
| **STARSS23** | 真实环境录制（3.8小时） | SELD任务 | 包含多种声音事件、需数据增强（使用空间场景生成器扩增至80小时） |

### 3.2 对比方法

**USS任务**：ByteDance-uss、MC-BSRNN、TF-GridNet、DeFTAN-II、SpatialNet、DeFT-Mamba（从零训练和精调）。
**SELD任务**：CST-former、MFF-EINV2、CST-former2、EINV-2（数据增强链，第2名）、NERC-SLIP系统（第1名，含集成和不集成）。
**统一评估**：在ASA2数据集上对比了ByteDance-uss、TF-GridNet、SpatialNet、DeFT-Mamba、EINV2、ResNet Conformer、SELD-Mamba、MFF-EINV2。

### 3.3 实验充分性与公平性

- **消融实验**：表1系统性消融了框架（MIMO vs MISO、引入不同SELD解码器）、对象分割器简化（移除Unfold、F-Mamba）、SED解码器增强（F-CRNN、ATST）、音频解码器改进（噪声解码器、直达/混响分离）、动态STFT、CoI。共10余组对比。
- **CoI消融**：表2比较了无CoI、仅SED分支、仅DoA分支、两者皆用、完整CoI（含音频解码器2）。
- **多数据集评估**：在3个不同基准上测试，并分别提供从零训练和精调结果。
- **统计显著性**：最终模型报告5次运行的平均值和标准差（表1最后一行）。
- **对比公平性**：在MC-FUSS上比较了从零训练和精调版本，并控制了预训练影响。在STARSS23上使用DCASE2023规则允许外部数据，与公开挑战赛方法对比。同时附录F中提供了在ASA2上与公开方法（使用相同预训练条件）的对比，进一步证明公平性。

## 4. 资源与算力

- **GPU**：8块 **GeForce RTX 3090** GPUs
- **批次大小**：2
- **训练轮数**：100 epochs，选择验证损失最低的epoch作为最终模型。
- **训练时间**：文中未明确给出训练时长（小时/天）。
- **模型参数与计算量**：完整DeepASA（含ATST预训练）参数量约105.3M（8.2M+96.8M ATST），MAC/s约104.0G。轻量版本（不含ATST）2.9M参数，77.3G MAC/s。

## 5. 实验数量与充分性分析

- **总实验数量**：约4个主要表格（表1~表4）加附录中多个补充实验（表5~表11），涵盖：
  - 主要消融（表1：10种变体）
  - CoI消融（表2：4种变体）
  - 多数据集对比（表3：6+3种方法；表4：5+2种方法）
  - 附录中噪声解码器影响、直达/混响解码器分析、动态STFT变体、多源数量表现、真实RIR对比等。
- **充分性**：非常充分。消融实验几乎覆盖了所有关键组件（编码器、对象分割器、各子解码器、动态窗、CoI），并且分别在三个不同类型数据集上验证泛化能力。对比方法均选用了近两年SOTA，结果具有说服力。
- **客观性**：报告了多次运行的平均值和标准差，使用了统一评价指标（SI-SDRi、SDRi、SELD score含ER/F1/LE/LR），并明确说明对比方法训练条件（如允许外部数据）。

## 6. 主要结论与发现

- DeepASA在所有评估任务上均达到**SOTA性能**：
  - ASA2：SI-SDRi 11.2 dB，SELD分数0.206
  - MC-FUSS（精调）：SI-SDRi 18.5 dB
  - STARSS23：SELD分数0.253
- 关键贡献验证：
  - **OOP**消除了参数关联歧义，提升了多任务一致性。
  - **CoI**通过跨线索注意力修复错误估计，SED和DoA互相增强。
  - **动态STFT**通过自适应时窗改善分离（尤其对瞬态声音如敲门声）。
  - **噪声解码器**显著提升家庭声音的分类召回率（+15.5%）。
  - **直达/混响分离**改善DoA精度（LE降低）。

## 7. 优点

- **统一框架**：首次在一个模型中整合源分离、去混响、SED、分类、DoAE，且所有任务可互相利用共享特征。
- **面向对象设计**：天然解决多输出间的对齐问题，无需PIT或后处理。
- **链式推理机制**：模拟人类听觉系统的线索互补能力，通过交叉注意力精化估计，实验证明比单分支更优。
- **强大的泛化能力**：在ASA2预训练后，通过微调即可迁移至不同领域（MC-FUSS、STARSS23），且性能优于从头训练的SOTA。
- **详尽消融**：全部关键组件影响均被量化，验证设计合理性。
- **轻量潜力**：不含ATST版本仅2.9M参数，仍具有竞争力（ASA2上11.0 dB SI-SDRi，SELD 0.240）。

## 8. 不足与局限

- **参数规模大**：ATST预训练模型带来约96.8M额外参数，增大了整体计算和存储需求。作者指出未来可探索为对象特征设计的轻量分类层。
- **混响和噪声范围限制**：训练数据混响时间0.2~0.6秒，信噪比6~30 dB。当混响>0.6s或SNR<0 dB时，性能可能下降。
- **最大源数限制**：模型预设最多J个前景源（本工作中J=5）。当真实源数超过J时，分离性能急剧下降（附录G表11：6源时Top4平均SI-SDRi 7.0 dB，Bottom2仅为-6.8 dB）。
- **真实环境泛化**：从模拟RIR到真实RIR存在性能下降（SI-SDRi从11.0降至10.6，SELD分数从0.230升至0.254），表明需要更多真实数据训练。
- **滥用风险**：模型可提取个体语音及方向信息，可能被用于窃听。作者在结论中提及但未提出防范措施。
- **训练耗时**：未报告训练时长，但批次大小仅2（8×RTX 3090），暗示模型复杂度较高，可能对资源要求不菲。
- **实验覆盖**：虽然数据集多样，但所有场景均为室内（混响、噪声可控），未见户外或极端环境的测试。

（完）
