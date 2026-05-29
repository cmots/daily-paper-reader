---
title: Learning World Models for Interactive Video Generation
title_zh: 面向交互式视频生成的学习世界模型
authors: "Taiye Chen, Xun Hu, Zihan Ding, Chi Jin"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=FzfYoUp8F1"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 面向交互式视频生成的世界模型，结合VRAG
tldr: 针对长视频生成中累积误差和记忆不足问题，本文通过动作条件化和自回归框架赋予图像到视频模型交互能力，并提出视频检索增强生成（VRAG）显式全局状态条件，显著降低长期漂移，使世界模型更适用于规划和决策。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-fzfyoup8f1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 726, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fzfyoup8f1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 656, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fzfyoup8f1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 807, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fzfyoup8f1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1015, \"height\": 829, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fzfyoup8f1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 720, \"height\": 325, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fzfyoup8f1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1016, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fzfyoup8f1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 697, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fzfyoup8f1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 870, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fzfyoup8f1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 611, \"height\": 277, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fzfyoup8f1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1163, \"height\": 647, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fzfyoup8f1/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1147, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fzfyoup8f1/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1150, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fzfyoup8f1/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1149, \"height\": 521, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fzfyoup8f1/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1161, \"height\": 522, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fzfyoup8f1/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1135, \"height\": 727, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fzfyoup8f1/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1310, \"height\": 418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fzfyoup8f1/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1312, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fzfyoup8f1/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1313, \"height\": 418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fzfyoup8f1/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1315, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-fzfyoup8f1/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1317, \"height\": 415, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-fzfyoup8f1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 713, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fzfyoup8f1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1050, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fzfyoup8f1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 463, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fzfyoup8f1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 409, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fzfyoup8f1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 800, \"height\": 186, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fzfyoup8f1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 860, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fzfyoup8f1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 942, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-fzfyoup8f1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 844, \"height\": 182, \"label\": \"Table\"}]"
motivation: 现有视频生成模型缺乏交互性且存在累积误差和记忆不足，无法作为世界模型用于规划。
method: 在图像到视频模型上加入动作条件，使用自回归框架和VRAG进行全局状态检索增强。
result: VRAG显著降低了长期生成的不一致性，在多个任务上提升了世界模型的预测准确性。
conclusion: 该方法推进了交互式世界模型的发展，可用于机器人规划和模拟。
---

## Abstract
Foundational world models must be both interactive and preserve spatialtemporal coherence to enable effective future planning with different action choices. However, present models for long video generation have limited inherent world modeling capabilities due to two main challenges: compounding errors and insufficient memory mechanisms. 
We enhance image-to-video models with interactive capabilities through additional action conditioning and autoregressive framework, and reveal that compounding error is inherently irreducible in autoregressive video generation, while insufficient memory mechanism leads to incoherence of world models. We propose video retrieval augmented generation (VRAG) with explicit global state conditioning, which significantly reduces long-term compounding errors and increases spatialtemporal consistency of video world models. 
In contrast, naive autoregressive generation with extended context windows and retrieval-augmented generation prove less effective for video generation, primarily due to the limited in-context learning capabilities of current video models. Our work illuminates the fundamental challenges in video world models and establishes a comprehensive benchmark for improving video generation models with internal world modeling capabilities.

---

## 论文详细总结（自动生成）

# 论文总结：Learning World Models for Interactive Video Generation

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：构建基础世界模型需要同时具备**交互性**（能够根据不同的动作选择进行未来预测）和**时空一致性**（长时间保持视觉和动态连贯性）。然而，现有长视频生成模型在作为世界模型时面临两大关键挑战：
  - **累积误差**：自回归生成中小误差随时间累积，导致预测严重偏离合理未来。
  - **记忆机制不足**：模型无法维持长期的对象身份、空间布局和世界状态，导致生成不一致。
- **研究背景**：视频扩散模型（如 Sora、Genie）展现了作为世界模拟器的潜力，但长视频自回归生成中的这两个问题常常相互加剧，阻碍了连贯世界模型的构建。类似 LLM 中的长上下文和检索增强生成（RAG）技术直接迁移到视频领域效果有限，因为当前视频模型的 in-context learning 能力较弱。

## 2. 提出的方法论：核心思想、关键技术细节

- **核心思想**：在图像到视频模型（Diffusion Transformer）上增加**动作条件化**和**自回归框架**以赋予交互能力，并提出**视频检索增强生成（VRAG）**，通过显式全局状态条件来显著降低长期累积误差并提升时空一致性。
- **关键技术细节**：
  1. **动作条件化**：采用自适应层归一化（AdaLN），将动作序列嵌入并调制各归一化层的缩放和平移参数。
  2. **自回归视频生成**：采用 Diffusion Forcing 技术，在训练时对每帧随机加入噪声，迫使模型对条件帧的噪声鲁棒；推理时逐帧（或逐块）生成。
  3. **VRAG（视频检索增强生成）**：
     - **全局状态条件**：将当前世界坐标（x, y, z, yaw）作为额外条件信号，通过 AdaLN 注入模型。
     - **记忆检索**：维护一个历史帧缓冲区，基于全局状态相似度检索最相关的历史帧，作为上下文与当前帧拼接。
     - **训练改进**：
       - 对检索帧增加时间偏移（RoPE 偏移），区分历史帧与当前帧。
       - 对检索帧施加更低的噪声水平，模拟推理时的不完美历史帧。
       - 在损失函数中只对当前帧计算扩散损失，对检索帧屏蔽损失（masked loss）。
       - 检索帧仅使用全局状态条件，不依赖动作序列，避免动作伪影。
     - 训练目标：`L_VRAG = E[||ε_t - ε_θ(˜z_˜t, ˜t, ˜a, ˜s)||² ⊙ m]`，其中 m 对检索帧为 0，对当前帧为 1。
  4. **对比基线**：还实现了三种来自 LLM 的长上下文扩展方法作为对比：
     - **YaRN**：对 RoPE 进行频率变换扩展上下文窗口（拉伸因子 4），微调后推理使用 40 帧窗口。
     - **历史帧检索缓冲区**：按指数衰减分段采样历史帧，与当前帧拼接。
     - **神经记忆注意力**：基于 Infini-Attention 的压缩记忆机制，存储和检索隐藏状态。

## 3. 实验设计：数据集 / 场景、Benchmark、对比方法

- **数据集**：
  - **训练**：使用 MineRL 收集 1000 段 Minecraft 长视频（共 17 小时），分辨率 640×360，每段 1200 帧，带有动作向量（移动、跳跃、视角旋转）和世界坐标（x, y, z, yaw）。
  - **测试集**：
    - 累积误差评估：20 段 1200 帧长视频，随机动作和位置。
    - 世界一致性评估：60 段精心设计的 300 帧序列，包含原地旋转、方向反转、圆形轨迹等受控运动模式。前 100 帧作为初始化缓存。
- **基准（Benchmark）**：模型自回归逐帧生成（步长 1），与 ground truth 对比：
  - 指标：SSIM（结构相似性）、PSNR（峰值信噪比）、LPIPS（学习感知图像块相似度），以及 VBench 五项视频质量指标（背景一致性、时间闪烁、运动平滑度、美学质量、成像质量）。
- **对比方法**：
  - Diffusion Forcing (DF) 窗口大小 10 和 20。
  - YaRN（窗口 40，fine-tune 后）。
  - History Buffer（历史帧检索，无 in-context 训练）。
  - Neural Memory（Infini-Attention）。
  - Frame Pack（压缩历史帧上下文）。
  - **VRAG**（本文方法，10 个检索帧 + 10 个当前帧）。
  - 消融变体：VRAG（无记忆）、VRAG（无训练）、VRAG（预测姿态）。

## 4. 资源与算力

- 论文明确说明：所有模型在 **8×A100 GPU** 上训练，批量大小 32，训练 3 个 epoch。
- 更细的细节：DiT 隐藏维度 1024，深度 16，学习率 8×10⁻⁵。YaRN 微调 10⁴ 步。VRAG 仅需要额外检索计算（CPU 上完成，内存仅 9.4 KB），推理时间与 DF20 相近（12 分钟/600 帧）。

## 5. 实验数量与充分性

- **实验组数**：
  - 世界一致性评估：7 种方法（DF10, DF20, YaRN, History Buffer, Frame Pack, VRAG, 消融变体）。
  - 累积误差评估：6 种方法（DF10, DF20, YaRN, History Buffer, Neural Memory, VRAG）。
  - VBench 评估：4 种方法（DF20, YaRN, History Buffer, VRAG）。
  - 真实场景泛化（RealEstate10K）：2 种方法（DFoT, VRAG）。
  - 消融实验：3 种变体（VRAG full, VRAG no memory, VRAG no training），在世界一致性和累积误差两个任务上均进行。
  - 姿态预测消融：VRAG vs VRAG（预测姿态） vs DF20。
- **充分性**：实验覆盖两个主要评估任务（世界一致性和累积误差），对比了多种来自 LLM 的扩展方法，消融实验验证了各组件贡献，并在真实场景进行了泛化验证。指标包括像素级、感知级和 VBench 综合质量，较为全面。但误差线未报告（因计算成本高），且仅在一个主数据集（Minecraft）上训练，泛化实验仅限 RealEstate10K（静态相机轨迹），可能缺乏多样性。

## 6. 主要结论与发现

- **VRAG 显著优于所有基线**：在世界一致性和累积误差评估中，VRAG 在 SSIM、PSNR、LPIPS 和 VBench 指标上均取得最佳表现。
- **长上下文扩展方法（YaRN、History Buffer、Frame Pack、Neural Memory）效果有限**，说明当前视频扩散模型的 in-context learning 能力较弱，无法有效利用长历史。
- **消融分析**：记忆组件（全局状态条件 + 检索）最关键，去除后 SSIM 下降 13.8%；训练组件（in-context 训练）也重要，去除后 SSIM 下降 10.1%。两者协同最佳。
- **泛化有效**：在 RealEstate10K 上，VRAG 仅在 2 个 epoch 微调后就显著超越 DFoT，SSIM 从 0.44 提升至 0.91。
- **累积误差本质上是自回归视频生成的内在问题**，但 VRAG 可显著缓解。
- **全局状态预测可行**：使用简单的姿态预测器代替真实全局状态，性能几乎无下降，验证了实用性。

## 7. 优点

- **问题解耦清晰**：明确区分“累积误差”和“记忆不足”两个问题，并分别设计评估协议（世界一致性 vs 累积误差），避免混淆。
- **方法创新性强**：将 RAG 概念引入视频领域，但针对视频模型 in-context learning 弱的特点，设计了训练阶段的记忆检索、噪声控制、损失屏蔽等关键改进，使其真正有效。
- **系统对比 LLM 迁移方法**：全面测试了 YaRN、History Buffer、Neural Memory 等方案，揭示了视频领域与语言领域的本质差异，为后续研究提供重要启示。
- **实验设计严谨**：使用受控运动模式（原地旋转、方向反转等）专门评估世界一致性，比随机动作更公平；采用 VBench 多维度指标；消融实验完整。
- **实用性验证**：在真实场景数据集上验证泛化，并探讨了姿态预测替代真实状态的可行性，考虑实际部署。

## 8. 不足与局限

- **计算资源限制**：受 GPU 内存约束，无法扩展到更长序列或更大架构，缓冲区大小和训练序列长度受限，可能影响长时一致性上限。
- **数据集单一**：主实验仅在 Minecraft 游戏环境，虽然补充了 RealEstate10K，但后者场景较简单（静态相机），对复杂动态世界的泛化能力仍待验证。
- **缺乏误差线**：未报告多次运行的标准差，统计显著性无法判断。
- **VRAG 依赖全局状态**：在无法获取全局状态（如坐标、方位）的场景下需要额外预测模型，增加了系统复杂度。
- **内存检索开销**：虽然 CPU 检索很快，但 GPU 上仍需拼接历史帧作为上下文，对内存仍有额外消耗（与 DF20 相近）。
- **未探索与其他压缩技术（如 Frame Pack）的组合**：作者提及正交性但未实验。
- **未见明显的社会影响讨论偏颇**：作者已提到视频生成可能被用于误导性内容，但未深入讨论具体缓解措施。

（完）
