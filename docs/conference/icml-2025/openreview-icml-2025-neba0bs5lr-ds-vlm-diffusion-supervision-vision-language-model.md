---
title: "DS-VLM: Diffusion Supervision Vision Language Model"
title_zh: "DS-VLM: 扩散监督视觉语言模型"
authors: "Zhen Sun, Yunhang Shen, Jie Li, Xing Sun, Pingyang Dai, Liujuan Cao, Rongrong Ji"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=NEBa0bs5LR"
tags: ["query:wm-vla-sa"]
score: 6.0
evidence: 扩散监督用于VLM视觉学习
tldr: 该论文针对VLM视觉表示学习中的监督退化问题，提出扩散监督视觉语言模型（DS-VLM），通过扩散模型重建输入图像来建立从像素空间到视觉特征的短路径梯度传播，同时保持文本语义对齐，提升了视觉表示质量。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-neba0bs5lr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 770, \"height\": 324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-neba0bs5lr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 789, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-neba0bs5lr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1775, \"height\": 506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-neba0bs5lr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1328, \"height\": 841, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-neba0bs5lr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-neba0bs5lr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 841, \"height\": 546, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 667, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 507, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1763, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 803, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 801, \"height\": 139, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 802, \"height\": 133, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1764, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-neba0bs5lr/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1222, \"height\": 192, \"label\": \"Table\"}]"
motivation: VLM视觉表示由于梯度传播损失和文本监督稀疏性而受限。
method: 通过扩散模型重建图像来直接监督视觉编码器。
result: 在多个基准上提升了视觉表示能力。
conclusion: 扩散监督是一种有效的VLM视觉增强方法。
---

## Abstract
Vision-Language Models (VLMs) face two critical limitations in visual representation learning: degraded supervision due to information loss during gradient propagation, and the inherent semantic sparsity of textual supervision compared to visual data. We propose the Diffusion Supervision Vision-Language Model (DS-VLM), a plug-and-play framework that introduces diffusion-based direct supervision for vision-language alignment. By reconstructing input images through a diffusion model conditioned on outputs of the visual encoder and the connector, our method establishes a short-path gradient propagation channel from pixel space to visual features. This approach simultaneously preserves high-level semantic alignment through conventional text supervision while enhancing visual feature quality via pixel-level reconstruction constraints. Extensive experiments conducted across various visual encoders and LLMs of different scales demonstrate the effectiveness of our approach.

---

## 论文详细总结（自动生成）

# DS-VLM 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **问题**：现有视觉语言模型（VLM）在视觉表示学习上面临两个关键局限：
  - **监督退化**：文本监督信号在通过大语言模型（LLM）反向传播时，因长路径梯度传播导致信息丢失。
  - **语义稀疏性**：文本监督相比图像本身，其语义信息密度低，难以充分指导视觉特征学习。
- **动机**：传统方法（如LLaVA、BLIP-2）依赖LLM生成的文本梯度来优化视觉编码器和连接器，传播链过长且信息损耗严重。作者希望利用图像自身的丰富语义，通过更短的路径直接监督视觉组件。
- **整体含义**：提出一种插件式框架DS-VLM，利用扩散模型对视觉编码器和连接器的输出进行重建监督，建立从像素空间到视觉特征的短路径梯度传播，同时保留文本监督的高层语义对齐，从而提升视觉表示质量。

## 2. 方法论：核心思想、关键技术细节

### 核心思想
- 在训练阶段，引入预训练的扩散模型（基于Stable Diffusion），以视觉编码器不同层的特征（低、中、高层）和连接器的输出特征作为条件，重建原始输入图像。
- 通过重建损失（重构图像与原图的差异）反向传播梯度，直接优化视觉编码器和连接器，绕过LLM，缩短知识传播链。
- 推理阶段不需要扩散模型，不增加额外参数和计算量。

### 关键技术细节
- **监督特征提取**：
  - 图像模态监督特征：从视觉编码器的第8、16、24层提取低层、中层、高层特征。
  - 文本模态监督特征：使用连接器（MLP）输出的特征（因其已将图像特征映射到文本嵌入空间）。
- **Multi-Adapter Diffusion**：
  - 基于Stable Diffusion的UNet架构，设计多个适配器分别接收不同模态的监督特征。
  - 使用**MOE Cross Attention（混合专家交叉注意力）**机制，为文本特征和不同层级的图像特征分别设置独立的交叉注意力层，通过可学习的路由权重加权融合输出。
- **重建损失**：
  - 对比了三种损失：像素级（MAE）、结构级（SSIM）、语义级（感知损失PL）。最终默认使用感知损失，实验表明其效果最佳。
- **训练流程**：
  - 在预训练和指令微调阶段，冻结LLM和扩散模型，仅训练视觉编码器、连接器以及扩散模型中的适配器参数（通过LoRA微调线性层，rank=8）。
  - 扩散模型的去噪步数设为50。

## 3. 实验设计

- **数据集**：
  - 预训练数据：LLaVA-1.5的558K图像描述。
  - 指令微调数据：665K多轮对话。
  - 额外扩展实验使用了Mini-Gemini的1.2M+1.5M数据。
- **基准（Benchmark）**：10个主流VLM评估数据集：
  - MMBench (MMB), MMStar (MMS), MMMU, MathVista (MV), OCRBench (OCRB), AI2D, HallusionBench (HB), LLaVABench (LB), ScienceQA (SQA), MME。
- **对比方法**：
  - 主要基线：LLaVA-1.5（Vicuna-7B/13B + CLIP-L）。
  - 扩展对比：替换视觉编码器为SigLIP-SO，替换LLM为Llama3-8B、Qwen2-7B。
  - 与其他SOTA方法对比：MiniGPT4, Qwen-VL, VisualGLM, PandaGPT, mPLUG-Owl2, Emu2-chat, Yi-VL, ShareGPT-4V。

## 4. 资源与算力

- **明确说明**：文中未明确提及GPU型号、数量、训练总时长。仅提到使用PyTorch框架，训练配置与LLaVA-1.5一致：
  - 预训练阶段：学习率1e-3，batch size 256。
  - 指令微调阶段：学习率2e-5，batch size 128。
- **推断**：考虑到模型规模（Vicuna-7B/13B、CLIP-L、扩散模型），训练可能需要多张高端GPU（如A100 80GB），但具体数值未披露。

## 5. 实验数量与充分性

- **实验数量**：约5类主要实验：
  1. **基线对比**：在LLaVA-1.5基础上，使用不同视觉编码器（CLIP-L、SigLIP-SO）和不同LLM（Vicuna-7B/13B、Llama3-8B、Qwen2-7B），共约8组对比。
  2. **SOTA对比**：与8种公开方法在10个基准上比较。
  3. **消融实验**：共4组——
     - 监督特征类型消融（文本监督+不同层图像监督组合）。
     - 重建损失函数消融（MAE、SSIM、PL）。
     - 交叉注意力机制消融（共享 vs 独立）。
     - 适配器结构消融（Q-Former vs 线性适配器）。
  4. **额外验证**：训练视觉编码器时的对比实验（附录A），验证视觉编码器确实被优化。
  5. **定性分析**：可视化扩散模型去噪过程。
- **充分性与公平性**：
  - 控制了训练数据、超参数与基线一致，对比公平。
  - 覆盖了不同规模的LLM和不同视觉编码器，泛化性验证充分。
  - 消融实验设计合理，验证了各模块的必要性。
  - 但缺少在更多VLM架构（如BLIP-2、Flamingo）上的应用验证，泛化性仅限于LLaVA-1.5系列。

## 6. 主要结论与发现

1. **性能提升显著**：DS-VLM在LLaVA-1.5基础上，平均提升约1.4%（Vicuna-7B），在MMBench、MMMU、LLaVABench等数据集上分别提升+2.4%、+2.1%、+2.5%。
2. **插件式有效**：方法可迁移至不同视觉编码器（SigLIP）和不同LLM（Llama3、Qwen2），在多数基准上保持领先。
3. **多级监督互补**：同时使用文本监督和图像多层级监督效果最佳，低层监督有助于细节捕捉，高层监督提升全局语义。
4. **感知损失最优**：相比MAE和SSIM，感知损失能更好地保留语义信息，提升下游任务表现。
5. **独立交叉注意力优于共享**：为不同模态特征设计独立注意力头可减少模态干扰，提升对齐质量。
6. **视觉编码器确实被优化**：通过控制实验证明，仅训练适配器无法达到相同重建效果，说明视觉编码器在训练中学习到了有效表示。

## 7. 优点

- **创新性**：首次将扩散模型作为直接监督信号用于VLM的视觉表示学习，利用图像自身语义来优化，思路新颖。
- **短路径梯度传播**：绕过LLM，从像素空间直达视觉特征，缓解梯度消失和信息损失。
- **插件式设计**：训练时引入扩散模型，推理时无需额外组件，不增加参数量和计算开销，易于集成到现有框架。
- **多级特征利用**：同时监督视觉编码器不同层和连接器输出，全面覆盖特征层次。
- **实验充分**：在多种配置和基准上验证，消融实验完整，证明了方法的鲁棒性和泛化性。

## 8. 不足与局限

- **实验覆盖有限**：仅基于LLaVA-1.5系列进行实验，未在其他主流VLM框架（如BLIP-2、InstructBLIP、Flamingo）上验证，通用性有待进一步检验。
- **训练开销**：训练阶段需要额外加载并运行扩散模型，虽然通过LoRA微调降低了参数，但显存占用和训练时间可能增加（未量化）。文中未比较训练效率。
- **重建损失选择**：感知损失虽效果最好，但计算复杂度较高；且未探讨联合多种损失的可能性。
- **超参数敏感性**：未分析监督特征层选择（第8、16、24层）以及扩散步数（50）的敏感性，可能存在更优配置。
- **潜在偏差风险**：重建损失可能偏向于生成与原图视觉相似的结果，但未必有利于语义理解（例如对抗样本或域外图像）。实验未讨论这种偏差。
- **可解释性不足**：仅定性展示了去噪过程，缺乏定量分析重建质量与下游性能之间的关联。
- **资源披露缺失**：未提供训练所需GPU型号、数量、时长，不利于复现和成本评估。

（完）
