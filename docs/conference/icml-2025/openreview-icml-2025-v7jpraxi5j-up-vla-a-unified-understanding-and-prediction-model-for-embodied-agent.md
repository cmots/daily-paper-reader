---
title: "UP-VLA:  A Unified Understanding and Prediction Model for Embodied Agent"
title_zh: UP-VLA：面向具身智能体的统一理解与预测模型
authors: "Jianke Zhang, Yanjiang Guo, Yucheng Hu, Xiaoyu Chen, Xiang Zhu, Jianyu Chen"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=V7JPraxi5j"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 面向具身智能体的统一理解与预测VLA模型
tldr: 该论文提出UP-VLA，一个统一的视觉-语言-动作模型，同时进行理解与预测。针对现有VLM忽略低层空间信息和物理动态的问题，通过联合训练提升具身控制能力。实验表明在多个基准上优于现有方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-v7jpraxi5j/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v7jpraxi5j/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 862, \"height\": 589, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v7jpraxi5j/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1727, \"height\": 632, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v7jpraxi5j/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1718, \"height\": 687, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v7jpraxi5j/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1734, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v7jpraxi5j/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 848, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-v7jpraxi5j/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1753, \"height\": 635, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-v7jpraxi5j/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1763, \"height\": 628, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v7jpraxi5j/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1628, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-v7jpraxi5j/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 872, \"height\": 348, \"label\": \"Table\"}]"
motivation: 现有VLA模型依赖VLM，但VLM缺乏细粒度空间和动态理解。
method: 提出联合训练框架，统一视觉语言理解和未来预测任务。
result: 在具身控制基准上取得最先进结果。
conclusion: 统一理解与预测能有效提升VLA模型的泛化能力。
---

## Abstract
Recent advancements in Vision-Language-Action (VLA) models have leveraged pre-trained Vision-Language Models (VLMs) to improve the generalization capabilities.
VLMs, typically pre-trained on vision-language understanding tasks, provide rich semantic knowledge and reasoning abilities. 
However, prior research has shown that VLMs often focus on
high-level semantic content and neglect low-level features, 
limiting their ability to capture detailed spatial information and understand physical dynamics.
These aspects, which are crucial for embodied control tasks, remain underexplored in existing pre-training paradigms.
In this paper, we investigate the training paradigm for VLAs, and 
introduce \textbf{UP-VLA}, a \textbf{U}nified VLA model training with both multi-modal \textbf{U}nderstanding and future \textbf{P}rediction objectives, enhancing both high-level semantic comprehension and low-level spatial understanding. Experimental results show that UP-VLA achieves a 33\% improvement on the Calvin ABC-D benchmark compared to the previous state-of-the-art method. Additionally, UP-VLA demonstrates improved success rates in real-world manipulation tasks, particularly those requiring precise spatial information.

---

## 论文详细总结（自动生成）

# 论文详细中文总结：UP-VLA

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：现有的视觉-语言-动作（VLA）模型通常使用预训练的视觉-语言模型（VLM）来提升泛化能力。但研究表明，VLM 主要关注高层语义内容（如物体类别、场景描述），忽视低层视觉特征（如物体的精确位置、形状、距离等），且缺乏对物理动态（physical dynamics）的理解。这些低层信息对于机器人操控任务至关重要，却未被充分利用。
- **整体含义**：本文提出一种新的训练范式，让 VLA 模型既能保留 VLM 强大的语义理解能力，又能获得对未来物理变化的预测能力，从而同时改善语义泛化和空间细节处理，最终提升机器人在开放环境中的任务成功率。

## 2. 论文提出的方法论
### 2.1 核心思想
联合训练一个统一的 **自回归模型**，同时优化三个目标：
- **多模态理解（Multi-modal Understanding, MMU）**：使用标准的 VQA 任务（如图片问答）训练语义理解。
- **未来图像预测（Future Prediction）**：给定当前图像和语言指令，预测未来的图像帧（捕捉视觉动态变化和空间细节）。
- **动作生成（Action Generation）**：基于当前观察、语言指令及模型自身产生的场景描述，联合预测未来图像和动作序列。

### 2.2 关键技术细节
- **骨干网络**：使用 Phi-1.5 作为 LLM，结合 CLIP-ViT（连续编码器）用于理解任务，VQ-GAN（离散编码器）用于图像生成任务。
- **统一输入格式**：通过特殊分隔符（如 `|MMU|`, `|T2I|`）区分任务，并将连续图像特征、离散图像 tokens 和文本 tokens 拼接后输入 LLM。
- **注意力机制**：针对不同任务修改因果注意力：
  - MMU：图像 token 之间可互相注意，文本 token 仅关注之前的 token。
  - 未来预测：图像 token 放在文本 token 之后，可以关注所有之前信息。
  - 动作学习：结合理解与预测，MMU 生成的场景描述被注入到预测的输入 prompt 中。
- **动作输出**：通过一个由 MAP（单层注意力）+ 线性层构成的小策略头输出低层动作，使用 MSE 损失（位置）和 BCE 损失（夹爪状态）。
- **训练流程**：
  - **阶段一（预训练）**：在 Bridge（机器人视频数据，25k 演示）上进行未来预测 + 在 LLaVA-tuning-665k（图像-文本对）上进行多模态理解。
  - **阶段二（微调）**：在机器人动作数据集上联合学习动作、未来预测和理解，并继续保留图像-文本对训练以维持理解能力。

### 2.3 损失函数
- 语言建模损失（MMU）：交叉熵。
- 图像建模损失（未来预测）：交叉熵。
- 动作建模损失：MSE + BCE，三者加权求和。

## 3. 实验设计
### 3.1 数据集与场景
- **仿真环境**：CALVIN benchmark，包含 4 个不同场景（A、B、C、D），评价长序列（5 个连续任务）完成长度。
  - **ABCD→D**：训练在全部 4 个场景，测试在场景 D（多任务学习）。
  - **ABC→D**：训练在场景 A、B、C，零样本测试在场景 D（泛化能力）。
- **真实世界**：Franka Emika Panda 机器人，包含 6 种技能（抓取、放置、布线、按按钮、开抽屉等），超过 2000 条演示数据。训练在简单场景，测试在复杂场景（引入未见物体、干扰物、细小物体）。

### 3.2 对比方法
- **VLM-based VLA**：Robo-Flamingo、3D-VLA、UP-VLA-RT-2（重新实现的 RT-2/OpenVLA）。
- **Prediction-based**：Uni-Pi、Susie、GR-1、UP-VLA-phi-w/o-mmu（初始化自纯 LLM Phi-1.5，没有 VLM 理解预训练）。
- **其他**：RT-1、Diffusion Policy、3D Diffuser Actor。

### 3.3 Benchmark 与指标
- CALVIN：连续完成 5 个任务的总长度（Avg. Len，最高 5.0）。
- 真实世界：每个任务 20 次尝试的成功率，分为 seen（训练见过的任务）、unseen（新物体）、precise（精细操作）。

## 4. 资源与算力
- 论文未明确说明所使用的 GPU 型号、数量或训练时长。仅提到在预训练阶段训练 20k 步，batch size=64；微调阶段 batch size=64，使用线性 warmup 1k 步。模型总参数量约为 1.3B（基于 Showo-512x512 骨干）。
- 因此，具体算力资源（如多少块 A100 或 V100）未知，属于未公开细节。

## 5. 实验数量与充分性
- **实验数量**：共进行了 3 大类评估：
  1. 仿真 CALVIN ABC→D（表 1）和 ABCD→D（表 2）。
  2. 真实世界 3 类任务（seen/unseen/precise），每个任务 20 次重复（图 6）。
  3. 消融实验（表 3）：分别移除 MMU、Bridge 预训练、未来预测、MMU-condition 的影响。
- **充分性评价**：
  - CALVIN 实验覆盖了零样本泛化和多任务学习，对比方法全面（10+ 种）。
  - 真实世界实验虽引入多样化场景，但仅显示了最后成功率，未报告多次运行的标准差或置信区间，部分评估次数较少（20 次）。
  - 消融实验仅报告了关键组件的影响，未对损失权重、batch size 等超参数进行系统敏感性分析。
  - 总体而言，实验设计能较好地验证核心假设，但统计严谨性（如重复次数、置信区间）可进一步加强。

## 6. 论文的主要结论与发现
- **联合训练理解与预测显著提升性能**：UP-VLA 在 CALVIN ABC→D 上平均完成长度达 4.08，比之前最好方法 GR-1（3.06）提升 33%。
- **未来预测有助于低层空间理解**：在需要精细操作的现实任务（如抓取小球、布线）中，包含未来预测的方法（UP-VLA）显著优于纯 VLM 方法（UP-VLA-RT-2）。
- **多模态理解有助于语义泛化**：在 real-world unseen 任务上，带 MMU 训练的 UP-VLA 优于不带 MMU 的模型，说明语义理解对应对新物体至关重要。
- **两个能力互补**：纯预测方法（如 GR-1）在 ABC→D 泛化上强于纯 VLM 方法（如 RoboFlamingo），而三者统一后效果最佳。

## 7. 优点
- **方法创新性**：首次将 VLM 的理解目标与视频预测的生成目标统一在同一个自回归框架内，并直接应用于机器人动作学习，区别于之前需要独立扩散模型或额外 3D 信息的方法。
- **统一架构与高效训练**：采用现有成熟组件（Phi-1.5、Show-o 骨干、CLIP、VQ-GAN），通过灵活的注意力 mask 和 prompt 机制实现多任务联合训练，工程实现简洁。
- **实验设计全面**：覆盖仿真到真实、从零样本泛化到精细操作，消融实验清晰验证了各模块贡献。
- **实用价值高**：在真实机器人上取得明显提升，且代码已开源，便于复现和后续研究。

## 8. 不足与局限
- **计算资源未公开**：未报告 GPU 型号、数量、训练总时间，影响可复现性和公平比较。
- **实验统计严谨性不足**：真实世界任务每类仅做 20 次试验，未报告方差或置信区间；CALVIN 上未给出多次独立运行的标准差（尽管引用论文中也常见只报告点估计）。
- **仅限桌面操控任务**：方法在更复杂的移动操作、人机交互等场景中未经验证。
- **预测图像质量有限**：在 CALVIN 场景 D 上，预测的图像背景错误（使用了训练场景的背景颜色），说明生成模型对新场景的泛化仍有缺陷。
- **依赖较大模型（1.3B）**：对算力要求较高，在边缘设备上部署可能困难。
- **缺乏对训练数据量的分析**：真实世界仅收集 2k 演示，未探讨数据量对性能的影响。

（完）
