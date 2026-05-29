---
title: "OpenOmni: Advancing Open-Source Omnimodal Large Language Models with Progressive Multimodal Alignment and Real-time Emotional Speech Synthesis"
title_zh: "OpenOmni: 通过渐进式多模态对齐和实时情感语音合成推进开源全模态大语言模型"
authors: "Run Luo, Ting-En Lin, Haonan Zhang, Yuchuan Wu, Xiong Liu, Yongbin Li, Longze Chen, Jiaming Li, Lei Zhang, Xiaobo Xia, Hamid Alinejad-Rokny, Fei Huang, Min Yang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=4iehXI36QG"
tags: ["query:speech-model"]
score: 9.0
evidence: 开源的具有实时情感语音合成的全模态大语言模型
tldr: 针对开源全模态研究中高质量数据集缺失和实时情感语音合成挑战，提出两阶段训练框架：先对预训练语音模型在图像-文本任务上进一步训练实现对齐，再集成语音生成模块。该方法使得模型在图像、文本和语音的理解与生成上均达到先进水平，特别实现了接近零样本的实时情感语音合成。开源模型和数据集推动了全模态研究的发展。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-4iehxi36qg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1397, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4iehxi36qg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1419, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4iehxi36qg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 665, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4iehxi36qg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1340, \"height\": 828, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-4iehxi36qg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1406, \"height\": 563, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-4iehxi36qg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 440, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4iehxi36qg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4iehxi36qg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1181, \"height\": 668, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4iehxi36qg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1445, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4iehxi36qg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4iehxi36qg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1035, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4iehxi36qg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1449, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4iehxi36qg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1448, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-4iehxi36qg/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1475, \"height\": 428, \"label\": \"Table\"}]"
motivation: 解决开源全模态大语言模型中缺乏高质量数据集和实时情感语音合成的挑战。
method: 提出两阶段训练框架，先进行全模态对齐，再进行实时情感语音生成。
result: 实现了先进的全模态理解和生成性能，特别是在实时情感语音合成上表现出色。
conclusion: 推动了开源全模态大语言模型的发展，提供了高质量数据集和模型。
---

## Abstract
Recent advancements in omnimodal learning have significantly improved understanding and generation across images, text, and speech, yet these developments remain predominantly confined to proprietary models. The lack of high-quality omnimodal datasets and the challenges of real-time emotional speech synthesis have notably hindered progress in open-source research. To address these limitations, we introduce OpenOmni, a two-stage training framework that integrates omnimodal alignment and speech generation to develop a state-of-the-art omnimodal large language model. In the alignment phase, a pretrained speech model undergoes further training on image-text tasks, enabling (near) zero-shot generalization from vision to speech, outperforming models trained on tri-modal datasets. In the speech generation phase, a lightweight decoder is trained on speech tasks with direct preference optimization, which enables real-time emotional speech synthesis with high fidelity. Extensive experiments demonstrate that OpenOmni surpasses state-of-the-art models across omnimodal, vision-language, and speech-language benchmarks. It achieves a 4-point absolute improvement on OmniBench over the leading open-source model VITA, despite using 5$\times$ fewer training examples and a smaller model size (7B vs. 7$\times$8B). Besides, OpenOmni achieves real-time speech generation with less than 1 second latency at non-autoregressive mode, reducing inference time by 5$\times$ compared to autoregressive methods, and improves emotion classification accuracy by 7.7\%. The codebase is available at https://github.com/RainBowLuoCS/OpenOmni.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题背景**：多模态大语言模型（MLLMs）在图像、文本、语音等模态的理解与生成上取得显著进展，但大多数优秀成果仍局限于闭源商业模型（如 GPT-4o）。开源全模态模型面临三大挑战：
  - **缺乏高质量三模态数据集**（图像-语音-文本），导致跨模态对齐困难。
  - **推理延迟高**：现有模型多采用自回归（AR）架构，语音生成依赖外部 TTS 模块，无法实现低延迟实时交互。
  - **情感表达能力弱**：模型生成语音缺乏情感一致性，语调机械、不自然。
- **整体含义**：该论文旨在构建一个完全开源、数据高效、实时且能生成情感语音的全模态大语言模型（OLLM），缩小与闭源模型的差距。

## 2. 论文提出的方法论

### 2.1 核心思想
- 采用**两阶段渐进式训练框架**，以**文本作为枢轴（pivot）**，先进行语音-文本对齐和图像-文本对齐，隐式实现三模态对齐，避免直接依赖昂贵的三模态数据。
- 在语音生成阶段，集成**轻量级流式语音解码器**，支持自回归（AR）和非自回归（NAR）两种模式，实现实时语音合成。
- 引入**直接偏好优化（DPO）** 用于情感语音生成，使模型能根据上下文生成情感连贯的语音，无需额外控制模块。

### 2.2 关键技术细节

1. **语音-文本对齐阶段**：使用预训练语音编码器（Whisper-large-v3）提取音频特征，对大规模语音-文本对进行语言建模训练，使模型获得语音理解能力。
2. **图像-文本对齐阶段**：使用图像编码器（CLIP-ViT-L）提取视觉特征，先进行预训练（冻结LLM），再进行指令微调（解冻LLM），使模型获得图像理解和指令跟随能力。
3. **文本引导的语音生成阶段**：
   - 训练一个轻量级语音解码器（基于 Qwen2.5-0.5B + MoE 层），使用连接时序分类（CTC）损失进行端到端训练，支持 NAR 模式下的并行解码。
   - 设计**文本引导模块（TGM）**，通过交叉注意力融合 LLM 隐藏状态和正确语义的文本特征，加速收敛并稳定训练。
4. **情感语音 DPO**：构建多轮对话情感偏好数据集 EO2S-9K，使用 CTC-DPO 损失优化，使模型生成与对话历史情感一致的语音。

### 2.3 核心公式（文字说明）

- 语音-文本对齐损失：语言建模目标，最大化文本响应的似然。
- 图像-文本预训练损失：语言建模目标，最大化图像描述文本的似然。
- 图像-文本指令微调损失：给定图像和指令，最大化回答的似然。
- 语音生成 CTC 损失：对所有可能对齐路径求和，最小化负对数似然。
- 情感 DPO 损失：基于偏好对，优化策略模型相对于参考模型的比值。

## 3. 实验设计

### 3.1 数据集
- **全模态对齐数据**：
  - 语音-文本：WeNetSpeech、LibriSpeech、AIShell-4 + 部分 O2S-300K（总计8000小时双语数据）。
  - 图像-文本：LLaVA-Pretrain-595K 用于预训练，MMEvol 用于指令微调。
- **语音生成数据**：O2S-300K（30万条指令，含中英文，使用 CosyVoice 合成语音）。
- **情感 DPO 数据**：EO2S-9K（9000条多轮对话偏好对，覆盖9种情感，包含中英文）。

### 3.2 评估基准
- **全模态理解**：OmniBench（1142个问答对）、AV-Odyssey Bench。
- **视觉-语言**：MMBench-EN/CN、MMStar、RealWorldQA、MMMU、MathVista、AI2D、HallusionBench。
- **语音-语言**：AIShell-2、LibriSpeech（S2T 和 T2S 任务的 WER）。
- **情感语音**：EO2S-9K 测试集，使用 Emotion2Vec 分类准确率。

### 3.3 对比方法
- 全模态模型：AnyGPT、Video-SALMONN、UnifiedIO2、VITA、VITA-1.5、Baichuan-Omni。
- 视觉-语言模型：GPT-4o/4o-mini、MiniCPM-V2.5、Qwen2-VL-Chat、EMOVA、Cambrian-I、MMEvol 等。
- 语音模型：SpeechT5、SALMONN、Mini-Omni、Freeze-Omni、Qwen2-Audio 等。

### 3.4 实验充分性
- 共进行了 **8 个以上主要基准**的评估，覆盖全模态、视觉、语音、情感四个方面。
- 进行了 **6 组消融实验**：TGM 模块效果、解码器层数和专家数、LLM 是否冻结、对齐顺序、联合训练 vs 渐进训练、训练数据规模等。
- 所有实验使用 VLMEvalKit 进行零样本评估，确保一致性。

## 4. 资源与算力
- **硬件**：8×NVIDIA A100-80G GPUs。
- **训练时间**：
  - Stage I（语音-文本对齐）：40 GPU 小时
  - Stage II（图像-文本预训练）：80 GPU 小时
  - Stage III（图像-文本指令微调）：500 GPU 小时
  - Stage IV（语音解码器训练）：36 GPU 小时
  - Stage V（情感 DPO）：8 GPU 小时
- **模型大小**：7B 参数（LLM 为 Qwen2.5-7B-Instruct），远小于 VITA（7×8B）。

## 5. 主要结论与发现

1. **全模态理解**：OpenOmni 在 OmniBench 上以 37.40 分超越 VITA（33.45），提升 4 个绝对百分点，且使用更少数据（1.6M vs 5M）和更小模型（7B vs 7×8B）。
2. **视觉-语言**：在 8 个 VLM 基准上全面超越 VITA，尤其在 MMBench-CN 和 HallusionBench 上分别提升 7.0% 和 11.3%。
3. **语音理解与生成**：在 S2T 和 T2S 任务上均取得最佳 WER，NAR 模式下生成 30 秒语音延迟 <1 秒，速度是 AR 模型的 5 倍以上。
4. **情感语音**：DPO 使情感分类准确率提升 7.7%（中文提升 12.5%，英文提升 2.8%）。
5. **渐进式对齐有效**：仅用双模态数据即可实现接近三模态数据训练的效果，且对齐顺序影响很小。

## 6. 优点

- **数据高效**：无需大规模三模态数据，利用语音-文本和图像-文本双模态数据即可。
- **实时性**：NAR 模式实现 <1 秒延迟，适合交互式应用。
- **情感表达**：DPO 使语音情感自然，无需额外控制模块。
- **完全开源**：代码、模型、数据集均公开，促进社区研究。
- **架构灵活**：支持 AR 和 NAR 两种解码模式，可根据需求平衡质量和速度。
- **消融充分**：对 TGM、层数、专家数、对齐顺序、联合训练等做了全面分析。

## 7. 不足与局限

- **语言覆盖有限**：仅支持中英文，未验证多语言场景。
- **NAR 模式质量略低**：虽然速度快，但生成质量不如 AR 模式。
- **情感分类依赖预定义模型**：使用 Emotion2Vec 进行评估，可能存在误差。
- **缺乏真实人类评测**：情感语音效果主要靠自动分类准确率，未进行主观听觉测试。
- **计算资源需求仍较高**：Stage III 需要 500 GPU 小时，对一般研究者仍有门槛。
- **未讨论泛化到视频模态**：当前只处理静态图像，视频理解能力较弱（附录中仅用帧平均方式简单测试）。
- **存在潜在安全风险**：如语音深度伪造、情感操纵等，论文仅简要提及。

（完）
