---
title: "DreamVLA: A Vision-Language-Action Model Dreamed with Comprehensive World Knowledge"
title_zh: DreamVLA：具备全面世界知识的视觉-语言-动作模型
authors: "Wenyao Zhang, Hongsi Liu, Zekun Qi, Yunnan Wang, XinQiang Yu, Jiazhao Zhang, Runpei Dong, Jiawei He, He Wang, Zhizheng Zhang, Li Yi, Wenjun Zeng, Xin Jin"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=PK07eretkF"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 结合世界知识预测的视觉-语言-动作模型用于机器人操作
tldr: 本文提出DreamVLA，一种新颖的VLA框架，通过集成全面的世界知识预测（包括动态、空间和语义信息）实现逆动力学建模，建立感知-预测-动作循环。该方法在机器人操作任务中显著提升了泛化能力和推理能力，优于现有基于图像预测的方法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-pk07eretkf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1422, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pk07eretkf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1436, \"height\": 693, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pk07eretkf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1400, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pk07eretkf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 642, \"height\": 634, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pk07eretkf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 667, \"height\": 605, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pk07eretkf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1418, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pk07eretkf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1448, \"height\": 1960, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pk07eretkf/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1403, \"height\": 1226, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pk07eretkf/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1393, \"height\": 1214, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pk07eretkf/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1408, \"height\": 1319, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-pk07eretkf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1462, \"height\": 650, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pk07eretkf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1368, \"height\": 372, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pk07eretkf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1439, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pk07eretkf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1418, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pk07eretkf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 698, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pk07eretkf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 696, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pk07eretkf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 700, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pk07eretkf/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 698, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pk07eretkf/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1378, \"height\": 342, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pk07eretkf/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1080, \"height\": 571, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pk07eretkf/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 753, \"height\": 495, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pk07eretkf/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 871, \"height\": 201, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pk07eretkf/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 917, \"height\": 360, \"label\": \"Table\"}]"
motivation: 现有VLA模型局限于图像预测，缺乏全面的世界知识，限制了机器人操作的泛化性和推理能力。
method: 引入动态区域引导的世界知识预测模块，结合逆动力学建模，形成感知-预测-动作循环。
result: 在多个机器人操作基准上，DreamVLA取得了优于现有方法的性能，展现了更强的泛化和推理能力。
conclusion: DreamVLA通过世界知识预测显著提升了VLA模型在机器人操作中的表现，为具身智能提供了新范式。
---

## Abstract
Recent advances in vision-language-action (VLA) models have shown promise in integrating image generation with action prediction to improve generalization and reasoning in robot manipulation.  However, existing methods are limited to challenging image-based forecasting, which suffers from redundant information and lacks comprehensive and critical world knowledge, including dynamic, spatial and semantic information.
To address these limitations, we propose DreamVLA, a novel VLA framework that integrates comprehensive world knowledge forecasting to enable inverse dynamics modeling, thereby establishing a perception-prediction-action loop for manipulation tasks. 
Specifically, DreamVLA introduces a dynamic-region-guided world knowledge prediction,  integrated with the spatial and semantic cues, which provide compact yet comprehensive representations for action planning.
This design aligns with how humans interact with the world by first forming abstract multimodal reasoning chains before acting.
To mitigate interference among the dynamic, spatial and semantic information during training, we adopt a block-wise structured attention mechanism that masks their mutual attention, preventing information leakage and keeping each representation clean and disentangled.
Moreover, to model the conditional distribution over future actions, we employ a diffusion-based transformer that disentangles action representations from shared latent features.
Extensive experiments on both real-world and simulation environments demonstrate that DreamVLA achieves 76.7 success rate on real robot tasks and 4.44 average length on the CALVIN ABC-D benchmarks.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：现有视觉-语言-动作（VLA）模型大多直接将观测映射到动作，缺乏对未来世界知识的预测能力。即使部分方法引入了图像/视频生成作为中间步骤，也面临冗余像素信息、缺少空间信息（深度）和高层语义信息等局限，导致动作规划效率低、泛化性不足。
- **动机**：人类在交互时首先形成抽象的多模态推理链（关注动态变化、空间结构和语义目标），再执行动作。因此，让VLA模型具备“感知→预测→动作”的闭环能力，可显著提升操作性能。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：提出DreamVLA，在VLA模型中集成全面的世界知识预测（动态区域、深度、高层语义），作为逆动力学建模的中间推理步骤，从而建立紧凑且具表现力的动作规划表示。
- **关键技术细节**：
  - **动态区域预测**：利用CoTracker提取光流轨迹，生成二进制动态掩码，指导模型仅重建与运动相关的区域（如机械臂末端、移动物体），而非整张未来帧。
  - **深度预测**：使用Depth-Anything作为教师模型，预测未来深度图，损失函数为尺度归一化MSE，保留相对深度关系。
  - **高层语义预测**：预测未来DINOv2和SAM特征，采用InfoNCE对比损失，促使模型区分类别。
  - **块状结构化注意力**：为动态、深度、语义三个子查询设置相互屏蔽的注意力掩码，仅允许它们关注共享的语言、视觉和状态令牌，防止信息泄漏，保持各表征干净解耦。
  - **扩散Transformer动作头**：利用DiT将噪声解码为连续动作序列，动作嵌入由<action>查询从大语言模型中聚合得到，克服MLP头无法解耦的局限。
- **公式/算法流程**（文字描述）：
  1. 编码语言（CLIP）、图像（MAE）和机器人状态（MLP）。
  2. 添加<dream>（含三个子查询）和<action>查询，送入GPT-2骨干。
  3. 输出世界嵌入，通过三个轻量解码器分别预测动态区域、深度和语义；仅训练时使用解码器。
  4. 利用<action>查询聚合的潜特征，传入DiT进行10步去噪，输出n步动作序列。
  5. 总损失为各项预测损失与动作损失的加权和（λ_dyn=0.1, λ_depth=0.001, λ_sem=0.1, λ_DiT=1）。

## 3. 实验设计

- **数据集/场景**：
  - **仿真**：CALVIN ABC-D基准（4个环境，34个任务），LIBERO（4个套件：Spatial/Object/Goal/Long，每套10个任务）。
  - **真实世界**：Franka Panda机械臂，两个Realsense D415摄像头（第三视角+腕部），收集四个类别物体进行pick/place，以及抽屉开闭任务。
- **基准/对比方法**：扩散策略（Diffusion Policy）、Octo-Base、OpenVLA、Roboflamingo、3D Diffusor Actor、RoboDual、UNIVLA、π0、CLOVER、UP-VLA、Robovlm、Seer、VPP等。
- **评价指标**：CALVIN上报告连续完成1-5个任务的成功率和平均长度；LIBERO报告各套件成功率；真实世界报告pick/place/drawer成功率。

## 4. 资源与算力

- **GPU**：8 张 NVIDIA A800 GPU。
- **训练配置**：批次大小 8/GPU（有效 64），优化器 AdamW，学习率 1e-3，权重衰减 0.01，训练 20 个 epoch（预热 1 个 epoch）。
- **备注**：文本未明确给出单次训练总时长，但提及使用混合精度（bfloat16）加速，且视觉特征（SAM、DINOv2等）预提取以节省计算。

## 5. 实验数量与充分性

- **实验数量**：
  - 主实验：CALVIN ABC-D（与12+基线对比）、LIBERO（与7+基线对比）、真实世界任务（与3个基线对比）。
  - 消融实验：共 7 组（Q1: 各模态贡献；Q2: 预测 vs 辅助重建；Q3: 光流 vs 动态区域；Q4: 结构化注意力 vs 因果注意力；Q5: 共享查询 vs 分离查询；Q6: 查询数量影响；附录还包含推理延迟测试）。
- **充分性与公平性**：
  - 实验覆盖了仿真和真实场景，任务类型多样（长时、空间、目标、开门等），对比方法均为当前最新最强模型（包括OPENVLA、π0等）。
  - 消融实验逐一验证每个设计选择，且控制变量一致（如均固定其余组件）。
  - 报告了平均成功率，并采用固定随机种子保证可重现性；但未提供误差线或置信区间，略有不足。

## 6. 主要结论与发现

- DreamVLA在CALVIN ABC-D上达到**4.44平均任务长度**（SOTA），比之前最佳Seer（4.28）和VPP（4.29）提升约3.5%。
- LIBERO所有套件平均得分**92.6%**，远超OpenVLA（76.5%）和CoT-VLA（81.1%）等。
- 真实世界三个任务平均成功率**76.7%**，显著高于扩散策略（50.8%）和OpenVLA（35.0%）。
- 动态区域预测贡献最大；单独使用深度或语义预测反而会降低性能，但与其他模态联合可带来额外增益。
- 结构化注意力比因果注意力有明显提升（4.44 vs 3.75）。
- 分离的模态查询优于共享查询（4.44 vs 4.17）。

## 7. 优点

- **方法创新**：首次将逆动力学建模与三种互补世界知识（动态、深度、语义）有机结合，形成“感知-预测-动作”闭环；块状结构化注意力设计精巧，有效防止模态间信息泄漏。
- **效率高**：推理时无需像素级解码（仅用世界嵌入），解码器仅训练时使用，延迟增加仅3ms（总91ms vs 88ms无dream查询）。
- **充分消融**：7组消融深入揭示了各设计要素的贡献与交互关系，验证了设计的合理性。
- **开源友好**：提供项目页面、代码和Hugging Face模型，便于复现和扩展。

## 8. 不足与局限

- **实验覆盖**：仅验证了平行夹爪操作，未涉及灵巧手、双机械臂或多物体复杂交互场景；真实世界任务数量较少（三类共五个子任务），局限性较强。
- **偏差风险**：依赖预训练光流模型（CoTracker）和深度估计器（Depth-Anything），这些工具在极端光照或纹理场景下可能失效，导致预测标签噪声；未进行鲁棒性分析。
- **应用限制**：模型当前基于RGB观测，缺乏3D点云或触觉输入，在需要精细力控或三维几何推理的任务中可能受限；训练数据来自DROID和CALVIN，场景多样性有限，跨域泛化有待验证。
- **其他**：未提供统计学显著性检验（如多次运行的标准差）；注意力机制和扩散步数等超参数未做更广泛搜索。

（完）
