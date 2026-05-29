---
title: "VITA-1.5: Towards GPT-4o Level Real-Time Vision and Speech Interaction"
title_zh: VITA-1.5：迈向GPT-4o级别的实时视觉和语音交互
authors: "Chaoyou Fu, Haojia Lin, Xiong Wang, YiFan Zhang, Yunhang Shen, Xiaoyu Liu, Haoyu Cao, Zuwei Long, Heting Gao, Ke Li, Long MA, Xiawu Zheng, Rongrong Ji, Xing Sun, Caifeng Shan, Ran He"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=8PUzLga3lU"
tags: ["query:speech-model"]
score: 9.0
evidence: 多阶段训练实现视觉和语音交互，支持语音到语音对话
tldr: 本文提出VITA-1.5，通过精心设计的多阶段训练，逐步让大语言模型同时理解视觉和语音信息，最终实现流畅的视觉-语音交互。该方法不仅保持了强大的视觉-语言能力，还能进行高效的语音到语音对话，无需单独的ASR模块。实验表明，VITA-1.5在视觉和语音任务上均达到GPT-4o水平，为多模态交互系统提供了新范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-8puzlga3lu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1088, \"height\": 697, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8puzlga3lu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 425, \"height\": 512, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8puzlga3lu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1450, \"height\": 1523, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-8puzlga3lu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1181, \"height\": 948, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8puzlga3lu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1456, \"height\": 558, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8puzlga3lu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1453, \"height\": 542, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8puzlga3lu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1387, \"height\": 311, \"label\": \"Table\"}]"
motivation: 现有多模态大模型侧重视觉和文本，较少强调语音在交互中的作用，难以同时实现高性能。
method: 采用多阶段训练策略，逐步训练LLM融合视觉和语音信息，最终实现语音到语音交互。
result: 在视觉-语言和语音对话基准上达到GPT-4o水平，且延迟低。
conclusion: 多阶段训练是构建统一视觉-语音交互模型的有效途径。
---

## Abstract
Recent Multimodal Large Language Models (MLLMs) have typically focused on integrating visual and textual modalities, with less emphasis placed on the role of speech in enhancing interaction. However, speech plays a crucial role in multimodal dialogue systems, and implementing high-performance in both vision and speech tasks remains a challenge due to the fundamental modality differences. In this paper, we propose a carefully designed multi-stage training methodology that progressively trains LLM to understand both visual and speech information, ultimately enabling fluent vision and speech interaction. Our approach not only preserves strong vision-language capacity, but also enables efficient speech-to-speech dialogue capabilities without separate ASR and TTS modules, significantly accelerating multimodal end-to-end response speed. By comparing against state-of-the-art counterparts across benchmarks for image, video, and speech, we demonstrate that our omni model is equipped with both strong visual and speech capabilities, making omni understanding and interaction.

---

## 论文详细总结（自动生成）

# VITA-1.5: 迈向GPT-4o级别的实时视觉和语音交互 — 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有多模态大语言模型（MLLMs）主要聚焦于视觉与文本模态的融合，对语音模态在增强交互中的作用重视不足。同时实现高性能的视觉与语音任务面临根本性挑战，因为视觉（空间信息）与语音（时序动态）存在本质差异，联合优化常导致模态冲突（如引入语音会损害视觉能力）。
- **研究动机**：随着人机交互需求增长，语音在对话系统中扮演关键角色。传统级联式语音系统（ASR+LLM+TTS）存在延迟高、丢失副语言信息（如语调、情感）等问题，难以实现实时、自然的交互。GPT-4o等闭源模型展示了端到端语音交互的可能性，但开源模型在多模态（视觉+语音）统一方面仍有显著差距。
- **整体含义**：本文提出 VITA-1.5，通过精心设计的三阶段训练策略，逐步将视觉和语音模态融入大语言模型，在保持强大视觉-语言能力的同时，实现无需独立ASR/TTS模块的端到端语音对话，显著加速响应速度，向GPT-4o级别的实时视觉-语音交互迈出重要一步。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
采用**渐进式多阶段训练**，逐步引入视觉和语音模态，缓解模态冲突，使模型同时具备强大的视觉理解和语音输入输出能力，最终实现流畅的语音到语音（speech-to-speech）交互。

### 模型架构
- **输入侧**：视觉编码器（InternViT-300M） + 视觉适配器（2层MLP）；语音编码器（350M参数，12.5Hz帧率） + 语音适配器（卷积层，2倍下采样）。通过“多模态编码器-适配器-LLM”结构输入LLM。
- **LLM**：使用 Qwen2-7B 作为基座。
- **输出侧**：基于 TiCodec 的编解码模型（单码本，40Hz离散语音token），后接非自回归（NAR）语音解码器（4层LLaMA decoder）和自回归（AR）语音解码器（4层LLaMA decoder），生成高质量语音token，再由Codec解码器恢复为24kHz波形。

### 三阶段训练策略

#### 阶段1：视觉-语言训练（Vision-Language Training）
- **1.1 视觉对齐**：仅训练视觉适配器，使用20%描述性标题数据，让LLM初步对齐视觉特征。
- **1.2 视觉理解**：训练视觉编码器、适配器及LLM，使用全部标题数据（约1.4M），学习生成图像描述。
- **1.3 视觉SFT**：使用全部QA数据（约22M）及20%标题数据，训练视觉编码器、适配器及LLM，增强指令跟随和视觉问答能力。

#### 阶段2：音频输入调优（Audio Input Tuning）
- **2.1 音频对齐**：
  - (a) 使用CTC损失训练语音编码器，使其能从语音输入预测转录文本。
  - (b) 冻结语音编码器，训练语音适配器+LLM，让LLM输出转录文本（引入特殊可训练输入token引导ASR任务）。
  数据：11万小时语音-文本配对数据。
- **2.2 音频SFT**：使用4%标题数据、20%QA数据，其中约一半文本问题随机替换为TTS生成的语音版本。训练视觉、音频模块及LLM，并添加分类头区分输入为语音或文本，提升多模态输入适应性。

#### 阶段3：音频输出调优（Audio Output Tuning）
- **3.1 Codec训练**：使用单码本编解码模型（TiCodec），3千小时文本-语音配对数据训练编解码器。
- **3.2 NAR+AR解码器训练**：冻结LLM，利用文本嵌入向量经NAR解码器生成全局语义特征，再由AR解码器逐帧预测语音token。训练不改变LLM参数，保持多模态性能。

## 3. 实验设计

### 使用的数据集/场景
- **图像理解**：MME、MMBench、MMStar、MMMU、MathVista、HallusionBench、AI2D、OCRBench、MMVet（共9个基准）。
- **视频理解**：Video-MME（含/无字幕）、MVBench、TempCompass。
- **语音识别**：中文测试集（aishell-1、test_net、test_meeting，CER指标）；英文测试集（LibriSpeech的dev-clean/dev-other/test-clean/test-other，WER指标）。

### 对比方法
- **图像/视频**：开源模型（VILA-1.5、LLaVA-Next、CogVLM2、InternLM-XComposer2.5、Cambrian-1、MiniCPM-V 2.6、Ovis1.5、InternVL系列、LLaVA-OV、Video-LLaVA等）和闭源模型（GPT-4V、GPT-4o、GPT-4o-mini、Gemini 1.5 Pro、Claude 3.5 Sonnet）。
- **语音ASR**：Wav2vec2-base、Mini-Omni2、Freeze-Omni、VITA-1.0。

## 4. 资源与算力

论文**未明确说明**训练所需的GPU型号、数量、训练时长等具体算力信息。仅在实验部分提及使用了Qwen2-7B等基座模型，但未披露完整训练过程的硬件配置。这属于论文的一个信息缺失。

## 5. 实验数量与充分性

- **实验数量**：图像理解9个基准，视频理解3个基准，语音ASR 2个语言共7个子集。共进行多组对比实验，覆盖主流基准。未包含消融实验（如逐步增加训练阶段的效果验证），仅在表格中对比了Stage1和Stage3的性能保持。
- **充分性与公平性**：对比方法全面（含闭源最强模型），评估指标标准。但缺少对语音输出质量（如自然度、MOS评分）和端到端延迟的定量评估，也未进行人工评估或用户体验测试。实验基本客观，但覆盖广度可进一步提升。

## 6. 论文的主要结论与发现

1. VITA-1.5通过三阶段训练成功缓解了视觉与语音模态间的冲突，在保持视觉-语言能力（与顶级开源模型相当，部分超越GPT-4V/GPT-4o-mini）的同时，大幅提升了语音能力。
2. 在图像理解基准上，VITA-1.5平均得分66.8，接近MiniCPM-V 2.6（68.5）和GPT-4o mini（66.3），优于GPT-4V（58.5）。
3. 在视频理解上，表现与LLaVA-OV、InternVL-2等开源模型相当，但与GPT-4o、Gemini 1.5 Pro仍有差距。
4. 在语音ASR任务上，中文CER最低2.2%，英文WER最低3.4%，均优于专有语音模型（如Freeze-Omni、Mini-Omni2）和VITA-1.0。
5. 端到端语音对话无需额外ASR/TTS模块，延迟显著降低（论文声称“near real-time”）。

## 7. 优点

- **方法创新**：渐进式多阶段训练策略，逐步引入模态，有效避免灾难性遗忘和模态冲突，是构建统一视觉-语音模型的实用范式。
- **架构设计**：采用单码本Codec + NAR/AR语音解码器，在LLM保持冻结的情况下独立训练，保证视觉-语言能力不退化。
- **数据规模大**：使用11万小时ASR数据、3千小时TTS数据，以及22M+多模态指令数据，覆盖面广。
- **结果全面**：在多种模态（图像、视频、语音）的多个基准上对比，提供SOTA开源模型表现，并附上补基于闭源模型的对比。

## 8. 不足与局限

- **未提供算力信息**：缺乏训练资源（GPU型号、数量、时长等）的说明，降低了可复现性。
- **消融实验不足**：没有系统性的消融实验（如是否使用三阶段、数据比例影响、模态冲突量化等），仅用Stage1和Stage3对比，论证力度有限。
- **语音输出评估缺失**：仅评估了ASR（语音识别）性能，未评估语音生成质量（如自然度、音质、合成延迟、情感表达等），且缺少端到端对话延迟的定量数据。
- **视频理解仍有短板**：在Video-MME等基准上落后于GPT-4o和Gemini 1.5 Pro，差距约15-20分，表明视频动态理解仍需改进。
- **应用局限**：未讨论个性化、长时记忆、安全与偏见等问题，实际部署中的鲁棒性和可控性未经验证。
- **仅用公开基准**：实验全基于学术基准，缺乏真实场景交互的评估（如多轮对话连续性、噪声环境下的语音识别等）。

（完）
