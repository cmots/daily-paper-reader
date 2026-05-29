---
title: "Seeing Sound, Hearing Sight: Uncovering Modality Bias and Conflict of AI models in Sound Localization"
title_zh: 听声见影：揭示AI模型在声音定位中的模态偏差与冲突
authors: "Yanhao Jia, Ji Xie, S Jivaganesh, Li Hao, Xu Wu, Mengmi Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=PWdWmw9wh0"
tags: ["query:wm-vla-sa"]
score: 4.0
evidence: 声音定位中的模态偏差分析
tldr: 本文系统探究了多模态AI模型在声音定位任务中的模态偏差和冲突处理能力。通过设计跨模态冲突场景，发现当前模型在视觉和听觉信息冲突时倾向于依赖特定模态，与人类灵活处理不同。该研究揭示了空间音频感知模型中的关键不足，对多模态融合技术提出改进方向。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-pwdwmw9wh0/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1201, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pwdwmw9wh0/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1212, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pwdwmw9wh0/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1356, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pwdwmw9wh0/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 680, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pwdwmw9wh0/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 669, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pwdwmw9wh0/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 680, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pwdwmw9wh0/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 698, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pwdwmw9wh0/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1315, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pwdwmw9wh0/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1432, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pwdwmw9wh0/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1434, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pwdwmw9wh0/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1431, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pwdwmw9wh0/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1429, \"height\": 582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pwdwmw9wh0/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1432, \"height\": 580, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pwdwmw9wh0/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1121, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pwdwmw9wh0/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 750, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pwdwmw9wh0/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1363, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pwdwmw9wh0/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1453, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pwdwmw9wh0/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1457, \"height\": 436, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-pwdwmw9wh0/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1402, \"height\": 408, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pwdwmw9wh0/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 919, \"height\": 258, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pwdwmw9wh0/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 943, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pwdwmw9wh0/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 700, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pwdwmw9wh0/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 692, \"height\": 2340, \"label\": \"Table\"}]"
motivation: 多模态AI模型在声音源定位中如何处理跨模态冲突尚不清楚，可能存在模态偏差。
method: 构建视觉-听觉冲突数据集，系统性测试多种多模态模型在声音定位任务中的模态偏好。
result: 发现模型普遍存在对视觉模态的过度依赖，听觉模态在冲突时被抑制。
conclusion: 该工作为多模态空间音频模型的设计提供了重要洞察，需要更好的模态融合机制。
---

## Abstract
Imagine hearing a dog bark and instinctively turning toward the sound—only to find a parked car, while a silent dog sits nearby. Such moments of sensory conflict challenge perception, yet humans flexibly resolve these discrepancies, prioritizing auditory cues over misleading visuals to accurately localize sounds.  Despite the rapid advancement of multimodal AI models that integrate vision and sound, little is known about how these systems handle cross-modal conflicts or whether they favor one modality over another. Here, we systematically and quantitatively examine modality bias and conflict resolution in AI models for Sound Source Localization (SSL). We evaluate a wide range of state-of-the-art multimodal models and compare them against human performance in psychophysics experiments spanning six audiovisual conditions, including congruent, conflicting, and absent visual and audio cues. Our results reveal that humans consistently outperform AI in SSL and exhibit greater robustness to conflicting or absent visual information by effectively prioritizing auditory signals. In contrast, AI shows a pronounced bias toward vision, often failing to suppress irrelevant or conflicting visual input, leading to chance-level performance. To bridge this gap, we present EchoPin, a neuroscience-inspired multimodal model for SSL that emulates human auditory perception. The model is trained on our carefully curated AudioCOCO dataset, in which stereo audio signals are first rendered using a physics-based 3D simulator, then filtered with Head-Related Transfer Functions (HRTFs) to capture pinnae, head, and torso effects, and finally transformed into cochleagram representations that mimic cochlear processing. To eliminate existing biases in standard benchmark datasets, we carefully controlled the vocal object sizes, semantics, and spatial locations in the corresponding images of AudioCOCO. EchoPin outperforms existing models trained on standard audio-visual datasets. Remarkably, consistent with neuroscience findings, it exhibits a human-like localization bias, favoring horizontal (left–right) precision over vertical (up–down) precision. 
This asymmetry likely arises from HRTF-shaped and cochlear-modulated stereo audio and the lateral placement of human ears, highlighting how sensory input quality and physical structure jointly shape precision of multimodal representations. All code, data, and models are available \href{https://github.com/CuriseJia/SSHS}{here}.

---

## 论文详细总结（自动生成）

# 论文结构化总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：声音源定位（SSL）要求模型整合视觉和听觉信息。然而，当模态信息冲突（如听到狗叫却看到猫）时，人类会优先利用听觉线索灵活校正，而多模态AI模型如何处理这些冲突、是否存在模态偏差，尚不清楚。
- **背景**：现有SSL模型多基于对比学习或跨模态注意力，但缺乏对模态冲突场景的系统评估；同时，常用数据集（如Mono音频、大且居中的发声物体）易导致视觉捷径学习。
- **核心问题**：AI模型在SSL中是否偏向视觉模态？模型能否像人类一样在冲突或缺失视觉信息时依靠听觉？如何构建更鲁棒、类脑的SSL模型？

## 2. 论文提出的方法论
- **核心思想**：
  - 构建六种可控的视听条件（一致、冲突视觉、缺失视觉、仅听觉、仅视觉、多实例）来系统探测模态偏差。
  - 提出神经科学启发的EchoPin模型，模拟人耳外周听觉处理：HRTF滤波（模拟耳廓/头部/躯干）→ 耳蜗图（ERB滤波器组）→ 双编码器（视觉+立体声音频）→ 对比学习+CIoU定位损失。
- **关键技术细节**：
  - **音频合成**：基于Unity 3D模拟器，结合深度图（DepthAnything）将2D图像对象映射到3D空间，设置听者位置（原点）、屏幕距离0.76m、耳间距0.17m，合成物理真实立体声。
  - **HRTF滤波**：使用KEMAR人头数据集，对立体声波形进行空间滤波（710个方向）。
  - **耳蜗图**：使用PyCochleagram库，ERB滤波器组将波形转化为66频率通道×时间序列×2通道的表示。
  - **模型训练**：初始权重来自IS3，替换首层1D卷积以融合双耳信息，在AudioCOCO上端到端微调（对比损失+CIoU损失）。
  - **预测**：对CNN模型，提取视觉/音频最终层特征图，计算余弦相似度，取最大激活点作为预测位置。

## 3. 实验设计
- **数据集**：
  - **AudioCOCO**：从MSCOCO筛选12类发声物体（人、动物、车辆等），按面积分为Size1（0-5%）、Size2（5-15%）、Size3（15-30%），每类每尺寸最多150张。音频来自VGGSound，经过语义一致性、频谱一致性、空间一致性三轮过滤。最终训练集9360对，测试集18864对（含六种条件）。
  - **人类实验**：14名被试，2100次试验，使用真实立体声耳机，每试次20秒内点击定位。
- **Benchmark方法**：
  - 对比模型：SSLTI、LVS、FNAC、CAVP、AVSegformer、IS3、ImageBind、LanguageBind，以及随机基线。
  - 评估指标：A-Acc（定位是否落在发声物体框内）、V-Acc（是否落在任何同类物体内），并补充了机会校正增益、cIoU、距离阈值分析。
- **消融实验**：EchoPin-M（单声道）、EchoPin-S（HRTF+梅尔谱）、EchoPin-Ro（旋转耳轴90°）对比完整EchoPin。

## 4. 资源与算力
- ImageBind和LanguageBind在8块NVIDIA A100 GPU上运行；其他模型（含EchoPin变体）在4块NVIDIA A6000 GPU上训练与评估。
- EchoPin微调：Adam优化器，学习率1e-5，batch size 16，10 epochs，每轮约16小时。
- 所有评估重复3次取均值，人类数据随机60%采样5次均值。

## 5. 实验数量与充分性
- **实验数量**：覆盖六种条件×三种对象大小×9+种AI模型+人类，主表（Table S4）包含所有组合的A-Acc和V-Acc。此外进行了消融实验（Mono/Stereo/Rotation）、cIoU对比、阈值分析、机会校正增益。
- **充分性、客观性、公平性**：
  - 所有模型使用相同HRTF滤波后的音频，避免结构差异。
  - AudioCOCO训练集与测试集同分布但无重叠，且排除与AVSBench重叠的图片。
  - 随机基线作为下界，人类作为上界。
  - 补充了多种稳健性分析（如距离阈值、面积校正），结论一致。

## 6. 论文的主要结论与发现
1. **人类优于AI**：在所有条件下，人类准确率显著高于AI，尤其在小型物体和冲突场景。
2. **AI过度依赖视觉**：冲突视觉线索导致AI性能骤降至接近随机；反之缺失视觉时AI尚可，但远逊人类。
3. **EchoPin显著提升鲁棒性**：超越所有对比模型，在冲突/缺失条件下保持高于机会的表现。
4. **类人水平-垂直不对称**：EchoPin在水平方向定位精度高于垂直方向（与神经科学一致），而IS3不对称性较弱；旋转耳轴（EchoPin-Ro）可反转此不对称，证明其源自立体声几何结构。
5. **训练数据质量与立体声关键**：EchoPin-M（单声道）仍优于IS3（数据质量好），而立体声版本进一步提升，凸显高质量立体声数据集的重要性。

## 7. 优点
- **系统性实验设计**：首次在SSL中构建六种模态冲突条件，结合人类行为直接对比，清晰揭示模态偏差。
- **物理真实的音频合成**：利用Unity+HRTF+耳蜗图生成带有空间线索的立体声，避免以往数据集弱对齐或单声道缺陷。
- **神经科学启发模型**：不依赖人类行为标签，却自然涌现类人定位不对称，验证生物结构对多模态表征的影响。
- **公平评估**：所有模型使用相同预处理，统一评价标准，消融实验设计清晰。

## 8. 不足与局限
- **性能差距**：EchoPin在小型物体、复杂多实例场景仍远逊人类，尤其在视觉显著性目标干扰时（如大物体）容易误判。
- **模拟与现实差距**：音频生成基于物理模拟，未涵盖衍射、混响等真实环境效应；HRTF源于标准KEMAR，未个体化。
- **静态图像限制**：当前数据集仅含静态图像，缺乏时间动态（如运动声源），无法建模人类利用运动线索的能力。
- **计算开销**：需预生成耳蜗图（每文件~160MB），训练和数据处理成本较高。
- **类别扩展性**：仅12类发声物体，未覆盖更多非典型声源或背景噪声下的定位。

（完）
