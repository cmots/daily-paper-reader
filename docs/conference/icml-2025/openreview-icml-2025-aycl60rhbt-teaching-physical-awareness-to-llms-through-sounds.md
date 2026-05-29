---
title: Teaching Physical Awareness to LLMs through Sounds
title_zh: 通过声音教授大语言模型物理意识
authors: "Weiguo Wang, Andy Nie, Wenrui Zhou, Yi Kai, Chengchen Hu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Aycl60Rhbt"
tags: ["query:wm-vla-sa"]
score: 4.0
evidence: 通过声音教授物理意识，涉及空间音频概念
tldr: 大型语言模型缺乏物理意识，本工作提出ACORN框架，通过声音（如多普勒效应、空间关系）来教学。其核心是一个物理模拟器，结合真实声源和受控物理通道生成训练数据，并构建音频问答数据集AQA-PHY。实验表明该方法成功提升了LLM对物理现象的理解。这在空间音频应用于AI教学方面提供新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-aycl60rhbt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1760, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-aycl60rhbt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1667, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-aycl60rhbt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 792, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-aycl60rhbt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 786, \"height\": 290, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-aycl60rhbt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 831, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-aycl60rhbt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 401, \"height\": 270, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-aycl60rhbt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 403, \"height\": 268, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-aycl60rhbt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 400, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-aycl60rhbt/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 396, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-aycl60rhbt/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1220, \"height\": 486, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-aycl60rhbt/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1404, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-aycl60rhbt/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1763, \"height\": 829, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-aycl60rhbt/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1401, \"height\": 2136, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-aycl60rhbt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 860, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-aycl60rhbt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1857, \"height\": 564, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-aycl60rhbt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1742, \"height\": 570, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-aycl60rhbt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1870, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-aycl60rhbt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1738, \"height\": 616, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-aycl60rhbt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1734, \"height\": 392, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-aycl60rhbt/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1733, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-aycl60rhbt/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 862, \"height\": 663, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-aycl60rhbt/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1817, \"height\": 417, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-aycl60rhbt/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1793, \"height\": 2188, \"label\": \"Table\"}]"
motivation: 大语言模型缺乏对现实物理现象的理解，特别是空间音频相关的物理规律。
method: 提出ACORN框架，使用物理模拟器生成包含多普勒效应、空间关系等物理现象的音频数据，并构建音频问答数据集训练模型。
result: 训练后的模型在物理意识问答上表现提升，验证了通过声音学习物理知识的有效性。
conclusion: 利用声音训练可以赋予大语言模型物理意识，为多模态学习开辟新途径。
---

## Abstract
Large Language Models (LLMs) have shown remarkable capabilities in text and multimodal processing, yet they fundamentally lack physical awareness--understanding of real-world physical phenomena.
In this work, we present ACORN, a framework that teaches LLMs physical awareness through sound, focusing on fundamental physical phenomena like the Doppler effect, multipath effect, and spatial relationships. To overcome data scarcity, ACORN introduce a physics-based simulator combining real-world sound sources with controlled physical channels to generate diverse training data. Using this simulator, we build AQA-PHY, a comprehensive Audio Question-Answer dataset, and propose an audio encoder that processes both magnitude and phase information. By connecting our audio encoder to state-of-the-art LLMs, we demonstrate reasonable results in both simulated and real-world tasks, such as line-of-sight detection, Doppler effect estimation, and Direction-of-Arrival estimation, paving the way for enabling LLMs to understand physical world.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：当前大型语言模型（LLM）虽在文本和多模态处理上性能卓越，但**缺乏对真实世界物理现象的理解**（即“物理意识”），例如无法通过声音感知多普勒效应、空间关系、声源方向等。
- **研究动机**：声音是环境感知的关键通道——人类能自然地从声音中提取物理信息（如车辆是靠近还是远离、空间是封闭还是开放），但LLM无法做到。这一缺陷限制了LLM在安全敏感场景的应用（如车内语音指令需判断是否来自车外）以及具身智能的交互自然性（如机器人应转向说话者）。
- **整体含义**：本文旨在通过声音教学赋予LLM物理意识，从而弥合语言模型与现实世界感知之间的鸿沟。

## 2. 论文提出的方法论

### 核心思想
将接收到的声音 \( y \) 分解为声源 \( s \) 和物理通道 \( h \) 的卷积：\( y = h \circledast s \)。通过模拟物理通道（含LOS、反射、混响、多普勒、麦克风阵列效应），结合现有声源数据集（AudioSet），合成带有精确物理标注的大规模训练数据，然后用音频-问答对监督微调LLM。

### 关键技术细节
1. **物理学通道模拟器**：  
   - **LOS与早期反射**：用阻尼正弦波模拟各路径，参数可调。  
   - **混响**：生成高斯噪声，经带通滤波器分为6个子带，每个子带以不同指数衰减速率叠加。  
   - **多普勒效应**：利用时变延迟建模相对运动，等价于对原始信号进行重采样（1D插值）。  
   - **麦克风阵列**：通过左右麦克风间的时间差（TDoA）模拟到达方向（DoA）。  
   - 各组件可独立开关或随机化，以生成多样化的物理条件。

2. **音频编码器**：  
   - 采用短时傅里叶变换（STFT）提取三种特征：**幅度**、**相位的正弦**、**相位的余弦**（避免相位卷绕数值问题）。  
   - 三个特征分别经3x3 1D卷积+GeLU后拼接，再用两个3x3卷积融合至1280维，添加正弦位置编码，最后经32层Transformer产生音频token。  
   - 相较传统仅用幅度（如Whisper），相位信息对物理感知（如多径、时间差）至关重要。

3. **LLM集成与训练**：  
   - 音频token经线性投影映射到LLM的embeding空间，与文本token拼接后输入LLM。  
   - 训练目标为自回归预测答案token。音频编码器初始化自Whisper-large-v2（幅度部分），相位相关子网随机初始化；LLM使用LoRA微调。

### 关键公式
- 接收信号模型：\( y = h \circledast s \)  
- STFT输出：\( M(f,t)=|X(f,t)| \)，\( \sin\theta(f,t)=\sin\angle X(f,t) \)，\( \cos\theta(f,t)=\cos\angle X(f,t) \)  
- 多普勒时变延迟：\( \tau(t) = (d_0+vt)/c \) → 输出为 \( y(t)=x\left(t - \frac{d_0+vt}{c}\right) \)

## 3. 实验设计

### 数据集与场景
- **训练数据**：AQA-PHY数据集，包含100万对<音频, 问题, 答案>。声源来自AudioSet（约200万段10秒音频），物理通道由模拟器生成（5个任务各20万条封闭式QA+1万条开放式QA）。
- **测试场景**：  
  - 模拟测试：5个任务（LOS检测、多普勒估计、到达方向估计、多径分析、距离估计），采用随机生成的测试集。  
  - 真实世界测试：在NIO ES6车辆内部署4个麦克风，采集200个LOS样本（内外各50%）、400个左右方向样本。

### Benchmark与对比方法
- **音频编码器对比**：ACORN编码器 vs Whisper-large-v2编码器（幅度-only）。  
- **LLM对比**：Llama3.1-8B-instruct 和 Qwen2-7B-instruct。  
- **性能基准**：还给出了随机基线（如LOS检测BCA=0.5、多普勒MAE=10.0等）。

### 评估指标
- LOS检测：二元分类准确率（BCA）  
- 多普勒估计：频率偏移百分比平均绝对误差（MAE_f）  
- DoA估计：TDoA样本数平均绝对误差（MAE_t）  
- 多径分析：三类分类准确率（TCA）  
- 距离估计：相对误差百分比（REP）

## 4. 资源与算力

论文明确给出：
- **硬件**：4块NVIDIA A100 GPU  
- **批大小**：32  
- **训练轮次**：7个epoch  
- **总训练时长**：约61小时  
- **其他**：采用LoRA（rank=8），优化器AdamW，预热-余弦退火学习率。

## 5. 实验数量与充分性

- **主要实验**（Table 2）：包含5个任务×2种LLM×2种编码器，分别报告合并训练和单独训练的结果，共20个配置。  
- **消融实验**：  
  - LOS对多径分析的影响（图6）  
  - 多普勒对LOS检测的影响（图7）  
  - SNR对距离估计的影响（图8）  
- **真实世界验证**：2个任务（LOS检测、左右方向分类），零样本迁移测试。  
- **补充分析**：LoRA rank消融（表9）、不同速度下的LOS检测（图11）。  
- **充分性评价**：实验覆盖了主要物理任务，对比了两种主流LLM，模拟与真实均涉及，消融探究了关键因素。但真实实验规模较小（仅车辆场景，200/400样本），且未展示跨场景泛化（如不同房型、室外）。整体客观公平，未发现显著偏见。

## 6. 论文的主要结论与发现

1. **可行性**：LLM可以通过学习音频-物理问答对获得对物理现象的理解，在所有任务上均显著优于随机基线。  
2. **编码器优势**：ACORN音频编码器（含相位信息）在5项任务中全面优于仅用幅度的Whisper编码器，尤其在多普勒和距离估计上提升明显（MAE_f从1.042降至0.181，REP从12.572%降至1.599%）。  
3. **模型无关性**：ACORN在Llama和Qwen上表现一致，表明其声学特征提取与LLM架构解耦。  
4. **真实世界有效性**：在零样本迁移至真实车辆环境时，LOS检测准确率约0.87，左右分类约0.93，验证了模拟训练的泛化能力。  
5. **噪声鲁棒性**：SNR从<10dB提升至>40dB时，距离估计误差显著下降，符合物理直觉。

## 7. 优点：方法或实验设计上的亮点

- **创新模拟器**：基于信号处理组件式模拟物理通道，避免昂贵真实采集，且能独立控制每类效应，数据生成可扩展；与几何建模方法相比更轻量、通用。  
- **相位感知编码器**：首次将正弦/余弦相位显式融入音频编码器，有效捕获物理信号中的时间结构。  
- **大规模问答数据集**：AQA-PHY提供100万条带精确物理标注的样本，支持监督微调，且包含开放式问答。  
- **主动感知能力**：不仅处理被动声音，还通过FMCW脉冲实现距离估计，拓展了LLM的交互范围。  
- **真实验证**：尽管模拟训练，在真实车辆中仍取得合理结果，证明了方法实用性。

## 8. 不足与局限

- **单轮交互**：当前仅支持单轮问答，缺乏多轮对话能力，无法在复杂推理中逐步引导。  
- **缺乏内部推理链**：模型直接输出答案，未显式展示中间物理推理步骤（如链式思考），可能影响复杂任务的可解释性。作者指出可借鉴OpenAI o1或DeepSeek-R1进行改进。  
- **真实实验规模有限**：仅在一个车型（NIO ES6）上测试，样本量（200+400）较小，未评估其他环境（如不同房间、室外空旷/嘈杂场景）的泛化。  
- **模拟与现实的差距**：虽然零样本结果尚可，但性能相比模拟测试有所下降（如LOS检测从0.92降至0.87），说明模拟器未能完全覆盖真实世界的复杂噪声与物理效应。  
- **计算资源需求**：61小时在4×A100 上训练，对资源有限的研究团队可能门槛较高。  
- **领域局限**：仅关注基本的声学物理现象，未涉及更高级的物理概念（如材料声学、声源类型识别）。  
- **标签来源**：封闭式QA依靠模板，开放式QA由GPT-4o生成，可能存在质量不一致或偏见。

（完）
