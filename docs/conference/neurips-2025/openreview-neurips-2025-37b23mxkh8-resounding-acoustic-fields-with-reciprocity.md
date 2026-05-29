---
title: Resounding Acoustic Fields with Reciprocity
title_zh: 利用互易性重新合成声场
authors: "Zitong Lan, Yiduo Hao, Mingmin Zhao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=37b23mxKH8"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 基于物理的声场学习与渲染方法
tldr: 针对虚拟环境中实现沉浸式听觉体验需要灵活声场建模的问题，提出“重新合成”任务，即从稀疏发射器位置估计任意发射位置的房间脉冲响应。利用互易性原理，通过交换发射器和听音器姿态生成密集虚拟发射位置，并采用自监督学习方法处理增益模式差异。实验表明该方法能高效学习声场，支持动态源位置的沉浸式音频渲染。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-37b23mxkh8/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1371, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-37b23mxkh8/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1297, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-37b23mxkh8/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1438, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-37b23mxkh8/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1363, \"height\": 995, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-37b23mxkh8/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 473, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-37b23mxkh8/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 629, \"height\": 325, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-37b23mxkh8/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 803, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-37b23mxkh8/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 856, \"height\": 200, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-37b23mxkh8/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1456, \"height\": 734, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-37b23mxkh8/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 731, \"height\": 444, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-37b23mxkh8/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 907, \"height\": 437, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-37b23mxkh8/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1390, \"height\": 467, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-37b23mxkh8/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 706, \"height\": 388, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-37b23mxkh8/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1388, \"height\": 478, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-37b23mxkh8/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 731, \"height\": 541, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-37b23mxkh8/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 553, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-37b23mxkh8/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 947, \"height\": 339, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-37b23mxkh8/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 729, \"height\": 573, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-37b23mxkh8/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 664, \"height\": 541, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-37b23mxkh8/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 818, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-37b23mxkh8/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 572, \"height\": 415, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-37b23mxkh8/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 583, \"height\": 345, \"label\": \"Table\"}]"
motivation: 实现虚拟环境中支持动态声源位置的沉浸式听觉体验。
method: 利用互易性原理和自监督学习从稀疏测量中估计房间脉冲响应。
result: 有效生成了密集虚拟发射位置，实现了准确的声场估计。
conclusion: 提出了一种基于互易性的物理启发式声场学习方法。
---

## Abstract
Achieving immersive auditory experiences in virtual environments requires flexible sound modeling that supports dynamic source positions.
In this paper, we introduce a task called resounding, which aims to estimate room impulse responses at arbitrary emitter location from a sparse set of measured emitter positions, analogous to the relighting problem in vision.
We leverage the reciprocity property and introduce Versa, a physics-inspired approach to facilitating acoustic field learning.
Our method creates physically valid samples with dense virtual emitter positions by exchanging emitter and listener poses.
We also identify challenges in deploying reciprocity due to emitter/listener gain patterns and propose a self-supervised learning approach to address them.
Results show that Versa substantially improve the performance of acoustic field learning on both simulated and real-world datasets across different metrics.
Perceptual user studies show that Versa can greatly improve the immersive spatial sound experience.

---

## 论文详细总结（自动生成）

好的，这是根据您提供的论文内容生成的中文总结，严格按照要求的格式和要点组织。

## 论文核心问题与整体含义（研究动机和背景）

- **问题**：在AR/VR等虚拟环境中，实现沉浸式听觉体验需要支持动态声源位置。现有神经声场建模方法通常假设声源（发射器）固定，或需要部署大量扬声器（数百上千个）才能泛化到新的发射器位置。
- **实际障碍**：扬声器体积大、功耗高、易产生干扰，难以像麦克风（体积小、成本低）那样密集部署。因此，从少量发射器位置（＜10个）出发，估计任意位置发射器产生的声场成为一个关键挑战。
- **任务定义**：作者提出了“重新合成”任务——类比视觉中的“重新照明”，即根据稀疏的测量发射器位置，估计任意发射器位置处的房间脉冲响应，从而实现对动态声源的灵活控制。

## 论文提出的方法论

- **核心思想**：利用声学中的 **互易性原理**——交换发射器和听音器的角色，声波传播路径反向但累积传播效应不变（在理想条件下脉冲响应应相同）。作者将此物理原理转化为机器学习训练策略。
- **关键技术细节**：
  - **Versa-ELE（发射器-听音器交换）**：作为一种数据增强方法，将训练样本中的发射器和听音器位置互换，并强制模型预测相同的脉冲响应。由于听音器位置可以密集采样，这一操作相当于将密集的麦克风位置转化为密集的虚拟扬声器位置，有效缓解了发射器稀疏的问题。该方法要求发射器与听音器的增益模式相同（如全向）。
  - **Versa-SSL（自监督学习）**：用于处理发射器和听音器增益模式不同的情况。通过解耦增益模式与声传播效应，设计一个自监督一致性约束：将发射器和听音器的增益模式都替换为共享增益模式后，交换位置得到的脉冲响应应保持一致。具体实现基于声学子体渲染（AVR）框架，通过两阶段训练（先拟合真实脉冲响应，再施加互易性一致性约束）。
- **算法流程（文字说明）**：
  1. 训练数据包含(发射器位置, 听音器位置, 发射器方向, 听音器方向, 脉冲响应)。
  2. **Versa-ELE**：对每个样本，生成交换后的新样本（听音器位置→发射器位置，发射器位置→听音器位置，方向互换，脉冲响应保持不变），加入训练集。
  3. **Versa-SSL**（仅用于AVR模型）：
     - 第一阶段：正常训练AVR模型拟合真实脉冲响应。
     - 第二阶段：估计发射器增益模式；将听音器增益模式替换为发射器增益模式；交换位置后，强制模型对交换前后的脉冲响应预测一致（自监督损失）。

## 实验设计

- **数据集**：
  - **模拟数据集**：使用AcoustiX模拟器在iGibson的三个场景（厨房、会议室、办公室）上生成，分为“相同增益模式”（AcoustiX-Same）和“不同增益模式”（AcoustiX-Diff）两个批次。每个场景训练用5个发射器位置。
  - **真实世界数据集**：MeshRIR（7个发射器位置，接近全向增益）、RAF（4个发射器位置，不同增益模式）、GWA（5个发射器位置，混合射线/波动模拟）。
- **Benchmark**：对比了多种基线方法——线性插值、最近邻、DiffRIR、INRAS、NAF、AV-NeRF、AVR。
- **评估指标**：T60（混响时间）、C50（清晰度）、EDT（早期衰减时间）、STFT（多分辨率短时傅里叶变换误差）、Amp.、Env.等。
- **补充验证**：在真实环境中（办公室、会议室、厨房）收集20对互换位置脉冲响应，验证互易性近似成立（配对脉冲响应的误差比非配对小约10倍）。

## 资源与算力

- **文中明确说明**：所有模型在 **NVIDIA L40s GPU** 上训练 **200个epoch**。
- **未明确说明**：未给出具体使用的GPU数量、总训练时长或内存消耗。但提到batch size为64（NAF、INRAS、AV-NeRF）或4（AVR）。

## 实验数量与充分性

- **实验数量**：论文报告了多个数据集（3个模拟场景+3个真实数据集）上的定量结果，以及消融实验（不同发射器数量、不同监听器数量、对比其他SSL损失、验证互易性学习、置换不变结构等）。还包含感知用户研究（15名参与者，8个音视频片段）。
- **充分性**：实验覆盖了多种基线方法、不同增益模式条件、不同数据规模，并且通过消融验证了各组件贡献。感知用户研究提供了主观证据。实验设计较为全面，能够支撑主要结论。
- **公平性**：对比方法均使用公开或复现的实现，评估指标标准。但部分实验（如消融）未报告误差条（作者说明计算成本过高），可能影响统计显著性判断。

## 主要结论与发现

- Versa-ELE作为模型无关的数据增强，可显著提升所有神经声场模型在重新合成任务上的性能：平均C50改进34%，STFT改进31%。
- Versa-SSL在AVR模型上进一步提升了性能：相比Versa-ELE，C50改进24%，STFT改进48%；相比原始AVR，C50改进49%，STFT改进66%。
- 感知用户研究表明，93.3%的参与者认为Versa-ELE优于原始基线，85%认为Versa-SSL优于Versa-ELE，在音量、方向感和整体相似度方面均有改善。
- 互易性验证实验表明，训练后的模型确实学到了互易性（交换位置后预测误差更小）。

## 优点

- **物理启发性**：将互易性原理转化为数据增强和自监督约束，方法简单有效，可迁移到其他波动现象（光、RF）。
- **通用性**：Versa-ELE可即插即用于现有神经声场模型（NAF、INRAS、AV-NeRF、AVR），无需修改模型架构。
- **解决了增益模式不对称问题**：Versa-SSL通过解耦增益模式，将互易性推广到更实际的异质设备场景。
- **稀疏发射器设置下效果显著**：仅用5个发射器位置即可获得明显提升，降低了实际部署成本。

## 不足与局限

- **仍需较密集的听音器位置**：方法依赖麦克风阵列的密集采样，在无法部署大量麦克风的场景中可扩展性受限。
- **声学模型假设**：基于几何声学（射线追踪），对低频声（波长与场景尺寸可比）的准确性可能不足。
- **未探索零样本泛化**：目前每场景需单独训练，未结合视觉信息或更广泛的声学先验进行跨场景泛化。
- **实验代价**：部分消融实验未报告误差条，结论稳健性有待进一步验证。
- **计算资源**：训练200个epoch在L40s上进行，对资源的要求较高，但未与其他方法的时间开销对比。

（完）
