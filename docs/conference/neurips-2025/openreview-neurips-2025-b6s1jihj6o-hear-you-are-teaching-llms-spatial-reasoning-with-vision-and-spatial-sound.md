---
title: "Hear you are: Teaching LLMs Spatial Reasoning with Vision and Spatial Sound"
title_zh: 听到你了：利用视觉和空间声音教授大语言模型空间推理
authors: "Hyeonggon Ryu, Joon Son Chung, David Harwath"
date: 2025-05-11
pdf: "https://openreview.net/pdf?id=b6s1jIHj6o"
tags: ["query:wm-vla-sa"]
score: 8.0
evidence: 空间声音处理用于音频-视觉推理
tldr: 本文研究音频-视觉空间推理问题，利用空间声音和视觉信息教授大语言模型进行空间推理。通过设计空间音频任务，模型能根据声音来源推断物体位置，展示了空间音频在智能体推理中的潜力。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-b6s1jihj6o/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1401, \"height\": 481, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b6s1jihj6o/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1338, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-b6s1jihj6o/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1276, \"height\": 418, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-b6s1jihj6o/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1462, \"height\": 816, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-b6s1jihj6o/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1450, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-b6s1jihj6o/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1379, \"height\": 1495, \"label\": \"Table\"}]"
motivation: 现有音频-视觉方法多使用单声道音频，缺乏空间位置信息，无法完成高级空间推理。
method: 设计空间音频-视觉任务，利用双耳音频和视觉输入训练LLM进行空间推理。
result: 实验表明模型能有效结合空间声音和视觉信息，准确推理物体位置。
conclusion: 空间音频显著增强智能体的空间推理能力，为人机交互和机器人提供新思路。
---

## Abstract
Many audio-visual learning methods have focused on aligning audio and visual information, either through semantic or temporal correspondence. However, most of these works have utilized monaural audio, which does not contain information about the spatial location of the sound source. In contrast, humans and other animals utilize binaural hearing to perceive this spatial information. Combining spatial sound and visual perception enables powerful high-level reasoning: for example, a person looking for their phone may hear the ringing sound coming from a backpack sitting on a table, and quickly infer that the missing phone is inside the backpack. In this paper, we investigate the problem of Audio-Visual Spatial Reasoning. We design a spatial audio-visual question answering dataset to cover scenarios where semantic correspondence between audio and visual signals is absent but spatial alignment exists, as well as cases with multiple audio-visual semantic correspondences that require spatial reasoning to disambiguate. We propose a model that learns spatial comprehension across the audio and vision modalities by connecting them with a large language model and experimentally demonstrate that spatial sound perception is an essential part of our task.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：现有音频-视觉学习方法大多使用单声道音频，仅依赖语义或时间对齐（如声音与物体类别的匹配），忽略了声音来源的空间位置信息。然而，人类利用双耳听觉感知空间信息，结合视觉可以实现高级空间推理（例如听到手机铃声从背包中传出，推断手机在背包里）。
- **核心问题**：定义并解决**音频-视觉空间推理**（Audio-Visual Spatial Reasoning）任务，即理解声音与视觉环境之间的空间关系，超越简单的声源定位或语义对应。
- **整体意义**：本研究首次系统性地将空间音频与视觉结合，通过大语言模型实现复杂空间推理，填补了该领域的空白，为多模态理解和智能体交互提供了新方向。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：构建一个多模态大语言模型（Hear You Are LLM），将空间音频（双耳音频）和全景视觉特征进行编码，并通过投影器送入大语言模型，使其能够回答关于音频-视觉空间关系的问题。
- **关键技术细节**：
  - **视觉编码器**：使用 SigLIP2 NaFLEX，输出空间对齐的视觉 token（保留空间布局）。
  - **音频编码器**：使用预训练的 Spatial-AST 双耳音频编码器（来自 BAT 工作），输入双耳音频频谱图，生成保留空间声学线索的音频 token。
  - **投影器**：采用 Q-Former 架构，音频侧使用 BAT 的预训练权重，视觉侧使用 BLIP-2 前两层预训练权重；音频 token 数 64，视觉 token 数 128。
  - **大语言模型**：使用 Qwen2-7B-Instruct 作为骨干。
  - **训练策略**：
    - 先进行单模态预热训练（对视觉和音频编码器分别用分类和定位任务训练）。
    - 然后端到端微调全部模型（LLM 和图像编码器使用 LoRA，音频编码器冻结）。
    - 训练目标为标准语言建模（交叉熵损失）。
- **数据集构建**：创建 **Hear You Are QA** 数据集，基于 SoundSpaces 2.0 仿真器、Matterport3D 场景、VGGSound 音频源、Stable Diffusion 3 和 InstantMesh 生成的 3D 物体。包含 1 百万问答对，覆盖 9 类问题（空间对应、相对位置、空间与语义对应、语义共现）。场景中可包含无视觉对应或语义不一致的声源，以迫使模型学习空间线索而非语义捷径。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：
  - 训练：72 个 Matterport3D 场景
  - 验证：9 个场景
  - 测试：9 个场景
  - 每个场景包含 360° 全景图像和 10 秒双耳音频。
- **基准**：
  - 针对声源定位任务评估了 ISSL、ACL-SSL 等经典方法。
  - 针对多模态推理任务，主要对比了 **VideoLLaMA2**（使用与本文相同的视觉和音频编码器，但使用单声道音频，并替换 LLM 骨干为 Qwen2）。
  - 还设定了仅问问题（无输入）的随机基线。
- **对比方法**：
  - ISSL 和 ACL-SSL：传统的音频-视觉声源定位方法（仅支持无需语言理解的任务）。
  - VideoLLaMA2：多模态 LLM 基线，使用单声道音频。
  - 本文方法：使用双耳音频 + 视觉 + 问题。

## 4. 资源与算力

- **文中明确说明**：
  - 训练硬件：8 块 A5000 GPU。
  - 有效 batch size：128。
  - 训练时长：3 天。
  - LoRA rank：16（用于图像编码器和 LLM）。
  - 整个训练过程（含单模态预热）的描述提供了足够细节。

## 5. 实验数量与充分性

- **实验组数**：
  - 主实验结果表（Table 2）：在 6 个指标上对比了本文方法与 3 个基线。
  - 消融实验表（Table 3）：比较了 R+B+Q（双耳音频）、R+M+Q（单声道音频）、B+Q、M+Q、R+Q 五种模态设置，覆盖所有 9 类问题，并报告了分类、方向、距离等多类指标。
  - 还进行了交叉评估（训练于 R+B+Q 下测试于其他模态），分析了视觉信号对空间音频学习的影响。
- **充分性**：
  - 消融实验全面，清晰展示了每种模态的贡献。
  - 实验设计客观：与 VideoLLaMA2 保持公平比较（相同编码器、相同 LLM 骨干，仅音频输入不同）。
  - 但未报告误差棒或统计显著性检验（文中解释为资源限制），这一点略有不足。
  - 整体上实验数量合理，结论有充分数据支撑。

## 6. 论文的主要结论与发现

- 双耳音频是空间推理的关键：在需要空间线索的任务（如声源不可见、多个相似物体竞争同一声音语义）中，仅用单声道音频的基线模型性能显著下降，而本文方法保持稳定。
- 当视觉场景中只有一个语义匹配的物体时，单声道音频加视觉也能利用视觉空间信息进行合理推理；但当存在多个语义匹配物体时，空间音频成为必要，因为单声道音频无法区分。
- 视觉信息在训练中对空间音频学习也有正面作用：训练时加入视觉，即使在测试时仅用双耳音频，某些任务表现更好，说明视觉提供了隐式空间对齐。
- 总体表明：纯单声道或纯双耳音频均无法独立完成复杂的音频-视觉空间推理，必须结合双耳音频与视觉。

## 7. 优点：方法或实验设计上的亮点

- **任务定义新颖**：首次系统定义并解决音频-视觉空间推理任务，超越传统声源定位。
- **大规模合成数据集**：基于仿真生成 1M 问答对，涵盖多种空间场景和反事实例子，避免语义捷径，促进模型学习真正空间对应。
- **合理且公平的基线对比**：将 VideoLLaMA2 改造为与本文相同的编码器和 LLM，仅变更音频输入，确保比较公平。
- **详实的消融实验**：不仅展示完整模态组合，还进行交叉评估，揭示不同模态在推理中的具体作用。
- **技术方案实用**：采用 LoRA 微调、预训练编码器冻结或部分微调，降低了训练开销。

## 8. 不足与局限

- **实验统计**：未报告误差棒或多次运行结果，无法评估方法的稳定性（文中解释因资源限制）。
- **场景限制**：
  - 数据集不包含移动声源、物体动作、或墙壁/房间遮挡的物体，与现实动态场景有差距。
  - 所有场景为室内（Matterport3D），未覆盖室外场景。
  - 声音源为单一声源，未处理多个同时发声源。
- **方法局限**：
  - 依赖仿真数据，可能存在域差距（渲染伪影、HRTF 简化）。
  - 音频编码器冻结，可能限制了空间音频表示的学习。
  - 未考虑声音与物体动作的关联（如人翻书的声音对应手的动作）。
- **可重复性**：文中承诺开源代码和数据，但当前提交尚不可获取。若仅依赖文本描述，部分细节（如数据生成脚本、超参数选择）可能不足以完全复现。
- **社会影响**：文中仅简要提及，未深入讨论潜在负面用途（如监控、隐私）。

（完）
