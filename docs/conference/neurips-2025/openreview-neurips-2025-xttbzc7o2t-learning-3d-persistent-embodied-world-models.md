---
title: Learning 3D Persistent Embodied World Models
title_zh: 学习3D持久化具身世界模型
authors: "Siyuan Zhou, Yilun Du, Yuncong Yang, Lei Han, Peihao Chen, Dit-Yan Yeung, Chuang Gan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=XTTbzC7O2T"
tags: ["query:wm-vla-sa"]
score: 8.0
evidence: 具有显式记忆的持久具身世界模型，支持长期一致性模拟
tldr: 本文提出一种新的持久化具身世界模型，通过显式记忆先前生成的内容，克服了现有视频模型缺乏场景记忆的局限性。该模型在生成时预测RGB-D视频，能够在复杂部分可观测环境中实现更一致的长期规划模拟。实验证明该方法在长期一致性上显著优于基线模型。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-xttbzc7o2t/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1230, \"height\": 700, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xttbzc7o2t/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1304, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xttbzc7o2t/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1418, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xttbzc7o2t/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1433, \"height\": 651, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xttbzc7o2t/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1420, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xttbzc7o2t/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1433, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xttbzc7o2t/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1298, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xttbzc7o2t/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1410, \"height\": 574, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xttbzc7o2t/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1168, \"height\": 1171, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xttbzc7o2t/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1166, \"height\": 702, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-xttbzc7o2t/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1433, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xttbzc7o2t/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 749, \"height\": 335, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xttbzc7o2t/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1203, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xttbzc7o2t/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1094, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xttbzc7o2t/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 698, \"height\": 202, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xttbzc7o2t/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 755, \"height\": 183, \"label\": \"Table\"}]"
motivation: 现有世界模型缺乏对场景的记忆，只能基于当前观测预测，导致长期规划不一致。
method: 提出持久化视频扩散模型，引入显式记忆存储先前生成的内容，预测RGB-D视频。
result: 在长期模拟一致性上大幅优于现有方法，支持更可靠的长期规划。
conclusion: 具有记忆的持久世界模型是提升具身智能体长期规划能力的关键方向。
---

## Abstract
The ability to simulate the effects of future actions on the world is a crucial ability of intelligent embodied agents, enabling agents to anticipate the effects of their actions and make plans accordingly. While a large body of existing work has explored how to construct such world models using video models, they are often myopic in nature, without any memory of a scene not captured by currently observed images, preventing agents from making consistent long-horizon plans in complex environments where many parts of the scene are partially observed. We introduce a new persistent embodied world model with an explicit memory of previously generated content, enabling much more consistent long-horizon simulation. During generation time, our video diffusion model predicts RGB-D video of the future observations of the agent. This generation is then aggregated into a persistent 3D map of the environment. By conditioning the video model on this 3D spatial map, we illustrate how this enables video world models to faithfully simulate both seen and unseen parts of the world. Finally, we illustrate the efficacy of such a world model in downstream embodied applications, enabling effective planning and policy learning.

---

## 论文详细总结（自动生成）

# 论文《Learning 3D Persistent Embodied World Models》详细总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：现有基于视频模型的世界模型（如NWM）存在“短视”缺陷——它们没有对场景的长期记忆，只能基于当前观测图像预测未来，导致在部分可观测的复杂环境（如多房间室内场景）中，生成的视频内容与历史观测不一致（如物体消失、房间结构变化）。
- **整体含义**：为了支持智能体进行可靠的长期规划，世界模型必须能够保持对已观测场景的持久记忆，并基于三维空间结构生成一致的内容。本文首次将显式的**3D特征地图记忆**集成到视频扩散模型中，实现了持久化的具身世界模型。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：将视频扩散模型（基于CogVideoX）与一个动态更新的**3D体素特征地图**相结合。在生成未来观测时，模型不仅依赖当前观测和动作，还参考该3D地图中存储的语义和几何信息；生成的新RGB-D视频帧又被反投影回地图中更新记忆，形成闭环。
- **关键技术细节**：
  - **3D记忆构建**：使用DINO-v2提取每帧图像特征，结合深度图和相机位姿将2D特征反投影到3D世界坐标网格中，通过最大池化聚合得到3D体素地图，并附加3D正弦位置编码。
  - **动作表示**：将动作命令（如导航/交互）转化为相对相机位姿（内参+外参），利用**Plücker嵌入**（每个像素的射线原点与方向）精确控制生成视角。
  - **视频模型结构**：基于CogVideoX骨干，修改输入/输出层以接收RGB-D和Plücker嵌入，生成RGB-D视频（9帧）。在原有Transformer块后插入**记忆块**（cross-attention expert block），该块将视频隐藏状态与3D地图特征通过交叉注意力融合，并采用专家自适应层归一化处理不同特征空间。
  - **两阶段训练**：
    1. 第一阶段：微调CogVideoX（不含记忆块）适应数据集，学习动作条件控制与RGB-D生成，损失为扩散噪声预测。
    2. 第二阶段：冻结第一阶段所有参数，仅训练记忆块，学习如何利用3D地图信息，损失相同。
  - **算法流程**：给定当前RGB-D观测、动作块和当前3D地图 → 生成RGB-D视频 → 使用生成帧深度和位姿构造新地图 → 更新原地图（Algorithm 1）。

## 3. 实验设计
- **数据集与场景**：
  - 使用**Habitat模拟器**，基于**HM3D**约1000个场景，收集约50k条轨迹（最长500步），包含多房间、深度图、交互命令。对比了RealEstate10K、Scannet++、ARKitScenes等，本文数据集在多样性、深度支持、交互能力上更优。
- **Benchmark与评价指标**：
  - **视频生成**：PSNR、SSIM、LPIPS、FVD、DreamSim、Scene Revisit Consistency (SRC，用DINO-v2特征余弦相似度计算)。
  - **规划应用**：导航轨迹排序（ATE、RPE、SIM）、模型预测控制（只报告SIM）、策略学习（成功率 vs 训练步数）。
- **对比方法**：
  - NWM（基于相同骨干的Navigation World Model，无记忆）
  - Image Memory（2D快照作为记忆）
  - Ours (w/o depth)（无深度生成）
  - Ours (w/ 2D-Map)（2D特征图记忆）
  - 此外还用NoMaD（扩散策略）作为策略基线。

## 4. 资源与算力
- **训练硬件**：8块NVIDIA H100 GPU。
- **训练时长**：约3天。
- **推理速度**：生成9帧视频约5秒（50步DDIM采样）。
- **模型参数量**：记忆块新增约1B参数（总参数未明确，但明确指出仅记忆块可训练）。

## 5. 实验数量与充分性
- **实验数量**：报告了多组实验：
  - 视频生成质量（Table 1，含6行指标，3个种子均值±标准差）
  - 轨迹排序（Table 2，不同采样数8/16）
  - MPC结果（Figure 6a，迭代曲线）
  - 策略学习结果（Figure 6b，训练曲线）
  - 消融实验：对比有无深度、2D vs 3D地图、不同体素大小（Table 5）、不同特征（脑谱 vs CLIP vs DINO，Table 6）
  - 长视频生成定性展示（Figure 5）
  - 未见场景泛化定性展示（Figure 7）
- **充分性**：实验设计较全面，包括定量与定性、消融、下游任务验证。对比方法公平（均基于相同骨干，参数数量相同）。使用三个随机种子并报告标准差，体现统计意义。
- **客观性**：指标覆盖感知质量（PSNR/SSIM/LPIPS）、生成分布（FVD）、人类感知（DreamSim）、场景一致性（SRC）、规划准确性（ATE/RPE/SIM），较为客观。

## 6. 主要结论与发现
- 本文模型在视频生成的所有指标上显著优于无记忆基线（NWM）和2D记忆基线（Image Memory、2D-Map），FVD从194降至92，SRC从63.4%升至81.7%。
- 深度信息注入（RGB-D生成）优于仅RGB（Ours w/o depth），证实了几何线索对3D记忆对齐的重要性。
- 3D体素地图优于2D特征图（Ours w/ 2D-Map），说明空间结构化记忆更有效。
- 在规划任务中：轨迹排序准确率高于NoMaD NWM（无记忆/少记忆版本）；MPC经过约720次迭代可实现与专家策略相当的性能；利用3D记忆可有效提升策略在新场景中的学习效率（few-shot适应）。
- 模型能生成长达112帧的连贯视频（Figure 5），并能泛化到未见场景（Figure 7）。

## 7. 优点
- **方法创新**：首次将动态3D特征地图与预训练视频扩散模型深度集成，解决世界模型长期一致性的核心难题。
- **设计巧妙**：两阶段训练冻结原有生成能力，仅训练轻量记忆块，降低计算开销；使用Plücker嵌入和RGB-D输出增强几何控制。
- **实验全面**：覆盖生成质量、一致性、规划、策略学习等多维度，消融充分。
- **实用价值**：可应用于机器人导航的模型预测控制和策略训练，具备实际落地潜力。

## 8. 不足与局限
- **数据依赖**：需要深度信息（GT或估计），限制了在无深度数据集（如RealEstate10K）上的直接应用。作者建议使用预训练深度估计模型（如Depth Anything）作为未来方向。
- **动态环境建模缺失**：当前3D地图是静态的，无法模拟环境动态变化（如移动车辆、行人），限制了在动态场景（交通、家居交互）中的应用。
- **计算成本**：训练需8块H100约3天，推理5秒/9帧，对实时性要求高的场景可能仍有挑战。
- **未见场景泛化**：定性展示有轻微视觉质量下降，定量泛化实验不够充分（未提供未见场景的量化指标）。
- **动作空间**：当前主要测试离散导航动作，交互动作（拾取、移动物体）仅提及但未充分实验。
- **偏差风险**：数据集来自Habitat模拟器，视觉风格单一，真实世界泛化能力需进一步验证。

（完）
