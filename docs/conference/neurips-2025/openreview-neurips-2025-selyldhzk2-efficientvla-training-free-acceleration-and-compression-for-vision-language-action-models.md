---
title: "EfficientVLA: Training-Free Acceleration and Compression for Vision-Language-Action Models"
title_zh: EfficientVLA：视觉-语言-动作模型的免训练加速与压缩
authors: "Yantai Yang, Yuhao Wang, Zichen Wen, Luo Zhongwei, Chang Zou, Zhipeng Zhang, Chuan Wen, Linfeng Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=SELYlDHZk2"
tags: ["query:wm-vla-sa"]
score: 8.0
evidence: VLA模型的免训练加速
tldr: EfficientVLA针对VLA模型推理计算和内存瓶颈，提出一种免训练的加速与压缩框架。该框架系统地利用模型中的多重冗余，在不需重新训练的情况下提升推理速度。实验证明其在保持性能的同时大幅降低资源消耗，使VLA模型更适用于实际机器人部署。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-selyldhzk2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 625, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-selyldhzk2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1396, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-selyldhzk2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1323, \"height\": 268, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-selyldhzk2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1412, \"height\": 353, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-selyldhzk2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1433, \"height\": 550, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-selyldhzk2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1434, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-selyldhzk2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 714, \"height\": 177, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-selyldhzk2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1233, \"height\": 472, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-selyldhzk2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 712, \"height\": 157, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-selyldhzk2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1438, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-selyldhzk2/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1436, \"height\": 349, \"label\": \"Table\"}]"
motivation: VLA模型计算和内存需求高，现有加速方案仅孤立优化，无法全面解决瓶颈。
method: 提出结构化的免训练推理加速框架EfficientVLA，利用多种冗余进行协同优化。
result: 在多个VLA基准上，EfficientVLA显著加速推理并减少内存占用，性能损失极小。
conclusion: EfficientVLA实现了VLA模型的高效部署，推动具身智能实际应用。
---

## Abstract
Vision-Language-Action (VLA) models, particularly diffusion-based architectures, demonstrate transformative potential for embodied intelligence but are severely hampered by high computational and memory demands stemming from extensive inherent and inference-time redundancies. While existing acceleration efforts often target isolated inefficiencies, such piecemeal solutions typically fail to holistically address the varied computational and memory bottlenecks across the entire VLA pipeline, thereby limiting practical deployability.  We introduce EfficientVLA, a structured and training-free inference acceleration framework that systematically eliminates these barriers by cohesively exploiting multifaceted redundancies. EfficientVLA synergistically integrates three targeted strategies: (1) pruning of functionally inconsequential layers from the language module, guided by an analysis of inter-layer redundancies; (2) optimizing the visual processing pathway through a task-aware strategy that selects a compact, diverse set of visual tokens, balancing task-criticality with informational coverage; and (3) alleviating temporal computational redundancy within the iterative diffusion-based action head by strategically caching and reusing key intermediate features.
We apply our method to a standard VLA model CogACT, yielding a $1.93\times$ inference speedup and reduces FLOPs to 28.9%, with only a 0.6% success rate drop in the SIMPLER benchmark.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：视觉-语言-动作（Vision-Language-Action, VLA）模型，尤其是基于扩散架构的模型，在具身智能领域展现出巨大潜力。然而，其推理过程中存在极高的计算和内存开销，严重阻碍了在资源受限的机器人平台上的实时部署。
- **现有不足**：已有的加速方法大多针对单一模块的孤立瓶颈（如仅优化视觉 token 或仅压缩语言层），缺乏系统性，导致整体加速效果有限。例如，优化视觉 token 后，推理瓶颈会转移至语言模块的内存瓶颈；仅加速动作头则无法缓解语言模块的计算负担。
- **整体目标**：提出一种**无需重新训练**的结构化加速框架 EfficientVLA，通过协同利用 VLA 模型中多层面的冗余（深度冗余、视觉冗余、时间冗余），系统性消除计算和内存瓶颈，实现显著加速且性能损失极小。

## 2. 论文提出的方法论

- **核心思想**：针对 VLA 模型的三个主要模块（语言模块、视觉处理模块、扩散动作模块），分别设计无需训练的优化策略，并协同整合，达到整体加速。
- **关键技术细节**：
  1. **语言模块层剪枝**：
     - 通过分析输入与输出隐藏状态的余弦相似度，量化每一层的功能重要性。重要性指标 \( I(\ell) = 1 - \frac{1}{|D|}\sum_{i}\frac{1}{L}\sum_{j}\frac{x_{i,j}^{(\ell)}\cdot x_{i,j}^{(\ell+1)}}{\|x_{i,j}^{(\ell)}\|_2\|x_{i,j}^{(\ell+1)}\|_2} \)。
     - 按重要性升序排序，移除前 \( n \) 个冗余层（非连续剪枝）。
  2. **视觉 token 剪枝**：
     - 步骤一：利用语言模块中视觉 token 对上下文 token 的 cross-attention 分数，计算任务相关性分数，选出前 \( K_{\text{key}} \) 个关键 token（无条件保留）。
     - 步骤二：在剩余 token 中，按比例 \( \alpha \) 选取高任务相关性的补充 token（\( V_{\text{task}} \)）。
     - 步骤三：从剩余 token 中选取与已选集合余弦距离最大的 token（\( V_{\text{div}} \)），保证多样性。
     - 最终保留集合：\( V_{\text{pruned}} = V_{\text{key}} \cup V_{\text{task}} \cup V_{\text{div}} \)，总数为 \( K_{\text{final}} \)。
  3. **扩散动作头中间特征缓存**：
     - 观察到相邻去噪步的 attention 和 MLP 输出高度相似，提出静态 N 步缓存机制。
     - 在每第 N 步重新计算并更新缓存，中间步直接复用缓存值，跳过 attention 和 MLP 计算。
- **整体流程**：图2给出了框架概览，三个策略协同执行，无需任何微调或训练。

## 3. 实验设计

- **使用的数据集/场景**：
  - **SIMPLER 环境**：仿真桌面操作基准，包含 Google Robot 和 WidowX 机器人任务。提供两种评估设置：Visual Matching（视觉匹配）和 Variant Aggregation（变体聚合），每个设置包含四项任务：Pick coke can、Move near、Open/close drawer、Open top drawer and place apple。评价指标为成功率。
  - **LIBERO 基准**（附录）：包含移动操作任务套件，测试泛化能力。
  - **视觉语言任务**（附录）：使用 LLaVA-1.5-7B 在 GQA、MMB、MME、POPE 等基准上评估 token 剪枝策略。
- **对比方法**：
  - **CogACT**（基线模型）：采用 Llama2-7B 语言模块、DINOv2+SigLIP 视觉编码器、DiT 动作头。
  - **Random Dropping**：随机保留 112 个视觉 token。
  - **FastV**：基于注意力分数的视觉 token 剪枝。
  - **VLA-Cache**：相邻时间步静态视觉 token 缓存。
  - **π0**（附录）：在 LIBERO 上对比。
- **主要实验**：在 SIMPLER 上对比不同层保留数（22/28 层）和 token 保留数（56/112）的多种配置，报告成功率、FLOPs、推理时间和加速比。

## 4. 资源与算力

- 文中明确提到：所有实验在 **NVIDIA A40 GPU** 上完成，推理时间测量为平均单步推理时长。未提及具体的 GPU 数量或训练时长（因为方法是免训练的），但未说明消融实验的总计算量。

## 5. 实验数量与充分性

- **实验数量**：较为充分。
  - SIMPLER 主实验结果（表2）：包含 8 种配置对比（不同 L 和 T），以及 3 种基线方法。
  - 扩展实验（表3）：在 CogACT-Small/Base/Large 三个规模上验证可扩展性。
  - 组件影响分析（表4）：分别改变 token 保留比例和缓存间隔。
  - 消融实验（表5）：逐步添加每个组件，验证协同效果。
  - 附录中补充了：
    - 视觉语言任务上的 token 剪枝实验（表6）。
    - LIBERO 上的泛化实验（表7）。
- **充分性与公平性**：
  - 实验对比了多种代表性方法（随机、FastV、VLA-Cache），且设置了相同实验条件。
  - 消融设计合理，逐步显示每个组件的贡献，并证明协同效果优于单独使用。
  - 可扩展性实验覆盖不同模型大小，证明方法不局限于单一模型。
  - 但未在更多开源扩散 VLA 模型（如 π0 不同变体）上详测，作者在局限中已指出这一点。

## 6. 论文的主要结论与发现

- EfficientVLA 在 CogACT 上实现 **1.93× 推理加速**，FLOPs 降至原来的 **28.9%**，平均成功率仅下降 **0.6%**。
- **语言层剪枝**在保留高层语义的同时，显著降低了内存瓶颈（表5显示压缩后速度提升）。
- **视觉 token 剪枝**策略（任务相关 + 多样性）远优于随机剪枝（随机保留 112 token 成功率仅 20.9%，而 EfficientVLA 保留 56 token 可达 75.5%）。
- **动作头缓存**机制有效降低迭代计算量，缓存间隔增大可进一步加速但影响略有增大。
- **协同效果**：单独优化某一模块加速有限（如纯视觉 token 剪枝仅 1.23×），而三者结合达到接近 2× 加速，且性能几乎无损。
- 方法在**不同模型规模**上均有效，且在大模型上加速效果更显著（Large 模型 2.0× 加速）。
- 该框架是**免训练**的，可直接应用于预训练 VLA 模型，无需额外数据和计算。

## 7. 优点

- **系统性**：首次提出覆盖语言、视觉、动作三个模块的协同加速方案，而非单独优化。
- **免训练**：所有策略均基于推理时的冗余分析，无需重新训练或微调，实用性强。
- **高效且性能损失小**：在 1.93× 加速下，成功率仅下降 0.6%，部分配置甚至提升（如 pick coke can 任务从 91.3% 提升至 94.0%）。
- **直观可解释**：利用余弦相似度衡量冗余，方法透明；剪枝和缓存策略有明确的冗余分析支撑。
- **实验设计全面**：涵盖不同配置、消融、可扩展性、多基准验证，对比方法合理。
- **代码开源**：提供 GitHub 链接，便于复现。

## 8. 不足与局限

- **测试模型有限**：由于开源扩散 VLA 模型不多，主要验证在 CogACT 上，虽在 π0 上做了 LIBERO 实验，但泛化性仍需更多模型验证。
- **固定缓存间隔**：动作头缓存采用固定 N 步，未考虑自适应策略，可能在某些任务下造成质量损失。
- **未与训练感知方法比较**：如 TinyVLA、DeeR-VLA 等需要微调的方法在极致压缩下可能更优，文中未对比。
- **缺乏真实机器人实验**：所有评估仅限仿真环境，实际硬件上的延迟和噪声可能影响结果。
- **统计显著性未报告**：结果来自单次运行，未提供误差棒或多重复实验。
- **内存与延迟分离分析不足**：虽提到内存瓶颈，但未给出具体显存占用对比。

（完）
