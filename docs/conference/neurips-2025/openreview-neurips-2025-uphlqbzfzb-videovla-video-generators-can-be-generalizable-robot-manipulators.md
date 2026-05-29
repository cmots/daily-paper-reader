---
title: "VideoVLA: Video Generators Can Be Generalizable Robot Manipulators"
title_zh: VideoVLA：视频生成器可成为通用机器人操作器
authors: "Yichao Shen, Fangyun Wei, Zhiying Du, Yaobo Liang, Yan Lu, Jiaolong Yang, Nanning Zheng, Baining Guo"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=UPHlqbZFZB"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 视觉-语言-动作模型用于机器人操作
tldr: 现有VLA模型泛化能力有限，难以应对新任务和场景。本文提出VideoVLA，将大型视频生成模型转化为机器人VLA操作器，通过多模态扩散Transformer联合建模视频、语言和动作模态，从语言指令和图像预测动作序列及未来视觉结果。实验表明该方法提升了泛化能力，为机器人操作提供了新范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-uphlqbzfzb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1419, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uphlqbzfzb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1430, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uphlqbzfzb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1315, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uphlqbzfzb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1447, \"height\": 564, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uphlqbzfzb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1419, \"height\": 921, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-uphlqbzfzb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1420, \"height\": 1851, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-uphlqbzfzb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1438, \"height\": 483, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uphlqbzfzb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1430, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uphlqbzfzb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1428, \"height\": 349, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uphlqbzfzb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1454, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uphlqbzfzb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uphlqbzfzb/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 789, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uphlqbzfzb/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1460, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uphlqbzfzb/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 625, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uphlqbzfzb/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 921, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uphlqbzfzb/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1454, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uphlqbzfzb/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1157, \"height\": 675, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uphlqbzfzb/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 457, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uphlqbzfzb/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1253, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-uphlqbzfzb/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1282, \"height\": 257, \"label\": \"Table\"}]"
motivation: 现有VLA模型泛化到新任务、物体和环境的能力有限，需要更通用的操作策略。
method: 基于多模态扩散Transformer，将视频生成模型转化为VLA操作器，联合建模视频、语言和动作模态。
result: 在多项机器人操作任务上，VideoVLA展现了对新任务的更好泛化能力。
conclusion: 视频生成模型可以有效地转化为VLA操作器，为通用机器人操作提供新思路。
---

## Abstract
Generalization in robot manipulation is essential for deploying robots in open-world environments and advancing toward artificial general intelligence. While recent Vision-Language-Action (VLA) models leverage large pre-trained understanding models for perception and instruction following, their ability to generalize to novel tasks, objects, and settings remains limited. In this work, we present VideoVLA, a simple approach that explores the potential of transforming large video generation models into robotic VLA manipulators. Given a language instruction and an image, VideoVLA predicts an action sequence as well as the future visual outcomes.  Built on a multi-modal Diffusion Transformer, VideoVLA jointly models video, language, and action modalities, using pre-trained video generative models for joint visual and action forecasting. Our experiments show that high-quality imagined futures correlate with reliable action predictions and task success, highlighting the importance of visual imagination in manipulation. VideoVLA demonstrates strong generalization, including imitating other embodiments' skills and handling novel objects. This dual-prediction strategy—forecasting both actions and their visual consequences—explores a paradigm shift in robot learning and unlocks generalization capabilities in manipulation systems.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：当前视觉-语言-动作（VLA）模型虽借助大规模预训练理解模型（如视觉-语言模型）显著提升了任务成功率，但在面对**未见过的任务、物体或环境**时泛化能力仍然有限。机器人操作需要真正开放世界中的通用性，而现有方法依赖于预训练的理解模型，未能充分挖掘生成模型的潜力。
- **整体含义**：论文提出将**大规模视频生成模型**（而非理解模型）作为 VLA 模型的骨干，通过联合预测**未来动作序列**与**未来视觉结果**（即“视觉想象”），实现更强的泛化。这一思路标志着从“理解范式”向“生成范式”的转变，为通用机器人操作提供了新路径。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将预训练的视频扩散 Transformer（DiT）直接改造为机器人 VLA 操作器，使得模型能同时生成动作和对应的未来视频帧，从而利用视频生成模型预训练中学到的物理动态与场景理解能力，提升泛化。
- **关键技术细节**：
  - **架构**：基于多模态 Diffusion Transformer（DiT），输入包括语言指令的 T5 编码、当前观测帧的 VAE 潜码，以及带噪声的未来帧潜码和动作向量。模型将它们拼接到统一序列中，通过自注意力块跨模态交互，采用 DDPM 扩散损失联合去噪。
  - **动作表示**：7 维向量（3 维旋转 + 3 维平移 + 1 维夹爪状态），预测未来 K=6 个动作（执行时只采前 3 个）。
  - **视频表示**：使用 CogVideoX 的 3D 因果 VAE 将视频帧编码为潜码，第一个潜码对应当前观测，其余对应未来帧。默认预测 13 个未来帧潜码（对应 49 帧），实际部署时可减少至 4 个潜码（13 帧）以提升速度。
  - **训练策略**：模型初始化自预训练的 CogVideoX-5B，训练时对视频潜码和动作向量同时添加噪声并去噪，使用 AdamW 优化器，学习率 1e-5，weight decay 1e-4，DDIM 采样 50 步（实际部署可减至 10 步）。
- **算法流程**（文字说明）：
  1. 输入：语言指令 T，当前观测图像 O。
  2. 编码：T 通过 T5 得到 226 维 token 序列；O 通过视频 VAE 编码器得到第一个潜码 V1。
  3. 构建多模态序列：拼接语言 token、V1、待预测的 N 个未来帧潜码（加噪后）、K 个动作向量（加噪后）。
  4. 通过多模态 DiT 进行扩散去噪，输出去噪后的未来帧潜码和动作向量。
  5. 可选：将未来帧潜码输入 VAE 解码器得到可视化的“视觉想象”视频。
  6. 执行前 3 个动作后，获取新的观测，重复以上步骤直至任务完成。

### 3. 实验设计：数据集、基准、对比方法

- **数据集**：
  - **预训练**：Open X-Embodiment (OXE)，含超过 100 万条真实机器人轨迹，选用与 Octo/OpenVLA/CogACT 一致的子集（约 2250 万帧），涵盖 22 种不同的机器人形态。
  - **真实世界微调**：自采集数据集，共 5824 条样本，包含“pick”“stack”“place”三类任务，使用 Realman 机器人（7-DoF 臂 + 夹爪）。
- **基准**：SIMPLER 模拟环境（支持 Visual Matching 和 Variant Aggregation 两种评估协议），以及真实世界实验台。
- **对比方法**：RT-1-X, RT-2-X, Octo-Base/Small, OpenVLA, SpatialVLA, π0, CogACT。所有方法在相同预训练数据和微调数据上训练，公平比较。

### 4. 资源与算力

- **明确指出**：预训练 100K 次迭代，微调 15K 次迭代，使用 32 块 AMD MI300X GPU，批大小 256。推理时单次预测约需 1.1 秒（10 步 DDIM，4 帧潜码），控制频率约 3 Hz。未提及总训练时长，但算力需求显著（32 GPU × 大规模迭代）。

### 5. 实验数量与充分性

- **实验组数**：
  - **模拟环境**：在 WidowX 和 Google 机器人上开展 12 项域内任务（表1）、10 项新物体泛化任务（表2）、7 项新技能泛化任务（表3），每项任务独立多次试次（具体试次数见附录表11，如 Pick Coke Can 300 次）。
  - **真实世界**：域内任务 3 类（各多次试次，表12），新物体泛化 12 个物体（每物体 12 次）、新技能泛化 5 项技能（每技能 16 次）。
  - **消融实验**：4 组（骨干选择、时间预测长度、双预测策略、因果掩码/扩散调度），均在 SIMPLER Google 机器人上评估。
- **充分性与客观性**：
  - 覆盖域内、新物体、新技能（跨形态迁移），并包含人工对视觉想象质量的评估。
  - 所有对比模型均在同一数据、相同设置下训练和评估，试次数明确，统计结果可靠。
  - 消融实验系统地验证了各组件贡献。
  - 结论：实验充分、客观、公平。

### 6. 论文的主要结论与发现

- **视频生成模型可作为 VLA 骨干**：在多个任务上达到或超越基于理解模型的 SOTA，尤其在泛化方面大幅领先。
- **双预测策略至关重要**：联合预测动作和未来视频帧比单独预测动作或仅使用视频损失效果更优（表9）。
- **视觉想象质量与动作可靠性正相关**：高相似度的“想象-执行”视频对应更高的任务成功率（图3）。
- **更长的预测时间跨度带来更好性能**：预测 49 帧优于 25 帧和 13 帧（表8）。
- **预训练数据起决定性作用**：从零训练版本性能极差，高质量视频生成器骨干（CogVideoX-5B vs OpenSora-1.1）也显著影响结果（表7）。
- **跨形态技能迁移成功**：Realman 机器人能执行从未接触过的 WidowX 机器人的技能（表6）。

### 7. 优点：方法或实验设计上的亮点

- **范式创新**：首次系统性地将大型视频生成模型直接转化为端到端 VLA 操作器，开辟了不同于理解模型的新路径。
- **双预测策略**：让模型不仅输出动作，还输出可视化的未来帧，既提供了可解释性，又作为隐式监督信号提升动作可靠性。
- **强泛化能力**：在新物体、新技能、跨形态迁移上均取得显著领先，展示了视频生成模型预训练的物理常识迁移潜力。
- **实验设计全面**：涵盖模拟和真实环境，多组消融与对比，使用公开数据集和统一评估协议，保证了公平性和可复现性。
- **分析深入**：通过运动相似性分析建立了想象质量与执行成功之间的定量关系，使结论更有说服力。

### 8. 不足与局限

- **推理速度慢**：当前基于 5B 参数的 CogVideoX，单次推理需约 1.1 秒，控制频率仅约 3 Hz，难以支撑高速或实时任务。论文本身也指出这是主要瓶颈。
- **依赖大规模视频生成模型**：模型尺寸大，训练和部署成本高，可能限制其在资源受限场景的应用。
- **实验覆盖仍有局限**：
  - 真实世界任务仅限于拾取、堆叠、放置等有限类别，未涉及更复杂的操作（如装配、精细抓取）。
  - 跨形态迁移仅在 Realman 和 WidowX 间验证，未扩展到更多形态。
  - 对真实世界中的动态干扰（如移动障碍）或环境变化鲁棒性未测试。
- **评估指标单一**：成功率为主要度量，缺乏对动作精度、鲁棒性、安全性的细粒度分析。
- **无开放代码/数据**：论文承诺开源，但当前未提供，影响了完全复现。

（完）
