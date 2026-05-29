---
title: "SALMONN-omni: A Standalone Speech LLM without Codec Injection for Full-duplex Conversation"
title_zh: "SALMONN-omni: 无需编解码器注入的独立语音大语言模型实现全双工对话"
authors: "Wenyi Yu, Siyin Wang, Xiaoyu Yang, Xianzhao Chen, Xiaohai Tian, Jun Zhang, Guangzhi Sun, Lu Lu, Yuxuan Wang, Chao Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=AsRB5nmlOD"
tags: ["query:speech-model"]
score: 9.0
evidence: 无需编解码器注入的独立语音大语言模型实现全双工对话
tldr: 现有全双工语音对话系统常采用模块化架构或注入音频编解码器，导致错误累积和性能下降。本文提出SALMONN-omni，首个无需编解码器注入的独立语音大语言模型，能够在单一模型中完成语音理解与生成，实现了自然的全双工对话，在多项指标上达到最优。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-asrb5nmlod/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1220, \"height\": 725, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-asrb5nmlod/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1296, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-asrb5nmlod/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1373, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-asrb5nmlod/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 607, \"height\": 462, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-asrb5nmlod/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1429, \"height\": 647, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-asrb5nmlod/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1435, \"height\": 675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-asrb5nmlod/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1439, \"height\": 757, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-asrb5nmlod/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1438, \"height\": 807, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-asrb5nmlod/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1395, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-asrb5nmlod/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1349, \"height\": 219, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-asrb5nmlod/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1416, \"height\": 668, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-asrb5nmlod/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1103, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-asrb5nmlod/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1050, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-asrb5nmlod/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1423, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-asrb5nmlod/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 727, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-asrb5nmlod/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 782, \"height\": 576, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-asrb5nmlod/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1028, \"height\": 340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-asrb5nmlod/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1421, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-asrb5nmlod/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1420, \"height\": 332, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-asrb5nmlod/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1419, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-asrb5nmlod/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1130, \"height\": 626, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-asrb5nmlod/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 648, \"height\": 412, \"label\": \"Table\"}]"
motivation: 现有全双工语音对话系统因模块化或编解码器注入导致错误累积和性能下降。
method: 提出SALMONN-omni，单一LLM直接处理语音输入输出，无需编解码器注入。
result: SALMONN-omni在全双工对话任务中展现了优越的性能和自然度。
conclusion: 无需编解码器注入的独立语音LLM是实现高效全双工对话的有前景方向。
---

## Abstract
In order to enable fluid and natural human-machine speech interaction, existing full-duplex conversational systems often adopt modular architectures with auxiliary components such as voice activity detectors, interrupters, conversation state predictors, or multiple LLMs. These systems, however, suffer from error accumulation across modules and struggle with key challenges such as context-dependent barge-in and echo cancellation. Recent approaches, most notably Moshi, simplify the pipeline by injecting audio codecs into the token space of a single LLM. However, such methods still incur significant performance degradation when operating on the speech rather than text modality. In this paper, we introduce SALMONN-omni, the first single, standalone full-duplex speech LLM that operates without audio codecs in its token space. It features a novel dynamic thinking mechanism within the LLM backbone, enabling the model to learn when to transition between speaking and listening states. Experiments on widely used benchmarks for spoken question answering and open-domain dialogue show that SALMONN-omni achieves at least 30\% relative performance improvement over existing open-source full-duplex models and performs highly competitively to half-duplex and turn-based systems, despite using substantially less training data. Moreover, SALMONN-omni demonstrates strong performance in complex conversational scenarios, including turn-taking, backchanneling, echo cancellation and context-dependent barge-in, with further improvements achieved through reinforcement learning. Some demo conversations between user and SALMONN-omni are provided in the following repository https://github.com/bytedance/SALMONN.

---

## 论文详细总结（自动生成）

# SALMONN-omni: 无需编解码器注入的独立语音大语言模型实现全双工对话 论文总结

---

## 1. 论文的核心问题与整体含义（研究动机和背景）

-   **痛点**：现有全双工（full-duplex）人机语音对话系统，要么采用模块化架构（集成VAD、中断检测、对话状态预测等），导致模块间错误累积；要么通过**注入音频编解码器（codec）** 到LLM词表来简化流程（如Moshi），但跨模态建模时出现性能退化（知识/推理能力下降），且需海量数据弥补模态差距。
-   **现状局限性**：
    -   模块化系统依赖外部VAD/对话控制器，错误传播，延迟高。
    -   Codec注入方法（Moshi等）仍无法媲美文本LLM的性能，且难以精确预测对话切换时机。
    -   其他“模型即服务器”方法（如VITA、Freeze-Omni）需要两个LLM进程分别处理听和说，增加开销且非独立。
-   **核心目标**：设计首个**无需注入音频编解码器**的**独立（standalone）单LLM**全双工语音对话系统（SALMONN-omni）：支持同时输入/输出语音，并自主决定何时说/停。

## 2. 论文提出的方法论：核心思想、关键技术细节

-   **整体架构**：流式语音编码器 (Mamba) → 编码器适配器 (MLP) → **单个LLM主干** (Llama-3-8B-Instruct + LoRA) → 合成器适配器 → 流式语音合成器 (基于CosyVoice2)。**全程不使用codec token**。
-   **核心挑战解决**：
    -   **挑战1（流式输入/输出）**：LLM主干通过**隐藏嵌入（hidden embeddings）** 直接接入流式编码器和流式合成器。
    -   **挑战2（同时处理环境和助手流）**：将对话分成**固定时间块**（80ms），在每个块内先处理**环境流**（用户语音+背景+自身回声），再生成**助手流**（回复文本 + 语音嵌入）。两者通过交织（interleaving）送入LLM的单一序列。
    -   **挑战3（时间感知与模态对齐）**：**周期性同步机制**：处理固定时长的输入同时生成匹配时长的输出。每80ms输入，LLM生成1个token；每4个文本token触发合成器生成12个语音token（480ms）。
    -   **挑战4（动态对话状态切换）**：提出 **“thinking”策略**，让LLM自行预测状态转换。
-   **“Thinking”策略（显式）**：引入两个特殊token `<think>` 和 `<shift>`。
    -   倾听状态：LLM每个时间块生成 `<think>`（模拟思考何时说话）。
    -   说出状态：响应完成后继续生成 `<think>` 直到状态切换。
    -   `<shift>` 标记“倾听→说话”或“说话→倾听”切换。
    -   该策略将状态预测**作为LLM正常自回归输出的一部分**，无需额外预测器。
-   **训练三阶段**：
    -   **阶段1**：连接流式编码器（冻结编码器/LLM，训练适配器和LoRA），任务：ASR + QA。
    -   **阶段2**：连接流式合成器，端到端训练（冻结编码器/LLM，训练适配器、LoRA、合成器），任务：ASR、QA、多轮对话（含barge-in和backchanneling）。
    -   **阶段3**：RL（DPO）优化全双工建模（barge-in和backchanneling场景的偏好对齐）。

## 3. 实验设计：数据集 / 场景、基准、对比方法

-   **评估数据集**：
    -   **口语QA**：Llama Questions（Acc%）、Web Questions（Acc%）、TriviaQA（Acc%）。
    -   **开放域对话**：AlpacaEval（GPTScore 1-5，由GPT-4.1打分）。
    -   **全双工建模**：人工收集barge-in/backchanneling样本，评估**turn-taking成功率**和**F1分数**（区分真正中断vs伪中断/回声）。
    -   **真实延迟统计**：真人机对话（3个场景，共60轮）统计IPU、Pause、Gap、TTFA。
-   **对比方法（11个基线）**：
    -   全双工：Moshi、Freeze-Omni（非独立）。
    -   半双工：GLM-4-Voice、Qwen2.5-Omni、VITA-1.5、miniCPM-o、Kimi-Audio、Baichuan-Audio。
-   **评估设置**：
    -   **Oracle turn-taking**：强制模型在问题结束时开始回答。
    -   **Predicted turn-taking**：模型自主决定何时开始（仅全双工能跑）。
    -   与Moshi对比时因其无法强制说话，仅用predicted setting。

## 4. 资源与算力

-   **Mamba流式编码器预训练**：LibriHeavy + GigaSpeech，300k步，batch size 512。
-   **SALMONN-omni训练**：**32张A100 GPU**。
    -   Stage 1：50k steps。
    -   Stage 2：30k steps。
    -   Stage 3（DPO）：batch size 128/256/512，学习率1e-6，约40 steps内收敛。
-   **未明确说明**：单卡内存、总训练小时数、推理时实时因子等细节未提供。

## 5. 实验数量与充分性

-   **实验组数**：
    -   主实验（Table 3）：对比11个模型在4个数据集上的S2T/S2S/UTMOS。
    -   消融实验：
        -   Thinking策略对比（Table 2）：隐式 vs 显式，训练阶段1/2的影响。
        -   Thinking策略变体（Appendix C）：5种变体在ASR上的对比。
        -   DPO训练消融（Table 6/10-12）：3种batch size，不同steps。
        -   Turn-taking成功率（Table 4）：3个模型在4个数据集上的结果。
        -   Barge-in/backchanneling F1（Table 5/6）：含回声因子。
        -   真实对话统计（Table 7）：IPU/Pause/Gap。
        -   UTMOS详细（Table 13）：各模型各数据集。
        -   情感强度（Table 14）：额外实验。
-   **充分性判断**：**充分且公平**。覆盖了主流基准、多种基线、消融考虑周全（策略、数据量、回声、DPO超参），对比方法涵盖近期开放模型，结果具有可重复性。

## 6. 论文的主要结论与发现

-   **全双工建模性能**：在predicted turn-taking设置下，SALMONN-omni在所有数据集上达到**SOTA**，平均相对提升**35.9%**（对比Moshi/Freeze-Omni）。
-   **与半双工模型竞争**：在oracle turn-taking设置下，性能堪比甚至超越训练数据大得多的半双工模型（如Kimi-Audio训练1300万小时音频）。
-   **Thinking策略有效性**：显式thinking优于隐式；引入助手流后turn-taking成功率从~70%提升至~90%。
-   **DPO效果**：SFT后模型倾向于被中断，使用DPO训练后，整体F1从0.86提升至**0.90**（batch size 256，40步）。训练初期模型变得极度保守（罕见中断），后逐渐恢复并超越SFT。
-   **真实延迟**：TTFA约405ms，barge-in场景响应约128-144ms，接近实时。
-   **情感表达**：情感强度得分3.49（优于所有基线），但仍存在情感不匹配问题。

## 7. 优点：方法或实验设计上的亮点

1. **首次提出codec-free独立全双工框架**：直接让LLM处理语音嵌入，无需修改LLM词表，避免模态间隙。
2. **新颖的“thinking”显式状态预测**：将对话状态切换任务转化为LLM自然语言生成的一部分，实现“your LLM is secretly a full-duplex predictor”。
3. **多流交织与同步机制**：优雅解决了同时处理环境音和助手回声的挑战，且通过固定时间块实现模态对齐。
4. **RL优化全双工动态**：首次将DPO用于全双工建模的后训练，有效改善了模型的barge-in判断（防止过于敏感或迟钝）。
5. **实验充分且公平**：覆盖多种场景（QA、对话、barge-in、backchanneling、回声、延迟），对比模型全面，消融实验细致（策略、回声因子、DPO步数/batch size）。
6. **实用性**：流式处理，延迟低；训练数据相对较小（~1M样本）仍达到高竞争力。

## 8. 不足与局限

1. **很少生成backchanneling（填充词）**：训练数据中backchanneling例子较少，模型在用户说话时很少主动插入“嗯”“哦”等，降低交互自然度。
2. **训练序列长度限制**：由于内存约束，训练序列最长3分钟。超出时性能下降；未来需引入长时记忆机制。
3. **情感表达不稳定**：情感强度分数高但仍不完美，有时产出情感不匹配的回复。
4. **计算资源未详尽**：未报告模型参数量、推理效率、实时因子等，难以对比实际计算开销。
5. **合成器依赖**：使用CosyVoice2合成器，其质量/延迟影响下游，且未在训练中优化合成器设计（如更早开始生成以减少TTFA）。
6. **评估局限**：
    -   AlpacaEval使用GPT-4.1打分，存在自动评估偏差。
    -   全双工建模的实际用户体验（如自然度、延迟感）仅通过有限真人对话统计，未进行大规模主观MOS。
    -   未测试多语言或噪音场景下的效果。
7. **潜在偏见与安全**：未讨论训练数据中的社会偏见或生成内容安全过滤机制；仅简单提及需确保无害。

---

（完）
