---
title: "EmbodiedBench: Comprehensive Benchmarking Multi-modal Large Language Models for Vision-Driven Embodied Agents"
title_zh: EmbodiedBench：面向视觉驱动具身智能体的多模态大语言模型综合基准
authors: "Rui Yang, Hanyang Chen, Junyu Zhang, Mark Zhao, Cheng Qian, Kangrui Wang, Qineng Wang, Teja Venkat Koripella, Marziyeh Movahedi, Manling Li, Heng Ji, Huan Zhang, Tong Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=DgGF2LEBPS"
tags: ["query:wm-vla-sa"]
score: 6.0
evidence: 视觉驱动具身智能体的基准测试，涉及世界模型与VLA评估
tldr: 该论文针对多模态大语言模型在具身智能体中的应用缺乏综合评估框架的问题，提出了EmbodiedBench基准。包含1128个测试任务，涵盖家庭、导航、操作等场景，以及6个精心设计的子集，用于评估视觉语言模型在具身环境中的推理、规划和执行能力。该基准可直接用于测试世界模型、视觉语言动作模型以及空间音频在具身智能中的表现，是相关研究的重要评估工具。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1680, \"height\": 907, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1705, \"height\": 986, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1744, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 842, \"height\": 284, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 847, \"height\": 647, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 823, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1769, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1774, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1157, \"height\": 546, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1333, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1333, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1246, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1740, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1244, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 343, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 344, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 343, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 346, \"height\": 347, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1247, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 744, \"height\": 716, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1379, \"height\": 1102, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1574, \"height\": 976, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1264, \"height\": 223, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1256, \"height\": 226, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1534, \"height\": 224, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1012, \"height\": 226, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1409, \"height\": 546, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1326, \"height\": 228, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1335, \"height\": 229, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1331, \"height\": 227, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dggf2lebps/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1390, \"height\": 1181, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-dggf2lebps/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 526, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dggf2lebps/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1765, \"height\": 1125, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dggf2lebps/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1682, \"height\": 1321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dggf2lebps/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1329, \"height\": 1142, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dggf2lebps/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1661, \"height\": 2124, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dggf2lebps/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1768, \"height\": 759, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dggf2lebps/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1594, \"height\": 651, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dggf2lebps/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1592, \"height\": 647, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dggf2lebps/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 878, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dggf2lebps/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1240, \"height\": 1306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dggf2lebps/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1654, \"height\": 854, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dggf2lebps/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 900, \"height\": 624, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dggf2lebps/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1537, \"height\": 1642, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dggf2lebps/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1547, \"height\": 740, \"label\": \"Table\"}]"
motivation: 缺乏针对多模态大语言模型驱动的具身智能体的全面评估基准。
method: 设计涵盖多种环境和任务的基准，包含1128个测试任务和6个评估子集。
result: 提供了对现有MLLM具身智能体的全面性能评估，揭示了其在不同任务上的优缺点。
conclusion: 该基准为世界模型、VLA和空间音频在具身AI中的研究提供了标准化评估平台。
---

## Abstract
Leveraging Multi-modal Large Language Models (MLLMs) to create embodied agents offers a promising avenue for tackling real-world tasks. While language-centric embodied agents have garnered substantial attention, MLLM-based embodied agents remain underexplored due to the lack of comprehensive evaluation frameworks. To bridge this gap, we introduce EmbodiedBench, an extensive benchmark designed to evaluate vision-driven embodied agents.
EmbodiedBench features: (1) a diverse set of 1,128 testing tasks across four environments, ranging from high-level semantic tasks (e.g., household) to low-level tasks involving atomic actions (e.g., navigation and manipulation); and (2) six meticulously curated subsets evaluating essential agent capabilities like commonsense reasoning, complex instruction understanding, spatial awareness, visual perception, and long-term planning.
Through extensive experiments, we evaluated 24 leading proprietary and open-source MLLMs within EmbodiedBench. Our findings reveal that: MLLMs excel at high-level tasks but struggle with low-level manipulation, with the best model, GPT-4o, scoring only $28.9\\%$ on average. EmbodiedBench provides a multifaceted standardized evaluation platform that not only highlights existing challenges but also offers valuable insights to advance MLLM-based embodied agents. Our code and dataset are available at [https://embodiedbench.github.io](https://embodiedbench.github.io).

---

## 论文详细总结（自动生成）

### 1. 核心问题与整体含义（研究动机和背景）

论文指出，虽然基于纯语言模型（LLM）的具身智能体评估已受到广泛关注，但针对多模态大语言模型（MLLM）驱动的具身智能体的标准化、综合性评估框架仍然缺失。现有基准（如 VisualAgentBench）仅覆盖高层规划任务，未能评估低层控制任务（如导航、操作）的能力，也未深入分析视觉信息在不同层级任务中的作用。为此，作者提出了 **EmbodiedBench**，旨在系统评测 MLLM 作为视觉驱动具身智能体的多项核心能力。

### 2. 方法论：核心思想、关键技术细节

- **核心思想**：构建一个覆盖不同动作层级（高层语义 vs. 低层原子动作）的多环境基准，并设计细粒度能力子集，以全面衡量 MLLM 在具身任务中的表现。
- **关键技术细节**：
    - **四个环境**：
        - **EB-ALFRED**：基于 ALFRED 数据集和 AI2-THOR 模拟器，高层家庭任务，包含 8 种技能（pick/place/open/close 等）。
        - **EB-Habitat**：基于 Language Rearrangement 和 Habitat 2.0，高层任务，导航仅限于 receptacle 类型物体。
        - **EB-Navigation**：基于 AI2-THOR，低层导航，动作空间包括前后左右平移、旋转、俯仰，共 8 个原子动作。
        - **EB-Manipulation**：扩展自 VLMBench，使用 CoppeliaSim 控制 Franka Panda 机械臂，7 维离散化动作空间（位置分 100 箱，姿态分 120 箱），并加入 YOLO 检测框和物体 3D 坐标提示。
    - **六项能力子集**：Base（基本解题）、Common Sense（常识推理）、Complex Instruction（复杂指令理解）、Spatial Awareness（空间意识）、Visual Appearance（视觉外观）、Long Horizon（长时规划）。
    - **统一智能体流水线**（图 2）：
        - 输入包括语言指令、当前帧图像（或滑动窗口历史图像）、任务相关信息（技能集合、动作格式）、检测框/物体位置。
        - 任务规划器在每个规划步骤中生成：视觉状态描述 → 反思与推理 → 语言计划 → 可执行计划（JSON 格式，支持多步输出）。
        - 支持多步规划，减少 API 调用；计划失败或动作无效时触发重新规划。

### 3. 实验设计

- **基准规模**：共 **1128 个测试任务**，分布在四个环境：
    - EB-ALFRED：300 例（6 子集各 50 例）
    - EB-Habitat：300 例（6 子集各 50 例）
    - EB-Navigation：300 例（5 子集各 60 例，缺少 Spatial Awareness）
    - EB-Manipulation：228 例（5 子集，Base、Common、Complex、Spatial 各 48 例，Visual Appearance 36 例，无 Long Horizon）
- **评估模型**：共 **24 个** MLLM，包括
    - 专有模型：GPT-4o、GPT-4o-mini、Claude-3.5/3.7-Sonnet、Gemini-1.5 Pro/Flash、Gemini-2.0 Flash、Qwen-VL-Max
    - 开源模型：LLaMA-3.2 Vision (11B/90B)、InternVL2.5/3 (8B/38B/78B)、Qwen2/2.5-VL (7B/72B)、Ovis2 (16B/34B)、Gemma-3 (12B/27B)
- **实验设置**：温度 0，最大 token 2048，图像分辨率 500×500，最大环境步数：高层 30、导航 20、操作 15。主要指标为 **任务成功率**。
- **对比基线**：还设置了纯语言对照（Lang）版本，即移除视觉输入。
- **消融实验**：
    - 语言中心消融：移除环境反馈、减少 in-context 示例数量（在 EB-ALFRED 上测试）。
    - 视觉中心消融：不同分辨率 (300/500/700)、是否使用检测框、多步图像输入、多视角图像、视觉 in-context learning（在 EB-Manipulation 上测试）。

### 4. 资源与算力

文中并未明确给出使用的 GPU 型号、数量或训练时长等算力信息。仅提及专有模型通过 API 调用，开源模型使用 lmdeploy 和 vllm 进行本地部署（推理）。因此可以推断本研究主要涉及推理评估，未提及预训练或微调阶段的计算资源消耗。

### 5. 实验数量与充分性

- **数量**：涵盖了 24 个模型 × 4 个环境 × 6 个能力子集（部分子集缺失），以及多组消融实验、错误分析（每个环境采样 110 个失败案例）和附加指标（子目标成功率、平均步数）。
- **充分性**：实验设计较为全面，对不同任务层级、不同能力维度、多种模型规模、多种视觉增强策略进行了对比。消融实验控制了关键变量（分辨率、检测框、多步图像、视觉 ICL），结果具有说服力。不足之处在于：部分环境子集不完整（如 EB-Manipulation 缺少长时规划）可能影响结论的完整性；此外，移除视觉输入后性能下降的结论仅在 GPT-4o 等模型上验证，未在全部模型上重复。
- **公平性**：所有模型使用相同提示模板、相同温度、相同最大步数，且统一了图像分辨率，保证了比较的公平性。但不同模型对同一提示的指令遵循能力存在差异，可能引入细微偏差。

### 6. 主要结论与发现

1. **MLLM 在高层任务上表现良好，但在低层操作任务上严重不足**：最佳模型 GPT-4o 在 EB-Manipulation 上的平均成功率仅 28.9%，而高层任务可达 60-70%。
2. **长时规划是最具挑战的子集**：几乎所有模型在 Long Horizon 上的成功率都显著低于 Base 子集（如 Claude-3.5-Sonnet 在 EB-Habitat 上从 96% 降至 58%）。
3. **视觉输入对低层任务至关重要，对高层任务影响较小**：移除视觉后，GPT-4o 在 EB-Navigation 上从 57.7% 降至 17.4%，长时子集跌至 0%；而在 EB-ALFRED 上甚至略有提升，说明文本信息和环境反馈更为关键。
4. **不同模型各有优势**：Claude-3.5-Sonnet 在高层任务领先（EB-ALFRED 64.0%, EB-Habitat 68.0%），GPT-4o 在低层任务领先（EB-Navigation 57.7%, EB-Manipulation 28.9%）。开源模型中 InternVL3-78B 表现接近 GPT-4o（EB-Navigation 53.7%, EB-Manipulation 26.3%）。
5. **视觉增强策略效果依赖任务**：中等分辨率 (500×500) 最优；检测框有助于操作任务但干扰导航；多步/多视角图像当前反而损害性能；视觉 in-context learning 能显著提升低层操作性能（最高 +16.7%）。

### 7. 优点

- **综合性**：首次系统性地将高层语义任务与低层原子动作任务整合到同一基准中，覆盖家庭、导航、操作等多领域。
- **细粒度能力评估**：设计六大能力子集，不仅看整体成功率高，还能定位模型在常识、空间、视觉、长时规划等具体维度上的短板。
- **标准化统一框架**：提供统一的 agent 流水线和提示模板，支持多步规划，便于公平比较不同 MLLM。
- **大量模型与消融实验**：涵盖 24 个当前最先进模型，并进行了语言和视觉两个方向的消融，结论具有可推广性。
- **公开代码与数据**：提供了易用的数据集生成脚本和评估代码，促进社区后续研究。

### 8. 不足与局限

- **仅限模拟环境**：所有实验在模拟器中进行，未涉及真实机器人部署，存在 sim-to-real 差距。作者也承认这是常见权衡，但真实物理环境的复杂性未被覆盖。
- **部分子集覆盖不完整**：EB-Navigation 缺少空间意识评估，EB-Manipulation 缺少长时规划评估，限制了跨任务能力的完全对比。
- **视觉处理能力有限**：当前 MLLM 对多步/多视角图像的利用仍很困难，导致相关增强策略效果不佳，这可能是模型本身的根本限制。
- **误差分析样本量较小**：每种环境仅采样 110 个失败案例进行手动分析，可能遗漏部分错误模式。
- **未评测微调方法**：论文仅评估了预训练 MLLM 的直接推理性能，没有探索对 MLLM 进行具身任务微调（如 VLA 训练）的表现。
- **算力开销未报告**：缺乏对评估成本（如 API 调用次数、本地推理时间）的量化，不利于其他研究者复现或成本估算。

（完）
