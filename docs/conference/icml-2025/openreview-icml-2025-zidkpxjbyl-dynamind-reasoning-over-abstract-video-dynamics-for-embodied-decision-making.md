---
title: "DynaMind: Reasoning over Abstract Video Dynamics for Embodied Decision-Making"
title_zh: DynaMind：基于抽象视频动态推理的具身决策
authors: "Ziru Wang, Mengmeng Wang, Jade Dai, Teli Ma, Guo-Jun Qi, Yong Liu, Guang Dai, Jingdong Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ziDKPXJBYL"
tags: ["query:wm-vla-sa"]
score: 6.0
evidence: 具身决策中的视频动态推理
tldr: 该论文针对具身智能体在融合自然语言指令与视觉感知进行决策时面临的模态鸿沟问题，提出了DynaMind框架。通过从视频中提取关键时空动态表示，并设计自适应帧评分器实现动态推理，增强决策能力。该方法可视为将世界模型中的动态预测与视觉语言动作模型相结合的尝试，为具身AI中的任务泛化提供了新途径。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 849, \"height\": 694, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1750, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1759, \"height\": 727, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 815, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1735, \"height\": 630, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 810, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 831, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 856, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 858, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 855, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 990, \"height\": 722, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1082, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1025, \"height\": 802, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1028, \"height\": 809, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 547, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 969, \"height\": 457, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zidkpxjbyl/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1299, \"height\": 1010, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 854, \"height\": 124, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 857, \"height\": 192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 862, \"height\": 192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 847, \"height\": 126, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 855, \"height\": 155, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 139, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 970, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 842, \"height\": 142, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zidkpxjbyl/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1034, \"height\": 333, \"label\": \"Table\"}]"
motivation: 现有具身智能体难以平衡语言指令的简洁性与视频内容的丰富性，缺乏有效的动态推理机制。
method: 提出DynaMind框架，通过自适应帧评分器提取视频中的时空动态表示，并基于此进行决策推理。
result: 在具身决策任务上，DynaMind显著提升了模型对视频动态的理解和后续动作决策的准确性。
conclusion: 动态推理是连接语言指令与视觉感知的有效桥梁，可推广至世界模型与VLA的集成。
---

## Abstract
Integrating natural language instructions and visual perception with decision-making is a critical challenge for embodied agents. Existing methods often struggle to balance the conciseness of language commands with the richness of video content. To bridge the gap between modalities, we propose extracting key spatiotemporal patterns from video that capture visual saliency and temporal evolution, referred to as dynamic representation. Building on this, we introduce DynaMind, a framework that enhances decision-making through dynamic reasoning. Specifically, we design an adaptive FrameScorer to evaluate video frames based on semantic consistency and visual saliency, assigning each frame an importance score. These scores are used to filter redundant video content and synthesize compact dynamic representations. Leveraging these representations, we predict critical future dynamics and apply a dynamic-guided policy to generate coherent and context-aware actions. Extensive results demonstrate that DynaMind significantly outperforms the baselines across several simulation benchmarks and real-world scenarios.

---

## 论文详细总结（自动生成）

# 中文总结：DynaMind: Reasoning over Abstract Video Dynamics for Embodied Decision-Making

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有具身智能体在融合自然语言指令与视觉感知进行决策时，面临语言指令的简洁性与视频内容的丰富性之间的模态鸿沟。一条简单的语言指令可能对应多种多样的视频执行路径，而现有方法往往依赖“语言到视频”的刚性映射或对语言指令进行精细化分解，但受限于语义表达的固有束缚，难以适应复杂、多变的环境。
- **研究动机**：作者提出一个新颖视角——不是去细化语言信息，而是从视频中抽象出高层次的时空动态表示（dynamic representation）。通过捕捉视觉显著性（visual saliency）和时序演化（temporal evolution），弥合语言与视频之间的差距，从而增强决策能力。
- **整体含义**：论文提出的DynaMind框架将输入视频转换为紧凑的动态序列，并基于此进行动态推理和动作决策，实现了从“逐帧视频生成”到“动态推理”的范式转变，为具身AI中的任务泛化提供了新途径。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 2.1 核心思想
DynaMind由三个紧密集成的模块构成：
1. **视频动态抽象（Video Dynamic Abstraction）**：使用自适应帧评分器（FrameScorer）评估每个帧的重要性，基于语义一致性与视觉显著性，将冗余帧融合为紧凑的动态表示。
2. **视频动态推理（Video Dynamic Reasoning）**：利用自回归Transformer预测未来的动态表示，捕获全局时间依赖关系。
3. **动态引导动作决策（Dynamic-Guided Action Decision）**：结合历史帧特征、历史动作和预测的未来动态，通过动作Transformer生成上下文连贯的动作序列。

### 2.2 关键技术细节
- **输入表示**：语言指令通过冻结的DistilBERT编码为语言嵌入；视频帧通过CNN编码器（从零训练）提取帧特征。
- **FrameScorer**：两层全连接网络加sigmoid激活，输出重要性分数 \(w_t\)。训练损失包含：
  - **语义一致性损失**：最大化动态序列与语言嵌入的余弦相似度。
  - **视觉显著性损失**：确保动态序列与语言的相关性高于仅基于高方差（高显著性）帧构建的序列的相关性。
- **滑动窗口融合**：将视频分为非重叠窗口（大小C），每个窗口内用重要性分数加权平均帧特征，得到窗口级动态表示 \(h_n\)。
- **动态推理模块**：采用带因果掩码的Transformer，结合自注意力和交叉注意力，以历史动态和语言为输入，预测未来动态（MSE损失）。
- **动作决策模块**：使用与推理模块相同结构的Transformer，输入包括历史帧特征、历史动作（投影到同一空间）以及未来动态作为目标条件。训练时采用**混合赋值策略**：早期使用真实未来帧特征稳定训练，后期逐渐过渡到使用预测的动态。
- **端到端训练**：三个模块共享特征编码，未来帧和动作作为监督信号。

## 3. 实验设计

### 3.1 使用的数据集/场景
- **仿真环境**：
  - **LOReL Sawyer**（机器人操作，6个子任务）：基于MetaWorld构建，包含5万条轨迹。
  - **Franka Kitchen**（长序任务，4个子任务）：基于Relay Policy Learning数据集，涉及7个交互对象。
  - **BabyAI**（导航任务）：网格世界，含GoToSeq、SynthSeq、BossLevel三个难度级别，仅使用0.1%数据（1k轨迹）训练。
- **真实世界实验**：使用Franka Research 3机械臂，设计5个任务（按按钮、取牛奶盒、推箱子、放零食进篮子、叠毛巾），每任务20条示范。

### 3.2 Benchmark和对比方法
- **基准方法**：
  - 简单模仿学习：Vanilla BC、Decision Transformer (DT)
  - 多模态对齐方法：GR-1、MT-R3M
  - 语言分解方法：LISA（将指令分解为细粒度语义技能）、SkillDiffuser（技能条件视频生成+逆动力学模型）。
- **公平比较**：保持相近参数量，使用相同视觉和语言编码器架构（与SkillDiffuser一致）。

## 4. 资源与算力

- **算力信息**：论文在4.3节明确说明，所有模型在NVIDIA A800 GPU上训练，batch size为64。给出了各方法的参数量（DynaMind为7.84M）和GPU内存占用（854 MiB），但**未报告训练时长**。相比SkillDiffuser（60.29M参数，1136 MiB）和LISA（7.52M参数，690 MiB），DynaMind在参数和内存方面处于中等水平。

## 5. 实验数量与充分性

- **实验组数**：相当充分。
  - **主要性能对比**：在LOReL Sawyer上报告6个子任务成功率（表1），在Franka Kitchen上报告平均成功率及完成1~4个子任务的成功率（图3），在BabyAI上报告3个难度级别成功率（表3）。
  - **指令泛化**：对LOReL Sawyer的5种未见过指令类型进行测试（表2、表7）。
  - **数据规模影响**：在Franka Kitchen上测试5、10、25条轨迹下的表现（图12，附录E.1）。
  - **消融实验**：对动态抽象（帧加权策略对比，图6）、动态推理（窗口大小C，图7a）、动作决策（输入消融：语言引导 vs 动态引导 vs 不含历史动作，图7b），以及架构配置（共享Transformer、使用R3M编码器，表8）。
  - **计算成本对比**：参数量、GPU内存（表4）。
  - **零样本迁移**：在BabyAI中用简单任务训练后测试复杂任务（表5），在LOReL Sawyer中测试未见过的组合指令（表6）。
  - **真实世界实验**：5个任务各10次试验，平均成功率（表9）。
  - **定性分析**：可视化FrameScorer的分数演化（图5），互信息分析（图8）。
- **充分性评价**：实验设计全面，覆盖多种环境、任务复杂度、数据稀缺性、泛化能力及真实场景。消融研究深入，对比方法多样。但部分实验（如真实世界）样本量较小（20条示范），且未提供统计显著性检验。总体而言，实验充分、客观，对比公平。

## 6. 论文的主要结论与发现

- **主要性能**：DynaMind在所有仿真基准上显著超越基线方法，尤其在长序任务（Franka Kitchen）和低数据设置（BabyAI）下优势明显。在LOReL Sawyer上平均成功率53.67%，接近最优（SkillDiffuser 43%）。
- **动态抽象有效性**：自适应FrameScorer能够识别关键帧，抑制冗余，且随着训练推进重要性分数更聚焦于任务相关帧。
- **动态推理的价值**：相比语言引导或混合引导，动态引导提供更有效的决策信息（消融实验）。
- **泛化能力**：对于未见过的语言指令、组合任务和新场景，DynaMind的泛化表现优于其他方法。
- **跨模态鸿沟缩小**：动态表示与语言之间的互信息在训练中持续增加，而语言分解方法（LISA）的互信息增长有限甚至下降，表明动态抽象比语言细化更有效地桥接模态差异。

## 7. 优点

- **创新视角**：从“抽象视频内容”而非“细化语言”入手，直接解决模态不对等问题。
- **模块化设计**：三个模块分工明确，可独立优化，且支持端到端训练。
- **自适应帧选择**：FrameScorer的软注意力机制比硬采样或均匀加权更灵活，且通过双向监督（语义+显著性+动作）学习。
- **混合赋值策略**：在动作决策中结合真实未来帧和预测动态，稳定早期训练，提升收敛效果。
- **计算效率**：参数量仅7.84M，GPU内存854 MiB，比SkillDiffuser（60.29M）轻量化，性能却更优。
- **泛化验证充分**：在多个仿真环境和真实世界均证明有效，且对数据量、指令变化、任务组合具有鲁棒性。
- **可视化与分析**：提供了帧重要性分数演化、互信息变化等深入分析，增强了方法可解释性。

## 8. 不足与局限

- **固定推理间隔**：使用固定的窗口大小C，缺乏自适应调整。在变化剧烈的场景中可能错过关键动态，而在平稳场景中造成冗余。
- **对视频质量的依赖**：FrameScorer依赖CNN特征的质量，若视频模糊或噪声大，可能影响重要性评分。
- **真实世界实验规模有限**：仅5个简单任务，每个任务20条示范，未涉及更复杂的长序操作或动态环境（如移动障碍物）。且真实世界测试仅在单一机器人平台，泛化至其他硬件尚未验证。
- **未评估实时性**：虽然计算量较小，但未明确说明推理速度是否满足实时控制需求。
- **缺乏统计显著性检验**：多次实验（如3个种子）的结果未提供方差或置信区间，仅报告平均值，难以判断差异是否显著。
- **长期依赖的潜在风险**：动态推理模块基于自回归预测，误差可能累积；虽然使用了真实帧避免递归预测，但在推理时仍需依赖预测的表示，长期任务中可靠性未充分测试。
- **与语言分解方法的互补性**：尝试与LISA结合未获提升（互信息分析），仅依赖动态抽象，可能牺牲了语言中的细粒度约束。

（完）
