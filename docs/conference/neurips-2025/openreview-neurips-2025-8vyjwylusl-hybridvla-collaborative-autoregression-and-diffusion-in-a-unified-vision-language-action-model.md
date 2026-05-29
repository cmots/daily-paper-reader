---
title: "HybridVLA: Collaborative Autoregression and Diffusion in a Unified Vision-Language-Action Model"
title_zh: HybridVLA：统一视觉-语言-动作模型中的协作自回归与扩散
authors: "Jiaming Liu, Hao Chen, Pengju An, Zhuoyang Liu, Renrui Zhang, Chenyang Gu, Xiaoqi Li, Ziyu Guo, Sixiang Chen, Mengzhen Liu, Chengkai Hou, Mengdi Zhao, KC alex Zhou, Pheng-Ann Heng, Shanghang Zhang"
date: 2025-05-10
pdf: "https://openreview.net/pdf?id=8VyjwyLuSl"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 混合自回归与扩散的视觉-语言-动作模型
tldr: 现有自回归VLA模型将动作离散化，损失连续性；扩散VLA模型未充分利用VLM推理能力。本文提出HybridVLA，在统一VLA模型中协作自回归与扩散，同时利用VLM推理和连续动作控制，提升机器人操作精度和泛化性。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-8vyjwylusl/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8vyjwylusl/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1427, \"height\": 699, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8vyjwylusl/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 732, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8vyjwylusl/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1450, \"height\": 657, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8vyjwylusl/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1410, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8vyjwylusl/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 661, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8vyjwylusl/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1395, \"height\": 781, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8vyjwylusl/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1398, \"height\": 790, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-8vyjwylusl/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 734, \"height\": 111, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8vyjwylusl/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1451, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8vyjwylusl/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 714, \"height\": 272, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8vyjwylusl/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 710, \"height\": 377, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8vyjwylusl/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 730, \"height\": 1478, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8vyjwylusl/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1449, \"height\": 159, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8vyjwylusl/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 638, \"height\": 131, \"label\": \"Table\"}]"
motivation: 自回归VLA离散化动作损失连续性，扩散VLA未充分使用VLM推理能力，需要两者结合。
method: 设计统一VLA架构，协作自回归预测离散动作token和扩散生成连续动作。
result: 在多个机器人操作基准上，HybridVLA实现了更高的控制精度和泛化能力。
conclusion: 自回归与扩散的协作可以兼顾VLM推理与连续控制，是VLA模型的有效设计。
---

## Abstract
A fundamental objective of manipulation policy design is to endow robots to comprehend human instructions, reason about scene cues, and execute generalized actions in dynamic environments. Recent autoregressive vision-language-action (VLA) methods inherit common-sense reasoning capabilities from vision-language models (VLMs) for next action-token prediction. However, these methods quantize actions into discrete bins, which disrupts the continuity required for precise control. In contrast, existing diffusion-based VLA methods incorporate an additional diffusion head to predict continuous actions solely conditioned on feature representations extracted by the VLM, without fully leveraging the VLM’s pretrained reasoning capabilities through token-level generation. To address these limitations, we introduce HybridVLA, a unified framework that absorbs the continuous nature of diffusion-based actions and the contextual reasoning of autoregression within a single large language model. To mitigate interference between the two generation paradigms, we propose a collaborative training recipe that seamlessly incorporates diffusion denoising into the next-token prediction process. With this recipe, we find these two action prediction methods not only reinforce each other but also exhibit varying strength across different tasks. Therefore, we design a collaborative action ensemble mechanism that adaptively fuses both predictions, leading to more robust control. HybridVLA outperforms previous state-of-the-art VLA methods by 14\% and 19\% in mean success rate on simulation and real-world tasks, respectively, while demonstrating stable manipulation in unseen configurations.

---

## 论文详细总结（自动生成）

# HybridVLA 中文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

近年来，视觉-语言-动作（VLA）模型成为机器人操作领域的研究热点。现有方法主要分为两类：
- **自回归 VLA 方法**（如 RT-2、OpenVLA）：继承 VLM 的常识推理能力，通过下一个动作 token 预测来生成动作。但这类方法将连续动作量化成离散 bin，破坏了动作的连续性，限制了精确控制。
- **扩散 VLA 方法**（如 π0、CogACT）：在 VLM 后附加一个独立的扩散头，预测连续动作。然而扩散头仅以 VLM 提取的全局特征为条件，未充分利用 VLM 通过 token 级生成（next-token prediction）获得的预训练推理能力。

核心问题：**如何在一个统一的 VLA 框架内优雅地融合自回归的上下文推理优势和扩散的连续动作表达能力，而非简单拼接？**

HybridVLA 提出在单个大型语言模型（LLM）内同时集成扩散动作生成和自回归动作生成，使两种范式相互增强，实现更鲁棒的操作控制。

## 2. 论文提出的方法论

### 核心思想
- 在同一个 LLM 骨干网络中，将扩散去噪过程嵌入到下一个 token 预测流程中，同时支持连续动作（扩散）和离散动作（自回归）的生成。
- 通过协作训练策略（Collaborative Training Recipe）和协作动作集成机制（Collaborative Action Ensemble），让两种方法相互增强，并根据置信度自适应融合输出。

### 关键技术细节

#### 模型架构
- **视觉编码器**：使用 DINOv2 和 SigLIP（7B 版本），特征拼接后经投影层输入 LLM；2.7B 版本仅使用 CLIP。
- **LLM**：采用 LLaMA-2（7B）或 Phi-2（2.7B）。
- **Token 序列设计**：将多模态输入（视觉、语言、机器人状态）、扩散噪声 token、自回归动作 token 组织成统一序列，用特殊标记 `<BOD>` 和 `<EOD>` 分隔扩散与自回归部分。
  - 扩散 token 放在自回归 token 之前，避免信息泄漏（因为自回归训练时使用真实动作，若放在扩散之前会泄漏条件）。
  - 机器人状态通过可学习 MLP 映射为连续嵌入，保持连续性。

#### 协作训练策略
- **混合目标函数**：`L_hybrid = L_diff + L_ce`
  - L_diff：扩散噪声预测的 MSE 损失。
  - L_ce：自回归离散输出的交叉熵损失。
  - 两个损失共同反向传播，共享 LLM 骨干，使模型同时吸收连续动作表示和语义推理表示。
- **训练阶段**：
  1. 大规模预训练：在 35 个开源机器人数据集（Open X-Embodiment、DROID、ROBOMIND 等，共 760K 轨迹、33M 帧）上训练 5 epoch。
  2. 下游微调：在自收集的仿真或真实数据上微调。

#### 推理与协作动作集成
- **扩散动作**：使用 DDIM 采样，仅需 4 步去噪，引入 KV cache 加速。
- **自回归动作**：在 `<EOD>` 后生成离散动作 token，并计算平均置信度。
- **集成规则**：若自回归 token 平均置信度 ≥ 0.96，则取扩散动作与自回归动作的均值；否则仅使用扩散动作。该设计基于观察：不同任务中两种方法各有优势（扩散擅长精确操作，自回归擅长语义推理）。

## 3. 实验设计

### 仿真实验
- **Benchmark**：RLBench（CoppeliaSim 模拟器），10 个桌面任务（Close box、Close laptop、Toilet seat down、Sweep to dustpan、Close fridge、Phone on base、Take umbrella out、Frame off hanger、Wine at rack、Water plants）。
- **数据**：每个任务 100 条轨迹，基于预定义路径点和 OMPL 运动规划器收集。
- **对比方法**：
  - 自回归：ManipLLM (7B)、OpenVLA (7B)
  - 扩散：π0 (2.6B)、CogACT (7B)
  - 本方法：HybridVLA (7B)、HybridVLA (2.7B)、HybridVLA-dif (7B，仅使用扩散）
- **评估**：每个任务 20 次 rollout，重复 3 次取平均成功率及方差。

### 真实世界实验
- **单臂机器人**：Franka Research 3，两个 RGB 相机（前视 + 腕部），5 个任务（Pick and place、Unplug charger、Open drawer and place inside、Pour water、Wipe blackboard），每任务 100 条遥操作数据。
- **双臂机器人**：AgileX 双臂机器人，三个相机（外部 + 左/右腕），5 个任务（Pick and place、Lift ball and place、Place bottles at rack、Wipe blackboard、Fold shorts），每任务 100 条遥操作数据。
- **对比方法**：π0、CogACT（仅单臂）。
- **评估**：20 次 rollout，成功由人工判定。

### 泛化实验
在单臂 Pick and place 上与 CogACT 对比，在双臂 Lift ball and place 上与 π0 对比，测试四种未见场景：新物体、杂乱背景、不同高度、不同光照。

## 4. 资源与算力

论文明确指出：
- **预训练**：使用 35 个数据集、760K 轨迹、33M 帧，花费超过 **10,000 A800 GPU 小时**。
- **微调**：在 8 张 NVIDIA A800 GPU 上使用混合精度训练，学习率 2e-5，优化器 AdamW，300 epoch。
- **推理速度**：HybridVLA-dif (7B) 可达 9.4 Hz，HybridVLA (2.7B) 达 12.3 Hz，HybridVLA (7B) 为 6.1 Hz（使用 bfloat16，未采用动作分块）。

## 5. 实验数量与充分性

### 实验数量
- **仿真**：10 个 RLBench 任务 × 多种方法（7 种配置）→ 约 70 组结果，含方差。
- **真实世界**：单臂 5 任务 + 双臂 5 任务 × 4 种方法 → 约 40 组结果。
- **消融实验**：
  - 协作训练策略效果（Ex1 vs Ex2, Ex3 vs Ex4）
  - 大规模预训练（Ex5 vs Ex0）
  - 机器人状态嵌入（Ex6 vs Ex1）
  - 置信度阈值（0.90~0.98）
  - KV cache 影响（9.4 Hz vs 5.0 Hz）
  - 去噪步数（4 步即可，无显著性能下降）
  - Token 序列设计（Type1~4 对比）
- **泛化实验**：4 种场景 × 2 组对比（单臂 + 双臂）。

### 充分性评价
- **客观公平**：对比方法均加载官方预训练参数并遵循各自训练设置；仿真采用固定 rollout 次数和方差报告；真实世界人工判定成功。
- **充分性**：消融实验覆盖了所有关键组件（协作训练、预训练、状态输入、集成阈值、推理加速、去噪步数、序列设计），实验设计较为系统。但存在部分局限（见不足部分）。

## 6. 论文的主要结论与发现

1. **HybridVLA (7B) 在 RLBench 上平均成功率 74%**，比 SOTA 自回归方法（OpenVLA）高 33%，比 SOTA 扩散方法（CogACT）高 14%。
2. **HybridVLA-dif (7B) 也优于 π0 和 CogACT**（分别高 11% 和 6%），证明将扩散集成到下一个 token 预测中更充分利用了 VLM 预训练知识。
3. **HybridVLA (2.7B) 性能良好（58%）**，验证了方法在不同模型规模上的有效性。
4. **真实世界实验**：单臂平均成功率 83%，双臂平均成功率 71%，均显著优于对比方法。
5. **泛化能力**：在四种未见场景下性能下降最小，表明协作设计的鲁棒性。
6. **协作训练使两种方法相互增强**：单独训练仅扩散（Ex2）60%，仅自回归（Ex4）57%，而联合训练后分别提升至 66% 和 62%。
7. **置信度引导的集成策略有效**：阈值设为 0.96 时最佳（74%），低于此值因自回归不可靠导致性能下降，高于此值因可用样本过少。

## 7. 优点

- **创新性**：首次在单个 LLM 中同时嵌入扩散和自回归动作生成，通过精巧的 token 序列设计和混合目标实现协同，而非简单拼接。
- **技术完整度高**：从架构设计、训练策略、推理加速到集成机制均有详细方案，消融实验全面。
- **实验规模大**：760K 轨迹跨本体预训练，仿真 + 真实世界（单臂/双臂）多场景验证，泛化实验系统。
- **性能显著**：在多个基准上实现 SOTA，且推理速度可与现有方法匹敌（HybridVLA-dif 9.4 Hz）。
- **可扩展性**：支持 2.7B 小模型，适合资源受限场景。

## 8. 不足与局限

- **推理速度受限**：完整 HybridVLA (7B) 仅 6.1 Hz，低于 π0 (13.8 Hz)，主要由于自回归生成较慢。作者通过 HybridVLA-dif 缓解，但以丢弃自回归优势为代价。
- **未能报告统计显著性**：如误差条、置信区间等，仅给出均值 ± 方差，未对差异进行显著性检验。
- **真实世界对比不完全**：双臂实验仅与 π0 对比（因 CogACT 不支持多视图），且各方法训练配置可能差异较大（如是否使用相同数据集、训练步数等）。论文提到“加载官方预训练参数”，但下游微调数据是否一致未充分说明。
- **泛化实验的局限性**：仅测试两个典型任务（单臂 Pick and place、双臂 Lift ball and place），未在更多任务上验证泛化，结论外推需谨慎。
- **失败案例分析不足**：论文附录 D 简要列出三类失败，但未量化各失败类别占比，也未提出具体改进方案。
- **环境依赖性**：机器人状态嵌入仅实验了直接 MLP 映射，未探索其他融合方式；置信度阈值 0.96 是经验值，可能在不同场景下需重新调整。
- **计算资源需求高**：预训练需超过 1 万 A800 GPU 小时，对于普通研究团队复制难度较大。

（完）
