---
title: Distilling LLM Prior to Flow Model for Generalizable Agent’s Imagination in Object Goal Navigation
title_zh: 将大语言模型先验蒸馏到流程模型以实现物体目标导航中智能体的可泛化想象
authors: "Badi Li, Ren-Jie Lu, Yu Zhou, Jingke Meng, Wei-Shi Zheng"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=W0sqoTL7rL"
tags: ["query:wm-vla-sa"]
score: 6.0
evidence: 用于物体目标导航的世界模型，生成式想象
tldr: 该论文针对物体目标导航中未知环境泛化难的问题，提出生成式流程框架GOAL。GOAL通过将大语言模型的先验知识蒸馏为二维高斯场注入语义地图，利用流程模型建模室内环境语义分布。该方法在多个导航基准上超越现有确定性方法，提升了智能体在未见环境中的想象与导航能力，展示了世界模型在具身导航中的应用价值。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-w0sqotl7rl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1312, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w0sqotl7rl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1458, \"height\": 830, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w0sqotl7rl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1439, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w0sqotl7rl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 558, \"height\": 224, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w0sqotl7rl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1475, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w0sqotl7rl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 640, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w0sqotl7rl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1435, \"height\": 1157, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w0sqotl7rl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1127, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w0sqotl7rl/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1123, \"height\": 1213, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w0sqotl7rl/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1339, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-w0sqotl7rl/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1126, \"height\": 1246, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-w0sqotl7rl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1239, \"height\": 490, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w0sqotl7rl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 644, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w0sqotl7rl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1455, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w0sqotl7rl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 712, \"height\": 431, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w0sqotl7rl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 764, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w0sqotl7rl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1405, \"height\": 727, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w0sqotl7rl/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1403, \"height\": 422, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-w0sqotl7rl/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 577, \"height\": 305, \"label\": \"Table\"}]"
motivation: 现有物体目标导航方法依赖确定性模型，无法处理室内布局不确定性，泛化能力有限。
method: 提出生成式流程框架GOAL，使用大语言模型的空间先验并通过二维高斯场蒸馏到语义地图生成中。
result: 在多种未知环境中成功导航至目标物体，泛化性能显著优于现有方法。
conclusion: 将大语言模型先验与生成式流程结合可有效提升导航智能体的环境想象与泛化能力。
---

## Abstract
The Object Goal Navigation (ObjectNav) task challenges agents to locate a specified object in an unseen environment by imagining unobserved regions of the scene. Prior approaches rely on deterministic and discriminative models to complete semantic maps, overlooking the inherent uncertainty in indoor layouts and limiting their ability to generalize to unseen environments. In this work, we propose GOAL, a generative flow-based framework that models the semantic distribution of indoor environments by bridging observed regions with LLM-enriched full-scene semantic maps. During training, spatial priors inferred from large language models (LLMs) are encoded as two-dimensional Gaussian fields and injected into target maps, distilling rich contextual knowledge into the flow model and enabling more generalizable completions. Extensive experiments demonstrate that GOAL achieves state-of-the-art performance on MP3D and Gibson, and shows strong generalization in transfer settings to HM3D.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **任务定义**：物体目标导航（ObjectNav）要求智能体在未知环境中仅依靠视觉观测，找到用户指定的目标物体实例。
- **现有局限**：已有方法大多使用确定性和判别性模型（如基于 ViT 的掩码自编码器等）完成语义地图的补全，但忽视了室内布局固有的不确定性。确定性模型将输入直接映射为固定输出，导致在未见环境上泛化能力有限。
- **核心洞察**：语义地图补全本质上是多模态的——相同的局部地图可能对应多种合理的全局布局。因此，论文将任务建模为**概率生成问题**，利用流匹配（Flow Matching）生成式模型学习室内场景的语义分布。
- **研究意义**：通过引入大语言模型（LLM）的外部常识知识作为训练监督，增强模型对物体共现和空间上下文的理解，从而提升智能体在未知环境中的想象与导航能力，展示了生成式世界模型在具身导航中的价值。

## 2. 方法论：核心思想、关键技术细节

- **整体框架（GOAL）**：生成式流框架，由三部分组成：
  - **基于 3D 场景理解的语义地图构建**：将多帧 RGB-D 观测融合为点云，用稀疏卷积网络（Sparse UNet）进行联合 3D 语义分割，再投影为鸟瞰语义地图。
  - **从 LLM 中提取空间上下文先验**：通过层级提示（角色设定、链式推理、少样本示例）让 LLM 输出常见物体对之间的距离及置信度，得到距离矩阵 D 和置信度矩阵 C。
  - **构造数据依赖耦合（data-dependent coupling）的训练样本**：利用 LLM 先验构建二维高斯场，叠加到完整语义地图上作为目标分布 X1，与带噪声的局部观测地图 X0 构成配对，通过线性插值训练流匹配模型。
- **关键技术细节**：
  - **LLM 先验构建**：对每个观测到的物体 o_i，根据距离阈值 τ_d 和置信度阈值 τ_c 抽取共现候选集合 N(o_i)，随机采样共现物体 o_j，将其中心置于从 o_i 到最近前沿的连线上，偏移距离 d_ij，并用置信度转换为高斯标准差。最终所有高斯分布叠加得到 LLM 先验 p_LLM。
  - **数据依赖耦合**：源地图 X0 = γ ⊙ X′ + γ̅ ⊙ N(0, Δσ²)；目标地图 X1 = λ γ̅ ⊙ p_LLM + X′。其中 γ 是可见区域掩码，X′ 是完整真实地图。耦合使得 X0 和 X1 共享相同的地图和掩码，简化模型架构（无需交叉注意力等额外条件机制）。
  - **训练目标**：条件流匹配损失 L_FM = E[||Ẋ_t - u_θ(X_t, t)||²]，其中 Ẋ_t = X1 - X0，线性插值 X_t = (1-t)X0 + tX1。
  - **导航策略**：由生成地图选出目标通道中概率最高的网格作为长期航点，使用快速行进法（FMM）进行局部规划。航点更新采用自适应策略（离旧航点太近或太远时才更新），减少计算开销。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：
  - **Gibson**：tiny-split 协议，25 训练场景 + 5 验证场景，1000 个验证 episode，6 个目标类别。
  - **MP3D**：标准 Habitat 设置，56 训练场景 + 11 验证场景，2195 个验证 episode，21 个目标类别。
  - **HM3D**：仅 20 验证场景，2000 个 episode，6 个目标类别，用于**零样本迁移实验**（在 MP3D 上训练，直接评估 HM3D）。
- **基准指标**：SR（成功率）、SPL（路径加权的成功率）、DTS（结束时到目标的距离）。
- **对比方法**：包括 SemExp、SSC-Nav、PONI、L2M、Stubborn、CoW、3DAware、T-Diff、L3MVN、SG-Nav、UniGoal、SGM 等。其中 SGM（CVPR 2024）为最相关的最先进方法，也使用了 LLM。
- **对比设置**：将方法分为“训练时使用 LLM”和“推理时使用 LLM”等类别，GOAL 仅在训练时使用 LLM（蒸馏），推理时无需 API 调用，降低延迟。

## 4. 资源与算力

- **训练**：GOAL 生成模型基于 DiT-B，使用 4× NVIDIA RTX 4090 GPU，batch size 64/GPU，训练 25 个 epoch，优化器 AdamW，学习率 1.5e-4，余弦退火。训练时从每个数据集采样 40 万个子地图。
- **场景分割模型**：使用 2× NVIDIA RTX 4090 GPU，batch size 64，SGD 优化器。
- **推理**：每个 episode 多次调用流模型，平均 FPS 1.2~1.8（6 线程并行），相比 PONI 的 1.5~3.5 略慢，但 SR 提升超 30%。
- **内存**：6 线程并行约 22GB VRAM（含点云），比 PONI 的约 20GB 多约 350MB/线程。

## 5. 实验数量与充分性

- **实验组数**：约 6~8 组主要实验：
  - 主表（表 6）在 Gibson 和 MP3D 上与 12 种方法对比。
  - 迁移实验（表 1）在 HM3D 上与 6 种方法对比，含 GOAL w/o LLM 消融。
  - 数据依赖耦合 vs 独立耦合对比（表 2）。
  - 消融实验（表 3）：场景分割和 LLM 先验的效果。
  - 流匹配 vs 掩码自编码器对比（表 5）。
  - 不同 LLM 变体（ChatGLM、DeepSeek、ChatGPT）和模型规模（DiT-B/L）对比（表 4）。
  - 超参数调优（附录 D.1，图 5、图 6）。
  - 多随机种子评估（附录 D.2，5 个种子，标准偏差 ±0.4%）。
- **充分性评估**：
  - **公平性**：与 SGM 对比时，明确替换了场景分割模块，使用与 SGM 相同的 RedNet 进行公平比较（表 5）。所有对比结果来自原始论文或官方代码复现。
  - **客观性**：消融实验充分验证了各组件贡献；迁移实验证明了泛化能力；不同 LLM 和模型尺寸实验显示相对鲁棒。
  - **不足**：部分基线（如 L3MVN、SG-Nav）使用 LLM 推理，但与 GOAL 训练时使用 LLM 的设置不同，对比不够完全公平；点云存储和推理速度没在所有方法上统一对比。

## 6. 主要结论与发现

- GOAL 在 MP3D 和 Gibson 上均取得 SOTA 结果（SR 41.7% / 83.5%），分别超越 SGM 约 4 个点和 5.5 个点。
- 在 HM3D 零样本迁移实验中，GOAL 达到 48.8% SR，显著优于直接训练在 HM3D 上的方法，证明强泛化能力。
- 数据依赖耦合相比独立高斯耦合（需交叉注意力）在简化架构的同时提升性能（SR 从 39.0% 到 41.5%）。
- 场景分割模块和 LLM 先验均贡献显著，且 LLM 先验在高性能基线上仍有额外提升。
- 流匹配比掩码自编码器在迁移设置下更好。
- 不同 LLM 表现相似，模型增大（DiT-B→L）反而可能过拟合，表明数据量和多样性仍是瓶颈。

## 7. 优点

- **方法创新**：首次将流匹配生成模型引入 ObjectNav，并利用 LLM 先验通过蒸馏方式（而非推理时使用）增强泛化，平衡了性能与效率。
- **生成式建模**：明确承认语义地图补全的固有不确定性，通过概率生成提升鲁棒性。
- **高效架构**：数据依赖耦合避免了额外条件机制（交叉注意力），减少计算开销，适合导航中多次推理的需求。
- **强实验验证**：在三大数据集上评估，包含零样本迁移、多种子误差分析、与多种 LLM 和模型尺寸对比，实验设计全面。
- **实用考虑**：LLM 仅用于训练，推理无 API 依赖，可作为即插即用模块。

## 8. 不足与局限

- **固定语义类别**：方法基于预定义物体类别通道，无法直接处理开放词汇或零样本新类别。
- **模拟可见区域偏差**：训练时使用矩形前沿路径模拟可见区域，而实际观测区域为扇形（图 4），导致分布不匹配，影响性能。
- **采样效率**：流模型使用 Euler 积分（96 步），推理速度较慢（1.2~1.8 FPS），未应用最新的蒸馏或一致性模型技术。
- **评估数据集规模有限**：当前基准场景数量和多样性有限，可能导致不同 LLM 的性能差异无法体现，且过拟合风险存在。
- **策略限制**：自适应航点更新策略使智能体难以快速纠正错误预测，导致路径效率（SPL）提升较小。
- **计算与内存开销**：点云表示占用额外内存，且多个推理线程并行时开销增加。

（完）
