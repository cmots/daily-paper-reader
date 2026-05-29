---
title: "E2E-VGuard: Adversarial Prevention for Production LLM-based End-To-End Speech Synthesis"
title_zh: E2E-VGuard：面向生产环境端到端LLM语音合成的对抗防御
authors: "Zhisheng Zhang, Derui Wang, Yifan Mi, Zhiyong Wu, JieGao, Yuxin Cao, Kai Ye, Jason Xue, Jie Hao"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=CHN4HG9R5e"
tags: ["query:speech-model"]
score: 6.0
evidence: 针对生产环境LLM语音合成系统的对抗防御方法
tldr: 本文提出E2E-VGuard，一种针对端到端大语言模型语音合成系统的对抗防御方法。现有防御假设手动标注文本，而真实场景使用ASR生成文本，存在安全漏洞。E2E-VGuard利用对抗样本技术，在ASR环节注入保护，有效防止语音克隆欺诈。实验表明该方法在保证合成质量的同时显著提升安全性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-chn4hg9r5e/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1383, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chn4hg9r5e/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 868, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chn4hg9r5e/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 877, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-chn4hg9r5e/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 868, \"height\": 393, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-chn4hg9r5e/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1415, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chn4hg9r5e/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1414, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chn4hg9r5e/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 630, \"height\": 170, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chn4hg9r5e/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 634, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chn4hg9r5e/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1418, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chn4hg9r5e/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1408, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chn4hg9r5e/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1437, \"height\": 645, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chn4hg9r5e/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 931, \"height\": 339, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chn4hg9r5e/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 938, \"height\": 327, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chn4hg9r5e/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 472, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-chn4hg9r5e/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 655, \"height\": 274, \"label\": \"Table\"}]"
motivation: 现有语音合成防御方法假设手动标注文本，不适用于自动标注的端到端系统，存在安全风险。
method: 在ASR生成文本阶段注入对抗性扰动，使得恶意用户无法利用合成语音进行身份模仿。
result: 在防范语音克隆攻击上取得高成功率，同时合成音频质量损失极小。
conclusion: E2E-VGuard为端到端语音合成系统提供了实用的安全防护方案。
---

## Abstract
Recent advancements in speech synthesis technology have enriched our daily lives, with high-quality and human-like audio widely adopted across real-world applications. However, malicious exploitation like voice-cloning fraud poses severe security risks. Existing defense techniques struggle to address the production large language model (LLM)-based speech synthesis. While previous studies have considered the protection for fine-tuning synthesizers, they assume manually annotated transcripts. Given the labor intensity of manual annotation, end-to-end (E2E) systems leveraging automatic speech recognition (ASR) to generate transcripts are becoming increasingly prevalent, e.g., voice cloning via commercial APIs. Therefore, this E2E speech synthesis also requires new security mechanisms. To tackle these challenges, we propose E2E-VGuard, a proactive defense framework for two emerging threats: (1) production LLM-based speech synthesis, and (2) the novel attack arising from ASR-driven E2E scenarios. Specifically, we employ the encoder ensemble with a feature extractor to protect timbre, while ASR-targeted adversarial examples disrupt pronunciation. Moreover, we incorporate the psychoacoustic model to ensure perturbative imperceptibility. For a comprehensive evaluation, we test 16 open-source synthesizers and 3 commercial APIs across Chinese and English datasets, confirming E2E-VGuard's effectiveness in timbre and pronunciation protection. Real-world deployment validation is also conducted. Our code and demo page are available at https://wxzyd123.github.io/e2e-vguard/.

---

## 论文详细总结（自动生成）

# E2E-VGuard 论文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：语音合成技术（尤其是基于大语言模型的生产级系统）的恶意使用（如语音克隆欺诈）带来严重安全风险。现有防御方法（如AntiFake、POP、SafeSpeech）假设手动标注文本，但真实场景中端到端（E2E）系统普遍使用自动语音识别（ASR）生成文本（例如商业API仅接受音频输入），手动标注成本高且不现实，因此存在安全漏洞。
- **核心问题**：如何针对“生产级LLM语音合成”和“ASR驱动的端到端场景”这两类新兴威胁，设计一种主动防御框架，防止未经授权的语音克隆与发音学习。
- **整体含义**：提出E2E-VGuard，从音色和发音两个层面破坏恶意合成，同时保证扰动对人耳不可感知，首次系统性地解决了ASR辅助的E2E语音合成保护问题。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式与流程

### 核心思想
- 采用**对抗性示例**技术，在原始音频上叠加微小扰动，同时作用于：
  - **音色保护**：使合成音频的说话人特征与原始说话人不同（无目标）或导向特定目标说话人（有目标）。
  - **发音保护**：使ASR系统识别出错误文本，破坏TTS模型学习正确的文本-发音对齐。
  - **扰动不可感知**：利用心理声学模型和ℓ₂范数约束，使扰动低于人耳掩蔽阈值。

### 关键技术细节
- **音色保护（Timbre Prevention）**：
  - 采用多个编码器集成（VITS、GPT-SoVITS、CosyVoice的发音编码器，WavLM、CAM++、StyleTTS2的风格编码器）以及MFCC特征提取器，计算原始音频与保护音频的特征余弦相似度作为损失。
  - 无目标保护：最大化特征距离；有目标保护：最小化与目标说话人特征的距离。
- **发音保护（Pronunciation Prevention）**：
  - 对ASR系统进行目标攻击，使ASR输出指定错误文本，破坏TTS模型学习正确的文本-发音对应关系。
  - 损失函数为CTC/交叉熵损失，目标文本选自目标音频（有目标）或随机等长文本（无目标）。
- **心理声学模型（Psychoacoustic Model）**：
  - 基于频率掩蔽效应，约束扰动功率谱密度低于原始音频的掩蔽阈值，同时加入ℓ₂范数正则化，减少人耳可感知噪声。
- **总体损失函数**：`L = L_asr + α·L_fea + β·L_psy`，其中α=500，β=5×10⁻³，扰动边界ϵ=8/255，优化迭代500步。

### 算法流程（文字说明）
1. 初始化扰动δ在[-ϵ, ϵ]范围内。
2. 循环max_epoch次：
   - 计算ASR损失C1（目标文本与ASR输出之间的损失）。
   - 根据模式选择：
     - 无目标：C2为原始音频与保护音频的余弦相似度之和。
     - 有目标：C2为保护音频与目标说话人音频的负余弦相似度之和。
   - 计算心理声学损失C3（包括掩蔽损失和ℓ₂损失）。
   - 总损失C = C1 + α·C2 + β·C3。
   - 使用PGD更新δ，并投影到ϵ-ball和[-1,1]范围。
3. 输出保护音频x'。

## 3. 实验设计：数据集、场景、Benchmark、对比方法

- **数据集**：
  - 英文单说话人：LibriTTS。
  - 英文多说话人：CMU ARCTIC。
  - 中文多说话人：THCHS30。
- **场景**：
  - 端到端微调场景（6个模型：VITS, GPT-SoVITS, CosyVoice, Llasa-1B/8B, StyleTTS2等）。
  - 零样本场景（7个模型：Index-TTS, FireRedTTS-1S, Step-Audio-TTS, Spark-TTS, XTTS-v2, FishSpeech, Dia-1.6B）。
  - 上下文学习（ICL）场景（3个模型：F5-TTS, E2-TTS, VALLE-X）。
  - 商业API测试（ByteDance, Alibaba, MiniMax）。
  - 真实世界录音场景。
- **Benchmark/对比方法**：
  - AttackVC, AntiFake, POP, POP+ESP, SafeSpeech。
- **ASR系统**：7个（Wav2vec2, Whisper-base/small/medium/large-v3, Conformer, CitriNet）。
- **评估指标**：WER（越高越好，表示发音破坏），SIM（越低越好，表示音色破坏），SNR，PESQ，MOS（主观）。
- **数据分割**：80%训练，20%测试；若需要验证集，从训练集中取10%。

## 4. 资源与算力

- **GPU**：实验全部使用**一张NVIDIA 4090 GPU（24GB显存）**。
- **时间开销**：
  - 保护一段音频平均时间：无目标约97.982秒，有目标约111.495秒。
  - 与基线对比：AttackVC 44.871秒，AntiFake 203.248秒。
- **其他**：未明确说明训练总时长或总GPU小时数，但单卡4090即可完成全部实验。

## 5. 实验数量与充分性

- **实验组数**：非常丰富。
  - 微调场景：6个模型 × 3个数据集（部分） = 多组结果。
  - 零样本场景：7个模型。
  - ICL场景：3个模型。
  - 商业API：3个平台。
  - 消融实验：组件移除、超参数选择。
  - 鲁棒性测试：3种扰动去除技术、9种数据增强、3种滤波、真实世界录音。
  - 多语言/多说话人：2个附加数据集。
  - ASR系统迁移：6个额外ASR系统。
  - 人类主观实验：36名志愿者，22个样本，有95%置信区间。
- **充分性评价**：实验覆盖了主流的开源/商业模型、多种语言、多种攻击场景、消融和鲁棒性测试，并包含主观评价，非常充分、客观、公平。对比方法均为最新SOTA基线，指标选用合理。

## 6. 论文的主要结论与发现

- **有效性**：在端到端微调和零样本场景中，E2E-VGuard在音色相似度（SIM）和词错误率（WER）上均显著优于所有基线，平均SIM降低0.043（微调）和0.119（零样本），WER提升19.8%（微调）和32.8%（零样本）。
- **迁移性**：对未参与训练的TTS模型、商业API、ICL模型均有效，表明编码器集成策略提高了迁移性。
- **鲁棒性**：即使经过降噪、数据增强、滤波等处理，以及真实世界录音后重新合成，仍能保持较高的WER和较低的SIM，保护效果稳健。
- **不可感知性**：心理声学模型使得SNR和PESQ优于基线，人类主观MOS达到3.522（略低于原始音频4.788），可接受。
- **发音破坏**：目标攻击下仅有8.3%的人类评估者认为合成音频发音匹配文本（clean为100%），证明发音保护有效。
- **实际部署**：在商业API和真实录音环境中均保护成功，具备实践可行性。

## 7. 优点

- **场景完整**：首次针对ASR辅助的端到端语音合成系统设计防御，覆盖微调、零样本、ICL、商业API等实际场景。
- **双重保护**：同时从音色和发音两个维度破坏恶意合成，比仅保护音色的方法更全面。
- **技术新颖**：利用编码器集成+MFCC特征提取器保护音色，采用ASR对抗样本破坏发音，并引入心理声学模型保证不可感知，三者结合形成系统性的算法。
- **鲁棒性强**：经过广泛的鲁棒性测试（降噪、数据增强、滤波、真实世界录音），证明扰动难以被移除或绕过。
- **可复现性**：提供代码和演示页面，实验设置详细（超参数、模型细节、数据集分割等均在附录中给出）。
- **人类主观验证**：完成了有统计学意义的主观实验（95%置信区间），增强了结论的可信度。

## 8. 不足与局限

- **时间开销**：保护一段音频需要约100秒（无目标），实时性差，难以用于在线场景（作者提到可通过批处理和并行加速缓解）。
- **依赖特定ASR**：当前设计针对单个目标ASR系统进行攻击，未采用通用攻击方法（虽然后续实验证明了向其他ASR的迁移性，但迁移效果有所下降）。
- **对抗人工标注**：若攻击者不使用ASR而是采用人工标注文本，发音保护效果会下降（作者实验显示此时WER降低较多，但仍能保持一定音色保护）。
- **主观偏差**：人类主观实验可能受环境、个体差异影响，作者已通过置信区间和筛选措施缓解，但仍存在固有偏差。
- **未讨论更高级自适应攻击**：论文未测试攻击者知道防御算法后的自适应攻击（如联合优化扰动去除与合成），鲁棒性有待进一步验证。
- **计算资源需求**：虽然单卡4090可运行，但保护大量音频时累积时间较长，可能影响大规模部署。

（完）
