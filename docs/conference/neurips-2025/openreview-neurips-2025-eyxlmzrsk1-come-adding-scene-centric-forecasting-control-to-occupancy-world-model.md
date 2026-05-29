---
title: "COME: Adding Scene-Centric Forecasting Control to Occupancy World Model"
title_zh: COME：为占用世界模型添加场景为中心的预测控制
authors: "Yining Shi, Kun Jiang, Qiang Meng, Ke Wang, Jiabao Wang, Wenchao Sun, Tuopu Wen, mengmeng yang, Diange Yang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=EYxLmZRSK1"
tags: ["query:wm-vla-sa"]
score: 7.0
evidence: 在占用世界模型中引入以场景为中心的预测控制，用于自动驾驶
tldr: 本文提出COME框架，将场景为中心的预测控制融入占用世界模型。现有方法难以解耦自车运动与场景变化，导致预测不佳。COME通过场景中心预测分支生成与自车无关的未来特征，并使用ControlNet将这些特征转化为条件，控制世界模型生成。在自动驾驶场景中，该方法显著提升了长期预测的准确性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-eyxlmzrsk1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1281, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eyxlmzrsk1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1432, \"height\": 667, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eyxlmzrsk1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1424, \"height\": 1290, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eyxlmzrsk1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1405, \"height\": 1822, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eyxlmzrsk1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1433, \"height\": 790, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eyxlmzrsk1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1442, \"height\": 588, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eyxlmzrsk1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1417, \"height\": 1101, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eyxlmzrsk1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1419, \"height\": 871, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eyxlmzrsk1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1435, \"height\": 598, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eyxlmzrsk1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1399, \"height\": 910, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eyxlmzrsk1/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1446, \"height\": 636, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-eyxlmzrsk1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1464, \"height\": 1069, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eyxlmzrsk1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1446, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eyxlmzrsk1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1069, \"height\": 385, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eyxlmzrsk1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1447, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eyxlmzrsk1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 475, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eyxlmzrsk1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 301, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eyxlmzrsk1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 522, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eyxlmzrsk1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 871, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eyxlmzrsk1/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 522, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eyxlmzrsk1/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1319, \"height\": 295, \"label\": \"Table\"}]"
motivation: 现有世界模型难以区分自车运动和环境变化，导致预测不准确。
method: 引入场景中心预测分支生成自车无关的未来特征，通过ControlNet条件化世界模型。
result: 在自动驾驶预测基准上，COME实现了更优的长期动态预测精度。
conclusion: 场景中心解耦是提升世界模型预测质量的有效策略。
---

## Abstract
World models are critical for autonomous driving to simulate environmental dynamics and generate synthetic data.
Existing methods struggle to disentangle ego-vehicle motion (perspective shifts) from scene evolvement (agent interactions), leading to suboptimal predictions. Instead, we propose to separate environmental changes from ego-motion by leveraging the scene-centric coordinate systems. In this paper, we introduce COME: a framework that integrates scene-centric forecasting Control into the Occupancy world ModEl. Specifically, COME first generates ego-irrelevant, spatially consistent future features through a scene-centric prediction branch, which are then converted into scene condition using a tailored ControlNet. These condition features are subsequently injected into the occupancy world model, enabling more accurate and controllable future occupancy predictions. Experimental results on the nuScenes-Occ3D dataset show that COME achieves consistent and significant improvements over state-of-the-art (SOTA) methods across diverse configurations, including different input sources (ground-truth, camera-based, fusion-based occupancy) and prediction horizons (3s and 8s). For example, under the same settings, COME achieves 26.3% better mIoU metric than DOME and 23.7% better mIoU metric than UniScene. These results highlight the efficacy of disentangled representation learning in enhancing spatio-temporal prediction fidelity for world models. Code is available at https://github.com/synsin0/COME.

---

## 论文详细总结（自动生成）

# COME: 添加场景中心预测控制的占用世界模型 — 详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：现有自动驾驶世界模型在预测未来场景时，通常将**自车运动**（视角变化、遮挡）与**场景演化**（其他交通参与者交互、背景变化）糅合在一起隐式学习，导致空间一致性差，预测不够准确。例如，当前最先进方法 DOME 在 3 秒未来占用预测上的平均 mIoU 仅为 27.10，而如果在场景中心坐标系（解耦自车运动）下用一个简单的 U-Net 即可达到 39.12 mIoU，说明现有模型缺乏对空间一致性的显式控制。
- **背景**：世界模型对于自动驾驶的环境模拟、合成数据生成至关重要；占用表示因其能同时编码几何与语义信息而成为热门方向；但现有方法（如 OccWorld、DOME、UniScene 等）在解耦自车运动和场景变化方面表现不足。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：采用**分而治之**策略，将占用世界模型中的复杂时空预测分解为两部分：(1) 与自车运动无关的场景演化预测（在场景中心坐标系下进行），(2) 基于该预测的显式引导，增强原生成模型的预测一致性与可控性。
- **整体架构（三阶段）**：
  1. **占用世界模型（Occupancy World Model）**  
     - 基于扩散 Transformer（DiT），输入历史占用序列、自车状态、可选的 BEV 布局等，预测未来占用。  
     - 包含一个 Occ-VAE 将占用压缩为隐变量，再通过堆叠的空间-时间注意力块进行生成。  
     - 在模型中引入了类似 U-Net 的跳连结构，为后续 ControlNet 控制特征注入留出接口。
  2. **场景中心预测模块（Scene-centric Forecasting Module）**  
     - 将历史占用序列变换到统一坐标系（当前帧自车坐标系），消除自车运动影响。  
     - 使用简单的 U-Net 预测未来占用（在该固定坐标系下），再将结果变换回未来自车视角下的占用，并通过 Occ-VAE 编码得到场景条件特征。
  3. **COME ControlNet**  
     - 从场景预测模块提取的条件特征通过一个可训练的ControlNet（复制世界模型前半部分的时空块 + 零卷积层）转换为控制特征。  
     - 由于场景预测模块对历史未观测区域可能产生噪声，作者设计了**可见性感知掩码策略**：根据每个未来体素是否在历史中可观测，生成二进制掩码，抑制不可靠的控制特征。  
     - 掩码后的控制特征通过残差加和的方式注入到世界模型的后半部分（与跳连特征合并），实现可控生成。
- **训练流程（多阶段）**：
  - Stage 1：训练占用世界模型（含 Occ-VAE）。
  - Stage 2：训练 U-Net 场景预测模块（交叉熵损失）。
  - Stage 3：冻结其余模块，只训练 ControlNet。

## 3. 实验设计

- **数据集与基准**：
  - **主数据集**：Occ3D-nuScenes（700 训练 / 150 验证 / 150 测试序列，20 秒长，18 个类别，体素分辨率 0.4m，空间范围 ±40m×±40m×[-3.2m, 3.2m]）。
  - **额外验证**：Occ3D-Waymo（798 训练 / 202 验证序列，16 个类别，相同体素范围，降采样至 0.5s 一帧）。
  - **评估指标**：几何 IoU（整体占用率）和语义 mIoU（逐类别交并比），报告各未来时间步及其平均值。
- **对比方法**：
  - 多种现有方法：OccWorld 系列（D、T、S、F）、OccLLaMA、OccVAR、DFIT-OccWorld、Occ-LLM、RenderWorld、DOME、UniScene 等。
  - 覆盖不同输入来源（相机图像、3D 占用真值、LiDAR-相机融合）、不同轨迹来源（预测轨迹 vs 真值轨迹）、不同预测时长（3s 和 8s）。
- **实验设置变体**：
  - 相机输入 + 预测轨迹 / 真值轨迹
  - 3D 占用输入 + 预测轨迹 / 真值轨迹
  - 额外输入：BEV 布局（边界框 + 高精地图）、不同历史帧数
  - 长期预测（8 秒）
  - 不同模型大小（Small / Base）

## 4. 资源与算力

- **文中明确说明**：所有模型在 **4 块 H20 GPU** 上训练。
- Stage 1（世界模型）：batch size 128，学习率 2e-4，训练 2000 epochs。
- Stage 2（场景预测）：batch size 32，CBGS 重采样，训练 12 epochs。
- Stage 3（ControlNet）：batch size 64，学习率 1e-4，训练 1000 epochs。
- 未详细报告总训练时长，但属于中等规模生成模型的训练资源需求。

## 5. 实验数量与充分性

- **实验数量丰富**：
  - 在 nuScenes 上进行了**4种主要配置**（相机输入+预测/真值轨迹，占用输入+预测/真值轨迹，以及带 BEV 输入的变体）。
  - Waymo 数据集复现并验证了主要结果（表 2）。
  - 长期预测（8s）实验（表 3）。
  - **消融实验**详细：
    - 三阶段模型性能分解（表 4）：可见/不可见/全部体素的 mIoU/IoU。
    - 训练设置（冻结 vs 微调世界模型、模型大小）（表 5）。
    - 推理设置（去噪步数、不同预测占用来源、不同轨迹质量）（表 6）。
    - 掩码策略对比（附录表 7）。
    - 额外可视化（多个附录图）。
- **充分性与公平性**：
  - 对比方法覆盖了最先进的多种范式（自回归、扩散、语言模型辅助等），且在不同设置下均单独比较。
  - 实验设计考虑了不同上游感知质量（BEVStereo、EFFOcc）的影响。
  - 缺乏多次运行的标准差报告（受限于计算资源），但主要趋势一致且显著。
- **结论**：实验充分且相对公平，有力地支撑了方法有效性。

## 6. 主要结论与发现

- COME 在所有设置下一致且显著地优于 SOTA 方法：
  - 相机输入 + 预测轨迹：mIoU 19.11（之前最好 OccVAR 11.79），提升 62%。
  - 占用输入 + 真值轨迹：mIoU 34.23（DOME 27.10），提升 26.3%。
  - 占用 + BEV + 真值轨迹：mIoU 39.28（UniScene 31.76），提升 23.7%。
  - 在 Waymo 上同样取得类似幅度提升。
- 长期预测（8s）也全面超越 DOME（平均 mIoU 19.07 vs 15.83）。
- **关键发现**：
  - 场景中心预测模块在可见区域准确性极高（mIoU 42.74），但缺乏想象生成能力（不可见区域 mIoU 0.09）。
  - 世界模型在不可见区域表现较好（mIoU 5.81），但可见区域一致性不足。
  - ControlNet 结合二者优势：不可见区域性能提升（mIoU 5.56 vs 0.09），整体生成质量与可控性增强。
  - 轨迹质量对生成评分影响显著，但当对齐坐标后，生成场景本身受轨迹误差影响很小，说明模型对场景内容的生成是鲁棒的。

## 7. 优点

- **创新性**：明确解耦自车运动与场景变化，引入场景中心预测作为显式控制信号，思路清晰且有效。
- **实用性**：支持多种输入模态（相机、纯占用、融合）、不同轨迹来源、不同预测时长，可灵活适配实际系统。
- **设计巧妙**：可见性感知掩码解决了简单预测模块在未观测区域引入噪声的问题；ControlNet 使得原世界模型保持不变，仅添加辅助控制。
- **实验完整性**：在两大主流数据集、多种配置、充分消融下验证，结果具有说服力。
- **可复现性**：代码开源，提供了详细的训练/推理参数（附录）。

## 8. 不足与局限

- **计算复杂度增加**：引入 ControlNet 增加参数量和计算量（Base 版 2066.6 GFLOPS vs 原世界模型 1375.4 GFLOPS），但性能提升显著，不过仍不利于实时部署。
- **多阶段训练**：当前分三阶段训练，流程较繁琐；作者也承认未来可研究端到端训练以简化。
- **对轨迹误差敏感**：当使用预测轨迹时，由于坐标对不准，mIoU 相对于使用真值轨迹下降明显（尽管场景生成本身受轨迹误差影响小，但指标上耦合了轨迹精度）。作者提出了对齐评价方式，但未在主要结果中采用。
- **缺乏统计显著性**：所有结果仅单次运行，未报告误差棒或置信区间，可能存在随机波动。
- **定性-定量矛盾**：不同掩码策略下，可视化更好的模型反而数值指标较低（表 7 讨论），说明现有指标可能不完全反映生成质量，有待改进。
- **应用限制**：模型依赖历史占用输入，对于感知误差累积较敏感；且仅在有限的几个数据集上验证，泛化到更多场景（如极端天气、乡村道路）尚未证明。

（完）
