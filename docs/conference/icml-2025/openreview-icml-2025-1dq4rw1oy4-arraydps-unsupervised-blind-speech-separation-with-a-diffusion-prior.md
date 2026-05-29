---
title: "ArrayDPS: Unsupervised Blind Speech Separation with a Diffusion Prior"
title_zh: ArrayDPS：基于扩散先验的无监督盲语音分离
authors: "Zhongweiyang Xu, Xulin Fan, Zhong-Qiu Wang, Xilin Jiang, Romit Roy Choudhury"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=1Dq4rW1Oy4"
tags: ["query:wm-vla-sa"]
score: 8.0
evidence: 使用麦克风阵列和扩散先验的无监督盲语音分离
tldr: 本文提出ArrayDPS，一种无监督盲语音分离方法，利用扩散后验采样并近似求解房间声学和相对传递函数，从而在未知阵列几何、房间冲激响应和声源的情况下分离多个说话人。该方法阵列无关且生成式，展示了扩散模型在空间音频处理中的潜力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-1dq4rw1oy4/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 846, \"height\": 1274, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1dq4rw1oy4/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1758, \"height\": 847, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1dq4rw1oy4/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1243, \"height\": 1071, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1dq4rw1oy4/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1242, \"height\": 1067, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1dq4rw1oy4/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1245, \"height\": 1070, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1dq4rw1oy4/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1242, \"height\": 1067, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-1dq4rw1oy4/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1762, \"height\": 735, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1dq4rw1oy4/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 859, \"height\": 623, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1dq4rw1oy4/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1728, \"height\": 543, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1dq4rw1oy4/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1791, \"height\": 753, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1dq4rw1oy4/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1790, \"height\": 754, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1dq4rw1oy4/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1790, \"height\": 754, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1dq4rw1oy4/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1789, \"height\": 570, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1dq4rw1oy4/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1782, \"height\": 142, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1dq4rw1oy4/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1428, \"height\": 145, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1dq4rw1oy4/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1425, \"height\": 146, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1dq4rw1oy4/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1425, \"height\": 144, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1dq4rw1oy4/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 566, \"height\": 143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1dq4rw1oy4/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 763, \"height\": 144, \"label\": \"Table\"}]"
motivation: 盲语音分离中麦克风阵列几何、房间冲激响应和声源均未知，极具挑战性。
method: 基于扩散后验采样，通过优化问题近似似然，估计房间声学和传递函数。
result: 在无监督设置下实现阵列无关的语音分离，性能优越。
conclusion: 为盲语音分离提供了一种通用且无需标注的扩散方法。
---

## Abstract
Blind Speech Separation (BSS) aims to separate multiple speech sources from audio mixtures
recorded by a microphone array. The problem is
challenging because it is a blind inverse problem,
i.e., the microphone array geometry, the room impulse response (RIR), and the speech sources, are
all unknown. We propose ArrayDPS to solve the
BSS problem in an unsupervised, array-agnostic,
and generative manner. The core idea builds on
diffusion posterior sampling (DPS), but unlike
DPS where the likelihood is tractable, ArrayDPS
must approximate the likelihood by formulating
a separate optimization problem. The solution to the optimization approximates room acoustics
and the relative transfer functions between microphones. These approximations, along with the
diffusion priors, iterate through the ArrayDPS
sampling process and ultimately yield separated
voice sources. We only need a simple single-speaker speech diffusion model as a prior, along
with the mixtures recorded at the microphones; no
microphone array information is necessary. Evaluation results show that ArrayDPS outperforms
all baseline unsupervised methods while being
comparable to supervised methods in terms of
SDR. Audio demos and codes are provided at:
https://arraydps.github.io/ArrayDPSDemo/ and
https://github.com/ArrayDPS/ArrayDPS.

---

## 论文详细总结（自动生成）

# ArrayDPS: 无监督盲语音分离的扩散先验方法 —— 详细中文总结

## 1. 核心问题与研究动机
- **问题定义**：盲语音分离（BSS）旨在从麦克风阵列采集的混合信号中分离出多个说话人的语音。这是一个“盲”逆问题，因为**麦克风阵列几何**、**房间冲激响应（RIR）** 以及**多说话人源信号**三者均未知。
- **现有方法局限**：
  - 监督方法依赖合成数据，存在**泛化性差**（模拟与真实环境不匹配）、**输出确定**（多模态后验被压缩为单点）、**阵列几何固定**（无法适应未见过的阵列配置）三大问题。
  - 传统无监督方法（如IVA、空间聚类）未充分利用语音先验，易出现频率置换、空间混叠等问题。
- **核心挑战**：如何在**无监督、阵列无关、生成式**的框架下，同时估计未知的混合过程（RIR与阵列几何）并恢复各说话人语音。

## 2. 方法论：ArrayDPS
### 2.1 总体思想
基于**扩散后验采样**（DPS），利用预训练的**单说话人语音扩散先验**（仅需干净语音训练），并通过在每步采样中**近似似然**来替代标准DPS中已知的测量模型。核心步骤：
1. 用扩散U-Net估计当前噪声源的**先验分数**。
2. 通过**独立优化**估计未知的**相对房间冲激响应（relative RIR）**，从而将虚拟源映射到各麦克风通道。
3. 使用估计出的相对RIR计算**似然梯度**（混合重构误差），与先验分数相加得到**后验分数**。
4. 沿概率流ODE采样，逐步从噪声恢复分离源。

### 2.2 关键技术细节
- **相对RIR估计**：在STFT域使用**前向卷积预测**（Forward Convolutive Prediction, FCP）求解加权最小二乘问题。每步采样中，利用当前去噪后的源估计ˆs⁰_k和混合信号x_c，FCP得到滤波器ˆG^{0→c}_k。
- **后验分数近似**：
  - 先验分数：S_θ(s^τ_k, σ(τ)) = (D_θ(s^τ_k, σ(τ)) - s^τ_k)/σ²(τ)  （Tweedie公式）。
  - 似然分数：将FCP估计的ˆG^{0→c}_k作用于ˆs⁰_k得到各通道源图像估计，计算混合重构误差L₂范数的梯度，并反向传播到s^τ_k。
  - 最终后验分数 = 先验分数 + Σ_c ∇ ξ(τ) ‖x_c - ISTFT(Σ_k ˆS_{k,c})‖²。
- **IVA初始化**：先用独立向量分析（IVA）分离粗源，并用这些源通过FCP初始化相对RIR，作为扩散采样的起点和早期步骤的滤波器，提升稳定性。
- **参考通道引导**（empirical）：早期采样步中额外加一项，使各源之和接近于参考通道混合，提高收敛鲁棒性。

### 2.3 算法流程（文字说明）
- **输入**：多通道混合x₁:C，源数K。
- **初始化**：
  1. IVA分离参考通道源图像，得到S^IVA_{k,1}。
  2. 用FCP从S^IVA_{k,1}和x_c估计滤波器ˆG^{IVA}_{1→c}。
  3. 初始化扩散噪声s^{τ₀}_k ∼ N(s^IVA_{k,1}, σ₀²I)。
- **迭代采样**（N步Heun二阶随机采样）：
  - 对每个源k：用扩散U-Net去噪得ˆs⁰_k，先验分数 = (ˆs⁰_k - s^{τ_i}_k)/σ²_i。
  - 若i ≤ N_{fg}，使用IVA初始化滤波器ˆG^{IVA}_{1→c}；否则用FCP重新估计。
  - 得到各通道源图像估计ˆs_{k,c}，计算混合重构L₂梯度，加入参考通道引导（i ≤ N_{ref}时）。
  - 后验分数 = 先验分数 + 似然梯度 + λ·参考引导梯度。
  - 按Euler/Heun步更新源。
- **后处理**：对最终虚拟源s^{τ_N}_k，用FCP再估计到参考通道的滤波器，卷积得到最终分离输出ˆs_{k,1}。

## 3. 实验设计
### 3.1 数据集与场景
- **固定阵列**：**SMS-WSJ**，6通道圆阵（10cm半径），模拟混响（T60 200–500ms），8kHz采样。测试集1332条（约3.4h）。
- **ad-hoc阵列**：**Spatialized WSJ0-2Mix**，每样本随机生成8通道阵列几何、房间大小、源位置，T60 200–600ms。测试集3000条（约5h）。另用**Spatialized WSJ0-3Mix**评估3说话人场景。
- **真实环境**：自录15段3麦克风混合（7m×4m×2.7m房间，两位志愿者同时说话）。

### 3.2 基线方法
- **无监督基线**：空间聚类（Spatial Cluster）、IVA（Laplace/Gaussian先验）、**UNSSOR**（基于麦克风迭代信号建模的无监督方法，需固定阵列训练）。
- **监督基线**：**TF-GridNet**（基于深度学习的强监督模型），在SMS-WSJ或Spatialized WSJ0-2Mix上分别训练。

### 3.3 主要实验（表1–7及附录）
| 实验组 | 数据集 | 通道数 | 核心比较 |
|--------|--------|--------|----------|
| 表1 | SMS-WSJ | 3ch | ArrayDPS-A vs. 无监督（IVA, Spatial, UNSSOR） vs. 监督（TF-GridNet） |
| 表6 | SMS-WSJ | 6ch | 同上 |
| 表2 | Spatialized WSJ0-2Mix | 4ch | ad-hoc阵列，对比无监督/监督 |
| 表4、5 | 同上 | 2ch、3ch | ad-hoc阵列 |
| 表7 | WSJ0-3Mix | 4ch | 3说话人ad-hoc |
| 附录K | SMS-WSJ验证集 | 3ch | 超参数敏感性（ξ, τ_max, F, N_fg等） |

### 3.4 消融实验
- **扩散先验类型**：消声（Anechoic）vs.混响（Reverb）→消声更好。
- **IVA初始化**：有/无（ArrayDPS-A vs. -D）→无初始化时性能崩溃（SDR下降7dB+）。
- **参考通道引导**：有/无（ArrayDPS-A vs. -C），稳定性和性能均有提升。
- **最大似然/最大采样选择**：从5个样本中选出似然最高的（-ML）或最好的（-Max）。

## 4. 资源与算力
- **扩散先验训练**：使用LibriTTS clean 100+360子集（约460h），U-Net架构（6层1D卷积ResNet+自注意力），**batch size=16**，学习率0.0001（每60k步×0.8），EMA更新，训练**840,000步**。未明确说明GPU型号/数量。
- **TF-GridNet监督基线**（附录F）：单个**A100 GPU**，训练约**1,000,000步**，耗时**5–6天**。
- **ArrayDPS推理**：每段混合需N=400步采样，每步调用一次U-Net和FCP，未报告具体时间，但生成方法计算成本较高。

## 5. 实验数量与充分性
- **数量**：涵盖**6种数据集/通道配置**（2/3/4/6ch固定阵列、2/3/4ch ad-hoc、4ch 3说话人），以及**真实房间测试**。消融实验覆盖**10个以上超参数维度**（ξ, τ_max, F, N_fg, 先验类型, IVA先验, 初始化有无, 参考引导有无等）。
- **充分性**：实验设计较为全面，与所有主流无监督方法对比，并补充监督基线做参考；ad-hoc场景下的表现优于所有无监督基线，并且在2/3ch ad-hoc上UNSSOR失效，ArrayDPS仍有效；3说话人场景下大幅超越监督方法。消融实验揭示了各组件的贡献。**公平性**：基线使用原论文开源代码或标准实现，ArrayDPS超参数在验证集上调优，未在测试集上过拟合。但未与最新如MixIT、伪标签迭代等方法对比（仅对比了UNSSOR）。
- **偏差风险**：所有数据集均为模拟混响（图像源法），真实场景仅15段自录，结果可能偏向模拟数据规律。

## 6. 主要结论与发现
1. **阵列无关性**：ArrayDPS无需任何阵列几何先验即可处理固定或随机ad-hoc麦克风配置，且在ad-hoc场景下达到甚至超过监督方法水平。
2. **无监督优势**：仅需单说话人语音扩散先验，不依赖配对标注，从根本上避免了合成数据的泛化问题。
3. **生成式特性**：输出后验样本，可提供多个合理分离结果（不同于确定性方法），且通过最大似然挑选能进一步提升指标。
4. **性能表现**：
   - 相比所有无监督基线，ArrayDPS-A在SDR/SI-SDR上通常提升**1–3 dB**（如固定3ch SMS-WSJ: 15.8 vs. 15.4 UNSSOR）。
   - 在ad-hoc 4ch上，ArrayDPS-A-ML（16.6 dB SDR）与监督TF-GridNet-Spatial（15.8 dB）持平甚至略优；在3说话人ad-hoc下，比监督方法领先**3.4 dB SDR**。
   - 有初始化时性能稳定（标准差小），无初始化时虽能偶尔分离（最佳样本可达14+ dB），但方差极大（SDR std ~5 dB）。
5. **可解释性**：可视化分析显示，分离出的虚拟源更接近消声源，表明算法隐含了去混响效果（因扩散先验训练于消声数据，且FCP对消声源估计更优）。

## 7. 优点
- **完全无监督与阵列无关**：突破了监督方法依赖固定阵列和配对数据的限制，可应用于任意未知麦克风布局。
- **生成式建模**：保留后验多峰性，避免确定性方法的模糊问题；可通过采样多样性提升最终选优概率。
- **结合语音先验**：利用强力的扩散先验，自动解决传统无监督方法难以处理的频率置换、空间混叠等问题。
- **方法通用性**：首次将DPS扩展到多通道阵列逆问题，为后续如多通道去混响、波束赋形等提供范式。
- **实验充分**：在多个数据集、通道数、说话人数上验证，消融实验全面，开源代码可复现。

## 8. 不足与局限
- **计算成本高**：需要数百步扩散采样（N=400），每一步包含U-Net推理和FCP求解，推理时间远超传统方法，难以用于实时场景。
- **对初始化敏感**：无IVA初始化时性能不可控（std大），需借助传统IVA提供可靠起点，限制了完全端到端的无监督性。
- **超参数多且需调优**：ξ, τ_max, N_fg, N_ref, λ等均需针对数据集调整，在附录K中显示出一定敏感性（如ξ从1.2变到2.8时SI-SDR波动约1 dB），缺乏自适应方案。
- **监督基线对比不完全**：仅对比TF-GridNet，未与更先进的监督模型（如MossFormer、Sepformer多通道版本）比较；且在6ch SMS-WSJ上ArrayDPS-A-ML（17.4 dB）仍落后监督TF-GridNet（19.4 dB）约2 dB，差距显著。
- **真实评估局限**：真实场景仅15段录音，且未与真实环境中的无监督基线（如IVA直接应用）对比，说服力不足。
- **潜在偏差**：扩散先验在消声数据上训练，导致输出偏向消声源，当目标结果应为混响源时可能引入额外失真；FCP假设线性模型，对极端非线性或快速变化环境可能失效。

（完）
