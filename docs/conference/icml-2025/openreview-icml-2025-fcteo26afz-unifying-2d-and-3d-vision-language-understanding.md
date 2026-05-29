---
title: Unifying 2D and 3D Vision-Language Understanding
title_zh: 统一2D和3D视觉语言理解
authors: "Ayush Jain, Alexander Swerdlow, Yuzhou Wang, Sergio Arnaud, Ada Martin, Alexander Sax, Franziska Meier, Katerina Fragkiadaki"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=FcTeo26AfZ"
tags: ["query:wm-vla-sa"]
score: 7.0
evidence: 统一2D和3D视觉语言理解以支持具身系统
tldr: 该论文针对3D视觉语言学习数据稀缺的问题，提出UniVLG统一架构，桥接2D预训练模型与3D传感数据。通过共享语言条件掩码解码器实现跨模态目标定位，并利用2D到3D提升策略增强3D性能。该方法可直接为视觉语言动作模型提供更强的3D场景理解能力，支持具身机器人抓取、导航等任务。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-fcteo26afz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1779, \"height\": 773, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fcteo26afz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1778, \"height\": 934, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fcteo26afz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1776, \"height\": 1332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fcteo26afz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1776, \"height\": 1254, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fcteo26afz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1776, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-fcteo26afz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1769, \"height\": 2068, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1748, \"height\": 687, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 889, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 878, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 868, \"height\": 310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 441, \"height\": 148, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 418, \"height\": 144, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 868, \"height\": 161, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 870, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 381, \"height\": 149, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 874, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 876, \"height\": 393, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 853, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 891, \"height\": 288, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1528, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1509, \"height\": 383, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1397, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-fcteo26afz/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1764, \"height\": 320, \"label\": \"Table\"}]"
motivation: 3D视觉语言数据集稀缺限制了具身系统的理解能力。
method: 提出UniVLG架构，从2D预训练模型初始化，共同训练2D和3D数据，并引入语言条件掩码解码器。
result: 在多个3D视觉语言任务上取得最优性能，同时保持2D任务能力。
conclusion: 统一2D和3D理解可显著提升具身智能体的视觉语言能力，是VLA模型的重要基础。
---

## Abstract
Progress in 3D vision-language learning has been hindered by the scarcity of large-scale 3D datasets. We introduce UniVLG, a unified architecture for 2D and 3D vision-language understanding that bridges the gap between existing 2D-centric models and the rich 3D sensory data available in embodied systems. Our approach initializes most model weights from pre-trained 2D models and trains on both 2D and 3D vision-language data. We propose a novel language-conditioned  mask decoder shared across 2D and 3D modalities to ground objects effectively in both RGB and RGB-D images, outperforming box-based approaches. To further reduce the domain gap between 2D and 3D, we incorporate 2D-to-3D lifting strategies, enabling UniVLG to utilize 2D data to enhance 3D performance. With these innovations, our model achieves state-of-the-art performance across multiple 3D vision-language grounding tasks, demonstrating the potential of transferring advances from 2D vision-language learning to the data-constrained 3D domain. Furthermore, co-training on both 2D and 3D data enhances performance across modalities without sacrificing 2D capabilities. By removing the reliance on 3D mesh reconstruction and ground-truth object proposals, UniVLG sets a new standard for realistic, embodied-aligned evaluation. Code and additional visualizations are available at https://univlg.github.io.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：3D视觉语言学习受限于大规模3D数据集稀缺且标注成本高昂，导致现有系统多依赖2D视觉语言模型，无法充分利用深度传感器和自运动提供的3D信息。
- **研究动机**：尽管3D模型在数据充足时优于2D模型，但实际中缺乏类似CLIP的高性能预训练3D编码器。即使扩增3D训练数据也不是唯一途径，可以通过迁移2D预训练知识和联合训练2D/3D数据来弥补这一差距。
- **整体含义**：论文提出一种统一2D与3D的视觉语言模型UniVLG，使得具身系统能同时利用稀疏的3D标注和丰富的2D数据，在不牺牲2D性能的前提下显著提升3D语言理解能力，并推动更贴近实际（传感器点云而非网格重建）的评估标准。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：共享所有参数处理2D RGB图像和3D RGB-D图像序列，通过2D-to-3D深度提升（lifting）将2D图像转化为3D点云，利用统一的语言条件掩码解码器输出分割掩码，并在训练时协同2D/3D数据。
- **关键技术细节**：
  - **视觉编码器**：使用预训练的DINOv2 ViT（冻结）提取2D图像特征，然后叠加3D相对注意力层（k-NN注意力+相对位置嵌入），利用点云XYZ坐标作为位置编码，融合多视角信息。
  - **语言编码器**：采用Jina-CLIP（支持长序列），生成文本令牌。
  - **语言条件掩码解码器**：借鉴Mask2Former，但关键创新在于**在解码器层中更新视觉特征**（通过交叉注意力关注查询和文本令牌），这对于3D指代性接地至关重要。解码器迭代细化一组可学习查询（object queries）以及视觉令牌，最终通过查询与视觉令牌的点积生成分割掩码。
  - **文本解码器**：使用预训练T5解码器，从细化后的查询生成问题答案。
  - **关键公式**：迭代过程描述为：  
    X(0) = [Q(0); T]; 每层包含MaskedCrossAttention、SelfAttention，并更新视觉令牌V。  
    损失函数：L_total = λ_mask L_mask + λ_text L_text + λ_box L_box + λ_gen L_gen，其中L_box是新提出的**掩码边界框损失**（通过掩码计算包围框并用L1+GIoU监督），用于惩罚远端点和多实例粘连。
- **2D-to-3D提升策略**：对2D单目图像以50%概率使用预测的3D点云（如MoGe），使模型所有参数在2D/3D间完全共享；测试时2D图像保持原空间以避免噪声影响。

### 3. 实验设计：使用的数据集/场景、基准测试、对比方法

- **数据集与场景**：
  - 3D指代性接地：SR3D、NR3D（ReferIt3D）、ScanRefer（均基于ScanNet场景）。
  - 3D问答：ScanQA、SQA3D。
  - 3D实例分割：ScanNet200、Matterport3D。
  - 2D指代性接地：RefCOCO、RefCOCO+、RefCOCOg。
  - 2D语义分割：COCO（用于辅助训练）。
  - 外域评估：L3DD（涵盖ScanNet++、HM3D、ARKitScenes）。
  - 泛化测试：AI2-THOR模拟器（2D-3D泛化实验）。
- **基准测试指标**：
  - 3D指代性接地：Top-1准确率（IoU@0.25/0.5/0.75），分为Det（无GT框）和GT（有GT框）设置；还提供了掩码mAP、以传感器点云（Sensor PC） vs 网格点云（Mesh PC）的对比。
  - 3D问答：Exact Match@1，以及BLEU-1、ROUGE、METEOR、CIDEr。
  - 2D指代性接地：Top-1准确率。
  - 3D实例分割：mAP、mAP25（语言提示设置）。
- **对比方法**：两阶段方法（3D-VisTA、PQ3D）、单阶段方法（BUTD-DETR、ODIN）、LLM方法（3D-LLM、NaviLLM）、2D基线（LAVT、X-Decoder）等。

### 4. 资源与算力

- 论文明确说明：**训练在32块NVIDIA A100 80G GPU上，采用数据并行，有效批次大小为64**。
- 参数量：可训练参数108M，加上冻结的文本编码器（220M）和图像编码器（304M），总计约632M参数。
- 推理速度：90帧场景约1050ms，VRAM约15GB（A100）。
- 未提及总训练时长或具体迭代次数。

### 5. 实验数量与充分性

- **实验数量**：相当充分，覆盖多个任务、多个数据集、多种设置。
  - 3D指代接地：在SR3D、NR3D、ScanRefer（Mesh和Sensor两种点云）上报告Det和GT结果，并与6种以上基线对比。
  - 3D问答：在ScanQA、SQA3D上报告EM@1及额外指标。
  - 2D指代接地：在RefCOCO/+/g上评估，并与4种基线对比。
  - 3D实例分割：在ScanNet200、Matterport3D上评估（语言提示设置）。
  - 外域泛化：在L3DD上4个子集的评估。
  - 2D-3D泛化测试：在AI2-THOR模拟器上的特殊实验。
  - **消融实验**（表5-8）：包含解码头类型（框 vs 掩码）、查询类型（参数/非参数）、是否更新视觉特征、是否使用预训练2D权重、是否加框损失、2D训练策略（有无2D-3D提升）等，共约6-7组消融，每组分多个子实验。
  - 鲁棒性分析：对姿态噪声和深度噪声的灵敏度测试。
- **充分性与公平性**：
  - 大部分对比方法在公平条件下重新训练或评估（例如在传感器点云上重新训练3D-VisTA、BUTD-DETR），排除了网格后处理带来的不公平优势。
  - 消融实验针对各个关键设计做了控制变量，验证了各组件必要性。
  - 但部分高级基线（如PQ3D）因无法在传感器点云上复现而未做同等对比，可能略有遗憾，但仍报告了网格上的性能以供参考。
  - 总体而言，实验设计严谨、覆盖全面、消融充分，结论可信。

### 6. 论文的主要结论与发现

- **主要结论**：
  1. UniVLG在3D指代性接地任务上大幅超越现有方法（在Det设置下提升15%以上），且无需GT对象建议，适用于真实传感器点云。
  2. 联合2D+3D训练比单独3D训练显著提升3D性能，且不损害2D性能。
  3. 掩码解码头优于框解码头，尤其是在高IoU阈值下（Acc@75提升巨大）。
  4. 解码时更新视觉特征（交叉注意力于查询和文本）是掩码解码成功的关键。
  5. 提出的掩码边界框损失有效改善了掩码紧致性和准确性。
  6. 2D-to-3D提升策略让2D数据真正为3D任务所用，避免了模型过拟合到单一模态。
- **关键发现**：即使在数据受限的3D领域，通过迁移2D预训练知识和共享训练，可以显著提升3D推理能力，而不必依赖大规模3D数据扩增。

### 7. 优点：方法或实验设计上的亮点

- **方法亮点**：
  - 统一2D/3D架构：所有参数共享，仅通过位置编码（2D网格 vs 3D坐标）区分模态，天然支持2D和3D数据联合训练。
  - 语言条件掩码解码器：创新的特征更新机制使模型能区分同类别不同实例，提升指代性接地精度。
  - 2D-to-3D提升：首次将单目深度估计集成到统一模型中，实现从2D图像到3D点云的“零成本”增强。
  - 掩码边界框损失：创新地利用掩码派生框进行辅助监督，解决掩码预测的常见失败模式。
- **实验亮点**：
  - 首次在传感器点云上系统评估3D指代性接地方法，设立更现实的基准。
  - 包含外域泛化和2D-3D泛化测试，验证模型鲁棒性。
  - 消融实验覆盖设计空间关键维度，结论清晰。
  - 提供开源代码和可视化，可复现性强。

### 8. 不足与局限

- **实验覆盖不足**：
  - 未在真实机器人/实际部署场景中测试（仅在室内扫描数据集上）。
  - 2D数据仅限于COCO和RefCOCO系列，未利用更大规模2D VLM数据集（如SA-1B、LAION-5B），尽管论文认为这是可行方向。
  - 部分基线（如PQ3D）仅报告了网格点云结果，传感器点上无法复现，对比可能不完全公平。
- **方法局限**：
  - **失败模式**：存在三种系统性错误：① 掩码包含远端离群点；② 同一类别多个实例被预测为一个；③ 语言理解失败。这些错误虽被部分缓解但未完全解决。
  - **依赖高质量2D预训练**：性能高度依赖DINOv2和Jina-CLIP，在新的视觉域可能泛化受限。
  - **静态场景假设**：当前设计针对静态3D场景，不适用于动态环境（如移动机器人、视频流）。
  - **算力需求较高**：训练需要32×A100，推理对15帧场景约1秒，实时性对低算设备可能有挑战。
- **偏差与伦理风险**：文中简短提及，但未深入探讨预训练2D模型中的偏见可能被迁移到3D任务，以及潜在监视或隐私风险。总体而言，论文承认需要未来工作来缓解偏见和提升透明度。

（完）
