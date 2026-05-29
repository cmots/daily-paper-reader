---
title: Aligning Spoken Dialogue Models from User Interactions
title_zh: 从用户交互中对齐口语对话模型
authors: "Anne Wu, Laurent Mazaré, Neil Zeghidour, Alexandre Défossez"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=kxFu9rQ0Mu"
tags: ["query:speech-model"]
score: 9.0
evidence: 语音到语音翻译的偏好对齐
tldr: 该论文针对实时口语对话中偏好学习缺乏的问题，提出了一种基于用户交互的偏好对齐框架，利用大型数据集和离线对齐方法微调全双工自回归语音到语音模型，显著提升了对话质量和自然度。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-kxfu9rq0mu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1729, \"height\": 539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kxfu9rq0mu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 841, \"height\": 619, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kxfu9rq0mu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kxfu9rq0mu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1595, \"height\": 1027, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kxfu9rq0mu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1400, \"height\": 802, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-kxfu9rq0mu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1225, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kxfu9rq0mu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1747, \"height\": 651, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kxfu9rq0mu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1595, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kxfu9rq0mu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1681, \"height\": 585, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kxfu9rq0mu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1466, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kxfu9rq0mu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1264, \"height\": 1445, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kxfu9rq0mu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 653, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kxfu9rq0mu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1394, \"height\": 637, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kxfu9rq0mu/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1382, \"height\": 764, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-kxfu9rq0mu/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1660, \"height\": 680, \"label\": \"Table\"}]"
motivation: 现有偏好学习方法主要针对文本，不适用于实时语音交互的复杂动态。
method: 收集15万对偏好数据，采用离线对齐方法微调全双工自回归语音到语音模型。
result: 实验表明该方法能有效提升语音对话模型的性能。
conclusion: 该框架为语音到语音模型的对齐提供了实用的解决方案。
---

## Abstract
We propose a novel preference alignment framework for improving spoken dialogue models on real-time conversations from user interactions. Current preference learning methods primarily focus on text-based language models, and are not directly suited to the complexities of real-time speech interactions, with richer dynamics (e.g. interruption, interjection) and no explicit segmentation between speaker turns.We create a large-scale dataset of more than 150,000 preference pairs from raw multi-turn speech conversations, annotated with AI feedback, to cover preferences over both linguistic content and temporal context variations. We leverage offline alignment methods to finetune a full-duplex autoregressive speech-to-speech model. Extensive experiments demonstrate that feedback on generic conversations can be consistently effective in improving spoken dialogue models to produce more factual, safer and more contextually aligned interactions. We deploy the finetuned model and conduct holistic human evaluations to assess the impact beyond single-turn conversations. Our findings shed light on the importance of a well-calibrated balance among various dynamics, crucial for natural real-time speech dialogue systems.

---

## 论文详细总结（自动生成）

# 从用户交互中对齐口语对话模型：论文总结

## 1. 核心问题与整体含义

**研究动机**：
- 现有的偏好学习方法（如 RLHF、DPO）主要针对**文本语言模型**，无法直接适用于**实时语音对话系统**。
- 实时语音交互具有更丰富的动态特性：打断、插话、重叠、无明确回合边界、时序敏感等，文本对齐方法无法处理这些语音特有的挑战。
- 语音对话系统正从传统级联架构（ASR→NLU→TTS）向**端到端全双工架构**演进（例如 Moshi），需要新的对齐框架来优化该类模型。

**整体含义**：
提出首个针对**全双工、实时语音对话模型**的偏好对齐框架，能够通过大规模用户交互数据，同时优化**内容质量**和**时序动态**，使模型更准确、更安全、更自然。

---

## 2. 方法论

### 核心思想
- 从真实用户与 Moshi 模型的**自由对话**中收集原始多轮语音交互日志。
- 使用 LLM 裁判（Mistral Large 2）识别有问题的模型回复（内容问题 + 时序问题），并生成改进后的**偏好回答**。
- 通过**离线偏好优化**（DPO-LN 等）微调全双工自回归语音-语音模型 Moshi。

### 关键技术细节
1. **偏好数据构建**：
   - 收集大量无约束对话，用户音频仅转录为文本（丢弃原始音频以保护隐私），保留模型生成的音频和时间戳。
   - 将模型回复的问题分为两类：
     - **内容相关**：不安全、不准确、不遵循指令等 → 由 LLM 生成改进回答。
     - **时序相关**：模型打断用户、长时间沉默不回应 → 程序化检测 + LLM 延迟/补答。
   - 最终合成**14 类偏好对**，覆盖内容与时序。

2. **模型适配**：
   - Moshi 是多流模型（文本流 + 模型音频流 + 用户音频流），DPO 需适配多流。
   - 核心技巧：**仅使用文本流概率**进行 DPO 计算（避免音频流的不稳定），采用**长度归一化 DPO（DPO-LN）**：
     \[
     L_{DPO-LN} = -\mathbb{E}\left[ \log\sigma\left( \frac{\beta}{|y_w|}\log\frac{\pi_\theta^T(y_w|x)}{\pi_{\text{ref}}^T(y_w|x)} - \frac{\beta}{|y_l|}\log\frac{\pi_\theta^T(y_l|x)}{\pi_{\text{ref}}^T(y_l|x)} \right) \right]
     \]
   - 使用 TTS 重新合成用户和模型音频（保持原始时间戳）作为输入上下文。

3. **训练**：
   - 双 Transformer：7B Temporal Transformer + 600M Depth Transformer。
   - 学习率：5e-9（Temporal）、1e-6（Depth），批次大小 16/32，β=0.3。
   - 1 个 epoch 遍历训练集。

---

## 3. 实验设计

### 数据集
- **偏好数据**：
  - 从真实用户与 Moshi 的自由对话中收集，共 **283,740 对**（含重叠上下文），去重后 **154,301 对**，最终精选 **93,490 对**（平衡内容/时序比例）。
  - 57% 纯时序问题，20% 纯内容问题，23% 两者兼有。
- **评估基准**：
  - **口语问答**：Llama Questions、TriviaQA（音频版）、Web Questions（音频版）。
  - **安全**：ALERT（毒性检测）、XSTest（音频版，判断拒绝/遵从）。
  - **人类评估**：8 小时对话（每模型 4 小时），由标注员对以下维度打分：连贯性与流畅度、参与度、相关性与帮助性。

### 对比的方法
- 基于 Moshi 的基线：Moshi-Instruct、M-Alt-Vox-Instruct（不同声音）。
- 外部基线：SpeechGPT (7B)、Spectron (1B)、Zeng et al. (2025) 的 9B 模型（含语音输入输出和语音输入文本输出两种）。

### 消融实验
1. **模态流选择**：仅用文本流 vs 加入音频流（得分、CE 等）。
2. **偏好数据类型**：仅内容 (A)、仅打断 (B)、仅沉默 (C)、组合等。
3. **对齐算法**：DPO、DPO-LN、SimPO、APO-Zero。
4. **跨声音迁移**：用 Moshi-Instruct 的数据微调 M-Alt-Vox-Instruct（不同声音）。
5. **β 值消融** (0.1, 0.3, 0.5, 2.0)。
6. **人类评估的时序分段**：30s / 90s / 120s 对话时长。

---

## 4. 资源与算力

论文**未明确说明 GPU 型号、数量、训练时长**等具体算力信息。仅提及使用了 Moshi 的 7B + 600M 参数模型，训练 1 个 epoch。在附录中简单提到超参数搜索，但无算力统计。推测使用了多卡 A100 或 H100 集群，但无法确认。

---

## 5. 实验数量与充分性

**实验数量**：
- 客观评估覆盖 5 个基准（3 个 QA + 2 个安全），每组实验报告平均精度和回复长度。
- 消融实验共 **6 类**，每一类包含多个子实验（例如模态流 4 种、数据组合 6+ 种、算法 4 种、声音迁移 2 种、β 5 种）。
- 人类评估包含 99 条对话/模型 × 3 种子种子，结果统计均值与方差。
- 附录还提供了 WER 分析、ALERT 细分类结果。

**充分性与公平性**：
- 客观实验设计较充分，对比了多种基线、多种数据组合和算法变体。
- 人类评估设计了分时间桶分析，考虑了对话长度的影响。
- 但存在局限性：
  - 外部基线多为**非全双工**（级联或链式），可比性有限。
  - 仅基于 Moshi 模型，未在其他架构上验证。
  - 人类评估仅包含 **语义/语用**维度，未涵盖声学质量（如自然度、韵律）。
  - 偏好数据来自**同模型**（Moshi-Instruct）的交互，存在分布偏差。

---

## 6. 主要结论与发现

1. **仅优化文本流**即可有效提升全双工语音模型的对话质量（QA 平均 +3.1%，安全 +6.9%），加入音频流反而降低 QA 但轻微提升安全。
2. **时序偏好数据**（沉默/打断）比纯内容偏好数据带来更大提升，且能调节语速；组合不同类型数据需平衡。
3. **DPO-LN** 在 QA 和安全上均优于 DPO、SimPO、APO-Zero，且回复长度可控。
4. **跨声音迁移**可行（相似音色），但不同音色可能导致适配退化或回复长度激增。
5. 人类评估表明：对齐后的模型在**短对话（30s）** 中连贯性、参与度、帮助性均优于基线；**长对话**时优势减弱，需进一步优化长程一致性。
6. 端到端语音模型对齐可在**不存储用户音频**（使用合成音频）的前提下实现，保护隐私。

---

## 7. 优点

- **创新性**：首次将偏好对齐扩展到全双工实时语音对话系统，填补了语音领域对齐空白。
- **数据构建**：利用真实用户交互日志 + AI 反馈，大规模且覆盖内容与时序两种偏好，保护隐私（丢弃用户音频）。
- **方法适配**：巧妙适配 DPO 到多流语音模型（仅文本概率），并针对语音特性设计时序偏好的检测与生成。
- **实验全面**：包含客观基准、消融、人类评估，验证了数据类型、算法、模态、迁移等关键因素。
- **实践价值**：训练后可部署，人类评估表明实际对话体验提升，且有开源模型 Moshi 作为基础，可复现性较好。

---

## 8. 不足与局限

- **模型单一**：仅基于 Moshi 进行验证，未在其他全双工语音模型（如 dGSLM、GPT-4o 语音模式）上实验。
- **在线对齐缺失**：目前为离线训练，未尝试在线 RLHF，无法实时更新。
- **长对话一致性不足**：人类评估显示长对话中优势减弱，偏好数据主要聚焦第一个问题回复，多轮轨迹对齐不足。
- **声学质量未评估**：人类评估只关注语义/语用，未评估发音自然度、韵律、音色等；WER 分析显示跨声音迁移时 WER 上升。
- **合成音频偏差**：用户音频用 TTS 合成，虽保留时序但丢失原始韵律、情感，可能影响对齐效果。
- **ASR 误差引入噪声**：依赖 Whisper 转录，会引入 ASR 错误，进而影响 LLM 裁判的判断。
- **偏好数据分布偏差**：数据来自同一模型早期版本，批评和改进均由 LLM 生成，可能系统性地偏向 LLM 的“理想”回答，而非真实人类偏好。

---

（完）
