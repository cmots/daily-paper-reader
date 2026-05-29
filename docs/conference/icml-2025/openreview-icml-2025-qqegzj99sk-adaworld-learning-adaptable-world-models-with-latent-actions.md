---
title: "AdaWorld: Learning Adaptable World Models with Latent Actions"
title_zh: AdaWorld：学习可适应的世界模型与潜在动作
authors: "Shenyuan Gao, Siyuan Zhou, Yilun Du, Jun Zhang, Chuang Gan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=QQegZj99sk"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 用潜在动作学习可适应的世界模型
tldr: 该论文提出AdaWorld，通过自监督方式从视频中提取潜在动作，将动作信息融入世界模型预训练，使得模型能高效适应新环境。克服了传统世界模型依赖大量动作标注数据的局限，在多个域适应任务中取得领先性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 945, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 856, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 843, \"height\": 486, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1674, \"height\": 1705, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1745, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1753, \"height\": 728, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 851, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1566, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1757, \"height\": 717, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1742, \"height\": 902, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1549, \"height\": 676, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1738, \"height\": 2262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1740, \"height\": 2257, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1739, \"height\": 2250, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1741, \"height\": 2248, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1740, \"height\": 2248, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1302, \"height\": 1081, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1300, \"height\": 1079, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1301, \"height\": 1079, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1298, \"height\": 1078, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1748, \"height\": 1773, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 863, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1673, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1307, \"height\": 391, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1784, \"height\": 189, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 609, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 691, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1380, \"height\": 392, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1719, \"height\": 1574, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1700, \"height\": 184, \"label\": \"Table\"}]"
motivation: 现有世界模型难以适应新环境，需要大量带标签动作数据。
method: 自监督提取潜在动作，将动作信息融入预训练。
result: 在零样本和新环境适应中显著优于基线。
conclusion: 潜在动作使世界模型更具泛化性。
---

## Abstract
World models aim to learn action-controlled future prediction and have proven essential for the development of intelligent agents. However, most existing world models rely heavily on substantial action-labeled data and costly training, making it challenging to adapt to novel environments with heterogeneous actions through limited interactions. This limitation can hinder their applicability across broader domains. To overcome this limitation, we propose AdaWorld, an innovative world model learning approach that enables efficient adaptation. The key idea is to incorporate action information during the pretraining of world models. This is achieved by extracting latent actions from videos in a self-supervised manner, capturing the most critical transitions between frames. We then develop an autoregressive world model that conditions on these latent actions. This learning paradigm enables highly adaptable world models, facilitating efficient transfer and learning of new actions even with limited interactions and finetuning. Our comprehensive experiments across multiple environments demonstrate that AdaWorld achieves superior performance in both simulation quality and visual planning.

---

## 论文详细总结（自动生成）

# AdaWorld 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有世界模型（World Models）高度依赖大量带动作标签的数据和昂贵的训练成本，难以在仅有少量交互的情况下适应具有异构动作的新环境。这限制了它们在更广泛领域的应用。
- **研究动机**：人类能够通过有限经验估计不同动作的效果，这得益于从大量观察中学习的内部动作表示，这些表示可跨上下文复用。受此启发，论文希望在学习世界模型时融入动作信息，实现类似人类的适应性。
- **整体含义**：提出 AdaWorld，一种创新的可适应世界模型学习方法，通过自监督方式从视频中提取潜在动作（latent actions），并作为条件预训练世界模型，使得模型能高效迁移和习得新动作，仅需少量交互和微调。

## 2. 论文提出的方法论

### 核心思想
- 在**预训练阶段**就融入动作信息，而不仅仅是使用无动作视频。通过自监督提取的**连续潜在动作**作为统一条件，实现动作可控且可迁移的世界模型。

### 关键技术细节
- **潜在动作自编码器（Latent Action Autoencoder）**：
  - 基于Transformer架构，包含编码器和解码器。
  - 编码器从连续两帧 \(f_t, f_{t+1}\) 中提取紧凑的潜在动作 \(\tilde{a}\)（维度32），采用信息瓶颈（information bottleneck）设计，迫使模型只编码帧间最关键的动态变化，从而解耦动作与上下文。
  - 解码器根据前帧 \(f_t\) 和潜在动作 \(\tilde{a}\) 预测后帧 \(f_{t+1}\)。
  - 使用β-VAE目标函数：\(L = E_q[\log p(f_{t+1}|\tilde{a}, f_t)] - \beta D_{KL}(q||p)\)，其中β控制表达性与上下文解耦能力的权衡（默认 \(2 \times 10^{-4}\)）。
- **动作感知预训练（Action-Aware Pretraining）**：
  - 使用训练好的潜在动作编码器从无标签视频中提取潜在动作序列，作为世界模型的条件。
  - 世界模型基于**Stable Video Diffusion (SVD)** 初始化，采用扩散模型架构，每次只去噪一帧，并以历史帧（最多6帧，带噪声增强）和潜在动作作为条件。
  - 通过最小化扩散损失 \(L = E[ \|x_0 - \hat{x}_0(x_t, t, c)\|^2 ]\) 进行预训练。
- **高效适应性**：
  - **动作迁移**：给定一个演示视频，提取潜在动作序列，可无需训练直接在不同上下文中生成相同动作。
  - **世界模型适应**：收集少量交互数据（如每个动作100样本），用潜在动作编码器提取动作表示并平均，初始化专用世界模型的动作接口，微调少量步数（800-1000步）即可适应新环境。
  - 连续动作空间通过轻量MLP映射到潜在空间。

### 算法流程（文字说明）
1. 训练潜在动作自编码器：从大量无标签视频中学习提取上下文无关的潜在动作。
2. 使用该编码器从视频中提取潜在动作，作为额外条件，预训练基于扩散的世界模型（动作感知预训练）。
3. 适应新环境时：收集少量交互样本 → 提取潜在动作 → 初始化动作嵌入（离散动作取平均，连续动作用MLP映射）→ 微调模型（可选）。

## 3. 实验设计

### 数据集与场景
- **预训练数据集**：约20亿帧，来源包括：
  - Gym Retro（1016个2D游戏环境，自动生成1000M帧）
  - Procgen Benchmark（16个环境，自动生成144M帧）
  - Open X-Embodiment（机器人数据，170M帧）
  - Ego4D（人类活动，330M帧）
  - Something-Something v2（SSv2，7M帧）
  - MiraData（3D渲染和城市漫游，320M帧）
- **评估环境**（均未在预训练中出现）：
  - 离散动作：Habitat, Minecraft, DMLab
  - 连续动作：nuScenes（自动驾驶）
  - 动作迁移：LIBERO, SSv2
  - 视觉规划：Procgen（4个环境：Heist, Jumper, Maze, CaveFlyer），VP²基准（Robosuite, RoboDesk）

### 对比方法
- **Action-agnostic**：预训练时动作条件恒为零（无动作信息）。
- **Flow cond.**：用光流（UniMatch预测）作为动作条件。
- **Discrete cond.**：用VQ-VAE离散潜在动作（类似Genie，8个码本）。

### 评价指标
- 模拟质量：PSNR, LPIPS
- 动作迁移：FVD, ECS, 人工评估
- 视觉规划：成功率

## 4. 资源与算力
- 潜在动作自编码器：5亿参数，训练200K步，batch size 960，16块NVIDIA A100 GPU（论文未明确总GPU小时，但提及使用16块A100）。
- 世界模型（1.5B参数）：训练80K步，batch size 64，学习率5e-5，16块A100。采用余弦学习率调度，10K预热，EMA。
- 微调阶段：适应新环境时仅需800-1000步微调（batch 32），连续动作MLP训练3K步（不到30秒在单GPU上）。

## 5. 实验数量与充分性
- **主要实验组数**：
  - 动作迁移：2个数据集（LIBERO, SSv2），每个含1300对视频，自动指标+人类评价（各50对）。
  - 模拟质量：4个环境（3离散+1连续），每环境300验证样本。
  - 视觉规划：4个Procgen环境×30场景（共120场景），5个随机种子；外加VP²基准（6个机器人任务×100个表头任务+7个RoboDesk任务）。
  - 消融实验：数据多样性（3种组合），接口初始化（随机vs初始化），超参数β（2个值），方法通用性（iVideoGPT），动作创建（9种聚类数）。
- **充分性评价**：实验覆盖了动作迁移、适应效率、规划能力、消融分析等，对比多种基线，统计报告带标准误差，结果客观。公平性方面：所有方法对比时使用相同的训练步数（50K）和架构，仅改变动作条件。结论可信。

## 6. 论文的主要结论与发现
1. **动作感知预训练显著提升适应性**：AdaWorld在动作迁移（FVD降低约50%，人工判断成功率70%+）、新环境适应（PSNR提升2-3dB）和视觉规划（成功率提升2-3倍）上均大幅优于无动作预训练基线。
2. **连续潜在动作优于离散**：相比离散动作（Genie风格），连续潜在动作更细腻，转移效果更好。
3. **数据多样性有益**：增加真实机器人视频（OpenX）有助于提升对未见2D游戏的泛化。
4. **方法具有通用性**：将动作感知预训练应用于iVideoGPT也能显著提升其适应性。
5. **低样本高效适应**：仅需100个动作样本、几百步微调即可达到较好效果，无需大量标注数据。

## 7. 优点
- **创新性**：提出“动作感知预训练”概念，通过自监督潜在动作统一不同环境动作表示，解决传统世界模型适应难的痛点。
- **实用性**：支持无训练动作迁移、少量样本微调、动作组合与创建，具有强实际部署潜力。
- **实验全面**：覆盖多种域（游戏、机器人、自动驾驶）、多种任务（模拟、规划、迁移），消融充分。
- **开源/可复现**：提供了项目页面。

## 8. 不足与局限
- **推理速度**：文中自述未达到实时频率（扩散模型较慢），未来需蒸馏或加速。
- **长程生成退化**：滚动超出初始场景时可能产生伪影或漂移；难以实现超长程生成。
- **物理理解不完美**：在复杂物理世界或剧烈视角变化下可能出现失败案例（论文附录C有展示）。
- **预训练数据依赖**：虽然利用了自动生成，但游戏环境仍需手动收集ROM，且数据质量影响泛化。
- **潜在动作解耦局限**：超参数β需要权衡，过小则丢失上下文解耦，过大则表达力不足。
- **未深入探讨与强化学习结合**：只展示了简单MPC规划，未在复杂RL任务中验证。

（完）
