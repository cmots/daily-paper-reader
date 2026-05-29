---
title: Empowering World Models with Reflection for Embodied Video Prediction
title_zh: 通过反思增强具身视频预测的世界模型
authors: "Xiaowei Chi, Chun-Kai Fan, Hengyuan Zhang, Xingqun Qi, Rongyu Zhang, Anthony Chen, Chi-Min Chan, Wei Xue, Qifeng Liu, Shanghang Zhang, Yike Guo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=onumui0nHi"
tags: ["query:wm-vla-sa"]
score: 8.0
evidence: 通过反思增强世界模型以实现具身视频预测
tldr: 该论文提出反思生成（RoG），一种中间推理策略，结合预训练视觉语言模型和视频生成模型，增强世界模型在具身场景中的多步预测和分布外泛化能力。同时提出了EVA-Bench基准。实验证明RoG显著提升了预测鲁棒性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 800, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1737, \"height\": 1216, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1757, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1759, \"height\": 1223, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1737, \"height\": 773, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1443, \"height\": 1170, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1778, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1723, \"height\": 900, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1669, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1502, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1447, \"height\": 1780, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 918, \"height\": 921, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-onumui0nhi/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 843, \"height\": 1004, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1707, \"height\": 490, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 858, \"height\": 402, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 355, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 854, \"height\": 293, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 824, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1075, \"height\": 963, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1457, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1771, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1768, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-onumui0nhi/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1774, \"height\": 762, \"label\": \"Table\"}]"
motivation: 现有世界模型在具身视频预测中缺乏鲁棒理解能力。
method: 利用VLM和视频生成模型进行中间推理反思。
result: 在多步预测和OOD场景中表现更好。
conclusion: 反思机制能有效提升世界模型的预测能力。
---

## Abstract
Video generation models have made significant progress in simulating future states, showcasing their potential as world simulators in embodied scenarios. However, existing models often lack robust understanding, limiting their ability to perform multi-step predictions or handle Out-of-Distribution (OOD) scenarios.  To address this challenge, we propose the Reflection of Generation (RoG), a set of intermediate reasoning strategies designed to enhance video prediction.  It leverages the complementary strengths of pre-trained vision-language and video generation models, enabling them to function as a world model in embodied scenarios. To support RoG, we introduce Embodied Video Anticipation Benchmark(EVA-Bench), a comprehensive benchmark that evaluates embodied world models across diverse tasks and scenarios, utilizing both in-domain and OOD datasets. Building on this foundation, we devise a world model, Embodied Video Anticipator (EVA), that follows a multistage training paradigm to generate high-fidelity video frames and apply an autoregressive strategy to enable adaptive generalization for longer video sequences. Extensive experiments demonstrate the efficacy of EVA in various downstream tasks like video generation and robotics, thereby paving the way for large-scale pre-trained models in real-world video prediction applications. The video demos are available at https://sites.google.com/view/icml-eva.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：现有视频生成模型在具身场景（embodied scenarios）中用作世界模型（world model）时，缺乏对当前状态和预测状态的鲁棒理解能力，导致只能进行固定帧数、单轮预测，无法处理多步预测或分布外（Out-of-Distribution, OOD）场景，严重依赖人工干预。
- **背景**：视频生成技术（如扩散模型）已能生成高质量预测视频，可应用于机器人规划、混合现实说明书、驾驶辅助等。但现有方法（如RoboDreamer、UniSim）忽略了理解环节，无法检测错误输出。
- **整体含义**：本文提出通过“反思”（reflection）机制将理解与生成分离，使预训练的视觉语言模型（VLM）和视频生成模型（VDM）协同工作，形成具备自我纠错和多步预测能力的统一世界模型。

## 2. 方法论

### 核心思想：Reflection of Generation (RoG)

- 将视频预测任务划分为**帧级预测**、**任务级预测**、**串行任务级预测**三个层次，聚焦于任务级预测。
- RoG世界模型 `W_RoG(O0, I)` 包含一个**理解模块**（VLM）和一个**生成模块**（VDM），通过动态反馈机制迭代优化预测。
- 理解模块对当前隐藏状态 `H` 进行反思，输出三种决策：**extend**（继续生成）、**regenerate**（重新生成）、**output**（输出结果）。
- 伪代码算法1描述了迭代过程：初始观测 `O0` 和指令 `I` 编码得到 `H`，反思模块决定是否扩展/重生成/输出，直到任务完成。

### 关键技术细节

- **EVA模型结构**：
  - VLM：基于Vicuna-v1.5语言模型 + CLIP视觉编码器（ViT-L/14），使用无参数令牌聚类减少视频令牌开销。
  - VDM：基于Dynamicrafter的1.5B参数视频生成模型，生成16帧/2秒的视频，输入条件包括图像、FPS、语言嵌入。
  - **Ensemble-LoRA**：为不同领域（人-第一人称、真实机器人、仿真机器人）训练独立的低秩适应模块，通过任务令牌控制的门控系统组合。
  - **交叉注意力生成适配器**（Generation Adapter）：将VLM隐藏特征线性变换为VDM文本嵌入，用扩散去噪损失优化。

- **多阶段训练策略**：
  1. **阶段1**：使用COCO和CC3M-595K预热VLM的视觉编码器适配器。
  2. **阶段2**：使用指令微调数据（VideoChatGPT等开放数据 + 自建的EVA指令数据集）将VLM转化为具身问答机器人。
  3. **阶段3**：训练生成适配器和VDM的Ensemble-LoRA，针对每个任务域最大化生成质量。

- **自回归帧扩展**：基于任务完成验证进行分块自回归扩展。首轮生成视频后，用VLM判断是否完成；若未完成，提取最后1帧和t帧作为下一轮输入，重复直到完成。

## 3. 实验设计

### 数据集与场景

- **EVA指令微调数据集**：500K问答对，来源包括Open-X-Embodiment、Ego4D、Ego-Exo4D、CALVIN，涵盖人类日常活动、真实机器人、仿真机器人。
- **EVA-Bench基准**：125个高质量样本，涵盖域内和OOD场景，包括四种元任务：
  - **Action-Description**（动作描述）
  - **Finish-Thinking**（完成思考）
  - **How-To**（如何做）
  - **Next-Step**（下一步）

### 对比的方法

- **VQA任务**（Action-Description）：对比ChatUniVi、LLaVA-NI、LLaVA-NV、LLaVA-OneVision、MiniCPMv2、Qwen2、GPT-4o等。本文模型EVA（微调后的VLM）优于所有基线。
- **视频生成质量**（Finish-Thinking）：对比Dynamicrafter（原始及微调）、EVA-Gen（仅VDM），以及各种两阶段VLM+VDM组合（ChatUniVi+DC、Qwen2+EVA-Gen等）。
- **How-To和Next-Step任务级生成**：对比LLaVA-O+EVA-Gen、Qwen2+EVA-Gen、EVA-2Stage（无适配器）和EVA。
- **机器人规划评估**：
  - **RT-1**：在域内和OOD任务上对比AVDC、EVA（无反思）和EVA。
  - **CALVIN**：4个任务（lightbulb、led、rotate、open drawer），对比有无RoG，并结合两种视频-动作头（CMLP、CMLP2）。

## 4. 资源与算力

- **训练硬件**：8块Nvidia A800 GPU（文中附录A.5表7注明）。
- **训练步数**：VDM训练20000步，采样步数50步。
- **其他细节**：VLM预训练使用128 batch size、余弦学习率、AdamW优化器。未明确给出总训练时长，但可推断资源中等（约8卡级别）。

## 5. 实验数量与充分性

- **多维度实验**：共约4大组主要实验（VQA、视频质量、任务级生成、机器人规划），每组合多项指标。
- **消融实验**：通过对比EVA与EVA w/o RoG（无反思）以及不同VDM微调方式（LoRA vs full-parameter），验证了反思机制和Ensemble-LoRA的有效性。
- **公平性**：与多种开源和闭源（GPT-4o）模型对比，采用统一评价指标（BLEU、METEOR、ROUGE-L、CIDEr、SPICE、CLIP、FVD、GCE等），并在附录中给出了详细评估prompt，保证公平。
- **覆盖足够**：涵盖域内和OOD场景、多种机器人任务、人类活动；评估包括文本匹配、视频质量、任务成功率。
- **结论充分**：实验数量较多，系统性较强，验证了所提方法的有效性。

## 6. 主要结论与发现

- RoG策略显著提升了世界模型在多步预测和OOD场景下的鲁棒性。
- EVA模型在VQA任务上达到最佳GPT-4o评分62.63（远超第二名Qwen2的29.58）。
- 在视频生成质量上，EVA在Subject Consistency（97.11）、Background Consistency（96.01）、Motion Smoothness（99.31）及FVD（184.81）均取得最优。
- 在任务级生成（How-To/Next-Step）中，EVA的EVA-Score（81.67/70.85）显著优于两阶段基线。
- 在机器人规划（RT-1）中，EVA在域内任务成功率为84%（比AVDC高28%），OOD任务成功率为12/15（远高于其他方法）。
- 在CALVIN模拟器中，EVA结合CMLP2实现最优成功率，尤其旋转任务从48/157提升至90/157。

## 7. 优点

- **方法创新**：首次将“反思”（reflection）机制引入视频预测世界模型，通过理解与生成分离实现自我纠错，思想简洁有效。
- **模块化设计**：可配合任意VLM和VDM，具有通用性。
- **多任务统一**：通过四个元任务分解具身视频预测，覆盖理解、生成、规划多方面能力。
- **Ensemble-LoRA**：低参数高效适应多领域，避免灾难遗忘。
- **Chunk-wise自回归扩展**：基于任务完成检测自动延长视频，无需固定步数。
- **评估全面**：EVA-Bench涵盖域内/OOD、多种场景和指标，且融合了语言和视频质量双重评价。

## 8. 不足与局限

- **算力需求**：需8卡A800训练，对一般研究团队门槛较高。
- **OOD场景有限**：OOD样本仅15个（RT-1实验），规模较小，可能不足以评估真实泛化能力。
- **视频帧数限制**：每轮生成固定16帧（约2秒），长序列需多次迭代，可能存在累积误差。
- **缺乏真实机器人部署**：仅在仿真环境（CALVIN）和人类标注评估（RT-1）上验证，未在真实机器人上部署。
- **依赖预训练模型质量**：RoG能力受限于VLM和VDM的预训练水平，可能在某些领域失效。
- **反思机制简化**：目前仅支持“扩展/重生成/输出”三种动作，未来可探索更细粒度的反思策略。

（完）
