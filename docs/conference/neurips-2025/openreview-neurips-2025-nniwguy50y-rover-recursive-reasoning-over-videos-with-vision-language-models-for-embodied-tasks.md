---
title: "ROVER: Recursive Reasoning Over Videos with Vision-Language Models for Embodied Tasks"
title_zh: ROVER：针对具身任务的视频递归推理框架
authors: "Philip Schroeder, Ondrej Biza, Thomas Weng, Hongyin Luo, James R. Glass"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=NNiwGUY50Y"
tags: ["query:wm-vla-sa"]
score: 7.0
evidence: 使用视觉语言模型进行递归视频推理以支持具身任务
tldr: 针对视觉语言模型在具身任务中难以对长视频序列进行有效推理的问题，提出ROVER递归推理框架。它通过递归将长视频轨迹分解为对应子任务的较短片段，使VLM能够集中注意力于时间局部帧序列，进行更精确的推理。实验表明，ROVER在多个具身推理基准上显著优于直接使用VLMs的方法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 899, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1162, \"height\": 580, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 604, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1086, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1452, \"height\": 625, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 805, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1451, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 835, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1175, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1177, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1295, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1295, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1296, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1369, \"height\": 1566, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1450, \"height\": 298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1163, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1447, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1289, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1290, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 689, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 682, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 669, \"height\": 574, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 666, \"height\": 574, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 668, \"height\": 579, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 667, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 669, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 667, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1422, \"height\": 402, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1427, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nniwguy50y/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1428, \"height\": 404, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 735, \"height\": 436, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 968, \"height\": 348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1140, \"height\": 1310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1455, \"height\": 1922, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1406, \"height\": 1956, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 918, \"height\": 420, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1379, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1380, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 491, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 489, \"height\": 378, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1458, \"height\": 2200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1462, \"height\": 2135, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 818, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nniwguy50y/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1409, \"height\": 342, \"label\": \"Table\"}]"
motivation: VLM在处理长视频序列推理时能力有限，影响具身任务执行。
method: 提出递归分解视频轨迹为子任务段，用VLM聚焦推理局部帧序列。
result: 在具身任务基准上显著提升了长视频推理的准确性。
conclusion: 提升了VLM在具身场景中的视频理解与推理能力。
---

## Abstract
Vision-language models (VLMs) have exhibited impressive capabilities across diverse image understanding tasks, but still struggle in settings that require reasoning over extended sequences of camera frames from a video. This limits their utility in embodied settings, which require reasoning over long frame sequences from a continuous stream of visual input at each moment of a task attempt. To address this limitation, we propose ROVER (Reasoning Over VidEo Recursively), a framework that enables the model to recursively decompose long-horizon video trajectories into segments corresponding to shorter subtasks within the trajectory. In doing so, ROVER facilitates more focused and accurate reasoning over temporally localized frame sequences without losing global context. We evaluate ROVER, implemented using an in-context learning approach, on diverse OpenX Embodiment videos and on a new dataset derived from RoboCasa that consists of 543 videos showing both expert and perturbed non-expert trajectories across 27 manipulation tasks. ROVER outperforms strong baselines across three video reasoning tasks: task progress estimation, frame-level natural language reasoning, and video question answering. We observe that, by reducing the number of frames the model reasons over at each timestep, ROVER mitigates model hallucinations, especially during unexpected or non-optimal moments of a trajectory. In addition, by enabling the implementation of a subtask-specific sliding context window, ROVER's time complexity scales linearly with video length, an asymptotic improvement over baselines.

---

## 论文详细总结（自动生成）

# 论文总结：ROVER: Recursive Reasoning Over Videos with Vision-Language Models for Embodied Tasks

## 1. 核心问题与整体含义（研究动机和背景）

视觉-语言模型（VLM）在图像理解任务中表现优异，但在处理来自视频的长时间摄像头帧序列推理时存在明显困难。这限制了其在具身任务中的应用——这类任务需要在每个时刻对连续视觉输入流中的长帧序列进行推理。现有方法要么只关注少量局部帧（丢失全局上下文），要么将所有帧拼接在一起（计算昂贵、容易导致幻觉）。为此，论文提出 ROVER（Reasoning Over VidEo Recursively），一个递归分解长视频轨迹的子任务框架，使 VLM 能在不丧失全局上下文的前提下，实现更聚焦、更准确的时序局部推理。

## 2. 方法论：核心思想、关键技术细节、算法流程

**核心思想**：将长视频任务递归分解为较短的子任务片段，并针对每个子任务独立生成推理序列，同时使用滑动上下文窗口限制每步推理的帧数，从而在保持全局任务结构的同时提高准确性和效率。

**关键技术细节**：

- **递归分解**：通过 VLM 生成的特殊 token（`[next-frame]` 和 `The robot needs to: {new_subtask}`）实现子任务切分。当模型认为当前子任务已完成，则生成新子任务描述并启动子递归过程（child process）。
- **滑动上下文窗口**：在每个子任务内，仅保留三帧：该子任务的起始帧、最近的前一帧以及当前帧。三帧均附有先前生成的文本描述，作为下一次推理的上下文。
- **ϕ 和 ψ 函数**：`ϕ(Y)` 将父进程的完整 token 序列转化为子进程的新任务描述和最后一帧；`ψ(Y)` 返回子进程的最终帧及其文本描述。
- **算法流程（Algorithm 1）**：ROVER(c, Y) 循环生成 token，当生成 `[next-frame]` 时追加下一帧图像，当生成新子任务时递归调用自身，当任务完成或视频结束则返回全部 token 序列。
- **复杂度**：由于上下文帧数上限为 3，推理时间复杂度与视频长度成线性关系（O(n)），而基线方法的二次复杂度 O(n²)。

## 3. 实验设计

**数据集**：

- **RoboCasa 模拟数据集**：543 个视频，覆盖 27 个机器人操作任务，每个视频在随机厨房场景中收集。通过向专家演示中插入随机扰动生成不同熟练度（从近乎专家到完全随机）的轨迹，并基于几何距离计算 ground-truth 任务进度标签。
- **OpenX Embodiment (OXE) 真实世界数据集**：1,000 个视频，来自 50 个数据集，包含多种机器人、任务和视角。

**Benchmark 任务**：

1. **帧级任务进度估计**：预测每个时间步的任务完成百分比，评估指标为 Pearson 相关系数和 L2 距离。
2. **帧级自然语言推理**：生成每帧描述后，使用 LLM（GPT-4.5）判断描述中是否有可验证的真/假陈述，计算错误率和成功率。
3. **视频问答**：回答关于事件是否发生及发生时间的问题，评估准确率、精确率、召回率和时间偏移。

**对比方法**：

- **GVL**：基于随机帧打乱的上下文学习价值预测方法。
- **TemporalConcat**：按时间顺序拼接所有帧的简单基线。
- **LocalConcat**：仅保留最后三帧的局部推理基线。
- **LIV**：基于对比学习的价值模型。
- 额外基线：VideoGemini、VideoLlama3、VideoLLaVA。

**骨干 VLM**：主要实验使用 Gemini-1.5-Pro，也在 Gemini-2.5-Pro-Preview、GPT-4o、Qwen-2.5-VL-32B-Instruct 上验证。

## 4. 资源与算力

论文未详细说明全部实验的算力消耗。对于开源模型 Qwen-2.5-VL-32B-Instruct，提及在 **A6000 GPU** 上运行。主要实验基于 Gemini-1.5-Pro API，无本地训练。由于 ROVER 是推理框架（不使用训练），因而没有训练阶段的算力报告。推理成本分析显示，ROVER 的 token 用量约为 GVL 的 1/3（30 帧）和 1/5（60 帧）。

## 5. 实验数量与充分性

实验较为充分，具体包括：

- **三大任务**：进度估计、语言推理、视频问答，覆盖定量和定性评估。
- **多种消融**：消去递归（仅滑动窗口）、消去滑动窗口（仅递归）、改变滑动窗口大小（3/6/9/12）。
- **不同骨干 VLM**：4 种 VLM，均显示 ROVER 一致优于基线。
- **不同相机视角**：手腕视图、左视图、右视图。
- **不同视频长度与帧率**：总帧数从 30 增加到 240，ROVER 性能下降最小。
- **错误分析**：人工审查 100 个真实视频和 100 个模拟视频，分类错误类型。
- **OXE 真实世界数据集**：50 个数据集上的进度预测。

实验设计客观：基准方法使用官方实现或最佳提示，在同一环境下比较，报告均值和标准误。多次实验覆盖了关键维度，足以支持论文结论。

## 6. 主要结论与发现

- ROVER 在三个基准任务上均显著优于所有基线，尤其在非专家轨迹上优势明显。
- ROVER 通过将每步推理的帧数限制为 3，有效减少了 VLM 的幻觉（尤其是感知错误），而基线在处理超过 10 帧的上下文时错误率飙升。
- ROVER 的时间复杂度与视频长度成线性关系，而基线为二次。
- 消融实验表明：滑动窗口单独使用即可减少幻觉，递归分解则进一步提升了多子任务任务的性能。
- 在大规模真实世界 OXE 数据集上，ROVER 的进度预测与帧号的相关系数高于 GVL，在高质量人类演示数据上提升尤为显著。

## 7. 优点

- **递归分解 + 滑动窗口协同设计**：有效平衡局部聚焦与全局结构，避免幻觉，提升准确性。
- **线性复杂度**：实际推理成本显著低于基线（token 数减少 3~5 倍）。
- **灵活的实现方式**：采用上下文学习，无需微调，可直接应用于任何 VLM。
- **新数据集与标注**：提供了包含非专家轨迹的 543 视频数据集，以及基于几何距离的 ground-truth 进度标签，为后续研究提供 benchmark。
- **全面的定量和定性分析**：包括错误分类、时间偏移分析、消融、不同骨干 VLM 和视角，展示了鲁棒性。

## 8. 不足与局限

- **分解失败风险**：当模型指定错误或冗余的子任务时，推理会变得碎片化，与实际任务进度不一致。本文报告在 7% 的模拟视频和 9% 的真实视频中出现错误子任务。
- **依赖于已知的子任务结构**：生成非专家轨迹和计算 ground-truth 进度时，假设任务可由对象中心子任务序列描述，这在某些复杂任务中可能不成立。
- **仅采用上下文学习**：未尝试微调 VLM 以进一步提升性能，微调可能带来更大的改进。
- **未在随机或未知任务结构中充分测试**：实验限于 RoboCasa 厨房场景和 OXE 的已知任务，对全新任务类型的泛化能力未知。
- **对滑动窗口大小的敏感性**：窗口大小从 3 增加到 12 时，感知错误率从 5% 升至 19%，性能下降明显。
- **真实世界评估的局限性**：OXE 数据使用帧号作为 ground-truth 标签，并非真正的任务进度，可能引入偏差。

（完）
