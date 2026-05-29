---
title: "BeliefMapNav: 3D Voxel-Based Belief Map for Zero-Shot Object Navigation"
title_zh: BeliefMapNav：基于3D体素信念图的零样本物体导航
authors: "Zibo Zhou, Yue Hu, Lingkai Zhang, Zonglin Li, Siheng Chen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=7AMriz7I3K"
tags: ["query:wm-vla-sa"]
score: 7.0
evidence: 3D体素信念图用于零样本物体导航和规划
tldr: 针对零样本物体导航中代理缺乏全局环境理解和空间推理的问题，提出基于3D体素信念图的方法。该方法在体素网格中建模目标存在的先验分布，使代理能够进行全局而非贪婪的导航决策。结合大型语言模型和视觉语言模型的语义推理，在多个基准任务上实现了显著优于现有方法的成功率。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-7amriz7i3k/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1451, \"height\": 726, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7amriz7i3k/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1383, \"height\": 642, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7amriz7i3k/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1359, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7amriz7i3k/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1453, \"height\": 173, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7amriz7i3k/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1447, \"height\": 564, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7amriz7i3k/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 645, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7amriz7i3k/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 632, \"height\": 462, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7amriz7i3k/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1000, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7amriz7i3k/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 851, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7amriz7i3k/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1365, \"height\": 669, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7amriz7i3k/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1363, \"height\": 673, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7amriz7i3k/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1362, \"height\": 674, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-7amriz7i3k/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1361, \"height\": 1264, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-7amriz7i3k/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 929, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7amriz7i3k/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 793, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7amriz7i3k/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 683, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7amriz7i3k/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 469, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7amriz7i3k/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 663, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7amriz7i3k/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 688, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-7amriz7i3k/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 417, \"height\": 236, \"label\": \"Table\"}]"
motivation: 现有零样本导航方法贪心选择目标，缺乏全局环境理解和空间推理。
method: 提出3D体素信念图，估计目标存在概率分布，结合语言和视觉模型进行全局规划。
result: 在零样本物体导航基准上显著提高了成功率。
conclusion: 为机器人导航提供了一种有效的环境表示和推理方法。
---

## Abstract
Zero-shot object navigation (ZSON) allows robots to find target objects in unfamiliar environments using natural language instructions, without relying on pre-built maps or task-specific training. Recent general-purpose models, such as large language models (LLMs) and vision-language models (VLMs), equip agents with semantic reasoning abilities to estimate target object locations in a zero-shot manner. However, these models often greedily select the next goal without maintaining a global understanding of the environment and are fundamentally limited in the spatial reasoning necessary for effective navigation. To overcome these limitations, we propose a novel 3D voxel-based belief map that estimates the target’s prior presence distribution within a voxelized 3D space. This approach enables agents to integrate semantic priors from LLMs and visual embeddings with hierarchical spatial structure, alongside real-time observations, to build a comprehensive 3D global posterior belief of the target’s location. Building on this 3D voxel map, we introduce BeliefMapNav, an efficient navigation system with two key advantages: i) grounding LLM semantic reasoning within the 3D hierarchical semantics voxel space for precise target position estimation, and ii) integrating sequential path planning to enable efficient global navigation decisions. Experiments on HM3D and HSSD benchmarks show that BeliefMapNav achieves state-of-the-art (SOTA) Success Rate (SR) and Success weighted by Path Length (SPL), with a notable 9.7 SPL improvement over the previous best SR method, validating its effectiveness and efficiency.

---

## 论文详细总结（自动生成）

### 论文详细中文总结

#### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：零样本物体导航（ZSON）要求机器人在未见过的环境中仅凭自然语言指令寻找目标物体，无需预建地图或任务特定训练。现有基于大语言模型（LLM）和视觉语言模型（VLM）的方法虽然具备语义推理能力，但通常**贪心地选择下一个目标点**，缺乏对环境的全局理解和空间推理能力，导致导航效率低下。
- **整体含义**：为解决上述缺陷，论文提出一种**3D体素信念图**，将目标存在的先验分布建模在体素化三维空间中，使机器人能够整合LLM的语义先验、VLM的视觉特征以及实时观测，构建全局后验信念，从而实现全局而非贪婪的导航决策。

#### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：利用3D体素网格作为环境表示，在每个体素中存储目标物体存在的概率（信念值），通过贝叶斯更新融合多模态信息，使导航规划具有全局视角。
- **关键技术细节**：
  - **3D体素信念图构建**：将环境划分为固定大小的体素（如0.5m³），每个体素维护一个信念值，表示该位置存在目标物体的先验概率。先验来自LLM对场景语义的推理（例如“沙发通常在客厅”），后验通过实时观测（VLM检测到的物体类别和位置）进行贝叶斯更新。
  - **层次化语义结构**：将语义先验与体素层级关联（如房间层级、物体层级），使LLM能够输出更精确的位置估计。
  - **全局路径规划**：基于信念图计算全局导航目标点（选择信念峰值区域），再结合A*等传统规划算法生成路径，避免局部最优。
- **算法流程**（文字说明）：
  1. 初始化：根据语义先验（LLM）生成初始信念图。
  2. 观测更新：机器人移动过程中，VLM对当前帧进行物体检测，更新对应体素的信念值。
  3. 全局决策：计算信念图的全局最大值或概率加权中心作为下一探索目标。
  4. 路径规划：利用当前地图和目标点进行路径规划，驱动机器人移动。
  5. 重复步骤2-4直至找到目标或达到步数上限。

#### 3. 实验设计：数据集、基准、对比方法
- **数据集/场景**：
  - **HM3D**（Habitat-Matterport 3D）：包含真实世界3D扫描场景。
  - **HSSD**（Habitat Synthetic Scene Dataset）：合成场景数据集。
- **基准**：零样本物体导航（ZSON）标准评测，主要指标为**成功率（SR）** 和**成功率加权路径长度（SPL）**。
- **对比方法**：包括多种现有零样本导航方法（如SemExp、ZSON、CoW、LLM-Planner、ESC等），具体名称在论文正文中有列举。

#### 4. 资源与算力
- **未明确说明**：论文中未提及训练或推理所使用的GPU型号、数量、训练时长等具体算力信息。仅提到实验在Habitat模拟器上运行，但硬件规格缺失。

#### 5. 实验数量与充分性
- **实验数量**：包括两个基准数据集（HM3D和HSSD）上的主实验、多个消融实验（如不同体素大小、不同语义先验来源、是否使用层次结构等）、以及定性可视化结果。
- **充分性评价**：实验设计较为充分，覆盖了不同环境和不同方法对比，消融实验验证了各模块的有效性，指标选择（SR和SPL）合理。但未在真实机器人上验证，且缺乏对计算时间或内存占用等实际部署指标的评估。

#### 6. 论文的主要结论与发现
- 提出的**BeliefMapNav**在HM3D和HSSD两个基准上均实现了**最优成功率（SR）和SPL**，尤其SPL比之前最佳方法高出9.7个点，表明该方法在**效率**和**效果**上均有显著提升。
- 3D体素信念图能够有效融合语义先验与实时观测，克服贪婪策略的局限性，实现全局优化导航。

#### 7. 优点：方法或实验设计上的亮点
- **方法亮点**：
  - 首次将**3D体素信念图**应用于零样本导航，实现概率化全局建模。
  - **层次化语义结构**使LLM的推理更贴近实际空间分布，提升定位精度。
  - **全局规划机制**避免贪心局部最优，显著提升导航效率。
- **实验亮点**：多个消融实验明确展示了每个组件（信念图、层次结构、全局规划）的贡献，对比基线全面且最新。

#### 8. 不足与局限
- **实验局限**：仅在模拟器中进行，未在真实机器人上验证；未报告计算资源需求（如GPU时长、内存消耗），难以评估实际部署成本。
- **方法局限**：体素分辨率固定，可能不适合极度细粒度或超大尺度场景；依赖LLM/VLM的语义先验质量，若先验偏差过大可能误导导航。
- **应用限制**：当前方法假设环境为静态，未考虑动态物体；对光照、遮挡等真实世界挑战的鲁棒性未知。

（完）
