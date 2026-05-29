---
title: "MindJourney: Test-Time Scaling with World Models for Spatial Reasoning"
title_zh: MindJourney：基于世界模型的测试时扩展用于空间推理
authors: "Yuncong Yang, Jiageng Liu, Zheyuan Zhang, Siyuan Zhou, Reuben Tan, Jianwei Yang, Yilun Du, Chuang Gan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=L2W4wQsNkY"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 用于空间推理的世界模型，测试时扩展
tldr: 该论文指出大视觉语言模型缺乏对3D动态场景的内部模型，提出测试时扩展框架SpatialNavigator。该框架将VLM与基于视频扩散的可控世界模型耦合，通过迭代规划相机轨迹并合成视图，使VLM能够利用多视角证据进行空间推理。在多个3D空间推理基准上，该方法显著提升了VLM的准确性，展示了世界模型在增强语言模型空间认知中的关键作用。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-l2w4wqsnky/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1311, \"height\": 802, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l2w4wqsnky/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1321, \"height\": 670, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l2w4wqsnky/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1310, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l2w4wqsnky/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1444, \"height\": 493, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l2w4wqsnky/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1085, \"height\": 657, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l2w4wqsnky/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1081, \"height\": 658, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l2w4wqsnky/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1107, \"height\": 1517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l2w4wqsnky/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 327, \"height\": 322, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l2w4wqsnky/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 372, \"height\": 808, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l2w4wqsnky/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1144, \"height\": 986, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l2w4wqsnky/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1005, \"height\": 1040, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l2w4wqsnky/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1022, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l2w4wqsnky/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1015, \"height\": 810, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l2w4wqsnky/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1014, \"height\": 910, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-l2w4wqsnky/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1014, \"height\": 899, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-l2w4wqsnky/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1051, \"height\": 728, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-l2w4wqsnky/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1027, \"height\": 568, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-l2w4wqsnky/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 881, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-l2w4wqsnky/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1394, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-l2w4wqsnky/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1245, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-l2w4wqsnky/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1243, \"height\": 460, \"label\": \"Table\"}]"
motivation: 大视觉语言模型缺乏对3D动态场景的内部模型，在简单空间推理任务中表现不佳。
method: 提出SpatialNavigator框架，将VLM与基于视频扩散的可控世界模型耦合，通过测试时迭代规划与视图合成增强空间推理。
result: 在多个3D空间推理基准上显著提升准确率，证明了世界模型的有效性。
conclusion: 将世界模型与VLM在测试时结合是增强空间推理能力的有效方法。
---

## Abstract
Spatial reasoning in 3D space is central to human cognition and indispensable for embodied tasks such as navigation and manipulation. However, state-of-the-art vision–language models (VLMs) struggle frequently with tasks as simple as anticipating how a scene will look after an egocentric motion: they perceive 2D images but lack an internal model of 3D dynamics. We therefore propose SpatialNavigator, a test-time scaling framework that grants a VLM with this missing capability by coupling it to a controllable world model based on video diffusion. The VLM iteratively sketches a concise camera trajectory, while the world model synthesizes the corresponding view at each step. The VLM then reasons over this multi-view evidence gathered during the interactive exploration. Without any fine-tuning, our SpatialNavigator achieves an average 7.7\% performance boost on the representative spatial reasoning benchmark SAT, showing that pairing VLMs with world models for test-time scaling offers a simple, plug-and-play route to robust 3D reasoning. Meanwhile, our method also improves upon the test-time inference VLMs trained through reinforcement learning, which demonstrates the potential of our method that utilizes world models for test-time scaling.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义

- **研究动机**：人类能够轻松进行3D空间推理（如预测自身运动后的场景变化），但现有的视觉语言模型（VLM）虽然擅长2D图像理解，却缺乏对3D动态场景的内部模型，无法像人类一样在脑海中模拟视角变化或物体运动。这种能力缺失严重制约了VLM在具身智能（如导航、操作）等任务中的应用。
- **整体含义**：作者提出 **MindJourney**，一种测试时扩展框架，通过将VLM与基于可控视频扩散的世界模型耦合，使VLM能够在测试时“想象”并探索隐含在单张图像背后的3D空间，从而显著提升空间推理能力。该工作首次将世界模型用于VLM的测试时增强，提供了一条无需微调、即插即用的新路径。

## 2. 方法论

- **核心思想**：利用世界模型模拟由VLM规划的相机轨迹，生成对应视图，VLM再基于这些新增的多视角证据进行推理。整个过程是一个“想象→筛选→作答”的迭代循环。
- **关键技术细节**：
  - **世界模型（World Model）**：基于可控视频扩散模型（如Search World Model, SWM 或 Stable-Virtual-Camera, SVC），输入单帧RGB图像和相机位姿序列，输出对应的第一人称视频。
  - **动作空间与轨迹**：定义基本动作为 {前进 d 米, 左转 θl, 右转 θr}，一个轨迹 τ 由若干基本动作组成，每个动作映射为 SE(3) 中的相对位姿变换。
  - **Spatial Beam Search 算法**（Algorithm 1）：
    1. 初始化束 B = {∅}，证据集 E = ∅。
    2. 每步扩展：对束中每个轨迹，生成候选扩展（每个基本动作重复 k 次），用世界模型渲染对应帧。
    3. 剪枝与筛选：VLM 根据问题对每个候选打出两个分数：探索分数（sexp，是否值得继续探索）和帮助分数（shelp，是否有助于立即回答）。低于阈值 γ 的丢弃；保留 top-B 的探索轨迹更新束；保留 top-H 的帮助轨迹存入证据集。
    4. 达到步数 n 或束为空后，将原始图像与所有证据视图一起输入回答VLM，生成最终答案。
- **轨迹描述辅助**：每次观察附带自然语言描述（如“向前0.25米然后右转9度”），帮助VLM理解空间关系。

## 3. 实验设计

- **数据集与基准**：
  - **SAT（Spatial Aptitude Training）**：包含 **SAT-Real**（150个真实场景查询，覆盖室内外）和 **SAT-Synthesized**（4000个合成场景问题，基于AI2-THOR渲染）。实验由于o1成本限制，合成部分采用500问随机子集。
  - 任务类型涵盖自我运动（EgoM）、物体运动（ObjM）、动作后果（EgoAct）、目标瞄准（GoalAim）、透视切换（Pers）五种。
- **对比方法**：
  - **VLM基线**：GPT-4o、GPT-4.1、InternVL3-14B、OpenAI o1（RL微调并具有测试时推理缩放能力的模型）。
  - **世界模型**：自训练的 Search World Model（SWM）与公开的 Stable-Virtual-Camera（SVC）。
  - **对照设置**：基线（无世界模型） vs. +MindJourney；同时将o1仅作为QA VLM（搜索阶段使用GPT-4o）以节省成本。
- **超参数**：搜索深度 n=3，束宽 B=2，阈值 γexp=γhelp=8，每次扩展最多重复 k=3 次，前进步长 0.25m，旋转步长 9°。

## 4. 资源与算力

- **推理阶段**：
  - SWM 使用 NVIDIA A40（40GB VRAM）；SVC 使用 H100（80GB VRAM）；InternVL3+SWM 组合使用 H100。
- **训练阶段**（SWM）：
  - 骨干网络：Wan2.2-TI2V-5B，采用 ReCamMaster 式相机条件注入。
  - 硬件：8 块 NVIDIA H100 GPU，训练约 **3 天**。
  - 优化器：Adam，峰值学习率 3e-5，混合精度 bf16。
- **备注**：论文对计算时间与精度的权衡做了额外分析（Appendix C.3），表明减少视频扩散步数（50→20）可大幅加速而精度损失有限。

## 5. 实验数量与充分性

- **主实验**：在 SAT-Real（150问）和 SAT-Synthesized（500问子集）上了 5 类任务，覆盖 **4 种 VLM × 2 种世界模型**，共约 4×2×2=16 组主结果（部分组合未全列），每种均报告平均准确率。
- **消融实验**：
  - 搜索深度（step 1/2/3）与修剪阈值（γ=4/6/8）的影响（Fig.4）。
  - 轨迹描述的贡献（Appendix C.2, Tables 5-6）。
  - 时间消耗与精度权衡（Table 4）。
- **失败案例分析**：附录 B 系统性地分析了世界模型（6类常见错误）和 VLM（评分与QA不足）的失败场景，提供定性示例。
- **充分性评价**：
  - **全面性**：覆盖了开闭源、有无 RL 缩放的不同 VLM；使用两种世界模型；包含合成与真实场景。
  - **公平性**：所有方法都基于相同搜索配置，未对任何基线调优。o1 仅用于 QA 部分以节省成本，但搜索仍由 GPT-4o 驱动（在控制变量下公平）。
  - **统计显著性**：报告了多次运行的平均值，但未提供标准误差线（文中提到会在补充材料中提供）。
  - **潜在偏差**：SAT-Synthesized 仅用 500 问，虽具代表性但可能损失统计精度；消融实验主要在 GPT-4o+SWM 上进行，未在所有组合上验证。

## 6. 主要结论与发现

1. **MindJourney 显著提升空间推理性能**：在 SAT-Real 上平均提升 7.7%（最高超 10%），在 SAT-Synthesized 上平均提升 8.0%。
2. **模型无关性**：跨四个 VLM（GPT-4o、GPT-4.1、InternVL3、o1）和两个世界模型（SWM、SVC）均获得正增益。
3. **超越 RL 缩放模型**：GPT-4.1+MindJourney 已超过单独使用 o1；o1+MindJourney 再创新高，说明世界模型提供的物理一致性信息与 RL 推理路径互补。
4. **世界模型能力是瓶颈**：随着搜索步数增加，长距离生成质量下降，导致 SAT-Real 上 3 步时精度不升反降（Fig.4a）；合成场景（更匹配训练分布）则持续受益于更深搜索。
5. **轨迹描述和 VLM 评分重要性**：去掉轨迹描述后性能下降（Tables 5-6）；VLM 评分/QA 能力不足或过滤掉关键视图时也会导致失败。

## 7. 优点

- **无需微调**：直接增强任何冻结的 VLM，即插即用，迁移成本极低。
- **概念创新**：首次将世界模型作为测试时推理的“物理一致想象空间”，为 VLM 提供缺失的 3D 内部表示，而不是单纯增大模型参数或后训练。
- **系统设计清晰**：Spatial Beam Search 将问题无关的扩展与问题相关的剪枝分离，高效利用生成资源。
- **实验覆盖全面**：多 VLM、多世界模型、合成/真实场景、消融与失败分析俱全，结论稳健。
- **开源友好**：计划公开 SWM 检查点、推理脚本、评估代码，可复现性强。

## 8. 不足与局限

- **单视图依赖**：当前仅利用单张参考图像，无法利用多张不同视角的同时探索（如多入口场景）。
- **世界模型长程生成不稳定**：随轨迹延长，几何一致性和细节保持能力下降，产生模糊、错位或伪影（附录 B.1），限制了更深搜索的收益。
- **VLM 评分/QA 能力不足**：即使世界模型生成高质量的视图，若 VLM 评分模块无法保留关键证据，或 QA 模块无法正确解读多视图信息，最终答案仍可能错误（附录 B.2）。
- **问题无关的世界模型**：生成过程未感知下游查询，可能生成与问题矛盾或无关的视图；未来可考虑查询条件注入。
- **计算成本较高**：每步扩展需调用视频扩散模型和 VLM（打分离），整体推理时间增加（即使降低扩散步数也仍比基线慢数倍）。
- **实验统计标注缺失**：未报告误差线或置信区间，难以判断性能差异的显著性。
- **合成子集规模**：SAT-Synthesized 仅使用 500/4000 问，可能对细粒度类别评估精度不足。

（完）
