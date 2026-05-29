---
title: "CogVLA: Cognition-Aligned Vision-Language-Action Models via Instruction-Driven Routing & Sparsification"
title_zh: CogVLA：通过指令驱动的路由与稀疏化实现认知对齐的视觉-语言-动作模型
authors: "Wei Li, Renshan Zhang, Rui Shao, Jie He, Liqiang Nie"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Fg9HufTI0K"
tags: ["query:wm-vla-sa"]
score: 8.0
evidence: 认知对齐的VLA模型，指令驱动路由与稀疏化
tldr: CogVLA针对VLA模型后训练开销大的问题，提出认知对齐的框架，通过指令驱动的路由与稀疏化策略，在保持端到端一致性前提下提升效率。在机器人任务上验证了其加速效果和性能。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-fg9hufti0k/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1432, \"height\": 838, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fg9hufti0k/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 584, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fg9hufti0k/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1443, \"height\": 768, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fg9hufti0k/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 952, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fg9hufti0k/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1445, \"height\": 1034, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fg9hufti0k/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1447, \"height\": 646, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fg9hufti0k/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1446, \"height\": 1445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fg9hufti0k/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1446, \"height\": 2146, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-fg9hufti0k/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1428, \"height\": 594, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fg9hufti0k/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1461, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fg9hufti0k/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 327, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fg9hufti0k/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 813, \"height\": 490, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fg9hufti0k/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 596, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fg9hufti0k/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 595, \"height\": 129, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fg9hufti0k/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1356, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fg9hufti0k/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1356, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fg9hufti0k/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 851, \"height\": 260, \"label\": \"Table\"}]"
motivation: 现有VLA模型需要大量后训练，且稀疏化策略忽视模态间语义耦合。
method: 提出CogVLA框架，利用指令驱动路由和稀疏化，保持视觉-语言-动作语义耦合。
result: 在多个VLA基准上实现显著加速，性能与完整模型相当。
conclusion: CogVLA提供了一种高效的VLA部署方案，促进具身智能的可扩展性。
---

## Abstract
Recent Vision-Language-Action (VLA) models built on pre-trained Vision-Language Models (VLMs) require extensive post-training, resulting in high computational overhead that limits scalability and deployment. Existing sparsification strategies—such as Mixture-of-Depths, layer skipping, and early exit—fall short by neglecting the semantic coupling across vision-language-action modalities, and focusing narrowly on intra-LLM computation while overlooking end-to-end coherence from perception to control. To address these challenges, we propose **CogVLA**, a Cognition-Aligned Vision-Language-Action framework that leverages instruction-driven routing and sparsification to improve both efficiency and performance. CogVLA draws inspiration from human multimodal coordination and introduces a 3-stage progressive architecture. 1) **Encoder-FiLM based Aggregation Routing (EFA-Routing)** injects instruction information into the vision encoder to selectively aggregate and compress dual-stream visual tokens, forming a instruction-aware latent representation. 2) Building upon this compact visual encoding, **LLM-FiLM based Pruning Routing (LFP-Routing)** introduces action intent into the language model by pruning instruction-irrelevant visually grounded tokens, thereby achieving token-level sparsity. 3) To ensure that compressed perception inputs can still support accurate and coherent action generation, we introduce **V‑L‑A Coupled Attention (CAtten)**, which combines causal vision-language attention with bidirectional action parallel decoding.
Extensive experiments on the LIBERO benchmark and real-world robotic tasks demonstrate that CogVLA achieves state-of-the-art performance with success rates of 97.4\% and 70.0\%, respectively, while reducing training costs by 2.5$\times$ and decreasing inference latency by 2.8$\times$ compared to OpenVLA.

---

## 论文详细总结（自动生成）

# 论文《CogVLA: Cognition-Aligned Vision-Language-Action Models via Instruction-Driven Routing & Sparsification》详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：现有的视觉-语言-动作（VLA）模型通常基于预训练的视觉-语言模型（VLM）构建，需要大量后训练（post-training）才能适配机器人控制任务，导致计算开销极高，限制了模型的可扩展性和实际部署。此外，已有的稀疏化策略（如Mixture-of-Depths、层跳过、早期退出等）主要关注语言模型内部的计算优化，而忽视了视觉、语言、动作模态之间的语义耦合，导致端到端的感知-推理-控制一致性受损。
- **研究动机**：从认知科学中的人体多模态协调机制获得启发（人脑在操作时能够高效地聚焦任务相关信息、注入动作意图并规划连贯动作序列），作者希望设计一种既提升效率又保持跨模态语义一致性的VLA框架。
- **整体含义**：CogVLA通过指令驱动的路由与稀疏化，在压缩视觉输入的同时，保持对任务相关语义的敏锐感知和动作生成的一致性，在LIBERO仿真基准和真实机器人任务上取得了SOTA性能，并显著降低训练和推理成本。

## 2. 方法论

### 核心思想
CogVLA采用三阶段渐进式架构，模拟人脑中的视觉注意力系统（VAS）、辅助运动区（SMA）和前运动皮层（PMC）的协调机制，实现指令驱动的视觉稀疏化和跨模态推理。

### 关键技术细节

#### 阶段一：Encoder-FiLM based Aggregation Routing (EFA-Routing)
- **目标**：模拟VAS，根据指令选择性聚焦视觉信息。
- **过程**：
  1. **编码器内聚合**：对每个视觉编码器分支（如SigLIP和DINOv2），利用FiLM层将指令嵌入调制为缩放和偏移参数，引导聚合令牌（aggregation tokens）从所有图像令牌中融合指令相关特征。经过多个编码器块后，只保留聚合令牌，丢弃原始图像令牌，将视觉令牌压缩至原始规模的25%。
  2. **跨编码器聚合**：设计一个指令条件门控（instruction-conditioned routing gate），通过一个MLP根据指令文本输出融合权重α，动态平衡两个编码器分支的聚合令牌。最终的双重聚合令牌为：`v_agg = α · v_SigLIP_agg + (1−α) · v_DINOv2_agg`。

#### 阶段二：LLM-FiLM based Pruning Routing (LFP-Routing)
- **目标**：模拟SMA，将动作意图注入语言模型，修剪与指令无关的视觉令牌，实现令牌级稀疏。
- **过程**：
  1. 在大语言模型的每个Transformer层之前，使用轻量级MLP根据当前指令生成FiLM调制参数，对双重聚合令牌进行语义调制。
  2. 通过任务导向修剪路由器（Task-Guided Pruning Router）计算每个视觉令牌的相关性分数（`R_j^l = MLP(Z_j^l)`），设定保留比率β（采用偏移余弦衰减调度），仅保留分数高于第β百分位的令牌，其余令牌跳过该层的注意力计算。
  3. 典型配置下，LFP-Routing约修剪50%的视觉令牌。

#### 阶段三：V-L-A Coupled Attention (CAtten)
- **目标**：模拟PMC，在压缩的多模态输入下维持语义一致性和时间连贯性。
- **过程**：
  1. **因果视觉-语言注意力**：对视觉和语言令牌拼接段使用下三角因果掩码，保证指令-视觉推理的时序顺序。
  2. **双向动作块并行解码**：对动作令牌内部使用全双向注意力，使所有动作可以一次性并行预测。
  3. **统一混合注意力掩码**：构建全局混合掩码，其中视觉-语言部分因果，视觉-语言到动作部分单向依赖，动作内部双向。公式表示为：
     ```
     M_hybrid = [
         [M_VL_causal , -inf , -inf],
         [0            , 0   , -inf],
         [0            , 0   , M_act_bi]
     ]
     ```
  这样，模型在压缩视觉输入后仍能基于指令和视觉上下文正确解码动作序列。

### 算法流程概要
1. 输入：图像观测I、指令文本t。
2. Stage 1：通过EFA-Routing得到双重聚合令牌v_agg，并设为Z0。
3. Stage 2：在每个LLM层中，根据指令tl对Zl进行LFP-Routing，选择保留关键视觉令牌，输出Zl+1。
4. Stage 3：将最终视觉令牌、指令令牌和K个可学习空动作占位符拼接，送入CAtten模块，一次性并行预测所有K个未来动作。

## 3. 实验设计

### 使用数据集/场景与Benchmark
- **仿真环境**：**LIBERO benchmark**（包含四个任务族：Spatial、Object、Goal、Long，每个族10个任务，每个任务50个人类遥操作演示，指令复杂多样，平均10.48个单词）。
- **真实实验**：**Cobot Agilex ALOHA**机器人平台，进行三个长程任务：
  - Task 1：物体放置（两步：方块放入盘子，玩具放入碗）
  - Task 2：抽屉操作（打开-放入玩具-关闭）
  - Task 3：折叠T恤（三个步骤）
  收集演示：Task 1-2各45条，Task 3有30条（另外两个附加任务各30/45条）。

  Benchmark覆盖多维度通用性，包括空间推理、物体属性理解、目标变化以及长时间序列规划。

### 对比方法
- **LIBERO仿真**：Diffusion Policy、Octo (fine-tuned)、OpenVLA、π0 (fine-tuned)、π0-Fast、π0.5-KI、OpenVLA-OFT、SpatialVLA、PD-VLA、STAR、Dita、CoT-VLA等。
- **真实实验**：VQ-BeT、QueST、STAR、PD-VLA、OpenVLA-OFT。
- 所有对比方法均在作者复现的最佳条件下运行。

## 4. 资源与算力
- **硬件**：4 × A800 GPU (80GB显存)。
- **训练时长**：
  - LIBERO实验：训练60K步，CogVLA每10K步约4.7小时，总体约28.2小时（估算）；对比OpenVLA每10K步11.7小时，OpenVLA-OFT每10K步12.5小时。
  - 真实实验：训练80K步，具体总时长未单独列出。
- 论文未明确说明总GPU小时数，但可根据步数和每步时间推算。

## 5. 实验数量与充分性
- 仿真LIBERO：对四个任务族，每个族进行500次试验（共2000次），报告平均成功率。
- 真实实验：每个任务10次试验，报告任务和子任务成功率。
- **消融实验**：
  - 表4：对各阶段（Stage 1/2/3）进行逐项消融，验证每个模块贡献。
  - 表5：不同稀疏率分配（Stage 1 vs Stage 2）在固定总压缩比下的性能影响。
  - 表6：与FastV、SliME等视觉压缩方法对比。
  - 附录C.1：多随机种子评估（3个种子）展示稳定性。
  - 附录C.2：额外真实任务（Tasks 4-5）结果。
  - 附录C.3：扩展稀疏率配置消融（2×2、4×4等）。
- **充分性评价**：实验设计较为全面，涵盖了仿真和真实环境、多任务类型、多维度消融、效率对比（推理时间、吞吐量、FLOPs、训练成本），且进行了多种子评估，结果客观公平。但缺少在更大规模、更复杂机器人场景上的验证。

## 6. 主要结论与发现
- CogVLA在LIBERO上达到平均97.4%成功率，排名第一，超过所有对比方法（如OpenVLA-OFT 97.1%、PD-VLA 94.7%等）。
- 在真实机器人三任务上平均成功率70.0%，也优于PD-VLA（50.0%）和OpenVLA-OFT（56.7%）。
- 效率方面：相比OpenVLA，推理时间降低2.79倍（0.091s vs 0.254s），吞吐量提升22.5倍（87.9 Hz vs 3.9 Hz），FLOPs降低3.12倍，训练成本降低2.49倍。
- 指令驱动的稀疏化比单纯视觉压缩方法（FastV、SliME）显著更优（成功率98.6% vs 88.2%、77.6%）。
- 三个模块协同作用，缺一不可；Stage 1与Stage 2之间的不对称稀疏分配（Stage 1更激进）效果最好。

## 7. 优点
- **认知启发的架构设计**：模拟人脑多模态协调的三阶段渐进式稀疏化，具有生物学合理性，同时提升效率与语义一致性。
- **指令驱动的跨模态稀疏化**：EFA-Routing和LFP-Routing均以指令为条件，使模型能够根据不同任务动态聚焦相关视觉信息，避免盲目压缩。
- **统一耦合注意力机制**：CAtten巧妙结合因果与双向注意力，在压缩输入下依然支持因果时序推理和并行动作解码，保证动作连贯性。
- **实验充分、效率高**：在多个基准和真实场景上验证性能优势，同时量化了训练和推理成本的大幅降低。
- **开源友好**：基于开源的OpenVLA模型和数据集，代码和模型将开放。

## 8. 不足与局限
- **稀疏率固定**：当前采用预设的稀疏比率和余弦衰减调度，无法根据不同任务或场景的复杂程度自适应调整，可能在某些困难场景下欠优。
- **OOD泛化未充分验证**：虽然展示了LIBERO和ALOHA平台实验结果，但未深入测试在未见过的指令类型、物体类别或环境下的表现。
- **真实场景多样性**：真实实验仅涉及三类任务，且演示数据量较小（30-45条），对更复杂的操作（如柔性物体、精细装配）缺乏评估。
- **计算资源需求**：尽管已显著优于其他VLA模型，但CogVLA仍依赖于多个高性能GPU（4×A800），部署到资源更受限的边缘设备可能仍有挑战。
- **未集成多模态反馈**：目前主要依赖视觉和语言，未结合触觉或力反馈等模态，限制了在精密操作任务中的适用性。
- **安全性风险**：在安全关键环境中，若指令模糊或视觉异常，可能导致错误动作，论文未提供鲁棒性分析或安全机制。

（完）
