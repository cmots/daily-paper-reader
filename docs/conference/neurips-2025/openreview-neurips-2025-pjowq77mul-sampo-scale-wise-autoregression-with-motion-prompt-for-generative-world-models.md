---
title: "SAMPO: Scale-wise Autoregression with Motion Prompt for Generative World Models"
title_zh: SAMPO：用于生成式世界模型的尺度自回归与运动提示
authors: "Sen Wang, Jingyi Tian, Le Wang, Zhimin Liao, lijiayi, Huaiyi Dong, Kun Xia, Sanping Zhou, Wei Tang, Gang Hua"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=PJOwQ77Mul"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 生成式世界模型，结合尺度自回归与运动提示
tldr: SAMPO针对自回归世界模型的视觉预测不连贯问题，提出混合框架，在帧内使用视觉自回归生成，帧间使用因果建模，并引入运动提示。该方法在保持空间局部性的同时支持并行解码，显著提升了世界模型的视觉质量和运动预测能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-pjowq77mul/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pjowq77mul/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pjowq77mul/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 666, \"height\": 462, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pjowq77mul/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1471, \"height\": 1038, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pjowq77mul/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1390, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pjowq77mul/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1439, \"height\": 218, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pjowq77mul/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1446, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pjowq77mul/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1446, \"height\": 868, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pjowq77mul/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1434, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pjowq77mul/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1446, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pjowq77mul/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1448, \"height\": 864, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pjowq77mul/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1445, \"height\": 1189, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pjowq77mul/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1432, \"height\": 1086, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pjowq77mul/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1404, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pjowq77mul/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1432, \"height\": 1691, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-pjowq77mul/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 686, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pjowq77mul/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1437, \"height\": 453, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pjowq77mul/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pjowq77mul/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1153, \"height\": 479, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pjowq77mul/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 940, \"height\": 436, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pjowq77mul/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1437, \"height\": 808, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pjowq77mul/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1093, \"height\": 1792, \"label\": \"Table\"}]"
motivation: 现有自回归世界模型在视觉预测中缺乏空间一致性，解码效率低且运动建模不足。
method: 提出尺度自回归与运动提示的混合框架，结合双向空间注意力和时序因果解码。
result: 在多个环境基准上，SAMPO生成的预测更清晰、运动更自然，优于现有方法。
conclusion: SAMPO为具身智能体提供更可靠的世界模型，支持高效规划与控制。
---

## Abstract
World models allow agents to simulate the consequences of actions in imagined environments for planning, control, and long-horizon decision-making. However, existing autoregressive world models struggle with visually coherent predictions due to disrupted spatial structure, inefficient decoding, and inadequate motion modeling. In response, we propose Scale-wise Autoregression with Motion PrOmpt (SAMPO), a hybrid framework that combines visual autoregressive modeling for intra-frame generation with causal modeling for next-frame generation. Specifically, SAMPO integrates temporal causal decoding with bidirectional spatial attention, which preserves spatial locality and supports parallel decoding within each scale. This design significantly enhances both temporal consistency and rollout efficiency. To further improve dynamic scene understanding, we devise an asymmetric multi-scale tokenizer that preserves spatial details in observed frames and extracts compact dynamic representations for future frames, optimizing both memory usage and model performance. Additionally, we introduce a trajectory-aware motion prompt module that injects spatiotemporal cues about object and robot trajectories, focusing attention on dynamic regions and improving temporal consistency and physical realism. Extensive experiments show that SAMPO achieves competitive performance in action-conditioned video prediction and model-based control, improving generation quality with 4.4× faster inference. We also evaluate SAMPO's zero-shot generalization and scaling behavior, demonstrating its ability to generalize to unseen tasks and benefit from larger model sizes.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- 问题：现有的自回归世界模型在生成未来帧时存在三大缺陷：(1) 因光栅扫描（raster-scan）展开导致空间结构破坏，生成结果中物体消失或模糊；(2) 逐个 token 预测导致推理效率低且误差累积；(3) 对场景中的显著运动和交互建模不足，影响时间一致性与物理真实感。
- 整体含义：论文旨在构建一个兼具视觉保真度、时间一致性和高效推理的可交互世界模型，为具身智能体提供更可靠的未来状态模拟，以支持规划、控制和长周期决策。

## 2. 论文提出的方法论

- **核心思想**：提出尺度自回归与运动提示（Scale-wise Autoregression with Motion Prompt, SAMPO）框架。它融合了：（1）帧间因果建模（时间维度的自回归）与帧内双向空间注意力（空间维度的从粗到细生成），保持空间局部性并支持并行解码；（2）非对称多尺度 tokenizer，对观测帧进行密集 token 化以保留静态背景细节，对未来帧进行稀疏 token 化以聚焦动态变化，减少冗余；（3）轨迹感知运动提示模块，利用点跟踪模型（CoTracker3）提取动态轨迹，过滤掉静态点，作为动态先验注入模型，引导注意力聚焦于机器臂和操作对象。
- **关键技术细节**：
  - **混合自回归解码**：似然分解为 \( p(\{z_t^{(l)}\} | a_{<T}) = \prod_{t=1}^T \prod_{l=1}^L p(z_t^{(l)} | z_{<t}^{(*)}, z_t^{(<l)}, a_{<t}) \)，其中帧内按尺度从粗到细生成，帧间按时间顺序生成。
  - **非对称 tokenizer**：观测帧使用全部 L_full 个尺度；未来帧仅使用 L_sub 个粗尺度（L_sub < L_full），并通过交叉注意力整合观测帧信息。
  - **运动提示生成**：在首帧均匀采样网格点，利用 CoTracker3 跨帧跟踪，根据置信度阈值和位移阈值过滤出动态轨迹，叠加到观测帧作为视觉提示输入。
- **训练目标**：基于多尺度交叉熵损失 \( \mathcal{L}_{\text{CE}} \)，仅对将来帧计算；可选增加奖励预测的 MSE 损失用于控制任务。

## 3. 实验设计

- **数据集与场景**：
  - 视频预测：BAIR Robot Pushing（低分辨率 64×64）、RoboNet（64×64 和 256×256）、1X World Model（256×256，真实室内交互）。
  - 视觉规划：VP² 基准，包含 Robosuite（8 个任务）和 RoboDesk。
  - 模型基强化学习：Meta-World 基准的 6 个任务（Button Press Topdown Wall、Plate Slide、Hammer、Door Lock、Handle Pull Side、Coffee Push）。
- **评估指标**：Fréchet Video Distance (FVD)、PSNR、SSIM、LPIPS（视频质量）；成功率（规划/强化学习）；推理速度。
- **对比方法**：MaskViT、FitVid、MCVD、SVG、GHVAE、iVideoGPT 等（视频预测）；DreamerV3、DrQ-v2、MBPO（强化学习）；以及多种基线规划方法。
- **消融实验**：验证混合框架、运动提示、时间位置嵌入、尺度设计、模型缩放的影响。

## 4. 资源与算力

- 论文明确说明：使用 8 张 A800 GPU。不同数据集和模型大小的训练时间大致为：低分辨率（64×64）预训练 20 天/24 天；高分辨率（256×256）预训练 20 天/11 天。具体时间见图 Table C（附录）。

## 5. 实验数量与充分性

- 实验数量充足，覆盖三大类基准（视频预测、规划、强化学习），共使用了 5 个公共数据集 + 2 个模拟基准（VP²、Meta-World）。消融实验系统分析了各组件（混合架构、运动提示、时间嵌入、尺度数、模型大小）的贡献。所有主要实验均报告多次随机种子的均值和标准差（例如强化学习 5 种子，规划 3 种子）。零样本泛化实验展示了跨数据集的迁移能力。实验设计客观公平，与当前 SOTA 方法在同协议下比较。

## 6. 论文的主要结论与发现

- SAMPO 在所有视频预测数据集上取得最优 FVD（例如 BAIR 上 55.5 vs iVideoGPT 60.8；RoboNet 上 55.5 vs 60.8；1X 上 227.1 vs 251.8）。
- 推理速度比标准自回归基线提升 4.4 倍（BAIR 上 2.06 s/vid vs 9.05 s/vid）。
- 在视觉规划（VP²）中平均成功率提升 2.1%（72.2% vs 70.1%）。
- 在模型基强化学习中，SAMPO 显著加速策略收敛，最终成功率超过 DreamerV3 和 iVideoGPT。
- 零样本泛化良好，在未见任务上仍生成高质量视频。
- 模型缩放遵循性能提升规律：更大模型（SAMPO-L）带来更低 FVD。

## 7. 优点

- **新颖的混合架构**：巧妙结合视觉自回归（VAR）的粗到细空间生成与时序因果模型，同时保持了空间结构和时间因果。
- **高效推理**：由于帧内并行解码，极大减少自回归步骤。
- **运动提示模块**：轻量有效，无需修改主架构即可注入动态信息，且通过 dropout 增强鲁棒性。
- **非对称 tokenizer**：针对世界模型中观测帧与未来帧的信息差异进行优化，节省内存并聚焦动态。
- **实验充分且严谨**：包含多数据集、多任务、消融、缩放和零样本，结果可靠。

## 8. 不足与局限

- **长程预测误差累积**：随着预测时间增长，误差逐渐累积，生成质量下降（在 5. Conclusion 中明确提及）。
- **单帧输入限制**：运动提示需要至少两帧才能提取轨迹，因此在仅有一帧观测时无法使用（在 Appendix D 中讨论）。
- **对运动提示的依赖增加预处理开销**：需运行 CoTracker3，增加了时间成本。
- **实验覆盖局限**：当前仅验证在机器人相关数据集，尚未在更通用的视频生成或多样动态场景（如驾驶、体育）中测试。
- **运动提示可能引入偏差**：若轨迹提取不准确（如遮挡、快速运动），可能误导模型。
- **计算资源需求较高**：大模型训练需多卡长时间，对资源有一定门槛。

（完）
