---
title: "SAVVY: Spatial Awareness via Audio-Visual LLMs through Seeing and Hearing"
title_zh: SAVVY：通过看和听实现音频-视觉大语言模型的空间感知
authors: "Mingfei Chen, Zijun Cui, Xiulong Liu, Jinlin Xiang, Caleb Zheng, Jingyuan Li, Eli Shlizerman"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=zwCb9cKHpd"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 空间音频处理，基于音频的3D空间推理
tldr: 该论文指出现有音频-视觉语言模型缺乏对动态3D场景中的空间推理能力，因此引入首个包含同步空间音频的3D空间推理基准SAVVY-Bench。同时提出无需训练的推理流水线SAVVY，通过两阶段处理实现方位和距离关系的细粒度推理。该工作推动了空间音频处理与渲染技术在具身智能中的应用。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwcb9ckhpd/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 603, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwcb9ckhpd/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1395, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwcb9ckhpd/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1429, \"height\": 735, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwcb9ckhpd/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 500, \"height\": 557, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwcb9ckhpd/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 238, \"height\": 128, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwcb9ckhpd/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1416, \"height\": 770, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwcb9ckhpd/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1419, \"height\": 1348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwcb9ckhpd/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1424, \"height\": 1203, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwcb9ckhpd/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1436, \"height\": 1233, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwcb9ckhpd/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 878, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwcb9ckhpd/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1444, \"height\": 1209, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwcb9ckhpd/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1445, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwcb9ckhpd/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1447, \"height\": 530, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwcb9ckhpd/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1442, \"height\": 769, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zwcb9ckhpd/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1435, \"height\": 983, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-zwcb9ckhpd/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1379, \"height\": 375, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zwcb9ckhpd/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 906, \"height\": 612, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zwcb9ckhpd/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 595, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zwcb9ckhpd/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 484, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zwcb9ckhpd/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 626, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zwcb9ckhpd/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 717, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zwcb9ckhpd/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 992, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zwcb9ckhpd/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1069, \"height\": 337, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zwcb9ckhpd/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1324, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zwcb9ckhpd/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1116, \"height\": 297, \"label\": \"Table\"}]"
motivation: 现有音频-视觉大语言模型缺乏对动态3D场景中带空间音频的空间推理能力。
method: 提出SAVVY-Bench基准和SAVVY无训练推理流水线，通过两阶段处理实现方向和距离推理。
result: 在SAVVY-Bench上验证了方法有效性，显著提升空间音频场景下的3D推理准确性。
conclusion: 空间音频的引入对于提升大语言模型的3D空间感知至关重要。
---

## Abstract
3D spatial reasoning in dynamic, audio-visual environments is a cornerstone of human cognition yet remains largely unexplored by existing Audio-Visual Large Language Models (AV-LLMs) and benchmarks, which predominantly focus on static or 2D scenes. We introduce SAVVY-Bench, the first benchmark for 3D spatial reasoning in dynamic scenes with synchronized spatial audio. SAVVY-Bench is comprised of thousands of carefully curated question–answer pairs probing both directional and distance relationships involving static and moving objects, and requires fine-grained temporal grounding, consistent 3D localization, and multi-modal annotation. To tackle this challenge, we propose SAVVY, a novel training-free reasoning pipeline that consists of two stages: (i) Egocentric Spatial Tracks Estimation, which leverages AV-LLMs as well as other audio-visual methods to track the trajectories of key objects related to the query using both visual and spatial audio cues, and (ii) Dynamic Global Map Construction, which aggregates multi-modal queried object trajectories and converts them into a unified global dynamic map. Using the constructed map, a final QA answer is obtained through a coordinate transformation that aligns the global map with the queried viewpoint. Empirical evaluation demonstrates that SAVVY substantially enhances performance of state-of-the-art AV-LLMs, setting a new standard and stage for approaching dynamic 3D spatial reasoning in AV-LLMs.

---

## 论文详细总结（自动生成）

## 论文详细中文总结

### 1. 论文的核心问题与整体含义（研究动机和背景）

**研究问题**：现有 Audio-Visual Large Language Models (AV-LLMs) 在 **动态 3D 场景** 中缺乏空间推理能力，尤其是无法利用 **空间音频**（spatial audio）进行方位和距离判断。主流基准大多聚焦于静态 2D/3D 场景，忽略了真实环境中物体移动、视角变化以及空间音频提供的定位线索。

**研究背景**：人类在动态声学环境中能自然地整合视觉和听觉信息进行 3D 空间推理（如确定声音来源的方位和距离），但现有的 AV-LLMs 主要依赖单声道音频（monaural audio），丢弃了空间信息；且缺乏对动态物体的跟踪与多视角坐标转换能力。

**贡献概述**：
- 提出 **SAVVY-Bench**：首个面向动态 3D 场景、融合空间音频的音频‑视觉空间推理基准。
- 提出 **SAVVY**：一种无需训练的模块化推理流水线，通过两阶段处理（自中心空间轨迹估计 + 动态全局地图构建）显著提升 AV-LLMs 的 3D 空间问答能力。

### 2. 论文提出的方法论

**核心思想**：利用视频、空间音频和文本查询，分两阶段将 AV-LLM 的粗粒度输出转化为结构化的空间地图，再进行精确推理。

**关键技术细节**：

- **阶段1：自中心空间轨迹估计 (Egocentric Spatial Tracks Estimation)**
  1. **Snapshot Descriptor** ：使用 AV-LLM（如 Gemini）提取查询相关的事件时间范围、物体角色（目标音源、参考物体、面向物体）以及对象描述和稀疏的轨迹点（时间戳、方向角 θ、距离 r）。
  2. **Text‑guided Snapshot Segmentation**：通过文本驱动的分割模型（CLIPSeg + SAM2）对均匀采样的视频帧进行目标分割，结合单目深度估计（ZoeDepth）获取每帧的方位角和距离，补全轨迹。
  3. **Spatial Audio Cues**：利用多通道麦克风阵列（7个麦克风）进行信号处理——SRP-PHAT 估计到达方向（DoA），Coherent‑to‑Diffuse Ratio (CDR) 估计距离，并剔除前方 ±5° 的干扰信号，得到音频轨迹。

- **阶段2：动态全局地图构建 (Dynamic Global Map Construction)**
  - 将阶段1得到的自中心轨迹通过 SLAM 提供的相机轨迹（位置+朝向）转换到全局 2D 坐标系。
  - 静态物体（参考/面向）的轨迹使用 DBSCAN 聚类求质心；动态目标使用 Kalman 滤波平滑和插值，形成连续轨迹。
  - 最终地图包含目标动态轨迹和静态参考点，通过坐标变换（对齐参考物体到正 y 轴）回答自中心或异中心查询。

**算法流程**（文字说明）：输入视频+多通道音频+查询 → 阶段1：AV-LLM 生成稀疏描述 → 分割模块补全轨迹 → 音频模块提供额外定位 → 阶段2：转换到全局坐标并聚类/滤波 → 从地图计算目标相对方向或距离。

### 3. 实验设计：使用的数据集、基准、对比方法

- **数据集**：基于 **Aria Everyday Activities (AEA) 数据集**（Meta 提供，包含 58 个日常生活场景、600+ 声学事件），从中筛选多房间动态场景，构建 **SAVVY-Bench**。
  - SA VVY‑Bench 规模：数千个 QA 对，分为四类任务（Egocentric Direction/Distance, Allocentric Direction/Distance），覆盖 360° 方位角和 0.5–9 米距离。
- **对比方法**：
  - 6 个开源 AV-LLM：VideoLLaMA2‑7B, LongVALE, EgoGPT, Ola, MiniCPM‑o 2.6, video‑SALMONN。
  - 2 个闭源 AV-LLM：Gemini‑2.5‑flash, Gemini‑2.5‑pro。
  - 人类水平基线（6 名标注者独立回答）。
  - 随机水平基线（基于频率分布）。
- **评价指标**：
  - **方向准确率**（多选，精确/模糊匹配）。
  - **距离准确率**（绝对误差阈值 0.1–1.0m 的平均准确率）。
  - **定位准确率 (loc_acc)**：方向误差 <45° 且距离误差 <1m。
  - **SD‑Eval**：时间定位（t‑mIoU, Recall@1 over IoU thresholds）和物体会指准确率。

### 4. 资源与算力

- **开源 AV-LLM**：7B 参数模型使用单张 NVIDIA A100 (40GB)；13B 模型使用单张 A100 (80GB)。仅推理，无训练。
- **闭源模型**：通过 Google Cloud API 调用 Gemini 系列。
- **SAVVY 各模块资源**：
  - SLAM 在 Aria 眼镜上实时运行。
  - Snapshot Descriptor 一次 AV-LLM 前向传播（与标准 AV-LLM 推理相当）。
  - 空间音频 & 全局地图：<0.1 秒/样本（CPU）。
  - Text‑guided segmentation (Seg)：约 0.52 秒/帧 (512×384)，峰值 GPU 内存 9.4 GB；深度估计约 0.44 秒/帧，≤6 GB。
- **总资源**：未提供完整实验总 GPU/CPU 时长，但推理评估可在单卡完成。

### 5. 实验数量与充分性

- **主要实验**：在 SAVVY‑Bench 上对比 8 种 AV-LLM 及人类水平，报告四个任务的准确率（Table 2）。
- **消融实验**：
  - 不同 egocentric track 类型组合（SD, Audio, Seg）→ Table 6。
  - 不同音频通道组合对定位和 DoA 的影响 → Table 4。
  - 不同 Seg 置信度阈值和采样帧数 → Table 7, 8。
  - 全局地图 vs 无全局地图的影响 → Table 9。
  - 盲测试验：Audio Only vs Audio+Visual → Table 10。
- **辅助评估**：SD‑Eval（temporal grounding & object referral）→ Table 3。
- **定性分析**：两类错误案例（方向、距离）及 SAVVY 如何修正。
- **充分性与公正性**：
  - 对比方法覆盖主流通用/可迁移模型，包括专为 egocentric 设计的 EgoGPT。
  - 消融实验系统，揭示各组件贡献。
  - 指标定义清晰，人类基线可信。
  - 不足之处：缺少与其他 3D 空间推理模型（如 SpatialVLM, VSI-Bench）的对比，但那些模型不支持音频或动态场景。

### 6. 论文的主要结论与发现

1. 现有 AV-LLMs（包括最强 Gemini‑2.5‑pro）在动态 3D 空间推理上远低于人类水平（总体 50.9% vs 78.7%），尤其在异中心任务上几乎随机。
2. **SAVVY 显著提升 SAVVY‑Bench 性能**：将 Gemini‑2.5‑pro 的总体准确率从 50.9% 提升至 58.0%（+7.1%），自中心方向准确率提升至 84.7%（+9.5%），异中心方向提升至 44.0%（+12.3%）。
3. 各模块互补：Seg 擅长动态目标定位；SD 擅长静态参照物和异中心推理；Audio 增强距离估计和前/后向区分。
4. 空间音频比视觉更早地提供关键定位；全局地图转换是处理动态视角变化的核心。
5. 时间定位和物体会指是 AV-LLM 的主要瓶颈（开源模型 t‑mIoU <5%）。

### 7. 优点：方法或实验设计上的亮点

- **首个动态 3D 空间音频‑视觉基准**，填补重要空白。
- **无需训练的插件式流水线**，可直接增强现有 AV-LLM，无需重新训练，可扩展性强。
- **多模态融合策略**（语言、视觉、空间音频）通过互补克服单一模态局限。
- **详细的消融与盲测试验**明确各组件贡献，包括音频通道选择、Seg 参数等。
- **定性分析**展示 SAVVY 如何修正典型错误（如 Gemini 因物体消失而误判方向，SAVVY 利用音频纠正）。
- **模块化设计**，支持未来升级（如替换更强分割模型或深度学习测距）。

### 8. 不足与局限

- **依赖强基座 AV-LLM**：阶段1的 Snapshot Descriptor 需要高能力的模型（如 Gemini），若基线较弱，整个流水线可能失效。
- **空间音频距离估计仍不稳定**：基于 CDR 的测距在环境变化或远/近场情况下精度有限。
- **Seg 模块效率瓶颈**：对每帧进行分割和深度估计，即使采样 32 帧仍有较大开销（GPU 内存 9.4GB + 0.52s/frame），不适合实时应用。
- **场景局限性**：仅基于室内 AEA 数据集，未验证户外、驾驶等场景的普适性。
- **实验对比不足**：未与特定 3D 场景理解模型（如 SpatialVLM, 3D-LLM）进行比较（虽然它们不支持音频且静态），但可增加说服力。
- **未讨论模型偏见或数据集偏差**：AEA 数据包含特定文化背景和场景，可能影响泛化性。
- **仅限推理，无训练范式**：无法嵌入端到端训练以利用更大规模空间音频数据。

---
（完）
