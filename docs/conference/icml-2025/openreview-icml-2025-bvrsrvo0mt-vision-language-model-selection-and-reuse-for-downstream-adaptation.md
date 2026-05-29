---
title: Vision-Language Model Selection and Reuse for Downstream Adaptation
title_zh: 视觉语言模型的选择与重用用于下游适配
authors: "Hao-Zhe Tan, Zhi Zhou, Yu-feng Li, Lan-Zhe Guo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=bvrsrvo0Mt"
tags: ["query:wm-vla-sa"]
score: 4.0
evidence: 视觉语言模型的选择与重用用于下游适配
tldr: 面对众多开源视觉语言模型（VLM），如何为特定下游任务选择最佳模型是个难题。本文提出模型标签学习（MLL）范式，通过为每个VLM标注专业性和有效性、匹配任务需求，并复用模型知识，高效选出适用模型。该方法避免了逐一评估所有VLM的时间和数据开销，对机器人领域VLA模型的选取和适配具有指导意义。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-bvrsrvo0mt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1100, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bvrsrvo0mt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1753, \"height\": 1138, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bvrsrvo0mt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 441, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-bvrsrvo0mt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1770, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bvrsrvo0mt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1771, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bvrsrvo0mt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 851, \"height\": 144, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bvrsrvo0mt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 749, \"height\": 402, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bvrsrvo0mt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1418, \"height\": 1066, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bvrsrvo0mt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1696, \"height\": 2199, \"label\": \"Table\"}]"
motivation: 缺乏高效的机制从大量预训练VLM中为特定下游任务选择最佳模型。
method: 提出模型标签学习（MLL），包含模型标注、模型选择和模型重用三个模块。
result: MLL能够高效选择出适合下游任务的VLM，提升任务性能。
conclusion: 为VLM的实用化部署提供了自动化选择方案，可推广至VLA模型选型。
---

## Abstract
Pre-trained Vision-Language Models (VLMs) are becoming increasingly popular across various visual tasks, and several open-sourced VLM variants have been released. However, selecting the best-performing pre-trained VLM for a specific downstream task is challenging since no single VLM can achieve promising performance on all downstream tasks, and evaluating all available VLMs is impossible due to time and data limitations. To address this problem, this paper proposes a novel paradigm to select and reuse VLM for downstream tasks, called **M**odel **L**abel **L**earning (**MLL**). The proposal contains three key modules: *model labeling*, which assigns labels to each VLM to describe their specialty and utility; *model selection*, which matches the requirements of the target task with model labels; and *model reuse*, which applies selected VLMs to the target task in an ensemble manner. The proposal is highly computationally efficient and growable since the model labeling process is completed target task independent and the ability could grow with the number of candidate VLMs. We also introduce a new benchmark for evaluating VLM selection methods, including 49 VLMs and 17 target task datasets. Experimental results clearly demonstrate the effectiveness of the proposed method for selecting and reusing VLMs.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义

- **研究动机**：预训练视觉语言模型（VLM，如 CLIP、ALIGN）在零样本视觉任务中表现优异，但没有任何单一 VLM 能在所有下游任务上达到最佳性能。实际中存在大量开源 VLM（如 open‑clip 模型库有上百个变体），用户无法逐一评估所有模型，传统基于 ImageNet 的排名对特定任务并不鲁棒（模型在不同任务和不同类别上的表现差异巨大）。
- **整体含义**：本文首次系统研究 VLM 的**选择与重用**问题，提出一个可在模型库层面自动化、高效率、可持续增长的选择范式，从而推动 VLM 在真实应用中的部署。

## 2. 方法论

### 核心思想：模型标签学习（MLL）
- 为每个候选 VLM 生成一个描述其专业性和效用的**标签**（基于对常见视觉概念的预测试结果）；当新任务到来时，通过匹配任务需求与模型标签来选择并重用模型。
- 该流程在模型上传阶段完成标签生成（目标任务无关），因此选择阶段极快。

### 三个关键模块

1. **模型标注（Model Labeling）**  
   - 构建一个**语义图**（Semantic Graph），节点为 WordNet 中的常见视觉概念（共 9055 个节点），每个节点关联一组采样图片（来自 ImageNet 及其变体、ImageNet‑Sketch、ImageNet‑A、ImageNet‑R 等 5 个样本数据集）。  
   - 对每个 VLM \(f_m\)，计算其在每个节点 \(v\) 上的图像‑文本匹配相似度分布 \(s_{m,v}\)，汇总为模型标签 \(S_m = \{ s_{m,v} \mid v \in V_G \}\)。

2. **模型选择（Model Selection）**  
   - 对于下游任务 \(T\)（含类别集合 \(Y_T\)），使用 GPT‑4 生成每个类别的详细描述（caption）；同时为语义图节点也生成 caption。  
   - 计算两类 caption 的嵌入相似度，选出每个目标类别最匹配的 top‑k 节点，构建转移矩阵 \(Z\)。  
   - 利用模型标签得到模型在各节点上的精度 \(p_{m,v}\)，通过转移矩阵将其映射到目标类别精度预估 \(p_{m,y}\)。  
   - 引入平衡参数 \(\alpha=0.7\)，综合类别级与整体性能得到复用指标 \(r_{m,y}\)（公式 7）。

3. **模型重用（Model Reuse）**  
   - 对每个类别 \(y\)，选择指标最高的 \(k\) 个模型组成集成预测器 \(F_y^k\)。  
   - 集成时使用**概率熵**作为权重 \(w_{m,y}\)，降低过度自信模型的贡献（公式 9）。  
   - 最终预测取置信度最高的类别（公式 10）。

## 3. 实验设计

### Benchmark
- **模型库**：从 OpenCLIP 库选取 49 个预训练 VLM（涵盖 ViT、ConvNeXt、CoCa、EVA 等架构，训练数据集包括 OpenAI 原版、LAION‑2B、DataComp 等）。
- **目标数据集**：17 个常用的零样本下游任务数据集（CIFAR‑100、Country211、CLEVR‑D、DTD、DMLab、Flowers102、MNIST、OxfordPet、PCam、FER2013、Food101、GTSRB、RESISC45、Rendered‑SST2、StanfordCars、STL10、UCF101），涵盖自然图像、纹理、遥感、医学、交通信号、表情识别等多种领域和任务类型。
- **语义图构建**：使用 WordNet 的 9055 个 synsets 作为节点，从 5 个样本数据集中为每个节点随机选取最多 75 张图片。
- **评价指标**：Accuracy （零样本，无额外微调）。

### 对比方法
1. **ImageNet Baseline (INB)**：直接选择 ImageNet 验证集上准确率最高的 VLM 用于所有下游任务。
2. **ModelGPT**（Zohar et al., 2023）：使用文本描述（caption 和同义词）代替图像来评估 VLM，并学习线性模型预测任务性能。论文中利用样本数据集上的真实性能训练其线性模型。

### 实验设置
- 在 \(k=1\)（每类仅重用一个模型）和 \(k=3\)（每类集成三个模型）两种场景下评估。
- 所有模型使用相同的提示模板（"a photo of {class}"），零样本推理。
- 消融实验：调整平衡参数 \(\alpha\)（0.5~0.9）和重用模型数量 \(k\)（1~6）。
- 扩展性实验：模拟模型库从 0 逐步扩充到 49 个模型，观察平均性能变化。

## 4. 资源与算力

- 文中仅提及：“All experiments are conducted on NVIDIA A800 GPUs.”  
- **未明确说明** GPU 数量、训练时长或具体算力消耗（论文的核心方法在预测试阶段需要一次性处理全部语义图节点，但该过程仅需执行一次；选择阶段计算量极小）。因此无法给出精确的算力统计。

## 5. 实验数量与充分性

- **实验数量**：
  - 主实验：17 个数据集 × 2 种设置（\(k=1, k=3\)） × 3 种方法，共约 102 个独立得分。
  - 消融实验：α 消融（5 个值）、k 消融（6 个值）各涵盖 17 个数据集，给出平均值。
  - 扩展性实验：30 次随机扩充序列，每次序列包含 49 步。
- **充分性评估**：
  - 数据集覆盖多种领域和任务，对比方法（INB 和 ModelGPT）具有代表性。
  - 消融研究系统地探索了关键超参数的影响，并显示了鲁棒性。
  - 扩展性实验验证了模型库规模增长对性能的正向作用。
  - **公平性**：所有方法均使用相同零样本推理配置；ModelGPT 也使用相同的提示和样本数据集训练线性模型，比较合理。
  - 不足：所有实验仅针对**零样本分类**，未涉及少样本微调场景；未与更多新近的模型选择方法（如 LogME、LEEP 等单模态方法）比较，因为这些方法无法直接用于 VLM。

## 6. 主要结论与发现

1. **MLL 显著优于 INB 和 ModelGPT**：在 17 个任务的平均准确率上，MLL（\(k=1\)）达到 0.6620，比 INB（0.6434）和 ModelGPT（0.6367）分别高出约 2% 和 3%。
2. **细粒度选择有效**：MLL 可以为不同类别选择不同模型，在类别差异大的任务（如 FER2013）上优势明显。
3. **模型库规模越大，MLL 性能越好**：扩展性实验表明，随着候选模型增加，平均性能持续上升，证明了方法的可增长性。
4. **参数鲁棒**：α 在 [0.5, 0.9] 范围内性能稳定；k=1 或 k=3 时效果最好，更大 k 可能引入噪声。

## 7. 优点

- **高效性**：模型标签在模型提交时一次性计算，选择阶段无需再运行候选模型，计算开销极低。
- **可扩展性**：语义图节点可以持续添加，模型库可以持续扩充，标签更新成本低。
- **细粒度**：按类别选择模型，能捕捉不同类别上模型的差异化能力。
- **降低过度自信风险**：集成时使用熵权重，减少错误高置信度模型的影响。
- **实用性强**：用户只需提供任务类别等基本信息即可获得良好性能，无需标注数据。
- **开源承诺**：论文提供了代码仓库（GitHub），有助于推动标准化评测。

## 8. 不足与局限

- **应用范围窄**：当前仅适用于**视觉分类任务**，未扩展到目标检测、分割、视觉问答等更复杂任务，也未支持 NLP 或纯视觉模型。
- **依赖外部资源**：语义图构建依赖 WordNet 和固定的采样数据集；GPT‑4 生成的 caption 质量可能影响跨域匹配。
- **场景单一**：所有实验均在零样本下进行，未考虑微调或 few‑shot 场景；实际应用中用户可能允许少量标注数据。
- **对比方法有限**：仅对比了 INB 和 ModelGPT，但缺少与更通用的模型选择方法（如 LogME）的适配比较；ModelGPT 的线性模型使用相同样本数据集训练可能并非其原始设定。
- **资源消耗不透明**：虽然标签生成只做一次，但语义图规模（9055 节点 × 最多 75 张图）的预测试需要大量 GPU 计算时间，论文未量化该成本。
- **评估偏差风险**：采样数据集与目标数据集可能有重叠（如 ImageNet 变体同时用于构建语义图和下游任务），可能造成性能高估。
- **理论分析缺失**：未对选择机制的可学习性、最优性提供理论保证。

（完）
