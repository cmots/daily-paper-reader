---
title: "ChatVLA-2: Vision-Language-Action Model with Open-World Reasoning"
title_zh: ChatVLA-2：具有开放世界推理能力的视觉-语言-动作模型
authors: "Zhongyi Zhou, Yichen Zhu, Xiaoyu Liu, Zhibin Tang, Junjie Wen, Yaxin Peng, Chaomin Shen, Yi Xu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=1lyKflUOhp"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 保留开放世界推理能力的视觉-语言-动作模型用于机器人
tldr: 针对视觉-语言-动作模型在适应机器人任务时丢失预训练VLM开放世界推理能力的问题，提出ChatVLA-2模型。它通过保留VLM的识别、数学和视觉空间智能，并设计推理遵循模块将推理转化为具体动作。实验表明ChatVLA-2在多个机器人任务中保持高泛化性能，显著优于现有端到端VLA方法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-1lykfluohp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1426, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1lykfluohp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1429, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1lykfluohp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1307, \"height\": 662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1lykfluohp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1417, \"height\": 683, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1lykfluohp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1433, \"height\": 647, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-1lykfluohp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 390, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1lykfluohp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 816, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1lykfluohp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1lykfluohp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 643, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1lykfluohp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1lykfluohp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 731, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1lykfluohp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 702, \"height\": 210, \"label\": \"Table\"}]"
motivation: 现有VLA模型在微调时会丢失VLM的关键能力。
method: 提出ChatVLA-2，保留并扩展VLM的开放世界推理和推理遵循能力，将推理转化为机器人动作。
result: 在多个机器人操控任务上展现了强大的泛化和推理能力。
conclusion: 为通用机器人智能提供了保留VLM能力的VLA范式。
---

## Abstract
Vision-language-action (VLA) models have emerged as the next generation of models in robotics. However, despite leveraging powerful pre-trained Vision-Language Models (VLMs), existing end-to-end VLA systems often lose key capabilities during fine-tuning as the model adapts to specific robotic tasks. We argue that a generalizable VLA model should retain and expand upon the VLM's core competencies: 1) **Open-world reasoning** - the VLA should inherit the knowledge from VLM, i.e., recognize anything that the VLM can recognize, capable of solving math problems, possessing visual-spatial intelligence, 2) **Reasoning following** – effectively translating the open-world reasoning into actionable steps for the robot. In this work, we introduce **ChatVLA-2**, a novel mixture-of-expert VLA model coupled with a specialized three-stage training pipeline designed to preserve the VLM’s original strengths while enabling actionable reasoning. To validate our approach, we design a math-matching task wherein a robot interprets math problems written on a whiteboard and picks corresponding number cards from a table to solve equations. Remarkably, our method exhibits exceptional mathematical reasoning and OCR capabilities, despite these abilities not being explicitly trained within the VLA. Furthermore, we demonstrate that the VLA possesses strong spatial reasoning skills, enabling it to interpret novel directional instructions involving previously unseen objects. Overall, our method showcases reasoning and comprehension abilities that significantly surpass state-of-the-art imitation learning methods such as OpenVLA, DexVLA, and $\pi_0$. This work represents a substantial advancement toward developing truly generalizable robotic foundation models endowed with robust reasoning capacities.

---

## 论文详细总结（自动生成）

# ChatVLA-2 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有的视觉-语言-动作（VLA）模型在微调过程中，为了适应特定的机器人控制任务，往往会丢失预训练视觉-语言模型（VLM）的关键能力（如开放世界物体识别、数学推理、空间推理等），导致机器人无法泛化到训练数据未曾见过的开放世界场景。
- **研究动机**：VLA 模型通常利用强大的预训练 VLM 作为骨干，但实际训练时，多模态理解与机器人控制两种任务会竞争共享参数空间，导致 VLM 的预训练知识被侵蚀。作者希望构建一种能够保留并主动利用 VLM 预训练知识的 VLA 模型，使机器人实现真正的开放世界泛化。
- **整体含义**：ChatVLA-2 旨在证明“端到端机器人系统可以通过保留 VLM 的推理能力，而无需外部规划器，即可泛化到未见任务”，是迈向真正通用机器人基础模型的重要一步。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 2.1 核心思想
- **两大原则**：
  1. **辨识多模态理解与机器人控制的共享与冲突特征**：多模态理解与机器人控制通常处于不同特征空间，需通过特定架构分离冲突特征并保留共享有益特征。
  2. **确保 VLA 模型的动作与内部推理一致**：模型产生的推理结果应当可靠地指导动作输出，避免推理与动作脱节。

### 2.2 关键技术细节
- **动态混合专家（Dynamic Mixture-of-Experts, MoE）架构**：
  - 在 VLM 骨干（Qwen2-VL）中集成动态 MoE，使用 8 个专家，推理时动态选择 2 个。
  - 期望部分专家专门负责多模态理解或机器人控制（任务专用特征），部分专家捕获共享有益特征（如空间推理）。
  - 避免使用静态/共享专家，因为这会破坏原始 VLM 结构并丢失预训练知识（实验证实）。

- **推理遵循增强模块（Reasoning-following Enhancement Module）**：
  - 将推理令牌（reasoning tokens）通过 MLP 投影，替换原始观测嵌入，与当前时间步嵌入结合，生成尺度和平移参数，注入到动作专家（基于 ScaleDP 的扩散策略）的后半部分层中。
  - 选择后半部分层注入，因为早期层对动作稳定性影响更大，后半部分层更适合注入推理上下文。
  
- **两阶段训练策略**：
  - **第一阶段**：联合训练图像-文本数据（COCO、TextVQA、GQA 等）与机器人数据，保留预训练知识，建立多模态理解与机器人动作的连接。保持图像-文本数据与机器人数据比例 1:3，训练 15k steps。
  - **第二阶段**：冻结 VLM 骨干，仅训练动作专家，增强模型对新推理场景的遵循能力，训练 50k steps。

## 3. 实验设计

### 3.1 数据集与场景
- **数学匹配游戏**（Math Matching Game）：
  - 机器人识别白板上的手写数学方程，从多个答案卡中选择正确卡片并放置。
  - 训练数据：600 条轨迹，均标注推理短语。
  - 评估指标：操作成功率、OCR 准确性（4 分）、数学推理准确性（2 分）。
  - 设 **In-domain**（数字与符号在训练集中）和 **Open-world**（方程完全未见）两种设置。

- **玩具放置任务**（Toy Placement）：
  - 机器人根据指令（如“将玉米放在粉色积木的左侧”）拾取物体并放置在目标物体的特定方位。
  - 训练数据：300 条轨迹。
  - 评估指标：操作成功率、开放世界物体识别（边界框正确性）、空间关系推理。
  - In-domain 设置中物体均出现在训练集；Open-world 中目标和参考物体均未见。

### 3.2 对比方法
- **基线方法**：Octo、Diffusion Policy、OpenVLA、GR00T N1、DexVLA、ChatVLA、π0。
- **多模态理解基准**：12 个 VQA 与多模态理解基准（TextVQA、DocVQA、ChartQA、AI2D、MMMU、MMStar、MME、OCRBench 等），对比 ChatVLA 和 ChatVLA-2。

### 3.3 消融实验
- MoE 架构消融：对比动态 MoE / 静态 MoE + 动态 MoE / 共享 MoE + 动态 MoE / 3B 密集模型 / 7B 密集模型。
- 训练策略消融：仅第一阶段 / 仅第二阶段 / 两阶段完整。
- 专家数量消融：8选2 / 6选3 / 4选2。
- 推理注入层位置消融：后半部分 / 全层 / 前半部分。

## 4. 资源与算力
- **GPU**：8 块 NVIDIA H800（每块 80GB）。
- **训练精度**：混合精度训练（FP16）。
- **优化器**：AdamW。
- **学习率调度**：第一阶段初始学习率 2e-5，训练 15k steps；第二阶段初始学习率 2e-5，热身 3k steps，之后 cosine 衰减至 2e-6，训练 50k steps。
- **总训练时长**：约 **340 GPU 小时**（约 42.5 小时 8 卡并行）。

## 5. 实验数量与充分性

- **实验组数**：主实验涵盖两个机器人任务（数学匹配游戏 + 玩具放置），每个任务都有 In-domain 和 Open-world 两种设置，对比 7~8 种方法。此外，在 12 个多模态理解基准上进行评估，并完成 4 组消融实验（MoE 结构、训练策略、专家数量、推理注入位置）。
- **充分性判断**：
  - **充分**：覆盖了泛化能力、推理能力、操控能力等多个维度；Open-world 设置有效验证了模型对未见场景的泛化。
  - **客观与公平**：对比方法均为近期 SOTA 模型，且提供了详细的评估指标定义（OCR 分、推理分、成功率等），实验设置描述清晰。
  - **不足**：未在仿真 benchmark（如 RLBench、CALVIN）中评估（作者解释为现有仿真无法衡量 ChatVLA-2 展示的能力），这可能让部分读者认为缺乏标准化的对比基础。

## 6. 论文的主要结论与发现

- ChatVLA-2 在 **Open-world 环境下的泛化能力显著优于所有对比方法**：
  - 数学匹配游戏：Open-world 下操作成功率 **82.7%**，而对比方法最高仅 15.4%（π0）。OCR 准确率 3.58/4，数学推理准确率 1.73/2。
  - 玩具放置：Open-world 下操作成功率 **81.4%**，物体识别准确率 **0.94**，空间关系推理准确率 **0.88**；第二名 ChatVLA 仅 14.1% 成功率。
- In-domain 场景下，ChatVLA-2 与 DexVLA、π0 等持平或略优，但提升不明显。
- 动态 MoE 架构对保留预训练知识至关重要，密集模型（3B/7B）在 Open-world 下几乎完全失败。
- 两阶段训练策略：第一阶段保留预训练知识，第二阶段强化推理遵循，缺一不可。
- 模型在 12 个多模态理解基准上中有 11 个取得提升（与 ChatVLA 相比），表明理解能力得到保持甚至增强。

## 7. 优点：方法或实验设计上的亮点

- **方法创新**：首次在 VLA 中引入动态 MoE 来分离冲突特征，同时利用路由机制保留共享特征；推理遵循增强模块设计精巧，仅在后半部分注入推理，避免了动作不稳定。
- **实验设计**：设计了两个具有挑战性的开放世界任务（数学匹配、玩具放置），直接测试 VLM 的推理能力能否迁移到机器人操作。Open-world 设置严格（方程/物体完全未见），结果说服力强。
- **泛华能力验证**：不仅在机器人操控上表现优异，还在标准多模态理解基准上做了全面评估，证明预训练知识确实得到保留。
- **消融实验全面**：对核心组件（MoE、两阶段训练、专家数量、推理注入位置）逐一分析，提供了清晰的解释。

## 8. 不足与局限

- **预训练知识保留不完整**：作者在附录中坦诚，尽管 ChatVLA-2 保留了大部分 VLM 能力，但仍有部分能力在微调中不可避免地消失，无法完全解决。
- **实验场景局限**：当前仅在桌面操作任务上验证（抓取、放置），尚未拓展到移动操作、长时域任务、人形机器人等更复杂场景。
- **未在标准仿真基准上评测**：缺少与主流仿真 benchmark（如 RLBench、CALVIN）的对比，可能会被质疑实验的标准化程度。
- **数据收集成本**：机器人训练数据需手动采集轨迹并标注推理短语（共约 900 条），且比例（1:3 图像-文本数据 vs 机器人数据）较为固定，扩展性需后续验证。
- **计算资源需求**：使用 8 块 H800 训练 340 GPU 小时，对普通实验室门槛较高。

（完）
