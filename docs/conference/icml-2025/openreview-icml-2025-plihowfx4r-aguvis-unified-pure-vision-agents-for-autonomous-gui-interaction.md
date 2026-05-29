---
title: "Aguvis: Unified Pure Vision Agents for Autonomous GUI Interaction"
title_zh: Aguvis：统一的纯视觉自主图形用户界面交互代理
authors: "Yiheng Xu, Zekun Wang, Junli Wang, Dunjie Lu, Tianbao Xie, Amrita Saha, Doyen Sahoo, Tao Yu, Caiming Xiong"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=PlihOwfx4r"
tags: ["query:wm-vla-sa"]
score: 6.0
evidence: 统一的纯视觉自主GUI交互框架，属于视觉语言动作模型的一种形式
tldr: 本文提出Aguvis，一个统一的纯视觉自主GUI交互框架，直接基于屏幕图像进行操作，通过内部独白实现结构化推理，并构建大规模多模态标注数据集。两阶段训练将GUI定位与规划分离，在离线和在线基准上均取得最优性能，标志着首个完全自主的纯视觉GUI代理。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1679, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 848, \"height\": 755, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 584, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 569, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 820, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 520, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1031, \"height\": 550, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 522, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 513, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 519, \"height\": 801, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 528, \"height\": 596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 516, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 517, \"height\": 810, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 340, \"height\": 198, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 340, \"height\": 243, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 332, \"height\": 206, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 336, \"height\": 205, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1244, \"height\": 2106, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1102, \"height\": 2062, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1118, \"height\": 2131, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1649, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-plihowfx4r/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1641, \"height\": 449, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-plihowfx4r/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1468, \"height\": 709, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-plihowfx4r/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1781, \"height\": 566, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-plihowfx4r/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 820, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-plihowfx4r/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 841, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-plihowfx4r/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 892, \"height\": 445, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-plihowfx4r/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1769, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-plihowfx4r/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 829, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-plihowfx4r/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 557, \"height\": 463, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-plihowfx4r/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 963, \"height\": 773, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-plihowfx4r/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1230, \"height\": 476, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-plihowfx4r/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1365, \"height\": 441, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-plihowfx4r/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1653, \"height\": 531, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-plihowfx4r/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1622, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-plihowfx4r/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1613, \"height\": 1019, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-plihowfx4r/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1771, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-plihowfx4r/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1769, \"height\": 359, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-plihowfx4r/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1773, \"height\": 463, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-plihowfx4r/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1769, \"height\": 270, \"label\": \"Table\"}]"
motivation: 现有GUI代理依赖文本表示和平台特定动作空间，推理能力有限。
method: 构建纯视觉框架，直接操作屏幕图像，通过内部独白推理，分阶段训练分离定位与规划。
result: 在离线与在线基准上达到最先进水平，实现自主纯视觉GUI交互。
conclusion: 为GUI自动化提供了统一的纯视觉解决方案。
---

## Abstract
Automating GUI tasks remains challenging due to reliance on textual representations, platform-specific action spaces, and limited reasoning capabilities. We introduce Aguvis, a unified vision-based framework for autonomous GUI agents that directly operates on screen images, standardizes cross-platform interactions and incorporates structured reasoning via inner monologue. To enable this, we construct Aguvis data collection, a large-scale dataset with multimodal grounding and reasoning annotations, and develop a two-stage training pipeline that separates GUI grounding from planning and reasoning. Experiments show that Aguvis achieves state-of-the-art performance across offline and real-world online benchmarks, marking the first fully autonomous vision-based GUI agent that operates without closed-source models. We open-source all datasets, models, and training recipes at https://aguvis-project.github.io to advance future research.

---

## 论文详细总结（自动生成）

# Aguvis: 统一的纯视觉自主图形用户界面交互代理 —— 论文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：现有GUI代理普遍依赖文本表示（如HTML、可访问性树）、平台特定的动作空间，以及有限的推理能力。这导致泛化性差、计算开销大、无法跨平台学习，且多数方法依赖闭源模型。
- **意义**：本文提出 **Aguvis**，一个**统一的纯视觉框架**，直接基于屏幕截图进行操作，通过标准化动作空间（基于pyautogui）和结构化推理（内部独白）实现跨平台自主交互，并完全开源，旨在推动自主GUI代理的普适化发展。

## 2. 论文提出的方法论
### 核心思想
- **纯视觉观测**：不依赖文本（HTML/可访问性树），直接处理图像，保持恒定的token开销（720p图像约1196 tokens），不受界面复杂性影响。
- **统一动作空间**：采用 pyautogui 作为基础，配合可插拔插件（如移动端手势、平台快捷键、终止/回答等），实现跨平台一致交互。
- **结构化推理**：每个步骤生成“内部独白”（Inner Monologue），包含**思考**（关于当前状态与目标的推理）和**低层指令**（自然语言描述的具体动作），再映射为实际动作代码。

### 关键技术细节
- **数据集 Aguvis Data Collection**：
  - **定位（Grounding）分片**：约103.6万条单步数据，来自SeeClick、GUIEnv、Widget Captioning等现有数据集，并通过模板增强。
  - **规划与推理分片**：约3.5万条多步轨迹数据，来自MM-Mind2Web、AndroidControl等，并通过GPT-4o对每步生成内部独白（思考+低层指令），人工验证86.7%质量合格。
- **模型架构**：基于Qwen2-VL（也可用LLaVA-OneVision验证），利用动态分辨率、2D-RoPE位置编码保持空间感知。
- **两阶段训练流水线**：
  - **第一阶段：定位训练**（Grounding Training）：在单步数据上训练，采用“定位打包”策略（同一截图捆绑多指令-动作对），提升效率。得到Aguvis-G。
  - **第二阶段：规划与推理训练**（Planning & Reasoning Training）：在多步轨迹数据上训练，输入包含内部独白，使模型学会生成思考与低层指令。最终得到完整Aguvis。

## 3. 实验设计
### 数据集与基准
- **离线评估**：
  - **ScreenSpot**（GUI定位基准）：覆盖手机、桌面、网站，含文本/图标元素，评估原始指令和自规划两种设置。
  - **Multimodal-Mind2Web**（网站导航）：跨任务/跨网站/跨域三个子集，报告元素准确率、操作F1、步骤成功率。
  - **AndroidControl**（手机操作）：从测试集随机采样500步，评估高/低层任务步骤准确率。
- **在线评估**：
  - **Mind2Web-Live**（真实网站）：基于BrowserGym环境，报告任务成功率（Task SR）。
  - **AndroidWorld**（虚拟安卓环境）：Pixel 6模拟器，自动化评估。
  - **MobileMiniWob**（安卓版MiniWob++）：92个任务。
- **泛化测试**：
  - **OSWorld**（桌面计算机）：369个真实计算机任务，评估跨平台迁移能力。

### 对比方法
- 包括GPT-4/4o、CogAgent、SeeClick、Qwen2-VL、UGround、OmniParser、Claude Computer-Use等，覆盖闭源和开源模型。

## 4. 资源与算力
- 训练基于Qwen2-VL骨干：
  - **Aguvis-7B**：使用 **8节点 H100-80G GPU**，定位训练约5小时，规划训练约1小时。
  - **Aguvis-72B**：使用 **16节点 H100-80G GPU**，定位训练约30小时，规划训练约6小时。
- 采用DeepSpeed、BF16、梯度检查点等优化。

## 5. 实验数量与充分性
- **实验组数**：涵盖离线/在线共7个基准，多组消融实验（训练阶段、内部独白、跨平台数据、数据策略、不同骨干等），总计超过20组对比。
- **充分性评估**：
  - 离线基准：ScreenSpot、MM-Mind2Web、AndroidControl均覆盖多种设置（跨任务/网站/域、高/低层）。
  - 在线基准：3个现实场景，并报告成本效率。
  - 泛化测试：OSWorld展示了强迁移能力。
  - 消融实验：系统性地验证了每个组件（两阶段、内部独白、跨平台数据）的贡献。
  - 结果客观：对比方法包括当前最强基线（GPT-4o、Claude等），并控制变量（如使用相同评估框架）。
- **潜在不足**：AndroidControl仅采样500步，可能不够全面；在线基准受网站反爬和reCAPTCHA影响，部分任务无法完成。

## 6. 主要结论与发现
- **Aguvis达到SOTA**：在ScreenSpot、Multimodal-Mind2Web、AndroidControl、Mind2Web-Live、MobileMiniWob等基准上均超越现有方法。
- **纯视觉+统一动作空间有效**：消除对平台文本表示的依赖，且显著降低计算开销（相比HTML减少70% token，成本降低93%）。
- **两阶段训练必要**：仅定位或仅规划训练均导致性能下降；阶段1→2优于联合训练。
- **内部独舞提升性能**：尤其在低层动作（如ScreenSpot）和高层规划（如AndroidControl）上均有显著增益。
- **跨平台数据促进泛化**：联合Web+Mobile训练比单一平台训练效果更好，并在OSWorld上展现跨桌面迁移能力。
- **首个完全开源纯视觉自主GUI代理**：无需闭源模型即可完成端到端交互。

## 7. 优点
- **方法亮点**：
  - 统一纯视觉框架避免文本瓶颈，更接近人类交互方式。
  - 结构化内部独舞（思考+低层指令）增强可解释性和规划能力。
  - 两阶段训练分离定位与规划，数据高效。
  - 可插拔动作空间灵活适应不同平台。
- **实验设计亮点**：
  - 全面覆盖离线+在线、移动+Web+桌面，验证跨平台能力。
  - 消融实验严谨（训练阶段、数据来源、内部独白等）。
  - 成本分析突出效率优势。
  - 开源全部数据、模型和训练配置，可复现。

## 8. 不足与局限
- **在线环境限制**：部分网站（如kohls、target、united）无法通过Playwright正常访问或遭遇reCAPTCHA，导致约24个任务无法评估。
- **推理数据依赖闭源模型**：规划数据由GPT-4o生成，可能引入噪声（人工验证5.5%存在意图误判），且未来可探索用开源VLM替代。
- **不确定性处理缺失**：模型未能对模糊指令表达拒绝或不确定性（占40%的失败案例），需引入安全机制。
- **规模有限**：AndroidControl测试仅500步，可能无法完全代表复杂手机场景；OSWorld测试未充分利用多次运行（文中未提及重复次数）。
- **计算资源需求较大**：72B模型需16节点H100，对小团队部署门槛高。
- **泛化范围待扩展**：虽在OSWorld有良好表现，但尚未在更广泛的桌面应用（如办公软件、设计工具）上验证。

（完）
