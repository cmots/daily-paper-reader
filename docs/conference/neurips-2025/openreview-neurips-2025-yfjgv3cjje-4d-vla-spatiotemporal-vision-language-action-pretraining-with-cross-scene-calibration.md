---
title: "4D-VLA:  Spatiotemporal Vision-Language-Action Pretraining with Cross-Scene Calibration"
title_zh: "4D-VLA: 具有跨场景校准的时空视觉-语言-动作预训练"
authors: "Jiahui Zhang, Yurui Chen, Yueming Xu, Ze Huang, Yanpeng Zhou, Yu-Jie Yuan, Xinyue Cai, Guowei Huang, Xingyue Quan, Hang Xu, Li Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=yFjgV3cJje"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 用于机器人学的时空视觉-语言-动作预训练
tldr: 针对现有VLA预训练中因输入不完整导致的坐标系混乱和状态混乱问题，提出将4D信息（深度和时间）融入视觉特征，利用连续RGB-D输入对齐机器人与场景的坐标系。该方法有效缓解了条件动作分布分散的问题，显著提升了预训练效率。在多个机器人数据集上的实验表明，4D-VLA能够学习更一致的表示，促进跨场景迁移。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-yfjgv3cjje/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1424, \"height\": 850, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yfjgv3cjje/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1405, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yfjgv3cjje/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1132, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yfjgv3cjje/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1428, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yfjgv3cjje/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1409, \"height\": 584, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yfjgv3cjje/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 708, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yfjgv3cjje/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 541, \"height\": 450, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-yfjgv3cjje/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1232, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yfjgv3cjje/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 699, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yfjgv3cjje/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1283, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yfjgv3cjje/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1451, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yfjgv3cjje/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 692, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yfjgv3cjje/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 701, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yfjgv3cjje/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1446, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yfjgv3cjje/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 711, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yfjgv3cjje/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1444, \"height\": 278, \"label\": \"Table\"}]"
motivation: 解决机器人数据预训练中因输入不完整导致的坐标系统混乱和状态混乱问题。
method: 通过引入深度和时间信息到视觉特征，使用连续RGB-D输入对齐坐标系。
result: 有效缓解了条件动作分布分散问题，提升了预训练效率。
conclusion: 提出了一种利用4D信息进行跨场景校准的VLA预训练方法。
---

## Abstract
Leveraging diverse robotic data for pretraining remains a critical challenge. Existing methods typically model the dataset’s action distribution using simple observations as inputs. However, these inputs are often incomplete, resulting in a dispersed conditional action distribution—an issue we refer to as coordinate system chaos and state chaos. This inconsistency significantly hampers pretraining efficiency. To address this, we propose 4D-VLA, a novel approach that effectively integrates 4D information into the input to mitigate these sources of chaos. Our model introduces depth and temporal information into visual features with sequential RGB-D inputs, aligning the coordinate systems of the robot and the scene. This alignment endows the model with strong spatiotemporal reasoning capabilities while minimizing training overhead. Additionally, we introduce Memory bank sampling, a frame sampling strategy designed to extract informative frames from historical images, further improving effectiveness and efficiency. Experimental results demonstrate that our pretraining method and architectural components substantially enhance model performance.  In both simulated and real-world experiments, our model achieves a significant increase in success rate over OpenVLA.To further assess spatial perception and generalization to novel views, we introduce MV-Bench, a multi-view simulation benchmark. Our model consistently outperforms existing methods, demonstrating stronger spatial understanding and adaptability.

---

## 论文详细总结（自动生成）

# 4D-VLA 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

现有视觉-语言-动作（VLA）预训练方法通常仅使用单张 RGB 图像和文本指令作为输入，导致输入信息不完整，引发两类关键问题：

- **坐标系混乱**：由于图像未完整捕捉机器人本体，无法准确推断机器人的位置和朝向，使动作分布在高维空间中呈现高方差。
- **状态混乱**：单帧缺乏时间上下文，导致动作歧义（如对称轨迹、视觉相似但动作不同）。

这些问题使得条件动作分布 \(A_t(\text{input})\) 分散、不光滑，严重阻碍预训练效率和泛化能力。论文旨在通过引入 4D 时空信息（深度+时间）来缓解这两种混乱，提升跨场景预训练效果。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

### 核心思想
将连续 RGB-D 帧中的深度信息转换为 3D 坐标嵌入，与视觉特征融合，并利用多帧时间信息构建 4D 时空表征，从而对齐机器人与场景坐标系，减少动作分布的不确定性。

### 关键技术细节

- **空间感知视觉令牌（Spatial-aware visual tokens）**：  
  使用相机内外参将深度图反投影到世界坐标系下的 3D 坐标 \(P_w\)，通过可学习的位置编码 \(E_S\) 编码后与视觉特征逐元素相加，再经 MLP 投影器生成空间视觉令牌 \(e_{ST}\)。
  \[
  P_w(u,v) = R \cdot D(u,v) \cdot K^{-1}[u,v,1]^T + T
  \]

- **4D 时空表征与多帧编码**：  
  将当前帧与历史帧（通过记忆库采样选取）的空间视觉令牌拼接，并引入时间位置编码 \(e_T\)（相对偏移），形成输入令牌序列：
  \[
  X = \bigcup_{i \in H} [e_T^i | e_{ST}^i] \cup \{e_{\text{text}}\}
  \]

- **记忆库采样（Memory Bank Sampling）**：  
  一种自适应历史帧采样算法（Algorithm 1），基于特征相似度从滑动窗口中选择信息量最大的 k 帧（默认 k=5，窗口 n=20），减少冗余并提升效率。

- **损失函数**：  
  总损失包括平移 L2 损失 \(L_t\)、旋转 L2 损失 \(L_r\)、抓取二分类损失 \(L_g\) 以及方向损失 \(L_d\)（强调平移方向一致性）。
  \[
  L = L_t + L_r + L_g + \lambda_d L_d
  \]

- **MV-Bench 基准**：  
  基于 LIBERO-SPATIAL 构建的多视角数据集，包含 6 个训练视角和 6 个测试视角（覆盖 270°范围），用于评估“面内视图”和“跨视图”泛化能力。

## 3. 实验设计：数据集、基准、对比方法

### 数据集与场景
- **预训练**：DROID 数据集（76,000 条轨迹，564 个场景，86 个任务，含 RGB-D）。
- **仿真微调**：LIBERO 套件（SPATIAL, OBJECT, GOAL, LONG 四组任务），以及自建的 **MV-Bench**。
- **真实世界**：Franka 机械臂上的 4 个任务（空间泛化、抗干扰、精确放置、指令跟随），以及多视角真实世界任务。
- **额外基准**：RLBench（ARM4R 协议）。

### 对比方法
- **主要基线**：OpenVLA, Octo, DiffusionPolicy, TraceVLA, SpatialVLA, UniAct, SparseVLM, FastV, VLA-Cache 等。
- **消融实验**：Base VLA（单 RGB）、+预训练、+坐标嵌入、+历史帧、+记忆库采样等逐步添加。

## 4. 资源与算力
论文明确说明：
- 预训练使用 **8 × NVIDIA A6000 GPU**，训练 **1 个 epoch**，约 **20k 步**，耗时 **96 小时**。
- 批量大小 512，余弦学习率 2e-5，冻结视觉编码器。
- 推理时使用 FlashAttention bf16，约需 **8 GB 显存**。

## 5. 实验数量与充分性
论文进行了较为充分的实验：
- **仿真实验**：在 LIBERO 四个子集上评估，每个任务使用 3 个随机种子报告均值和标准差。
- **MV-Bench**：3 个面内视角 + 6 个跨视角测试，共 9 种角度设置。
- **真实世界实验**：4 个任务（每个 50 条轨迹），以及多视角真实任务（2 个任务，各 20 次测试）。
- **消融实验**：历史帧窗口/采样数、时间编码方式、动作头类型（MLP vs. 自回归 vs. 扩散）、预训练/坐标/本体感受的贡献、坐标系混乱程度的影响等。
- **与其他视频采样方法对比**：自适应池化、网格池化、Q-Former 等。

整体而言，实验覆盖了仿真、真实、多视角、长时域、不同干扰条件，且报告了统计误差，设计较为公平。

## 6. 论文的主要结论与发现
1. **4D 信息有效缓解坐标系混乱**：随着随机旋转幅度增大，无 3D 信息的模型成功率从 64% 暴跌至 8%，而有 3D 信息的模型仅从 75% 降至 30%。
2. **4D-VLA 在 LIBERO 上平均成功率提升 12.1%**（相比 OpenVLA），尤其在长时域任务（LIBERO-LONG）上提升 25.4%。
3. **MV-Bench 上面内视图 81.0%，跨视图 73.8%**，显著高于 OpenVLA（52.2% / 50.5%），展示出较强的空间泛化能力。
4. **记忆库采样优于均匀采样和其他视频采样方法**（成功率 0.866 vs. 0.738），且保持了合理的效率。
5. **时间编码采用 `concat` 优于 `additive` 或 `absolute`**，且相对位置编码优于绝对位置编码。
6. **预训练优于未预训练**，且匹配下游输入模式（坐标+历史）时迁移效果最佳。

## 7. 优点
- **问题洞察深刻**：明确指出现有 VLA 预训练效率低下的根本原因——输入不完整导致的分布混乱。
- **方法简洁有效**：仅靠添加 3D 坐标嵌入和历史帧，无需复杂的外部参数或数据集特定调整，即可显著提升性能。
- **记忆库采样设计巧妙**：在线式自适应采样，避免冗余，适合闭环控制流式输入。
- **实验全面**：涵盖仿真、真实世界、多视角、消融、鲁棒性分析，并自建多视角基准。
- **开源潜力**：提及代码链接，有助于复现和社区发展。

## 8. 不足与局限
- **依赖 RGB-D 输入**：需要深度相机和相机标定，增加了硬件限制，在纯 RGB 场景中无法直接使用。
- **预训练仅用 DROID 数据集**：未探索在更大规模或更多样化数据集（如 Open X-Embodiment）上的表现。
- **真实世界实验规模有限**：任务数量和轨迹数较少（每个任务 50 条），且只在一类机械臂（Franka）上验证，泛化性仍需更大规模测试。
- **未讨论安全与伦理问题**：如失败模式、对环境的潜在风险等。
- **计算资源要求较高**：8×A6000 训练 96 小时，对一般实验室可能负担较重。

（完）
