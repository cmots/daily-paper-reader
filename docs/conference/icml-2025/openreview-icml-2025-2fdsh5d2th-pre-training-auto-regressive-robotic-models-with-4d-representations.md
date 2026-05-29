---
title: Pre-training Auto-regressive Robotic Models with 4D Representations
title_zh: 使用4D表示预训练自回归机器人模型
authors: "Dantong Niu, Yuvan Sharma, Haoru Xue, Giscard Biamby, Junyi Zhang, Ziteng Ji, Trevor Darrell, Roei Herzig"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=2FDsh5D2Th"
tags: ["query:wm-vla-sa"]
score: 4.0
evidence: 使用4D表示预训练机器人模型以建模世界
tldr: 该论文提出ARM4R，利用从人类视频中学习的4D表示（如3D点跟踪）来预训练自回归机器人模型，克服了传统机器人预训练需要昂贵标注的问题。实验表明该方法在多种机器人任务上提升了泛化能力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-2fdsh5d2th/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1767, \"height\": 908, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2fdsh5d2th/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1608, \"height\": 903, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2fdsh5d2th/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1747, \"height\": 584, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2fdsh5d2th/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1715, \"height\": 1151, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2fdsh5d2th/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1762, \"height\": 1914, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2fdsh5d2th/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 859, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2fdsh5d2th/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1758, \"height\": 756, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2fdsh5d2th/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 857, \"height\": 649, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-2fdsh5d2th/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1659, \"height\": 415, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2fdsh5d2th/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1721, \"height\": 609, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2fdsh5d2th/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 866, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2fdsh5d2th/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 864, \"height\": 251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2fdsh5d2th/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 881, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2fdsh5d2th/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 871, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2fdsh5d2th/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 857, \"height\": 247, \"label\": \"Table\"}]"
motivation: 机器人预训练面临标注数据昂贵和表示能力不足的挑战。
method: 通过从视频中提取3D点跟踪表示并提升到4D空间，预训练自回归机器人模型。
result: 在多个机器人基准上取得更好的泛化性能。
conclusion: 4D表示能有效提升机器人模型预训练效果。
---

## Abstract
Foundation models pre-trained on massive unlabeled datasets have revolutionized natural language and computer vision, exhibiting remarkable generalization capabilities, thus highlighting the importance of pre-training. Yet, efforts in robotics have struggled to achieve similar success, limited by either the need for costly robotic annotations or the lack of representations that effectively model the physical world. In this paper, we introduce ARM4R, an **A**uto-regressive **R**obotic **M**odel that leverages low-level **4**D **R**epresentations learned from human video data to yield a better pre-trained robotic model. Specifically, we focus on utilizing 3D point tracking representations from videos derived by lifting 2D representations into 3D space via monocular depth estimation across time. These 4D representations maintain a shared geometric structure between the points and robot state representations up to a linear transformation, enabling efficient transfer learning from human video data to low-level robotic control. Our experiments show that ARM4R can transfer efficiently from human video data to robotics and consistently improves performance on tasks across various robot environments and configurations.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机与背景）

- **研究动机**：在自然语言和计算机视觉领域，大规模预训练基础模型已取得巨大成功，但在机器人领域，预训练仍面临瓶颈。主要障碍包括：（1）大规模机器人标注数据稀缺且收集成本高昂；（2）现有机器人预训练方法使用的表示未能有效建模物理世界（如缺乏几何和空间理解）。因此，如何利用丰富的未标注人类视频数据，学习能迁移到机器人控制的低层级表示，成为关键问题。
- **整体含义**：本文尝试通过从人类视频中学习4D表示（3D点轨迹随时间的变化），实现从人类数据到机器人数据的有效迁移，从而降低对机器人数据的依赖，提升机器人模型的泛化能力和预训练效果。

## 2. 方法论：核心思想、技术细节与算法流程

- **核心思想**：利用单目深度估计将2D像素点提升到3D空间，并跨时间跟踪这些3D点，形成4D表示（3D空间+时间）。这种表示与机器人状态表示之间存在线性变换下的共享几何结构，因此可以高效地从人类视频数据迁移到机器人低级控制。
- **关键技术细节**：
  - **4D场景表示**：从视频第一帧定义g×g网格点（n=g²个点），跟踪这些点在后续帧中的3D坐标（相机坐标系下）。
  - **模型架构**：自回归模型，输入包括语言指令、当前图像、当前3D点坐标（或机器人状态），输出下一时刻的3D点坐标（或下一状态）。采用**冻结的CLIP文本编码器**、**预训练的Vision Transformer (ViT-Base)**（通过CrossMAE在ImageNet+OpenX上预训练）、**2层MLP**编码点坐标、**注意力池化**融合图像和点特征、**随机初始化的因果Transformer**进行自回归预测。损失函数为L1距离。
  - **三阶段训练**：
    - **Stage 1：人类视频预训练**。在Epic-Kitchens100数据集（约75K视频）上训练，使用现成的SpatialTracker生成伪3D点轨迹标注，模型学习预测下一时刻的3D点坐标。
    - **Stage 2：机器人场景3D点跟踪微调**。在目标机器人设置的小规模视频（约1-2K演示）上对同一任务进行微调，弥合人类与机器人之间的分布差异。
    - **Stage 3：机器人控制微调**。将点坐标替换为机器人本征状态（如末端执行器位姿+夹爪状态），模型预测下一状态。训练中同时预测多个未来步，但执行时仅使用第一步。
- **算法流程**：第1、2阶段：`π(l, i_{t-C+1:t}, p_{t-C+1:t}) → p_{t+1}`；第3阶段：`π(l, i_{t-C+1:t}, s_{t-C+1:t}) → s_{t+1}`。

## 3. 实验设计：数据集、Benchmark与对比方法

- **仿真环境**：RLBench（12个任务，如开抽屉、关罐子、推按钮等）。使用190个成功演示/变体，25个episode/任务评估，5个随机种子。对比方法：Image-BC (ViT)、C2FARM-BC、ManiGaussian、LLARVA、PerAct。
- **真实机器人**：
  - **Kinova Gen3（7-DoF）**：13个任务，分5类（pick, destack, stack, pick&place, push）。25个episode/任务，3个种子。对比方法：ATM、LLARVA、π0-FAST、OpenVLA。
  - **Franka Emika Panda（7-DoF）**：3个cube任务（pick, stack, destack），用于跨机器人泛化实验。对比方法：MVP、RPT、Octo、ATM、OpenVLA、LLARVA。
- **消融实验**：评估Stage 1（人类视频预训练）和Stage 2（机器人视频微调）的贡献，在Kinova上对pick, destack, stack三个任务进行消融。
- **鲁棒性实验**：在动态环境（物体移动）、光照变化、背景干扰、桌面干扰等条件下测试。
- **跨机器人泛化**：从Kinova视频微调后迁移到Franka机器人。

## 4. 资源与算力

- **训练**：使用4张NVIDIA A6000 GPU进行训练。
- **评估**：单张NVIDIA A6000 GPU。
- 论文未明确说明训练总时长，但提及各阶段训练epoch数：Stage 1为520 epoch，Stage 2（未明确epoch数），Stage 3训练至损失收敛（10-50 epoch不等）。未提及具体耗时。

## 5. 实验数量与充分性

- **数量**：实验覆盖了仿真（12任务）、真实Kinova（13任务）、真实Franka（3任务），以及多组消融（4种配置）、鲁棒性（4种条件）、跨机器人（多种预训练组合）等，总计超过20组对比实验。
- **充分性与公平性**：
  - 对比方法包括基于2D点跟踪（ATM）、VLA（LLARVA, OpenVLA）、3D体素（PerAct）、动态高斯（ManiGaussian）等，覆盖主流方向。
  - 消融实验揭示了各阶段贡献，且控制变量合理。
  - 公平性方面，对比方法均使用各自官方或推荐的设置，但未提及是否完全对齐训练数据量（如OpenVLA预训练于OpenX，而ARM4R仅使用人类视频，数据量差异较大）。跨机器人实验中，从Kinova迁移到Franka时，验证了不同机器人设置下的泛化性。
- **潜在偏差**：部分RLBench任务被修改（如增加变体），可能导致与原始PerAct设置不完全一致。真实任务可能较简单（如仅操作简单几何物体），未见复杂长程操作。

## 6. 主要结论与发现

- ARM4R在RLBench上平均成功率59.47%，超过所有对比方法（PerAct 55.33%，LLARVA 48.33%等）。
- 在真实Kinova上平均成功率83.1%，远超OpenVLA（37.2%）和ATM（6.4%）。
- 仅使用人类视频预训练（Stage 1）即可带来显著提升，且预训练在人类数据上的效果优于部分在机器人数据上预训练的方法（如OpenVLA）。
- 4D表示（3D点跟踪）相比2D点跟踪（ATM）更有效，能提供更好的空间理解。
- 模型展现出跨机器人泛化能力，从Kinova迁移到Franka时，加入人类及Kinova视频预训练相比仅使用机器人控制微调，性能提升约19.6%。
- 模型对动态环境、光照变化、背景干扰具有较强鲁棒性，但对桌面干扰物鲁棒性下降。

## 7. 优点

- **方法创新**：提出利用3D点跟踪作为预训练任务，巧妙地将人类视频中的低层级物理信息与机器人控制建立联系（通过线性变换的几何共享结构）。
- **数据效率**：仅使用人类视频预训练，无需大规模机器人数据集，即可获得优于部分需机器人数据预训练的方法。
- **架构简洁**：自回归模型结构清晰，三阶段训练流程实用，易于复现。
- **实验全面**：覆盖多种仿真和真实机器人场景，消融、鲁棒性、跨机器人泛化等实验充分。
- **开源可复现**：论文提供了项目网站和代码（预计）。
- **实物验证**：在两种不同机器人（Kinova、Franka）上均取得优异性能，泛化性得到验证。

## 8. 不足与局限

- **表示局限**：3D点跟踪在相机坐标系下进行，无法区分物体运动与相机运动（尤其是人类视频中的自我中心运动），限制了模型对世界坐标系下物理规律的学习。
- **依赖伪标签**：预训练依赖现成3D点跟踪器（SpatialTracker）生成的伪标注，其质量影响预训练效果。
- **网格采样**：固定均匀网格点采样，缺乏自适应重点区域（如小物体或关键交互点）的聚焦能力。
- **任务覆盖**：真实任务均为桌面级简单操作（拾取、堆叠、推按），未涉及精细操作、长程多步任务或动态非刚性物体。
- **模拟器修改**：RLBench实验中部分任务被修改（如增加变体数），与原始PerAct设置不完全一致，可能影响公平比较。
- **偶发失败模式**：模型在处理不自然的旋转（如放刀任务）和需要极高精度的插入任务（如拧灯泡）时表现不佳。
- **未评估大规模真实场景**：未在复杂、杂乱、多干扰的真实环境中测试，也未考虑人机协作或动态物体互动。

（完）
