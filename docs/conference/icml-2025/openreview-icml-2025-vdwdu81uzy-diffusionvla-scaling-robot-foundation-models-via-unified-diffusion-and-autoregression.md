---
title: "DiffusionVLA: Scaling Robot Foundation Models via Unified Diffusion and Autoregression"
title_zh: "DiffusionVLA: 通过统一扩散与自回归来扩展机器人基础模型"
authors: "Junjie Wen, Yichen Zhu, Minjie Zhu, Zhibin Tang, Jinming Li, Zhongyi Zhou, Xiaoyu Liu, Chaomin Shen, Yaxin Peng, Feifei Feng"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=VdwdU81Uzy"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: DiffusionVLA融合自回归推理与扩散策略用于视觉语言动作模型
tldr: DiffusionVLA提出统一扩散与自回归的框架，利用预训练VLM进行任务分解与解释生成，通过推理注入模块将推理短语嵌入策略学习，实现了自回归推理与扩散策略的紧密结合，显著提升了机器人的决策与动作生成能力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1597, \"height\": 1235, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1754, \"height\": 780, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1569, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 769, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 861, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 858, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 853, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 844, \"height\": 224, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 858, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1747, \"height\": 897, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1759, \"height\": 890, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vdwdu81uzy/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 860, \"height\": 375, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1779, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 724, \"height\": 160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 815, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1778, \"height\": 798, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 865, \"height\": 126, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 727, \"height\": 138, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 810, \"height\": 128, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 809, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 861, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 838, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vdwdu81uzy/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 894, \"height\": 561, \"label\": \"Table\"}]"
motivation: 现有VLA模型在推理与精确动作生成上存在矛盾。
method: 提出DiffusionVLA框架，集成自回归推理与扩散策略，并设计推理注入模块。
result: 在多种机器人任务上实现了高精度且具备推理能力的动作生成。
conclusion: 该方法为构建具身AI的基础模型提供了新途径。
---

## Abstract
In this paper, we present DiffusionVLA, a novel framework that integrates autoregressive reasoning with diffusion policies to address the limitations of existing methods: while autoregressive Vision-Language-Action (VLA) models lack precise and robust action generation, diffusion-based policies inherently lack reasoning capabilities. Central to our approach is autoregressive reasoning — a task decomposition and explanation process enabled by a pre-trained VLM — to guide diffusion-based action policies. To tightly couple reasoning with action generation, we introduce a reasoning injection module that directly embeds self-generated reasoning phrases into the policy learning process. The framework is simple, flexible, and efficient, enabling seamless deployment across diverse robotic platforms.

We conduct extensive experiments using multiple real robots to validate the effectiveness of DiVLA. Our tests include a challenging factory sorting task, where DiVLA successfully categorizes objects, including those not seen during training. The reasoning injection module enhances interpretability, enabling explicit failure diagnosis by visualizing the model’s decision process. Additionally, we test DiVLA on a zero-shot bin-picking task, achieving \textbf{63.7\% accuracy on 102 previously unseen objects}. Our method demonstrates robustness to visual changes, such as distractors and new backgrounds, and easily adapts to new embodiments. Furthermore, DiVLA can follow novel instructions and retain conversational ability. Notably, DiVLA is data-efficient and fast at inference; our smallest DiVLA-2B runs 82Hz on a single A6000 GPU. Finally, we scale the model from 2B to 72B parameters, showcasing improved generalization capabilities with increased model size.

---

## 论文详细总结（自动生成）

# DiffusionVLA 论文总结

## 1. 核心问题与整体含义（研究动机与背景）

现有视觉-语言-动作（VLA）模型主要有两类：自回归模型（如 RT-2、OpenVLA）通过 next-token prediction 预测离散化的动作，但存在动作精度损失、推理速度慢的问题；扩散策略（如 Diffusion Policy）能生成连续、多模态的高频动作，但缺乏语言推理能力。本文旨在**统一自回归模型的推理优势与扩散模型的精确动作生成能力**，构建一个既能“思考”又能“行动”的机器人基础模型。

## 2. 方法论

### 核心思想
- 以预训练视觉语言模型（VLM）为骨干，保留其自回归推理能力（任务分解与解释生成）；
- 引入一个**扩散策略模型**负责动作生成，两者通过**推理注入模块**紧密结合。
- 训练目标：联合优化扩散损失 $L_{\text{diff}}$ 与下一词预测损失 $L_{\text{ntp}}$：$L = L_{\text{diff}} + \alpha L_{\text{ntp}}$，设置 $\alpha = 10$ 以平衡量级。

### 关键技术细节
- **视觉编码**：SigLIP 将多视角图像编码为固定数量的视觉 token。
- **语言骨干**：Qwen2-VL（2B/8B/72B），使用公开 checkpoint 初始化。
- **动作 token 投影**：VLM 输出经两层 MLP + LayerNorm 投影到扩散模型维度。
- **扩散策略**：标准 Diffusion Policy 架构，随机初始化；最后接 MLP 预测关节空间动作。
- **推理注入模块**：将 VLM 生成的推理 token 的最终 embedding 通过 **FiLM（Feature-wise Linear Modulation）** 注入到策略网络各层，实现推理信号对动作生成的直接调控。
- **训练流程**：先在大规模机器人数据（Droid、OXE）上预训练，再在目标任务上微调。预训练阶段使用 GPT-4o 自动生成推理文本。

## 3. 实验设计

### 数据集与场景
- **预训练数据**：Droid 数据集（约 39K 轨迹），对于 72B 模型额外增加 OXE（970K 轨迹）。
- **微调/评测场景**：
  1. **多任务学习**（Franka 机器人）：5 个任务（物体选择、翻转锅、放置方块到指定盒、放杯子到盘子、放置方块到盒中），共 580 条轨迹。
  2. **工厂排序**（Franka 机器人）：4 类物体（玩具车、针织手套、毛绒玩具、六角扳手），500 条轨迹，含 seen/unseen、cluttered 等子场景。
  3. **零样本抓取**（Franka 机器人）：102 个未见物体，无训练数据。
  4. **双机械臂摆台**（AgileX 机器人）：清空桌面的餐具和垃圾，400 条轨迹，分 seen/unseen。
  5. **视觉泛化**：附加干扰物、不同背景、彩色光照。
  6. **视角变化**：改变相机位置。
  7. **新指令遵循**：如“先拿西瓜，再拿蓝色纸垃圾，最后拿柠檬水”。
  8. **VQA**：测试对话能力。

### 对比方法
- **Diffusion Policy**（DP）
- **TinyVLA**
- **Octo**
- **OpenVLA-7B**
- 所有基线均在同一实验设置下微调（OpenVLA 扩展为三视图以公平比较）。

## 4. 资源与算力

论文未明确报告训练总耗时或 GPU 数量，仅提及：
- 推理在单张 A6000 GPU 上测试：DiVLA-2B 达 82Hz，DiVLA-7B 达 42Hz。
- 微调使用 LoRA，学习率 2e-5，VLM backbone 冻结，仅 LoRA 可训练。
- 预训练用 Droid 数据（39K 轨迹），72B 模型额外用 OXE（970K 轨迹）。

**结论：未公开训练算力具体消耗（GPU 型号、数量、训练时长）。**

## 5. 实验数量与充分性

- **总实验组数**：
  - 多任务学习：77 次室内测试 + 45 次视觉泛化测试。
  - 工厂排序：4 种条件（seen、mixed、cluttered seen、cluttered mixed），各 65~80 次试验。
  - 零样本抓取：102 个物体，各对比方法均做一次成功率计算。
  - 双机械臂：48 次/条件（seen/mixed）。
  - 消融实验：推理注入模块、多视图 vs 单视图、模型规模（2B/7B/72B）。
  - 额外实验：视角变化（5 trail）、新指令（每个 3 trail）、VQA（定性）。
- **充分性评估**：
  - 场景覆盖广泛（单臂、双臂、排序、抓取、泛化变体），对比方法全面。
  - 多次重复试验（重复次数合理），统计成功率。
  - 消融实验验证了核心模块的必要性。
  - 但部分实验（新指令、VQA）样本量较小（3 trail），可能不够稳健；未与近期其他推理增强方法（如 ECoT）直接对比。
  - 公平性上：作者承认 Octo/OpenVLA 预训练数据比 DiVLA 大 25 倍，但 DiVLA 仍表现更优，说明其设计高效。但数据量差异可能引起偏袒性争议。

## 6. 主要结论与发现

1. DiVLA 在多任务、排序、零样本抓取、双臂操作任务上**显著优于所有基线**，尤其视觉泛化场景下优势更大。
2. 推理注入模块不仅提升了动作性能（消融实验显示成功率从 50.3% 提升至 83.6%），还提供了可解释性（可通过生成的推理文字理解模型决策）。
3. DiVLA 具备良好的**规模缩放特性**：从 2B 到 72B，任务成功率单调提升（排序：66.2% → 82.4%；抓取：63.7% → 75.9%）。
4. 模型可以**零样本适应新物体、新背景、新视角、新机械臂形态**，且保留对话能力（VQA）。
5. 推理速度极快：DiVLA-2B 82Hz，DiVLA-7B 42Hz，远高于 OpenVLA-7B 的 5Hz。

## 7. 优点

- **架构创新**：首次将自回归推理与扩散策略统一，并设计推理注入模块直接利用推理信号指导动作，避免了递归调用导致的计算开销。
- **数据高效**：仅使用 39K 轨迹训练的 DiVLA-2B 性能优于使用 970K 轨迹的 OpenVLA-7B。
- **推理速度快**：得益于一次性生成推理 token + 扩散去噪并行化，实际控制频率满足实时需求。
- **泛化能力强**：对未见物体、视觉变化、新指令、双机械臂均表现出良好适应性。
- **可解释性**：推理输出可直接用于诊断失败原因，提升了机器人模型的透明性。
- **开源与拓展性**：模型架构灵活支持不同 VLM 主干，提供 2B/7B/72B 多规模选择。

## 8. 不足与局限

- **依赖自动推理标注**：预训练数据中的推理文本由 GPT-4o 生成，可能引入噪声或错误，缺乏人工验证。
- **实验规模有限**：部分子实验（如新指令遵循、视角变化）样本量较小（3~5 次），统计置信度不足。
- **未对比近期推理增强方法**：例如 ECoT 等同样使用 CoT 的 VLA 模型未纳入对比。
- **量化敏感性**：低精度推理（8bit/4bit）性能明显下降，当前 VLA 模型缺乏专用量化方案。
- **平台限制**：仅在 Franka 和 AgileX 两款机器人上验证，未在更多形态（如轮式机械臂、灵巧手）上测试。
- **与最先进模型对比不全**：虽然提及 π0，但未将其纳入定量比较。
- **可能的数据泄露风险**：预训练 VLM 可能已在 internet 数据中见过某些测试物体，新物体归类可能并非完全零样本。

（完）
