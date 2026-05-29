---
title: Video World Models with Long-term Spatial Memory
title_zh: 具有长期空间记忆的视频世界模型
authors: "Tong Wu, Shuai Yang, Ryan Po, Yinghao Xu, Ziwei Liu, Dahua Lin, Gordon Wetzstein"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=HbTxc6U1fO"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 具有长期空间记忆的世界模型，用于规划
tldr: 本文提出基于几何的长期空间记忆机制，解决视频世界模型在重复访问时场景遗忘问题。记忆模块显式存储和检索3D信息，配合定制数据集训练，在生成质量和一致性上显著优于现有方法，为具身智能中的规划与推理提供了更稳定的世界模型。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-hbtxc6u1fo/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1419, \"height\": 557, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hbtxc6u1fo/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1435, \"height\": 601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hbtxc6u1fo/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1432, \"height\": 675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hbtxc6u1fo/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1431, \"height\": 1122, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hbtxc6u1fo/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1429, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-hbtxc6u1fo/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 855, \"height\": 533, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-hbtxc6u1fo/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1479, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hbtxc6u1fo/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1454, \"height\": 294, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-hbtxc6u1fo/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1451, \"height\": 228, \"label\": \"Table\"}]"
motivation: 现有视频世界模型因上下文窗口有限，在场景重访时容易出现遗忘和矛盾。
method: 引入几何空间记忆，存储场景的3D表示，并在生成时检索相关记忆以维持一致性。
result: 在生成的视频质量和场景一致性上显著优于基线，特别是在长序列和重访场景中。
conclusion: 长期空间记忆有效增强了世界模型的时空连贯性，对强化学习和规划具有重要意义。
---

## Abstract
Emerging world models autoregressively generate video frames in response to actions, such as camera movements and text prompts, among other control signals. Due to limited temporal context window sizes, these models often struggle to maintain scene consistency during revisits, leading to severe forgetting of previously generated environments. Inspired by the mechanisms of human memory, we introduce a novel framework to enhancing long-term consistency of video world models through a geometry-grounded long-term spatial memory. Our framework includes mechanisms to store and retrieve information from the long-term spatial memory and we curate custom datasets to train and evaluate world models with explicitly stored 3D memory mechanisms. Our evaluations show improved quality, consistency, and context length compared to relevant baselines, paving the way towards long-term consistent world generation.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
现有视频世界模型（Video World Models）能够自回归地生成视频帧，并响应动作（如相机移动、文本提示等）来控制生成过程。然而，由于模型采用的临时上下文窗口大小有限（注意力机制计算复杂度随帧数二次增长），当模型在生成过程中“重访”先前已经生成过的场景区域时，常常会出现严重的“遗忘”现象——即无法保持场景的一致性，产生矛盾内容。这一问题严重制约了视频世界模型在长序列、交互式仿真等场景中的应用。

受人类记忆机制的启发，本文提出一种基于几何结构的长期空间记忆（Long-term Spatial Memory）框架，通过显式存储和检索三维信息，大幅提升了视频世界模型在长时间生成中的场景一致性。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
### 核心思想
将人类记忆划分为三种类型，并分别建模：
- **工作记忆（Working Memory）**：对应最近生成的几帧上下文，负责短期运动连续性。
- **空间记忆（Spatial Memory）**：对应场景的静态几何结构，用点云表示，通过TSDF融合过滤动态物体。
- **情景记忆（Episodic Memory）**：对应历史上少数关键帧，用于保留细节和身份信息。

### 关键技术细节
1. **空间记忆存储**：
   - 使用CUT3R在线重建每帧的深度图，并通过TSDF（Truncated Signed Distance Function）融合更新体素网格。公式如下：
     \[
     D'(v) = \frac{W(v) \cdot D(v) + w_i \cdot d_i(v)}{W(v) + w_i}, \quad W'(v) = W(v) + w_i
     \]
     其中 \(D(v)\) 和 \(W(v)\) 是体素 \(v\) 的TSDF值和权重，\(d_i(v)\) 为当前帧观测的截断符号距离。动态物体由于深度不一致会被自然抑制。
   - 静态点云被渲染成条件视频，输入生成模型。

2. **工作记忆**：
   - 简单地将最近 \(k+1\) 帧的潜在特征拼接作为条件，实现自回归生成。

3. **情景记忆**：
   - 当新生成的区域（通过掩码可见性检查）超出阈值时，将该帧作为代表性历史帧存入记忆集。
   - 在生成时，这些帧通过历史交叉注意力（Historical Cross Attention）与当前生成帧进行信息交换。

4. **模型架构**：
   - 基于CogVideoX-5B-I2V + DiT，引入条件DiT（类似ControlNet）处理静态点云渲染，并通过零初始化的线性层注入主网络。
   - 使用3D VAE编码所有输入（静态点云渲染、近期上下文帧、历史参考帧）。

### 算法流程（文字描述）
- 输入：动作（文本提示+相机轨迹）。
- 每一步自回归生成 \(N-k\) 帧，条件包括：
  - 最近 \(k=5\) 帧的潜在特征（工作记忆）。
  - 从全局静态点云沿目标轨迹渲染得到的条件视频（空间记忆）。
  - 选定的历史关键帧（情景记忆）。
- 生成后，对最新帧进行深度估计和TSDF融合，更新全局点云；若新露区域超过阈值，则将该帧加入情景记忆集。
- 迭代进行，实现无限长生成。

## 3. 实验设计：数据集、Benchmark、对比方法
### 数据集
- 从MiraData中收集视频，分割为97帧片段（前49帧为源，后48帧为目标，共享一帧过渡）。
- 使用Mega-SaM提取相机参数和每帧深度，TSDF融合源帧得到静态点云。
- 最终数据集包含90K个结构化样本，每个样本配有显式3D空间记忆和未来观察。

### 基准与对比方法
- **基线方法**：TrajectoryCrafter、DiffusionAsShader (DaS)、GEN3C、Wan2.1（Inpainting版本）。
- 测试集：从MiraData中随机选取500个未见过的序列。

### 评价指标
- **视图召回一致性**：使用正反向相机轨迹生成视频，对同一相机位姿的帧计算PSNR、SSIM、LPIPS。
- **视频质量**：FVD以及VBench的6个指标（美学质量、成像质量、时间闪烁、运动平滑度、主题一致性、背景一致性）。
- **用户研究**：邀请20名有经验的受试者对4种方法在“相机准确性”、“静态一致性”、“动态合理性”三方面进行1-4分排序（平均人类排名AHR）。

## 4. 资源与算力
论文明确说明：
- 训练基于CogVideoX-5B-I2V架构，预训练权重来自DaS。
- 视频长度49帧，分辨率480×720。
- 训练6,000个迭代，学习率2×10⁻⁵，mini-batch size为8。
- 使用8张NVIDIA A100 GPU。
- 推理时采用5帧历史上下文。

## 5. 实验数量与充分性
- **定量实验**：包含FVD、视图召回一致性（PSNR/SSIM/LPIPS）、VBench六大指标对比，以及用户研究。
- **定性实验**：展示多组可视化对比（相机准确度、视图召回一致性、动作准确性）。
- **消融实验**：分别移除工作记忆（无上下文帧）和情景记忆（无历史参考帧），在VBench上评测各组件贡献。
- **结论**：实验覆盖了主流评价维度，基线选择具有代表性（涵盖几何引导和纯视频生成方法），消融实验分析充分。用户研究采用了主观排序并报告平均排名，具有一定客观性。总体而言，实验设计较为充分、公平。

## 6. 论文的主要结论与发现
- 提出的包含工作记忆、空间记忆和情景记忆的三元记忆机制显著提升了视频世界模型的长时一致性。
- 在视图召回一致性、FVD、VBench指标以及用户研究上均全面超越所有基线。
- 消融实验表明，每种记忆组件都对最终性能有正向贡献，其中工作记忆对运动连贯性不可或缺，情景记忆有助于保留远处细节。
- 尽管PSNR等绝对指标仍不完美（说明精确记忆所有视觉细节仍具挑战），但相比基线有了大幅提升。

## 7. 优点：方法或实验设计上的亮点
- **创新性**：首次将人类记忆的三类机制系统引入视频世界模型，并设计了对应的显式存储与检索方式。
- **技术完善性**：空间记忆使用TSDF融合有效分离静态/动态，情景记忆通过自适应触发器存储关键帧，架构上采用条件DiT + 历史交叉注意力。
- **数据集构建**：为解决“记忆”任务，专门构建了附带3D点云监督的大规模视频数据集，为后续研究提供资源。
- **评估全面**：不仅使用自动化指标（FVD、PSNR等），还设计了正反向轨迹的视图召回一致性测试，并开展了用户研究，从多个角度验证方法有效性。

## 8. 不足与局限
- **存储缺陷**：TSDF融合算法在相机姿态剧烈变化（如快速大幅度转向）时，重建质量下降，导致点云稀疏、产生伪影（论文中Fig.6展示失败案例）。
- **遗忘与漂移**：本文主要解决场景一致性（重访一致），但未处理误差累积导致的质量漂移（drift）。
- **实验覆盖有限**：仅在MiraData上测试，未评估其他长视频或真实世界场景。用户研究受试者仅20人，统计显著性未明确报告。
- **计算开销**：自回归生成过程中每一步都需要深度估计、TSDF融合和点云渲染，推理效率较低。
- **应用限制**：目前主要针对静态场景一致性，处理高度动态场景（如大量运动物体）的能力有待增强。

（完）
