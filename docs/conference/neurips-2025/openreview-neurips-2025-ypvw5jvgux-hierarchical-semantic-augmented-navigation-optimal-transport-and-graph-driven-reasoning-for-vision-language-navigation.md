---
title: "Hierarchical Semantic-Augmented Navigation: Optimal Transport and Graph-Driven Reasoning for Vision-Language Navigation"
title_zh: 层次语义增强导航：基于最优传输和图驱动推理的视觉语言导航
authors: "Xiang Fang, Wanlong Fang, Changshuo Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ypVW5jvguX"
tags: ["query:wm-vla-sa"]
score: 6.0
evidence: 用于机器人的视觉语言动作模型
tldr: 针对连续环境下的视觉语言导航（VLN-CE）在长时任务中场景理解不足和规划低效的问题，本文提出层次语义增强导航（HSAN）框架。通过动态层次语义场景图结合最优传输和图驱动推理，显著提升了导航的鲁棒性和决策能力。在多个数据集上取得了领先性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ypvw5jvgux/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 609, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ypvw5jvgux/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 996, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ypvw5jvgux/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 298, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ypvw5jvgux/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 861, \"height\": 422, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ypvw5jvgux/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 942, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ypvw5jvgux/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 941, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ypvw5jvgux/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 848, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ypvw5jvgux/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 745, \"height\": 207, \"label\": \"Table\"}]"
motivation: 现有方法在长时VLN任务中因场景理解有限和规划低效而表现不佳。
method: 提出HSAN框架，构建动态层次语义场景图，并利用最优传输和图推理增强决策。
result: 在多个VLN-CE基准上达到新高度。
conclusion: 层次语义增强与图推理能显著提升视觉语言导航的性能。
---

## Abstract
Vision-Language Navigation in Continuous Environments (VLN-CE) poses a formidable challenge for autonomous agents, requiring seamless integration of natural language instructions and visual observations to navigate complex 3D indoor spaces. Existing approaches often falter in long-horizon tasks due to limited scene understanding, inefficient planning, and lack of robust decision-making frameworks. We introduce the \textbf{Hierarchical Semantic-Augmented Navigation (HSAN)} framework, a groundbreaking approach that redefines VLN-CE through three synergistic innovations. First, HSAN constructs a dynamic hierarchical semantic scene graph, leveraging vision-language models to capture multi-level environmental representations—from objects to regions to zones—enabling nuanced spatial reasoning. Second, it employs an optimal transport-based topological planner, grounded in Kantorovich's duality, to select long-term goals by balancing semantic relevance and spatial accessibility with theoretical guarantees of optimality. Third, a graph-aware reinforcement learning policy ensures precise low-level control, navigating subgoals while robustly avoiding obstacles. By integrating spectral graph theory, optimal transport, and advanced multi-modal learning, HSAN addresses the shortcomings of static maps and heuristic planners prevalent in prior work. Extensive experiments on multiple challenging VLN-CE datasets demonstrate that HSAN achieves state-of-the-art performance, with significant improvements in navigation success and generalization to unseen environments.

---

## 论文详细总结（自动生成）

# 论文总结：Hierarchical Semantic-Augmented Navigation ...

## 1. 核心问题与整体含义
- **问题**：连续环境下的视觉语言导航（VLN-CE）要求智能体根据自然语言指令在复杂3D室内场景中导航。现有方法在长时程任务中常因场景理解有限、规划低效、缺乏鲁棒的决策框架而失败。
- **整体含义**：本文提出 **HSAN（层次语义增强导航）** 框架，通过三大创新——动态层次语义场景图、基于最优传输的拓扑规划、图感知的强化学习控制——系统性地提升了导航的鲁棒性和决策能力，为VLN-CE任务提供了新的解决方案。

## 2. 方法论
- **核心思想**：融合层次环境表示、最优传输理论和图学习，实现从“理解”到“规划”到“执行”的端到端导航。
- **关键技术细节**：
  - **层次语义场景图构建**：利用Grounded-SAM检测对象，LLaVA-Onevision生成语义描述；通过光谱聚类（相似度含位置和语义项）将对象聚为区域；再通过VLM评估相邻区域合并为区域（如厨房、卧室）。图在每一步动态更新（匹配与新增）。
  - **最优传输（OT）拓扑规划**：将目标选择建模为OT问题，在“幽灵节点”（未探索但可见）和停止节点上定义成本矩阵，包含地理距离、探索惩罚和语义相关性得分。使用Sinkhorn算法求解，平衡语义对齐与空间可达性。理论上基于Kantorovich对偶证明最优性。
  - **图感知低层控制**：采用PPO训练策略，状态由视觉特征、当前子图的GCN嵌入、位姿和下一子目标位置组成。奖励函数鼓励到达子目标、惩罚距离增加和碰撞。使用“Tryout”启发式避开障碍。
- **训练流程**：VLM和GCN在Matterport3D上预训练，然后在VLN-CE数据集上使用学生迫近（student-forcing）联合优化OT损失和RL策略损失。

## 3. 实验设计
- **数据集与场景**：R2R-CE（61个训练场景，14个未见场景）和RxR-CE（83个训练场景，多语言指令），基于Habitat Simulator和Matterport3D。
- **基准方法**：CMM、WM、NTS、SMN、LLaVA-Nav、GraphNav。
- **评估指标**：成功率（SR）、加权成功率（SPL）、导航误差（NE）、oracle成功率（OSR）。
- **额外实验**：RxR-CE多语言子集（英语、印地语、泰卢固语共2000条）和R2R-CE高杂波子集（500条）；消融实验（4组，分别移除层次图、OT规划、图感知控制、VLM描述）；训练过程曲线（图3）。

## 4. 资源与算力
- **硬件**：8张NVIDIA A100 GPU训练，batch size为32，训练100,000个episode。
- **推理**：单GPU上5 FPS。
- **训练时长**：文中未明确说明具体小时数。

## 5. 实验数量与充分性
- **实验数量**：主表对比6种基线，消融4种变体，2种泛化子集，加上训练曲线，共约10组定量结果。
- **充分性**：实验覆盖了两个主流数据集，包括多语言和高杂波挑战场景；消融实验验证了各组件贡献。但仅报告了验证集（validation unseen）结果，未提供测试集成绩；消融实验只对比了有无，缺乏参数敏感性分析。总体而言，实验设计较充分，对比方法较新，结果客观公平。

## 6. 主要结论与发现
- HSAN在R2R-CE和RxR-CE上均达到SOTA：R2R-CE SR 64%（比最强基线LLaVA-Nav高6%），SPL 0.59；RxR-CE SR 59%（高6%），SPL 0.54。
- 各组件显著贡献：移除层次图使SR下降7%，移除OT使下降5%，移除图感知控制使下降8%，移除VLM描述使下降6%。
- 在更具挑战的子集（多语言、高杂波）中，HSAN仍显著优于其他方法，表明其泛化能力强。

## 7. 优点
- **创新性**：首次将最优传输引入VLN规划，具有理论最优性保证；层次场景图结合VLM实现了细粒度环境理解。
- **系统完整性**：从场景表示到决策到控制形成完整闭环，各模块协同工作。
- **实验验证扎实**：消融实验明确量化了每个创新的贡献；泛化实验覆盖了多语言和杂乱场景，验证了鲁棒性。
- **通用性**：框架可适用于不同主流数据集，且不依赖预定义导航图。

## 8. 不足与局限
- **计算开销**：实时构建层次场景图需要VLM推理，推理速度仅5 FPS，难以满足实时机器人控制。
- **环境假设**：仅测试了室内静态场景，未验证动态障碍、户外环境或复杂光照变化。
- **评估范围**：所有实验仅在验证集上进行，测试集结果缺失；消融实验仅做了单一版本，未探索不同参数（如聚类阈值、λ、α、β）的影响。
- **现实部署**：未在真实机器人上部署验证，仿真到现实的迁移效果未知。
- **未见报告**：误差线仅出现在部分子集表中，主表未报告方差，但考虑到VLN-CE的随机性，可能影响统计可靠性。

（完）
