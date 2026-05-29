---
title: "SAFE: Multitask Failure Detection for Vision-Language-Action Models"
title_zh: SAFE：面向视觉-语言-动作模型的多任务故障检测
authors: "Qiao Gu, Yuanliang Ju, Shengxiang Sun, Igor Gilitschenski, Haruki Nishimura, Masha Itkina, Florian Shkurti"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=XPyAukgsFf"
tags: ["query:wm-vla-sa"]
score: 6.0
evidence: 面向通用VLA策略的多任务故障检测器
tldr: 本文首次定义多任务故障检测问题，并提出SAFE检测器，专为通用机器人策略（如VLA）设计。SAFE能在未见过的任务和环境中检测故障，及时发出警报使机器人停止或求助。实验表明，SAFE在多个任务上具有良好泛化性，提升了VLA部署的安全性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpyaukgsff/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 827, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpyaukgsff/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 563, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpyaukgsff/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 822, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpyaukgsff/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1426, \"height\": 666, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpyaukgsff/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1416, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpyaukgsff/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1450, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpyaukgsff/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1009, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpyaukgsff/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1004, \"height\": 419, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpyaukgsff/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1010, \"height\": 418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpyaukgsff/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1012, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpyaukgsff/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1009, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpyaukgsff/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 631, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpyaukgsff/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 627, \"height\": 609, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpyaukgsff/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 629, \"height\": 601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpyaukgsff/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 629, \"height\": 663, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpyaukgsff/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 628, \"height\": 611, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpyaukgsff/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 626, \"height\": 601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpyaukgsff/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1425, \"height\": 1923, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpyaukgsff/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1406, \"height\": 1830, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpyaukgsff/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1456, \"height\": 663, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpyaukgsff/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1454, \"height\": 358, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpyaukgsff/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1243, \"height\": 593, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpyaukgsff/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 623, \"height\": 386, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpyaukgsff/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1453, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpyaukgsff/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1172, \"height\": 393, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpyaukgsff/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 848, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpyaukgsff/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1454, \"height\": 575, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpyaukgsff/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 654, \"height\": 922, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpyaukgsff/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 736, \"height\": 1199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpyaukgsff/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1463, \"height\": 1074, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpyaukgsff/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 680, \"height\": 549, \"label\": \"Table\"}]"
motivation: 通用VLA策略在部署时成功率有限，需要能够泛化到新任务的故障检测器来保证安全交互。
method: 提出多任务故障检测问题，并设计SAFE检测器，利用多任务训练实现对新任务和环境的泛化。
result: SAFE在多个未见任务上实现了高精度故障检测，有效提升了VLA策略的安全性。
conclusion: 多任务故障检测是通用机器人策略安全部署的重要组件，SAFE为此提供了有效方案。
---

## Abstract
While vision-language-action models (VLAs) have shown promising robotic behaviors across a diverse set of manipulation tasks, they achieve limited success rates when deployed on novel tasks out of the box. To allow these policies to safely interact with their environments, we need a failure detector that gives a timely alert such that the robot can stop, backtrack, or ask for help. However, existing failure detectors are trained and tested only on one or a few specific tasks, while generalist VLAs require the detector to generalize and detect failures also in unseen tasks and novel environments. In this paper, we introduce the multitask failure detection problem and propose SAFE, a failure detector for generalist robot policies such as VLAs. We analyze the VLA feature space and find that VLAs have sufficient high-level knowledge about task success and failure, which is generic across different tasks. Based on this insight, we design SAFE to learn from VLA internal features and predict a single scalar indicating the likelihood of task failure. SAFE is trained on both successful and failed rollouts and is evaluated on unseen tasks. SAFE is compatible with different policy architectures. We test it on OpenVLA, $\pi_0$, and $\pi_0$-FAST in both simulated and real-world environments extensively. We compare SAFE with diverse baselines and show that SAFE achieves state-of-the-art failure detection performance and the best trade-off between accuracy and detection time using conformal prediction. More qualitative results and code can be found at the project webpage: https://vla-safe.github.io/

---

## 论文详细总结（自动生成）

## 主要结构

### 1. 论文的核心问题与整体含义

- **动机**：通用视觉-语言-动作模型（VLA）在未见任务上成功率低（30-60%），需要及时的故障检测以保证安全交互；但现有检测器仅针对单任务训练，无法泛化到新任务。
- **问题定义**：首次提出**多任务故障检测**——检测器仅在已见任务上训练，需零样本泛化到未见任务，并对VLA策略进行在线检测。
- **意义**：为通用机器人策略（如OpenVLA、π₀）的可靠部署提供关键安全组件。

### 2. 方法论：核心思想、技术细节与流程

- **核心发现**：VLA内部特征（最后一层隐藏向量）在成功与失败轨迹上存在清晰分离的“故障区域”（failure zone），且该区域跨任务一致。
- **特征提取**：从VLA最后层提取嵌入向量 eₜ（通过均值/首尾等聚合方式），不修改VLA本身。
- **故障得分预测**：
  - **SAFE-MLP**：对每一时刻的 eₜ 独立预测一个标量，累积求和作为故障得分；使用L1损失（鼓励失败轨迹得分高、成功轨迹得分低）。
  - **SAFE-LSTM**：用LSTM建模时序，输出0~1的概率；使用交叉熵损失。
- **阈值校准**：采用**功能共形预测（Functional Conformal Prediction）**，在成功轨迹的校准集上构建时变预测带 Cα，保证新成功轨迹的得分以1-α概率不超出该带。当预测试失败得分超出上限时，即触发故障警报。
- **计算公式**：详见文中公式（4.2节损失函数，4.3节CP带构造），核心是时变均值μₜ + 带宽hₜ。

### 3. 实验设计

- **仿真环境**：
  - **LIBERO-10**：10个长时任务，测试OpenVLA、π₀-FAST、π₀（预训练模型）。
  - **SimplerEnv**：高保真仿真，使用π₀*（复现模型），分别测试Google Robot和WidowX具身。
- **真实机器人**：
  - **Franka Emika Panda** + π₀-FAST-DROID：13个任务，每个任务30成功+30失败。
  - **WidowX 250** + OpenVLA：8个任务，共532次滚动。
- **划分方式**：每个benchmark中随机选取若干任务作为未见任务（seen/unseen比例因benchmark而异），训练数据仅来自已见任务。
- **对比方法**：
  - 基于Token不确定性（最大概率/熵）
  - 基于嵌入距离（马氏距离、欧氏kNN、余弦kNN、PCA-KMeans）
  - 基于OOD学习（RND、LogpZO）
  - 基于样本一致性（动作方差、簇熵、STAC）
  - 所有baseline均适配到VLA输入格式。
- **评价指标**：ROC-AUC（主指标）、Bal-acc、检测时间T-det，并利用功能CP给出可调节的阈值。

### 4. 资源与算力

- **GPU**：单张NVIDIA A100 40GB GPU。
- **训练时间**：SAFE训练通常<1分钟（网络极轻量：1-2层MLP或单层LSTM，隐层维度256）。
- **推理开销**：<1ms，占VLA推理时间<1%。
- 未明确给出总计算量或总GPU小时数，但开销很低。

### 5. 实验数量与充分性

- **覆盖范围**：4个仿真benchmark + 2个真实机器人环境，涉及3个不同VLA模型。
- **重复次数**：平均3或5个随机种子，每个种子不同任务划分，结果报告均值和标准差。
- **消融实验**：
  - 不同特征聚合方式（首/尾/均值/首尾拼接）
  - π₀-FAST中特征层选择（encoded vs pre-logits）
  - 训练任务数量（3/5/7个）对泛化影响
  - 不同视觉特征（DINOv2/CLIP vs VLA特征）
- **充分性**：实验设计系统，对比基线全面（包括LLM UQ方法、机器人领域SOTA），结果具统计显著性，公平性较好（统一阈值校准、控制检测时间等）。

### 6. 论文的主要结论与发现

- SAFE在几乎所有benchmark上取得SOTA的ROC-AUC，尤其在未见任务上平均领先最佳基线4-5%。
- 功能CP校准可实现可控的误报率，SAFE在精度-检测时间权衡上优于所有方法。
- SAFE能在故障实际发生前（或发生早期）准确触发警报，符合人类判断。
- 内部特征空间分析验证了VLA具备任务无关的成败知识。

### 7. 优点：方法或实验设计上的亮点

- **简单高效**：仅使用VLA最后一层特征，无需修改VLA或额外采样，开销极小。
- **强泛化性**：通过多任务训练学习通用故障模式，零样本迁移到新任务。
- **理论保证**：功能共形预测提供在线故障标志的统计性假阳性控制。
- **兼容性**：可应用于不同VLA架构（离散token/扩散/流匹配）。
- **实验扎实**：覆盖仿真、真实、多种机器人平台，对比基线多样，重视检测时间与精度的权衡。

### 8. 不足与局限

- **任务范围有限**：仅针对操作任务，未验证跨具身、sim2real或动作缺失视频的泛化。
- **特征使用**：仅用最后一层，多层信息可能更有用（文中留作未来工作）。
- **训练需求**：仍需收集成功和失败滚动以训练检测器（但训练成本低）。
- **分布偏移**：在未见任务上TNR有时偏离CP假设（1-α），表明跨任务分布不独立同分布。
- **人工标注**：故障时刻由人工标注，存在一定主观性（尤其模糊故障模式）。

（完）
