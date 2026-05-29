---
title: "Hi Robot: Open-Ended Instruction Following with Hierarchical Vision-Language-Action Models"
title_zh: Hi Robot：基于分层视觉-语言-动作模型的开放式指令跟随
authors: "Lucy Xiaoyang Shi, brian ichter, Michael Robert Equi, Liyiming Ke, Karl Pertsch, Quan Vuong, James Tanner, Anna Walling, Haohuan Wang, Niccolo Fusai, Adrian Li-Bell, Danny Driess, Lachy Groom, Sergey Levine, Chelsea Finn"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=lNVHg9npif"
tags: ["query:wm-vla-sa"]
score: 9.0
evidence: 分层视觉-语言-动作模型用于机器人开放式指令跟随
tldr: 通用机器人需要处理复杂指令和实时反馈。本文提出Hi Robot系统，使用分层视觉-语言-动作模型，先通过高层VLM理解指令和反馈，再生成具体动作序列。实验表明该系统能够遵循开放式指令并适应在线反馈。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-lnvhg9npif/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1717, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lnvhg9npif/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 813, \"height\": 588, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lnvhg9npif/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 808, \"height\": 771, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lnvhg9npif/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1727, \"height\": 1829, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lnvhg9npif/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1730, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lnvhg9npif/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1733, \"height\": 594, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lnvhg9npif/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 816, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-lnvhg9npif/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 822, \"height\": 545, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-lnvhg9npif/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 617, \"height\": 285, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-lnvhg9npif/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 878, \"height\": 1392, \"label\": \"Table\"}]"
motivation: 现有机器人系统无法处理包含复杂指令和用户反馈的开放式任务。
method: 构建分层VLA架构，上层用视觉语言模型推理任务步骤，下层执行具体动作。
result: 在多个真实场景中成功执行了包含模糊指令和实时纠偏的任务。
conclusion: 分层VLA有效结合了高层推理与低层控制，提升了机器人的通用性。
---

## Abstract
Generalist robots that can perform a range of different tasks in open-world settings must be able to not only reason about the steps needed to accomplish their goals, but also process complex instructions, prompts, and even feedback during task execution. Intricate instructions (e.g., "Could you make me a vegetarian sandwich?" or "I don't like that one") require not just the ability to physically perform the individual steps, but the ability to situate complex commands and feedback in the physical world. In this work, we describe a system that uses vision-language models in a hierarchical structure, first reasoning over complex prompts and user feedback to deduce the most appropriate next step to fulfill the task, and then performing that step with low-level actions. In contrast to direct instruction following methods that can fulfill simple commands ("pick up the cup"), our system can reason through complex prompts and incorporate situated feedback during task execution ("that's not trash"). We evaluate our system across three robotic platforms, including single-arm, dual-arm, and dual-arm mobile robots, demonstrating its ability to handle tasks such as cleaning messy tables, making sandwiches, and grocery shopping.
Videos are available at https://www.pi.website/research/hirobot

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：现有机器人系统大多只能执行简单的原子指令（如“拿起杯子”），无法处理开放式、复杂的人类指令——例如“你能帮我做一个素食三明治吗？不要西红柿。如果有火腿或烤牛肉，请再为我的朋友做一个三明治。” 这类指令要求机器人能够解析多步骤任务、理解上下文、响应实时反馈（如“那个不是垃圾”）。
- **研究背景**：受卡尼曼“系统1/系统2”认知理论启发，简单指令遵循对应“系统1”（自动执行），复杂推理对应“系统2”（深思熟虑）。现有工作（如RT-2、SayCan、YAY Robot等）要么只能处理简单指令，要么在物理灵巧性和实时交互能力上受限。
- **本文目标**：构建一个分层视觉-语言-动作（VLA）系统——Hi Robot，使机器人能够处理复杂的开放式指令、融合人类实时反馈，并在多种机械平台（单臂、双臂、移动双臂）上执行物理任务，如清理桌子、制作三明治、杂货购物。

## 2. 方法论

### 核心思想
- **分层架构**：将策略分解为高层和低层两个VLM模型。
  - **高层策略（High-level Policy）**：使用VLM，接收图像观测和开放式任务提示（包括用户指令和实时反馈），输出一个**低层语言命令**（例如“拿起生菜”）。
  - **低层策略（Low-level Policy）**：基于π0 VLA，接收图像、机器人状态和高层输出的语言命令，通过流匹配（flow-matching）输出连续的动作块（action chunk）。
- **推理频率**：高层推理每1秒或接到用户新输入时触发一次，低层推理以更高频率（约10Hz）执行。
- **用户交互**：用户可实时输入文本或语音（转录为文本），系统立即触发高层推理，重新生成命令。高层模型还可输出语言回应（如“好的，我不放奶酪”），由TTS播放。

### 关键技术细节
- **高层模型训练数据**：
  - 首先通过遥操作收集机器人演示，分割为短技能（如“拿起KitKat”）并标注。
  - 使用大型VLM（pgen）根据视觉上下文和技能标签，**合成生成**假设的用户指令和机器人回应。通过场景分类（否定任务、情境纠正、特定约束）和回应分类（简单确认、澄清、错误处理）指导生成，确保多样性。
  - 最终数据集Dsyn ∪ Dlabeled用于训练高层策略（交叉熵损失）。
- **低层模型训练**：使用Dlabeled ∪ Ddemo，采用流匹配目标训练π0（基于PaliGemma-3B）。
- **基础模型**：两者均基于PaliGemma-3B VLM，低层额外添加流匹配“动作专家”输出连续动作。

### 算法流程（文字说明）
1. 系统接收当前图像、机器人状态、用户开放式指令或反馈。
2. 高层策略基于这些输入，输出一个低层语言命令（可能包含机器人口头回应）。
3. 若包含口头回应，则通过TTS播放并从命令中移除。
4. 低层策略根据图像、状态和语言命令，生成未来H步动作块并执行。
5. 每隔1秒或收到新用户输入，返回步骤2。

## 3. 实验设计

### 场景与数据集
- **任务域**：三个复杂物理任务：
  - **Table Bussing（清理桌子）**：将不同物品（餐具、垃圾）分别放入缓存箱或垃圾桶。包含物理挑战（抓取盘子边缘、倾倒垃圾）和语义理解（“只清理垃圾，不清理盘子”“清理所有黄色物品”）。
  - **Sandwich Making（制作三明治）**：使用最多6种配料和面包，涉及精细操作（抓取生菜、奶酪等软质物品）。训练数据包含多种三明治类型，技能标签如“拿起一片面包”。
  - **Grocery Shopping（杂货购物）**：在货架上拾取物品放入购物篮，再放到桌上。涉及移动双臂操作和数量/语义理解（“给我一些薯片”“甜的东西”“Twix和Skittles”）。
- **平台**：UR5e单臂、Bimanual ARX双臂、Mobile ARX移动双臂（基于Mobile ALOHA）。
- **训练数据**：通过遥操作收集每类任务的演示，并进行技能分割和标注。然后使用VLM生成合成交互数据。

### Benchmark与对比方法
- **Expert human high level（专家人工高层）**：由人类手动选择低层命令，作为低层策略的上限。
- **GPT-4o high-level model**：使用GPT-4o API作为高层，低层与Hi Robot相同。通过精心提示限制技能选项。
- **Flat VLA**：仅使用π0低层策略，无高层，代表SOTA直接指令跟随。
- **Flat VLA with synthetic data**：Flat VLA，但训练数据包含合成数据。
- **Hi Robot without synthetic data**：Hi Robot但无合成数据，类似YAY Robot。
- **Hi Robot（完整方法）**：含高层和低层，训练于真实+合成数据。

### 指标
- **Instruction Accuracy (IA)**：由人工盲评，衡量高层输出指令与用户意图和观察的一致性。
- **Task Progress (TP)**：任务完成进度的比例（如正确放置的物品数）。

### 实验设置
每个任务每个方法20个试验（trial），共多个任务和方法对比。主要结果在Figure 5中展示，消融在Figure 7和Figure 8中。

## 4. 资源与算力

- **GPU型号**：训练使用8× H100 GPU。
- **训练时间**：
  - 高层策略约2小时。
  - 低层策略训练时间因数据集大小和任务复杂度而异，但未给出具体时间。
- **推理硬件**：使用1-2块NVIDIA RTX 4090消费级GPU。
- **延迟数据**：低层每步推理约73ms（板载）至86ms（WiFi），高层单步解码在RTX 4090上47ms（预填充）+13.2ms（解码），在H100上17.3ms+5.7ms。

## 5. 实验数量与充分性

- **实验数量**：主要对比在3个任务×4种主要方法（Hi Robot、GPT-4o、Flat VLA、Expert human）加上消融实验（2组：有/无合成数据、分层/平坦），每组20个试验，总试验数至少达到12组×20=240次（加上消融更多）。比较充分。
- **充分性**：
  - 对比了多个基线：专家人类上限、API VLM、平坦VLA、有/无合成数据变体，覆盖了推理和物理执行层面。
  - 使用盲评，减少主观偏差。
  - 消融实验明确分离了合成数据贡献和层次结构贡献。
  - 但未进行跨任务迁移或多任务训练（虽然文本提到未来可扩展），且所有实验在特定物理场景下进行，未在更广泛环境中测试。
- **客观公平性**：指标定义清晰，盲评；GPT-4o基线使用了精心设计的系统提示；Flat VLA使用了相同低层策略。总体上公平。

## 6. 主要结论与发现

1. **Hi Robot在开放式指令跟随上远超基线**：在所有任务中，指令准确性和任务进度均显著高于GPT-4o和平坦VLA。能正确处理“只清理垃圾”“不加番茄”等约束，以及实时反馈。
2. **适应实时反馈的能力强**：面对“leave the rest”“I also want a KitKat”等中断，Hi Robot能正确调整低层命令，而GPT-4o常丢失上下文，平坦VLA不反应。
3. **跨多样任务和机器人平台有效**：在单臂、双臂、移动双臂上均表现良好。
4. **专家人类高层揭示了低层策略的潜力**：使用人类高层命令时，低层策略几乎完美执行，说明失败主要源于高层推理而不是物理执行。
5. **合成数据对开放式指令跟随至关重要**：无合成数据时，模型会忽略用户约束（如过敏），无法适应开放式修正。合成数据提供了丰富的组合语言模式。
6. **分层结构优于平坦策略**：平坦策略常退化为全部清理或无法处理部分指令，而分层架构在每一步重新检查提示，更好维护多步一致性。

## 7. 优点

- **创新性**：将两个VLM（高层+低层）以分层方式组合，使用合成数据生成实现开放式交互，是首创。
- **实用性强**：系统在多种真实机器人上工作，能够处理模糊指令、实时纠错、多步骤任务，展现了良好的通用性。
- **数据效率**：仅使用少量人类演示+合成生成，无需大量人工标注交互数据。
- **清晰的消融**：通过消融实验分别证明了合成数据和层次结构的重要性。
- **客观评估**：使用盲评，排除实验者偏倚；对比多种基线，包括使用GPT-4o等外部模型。

## 8. 不足与局限

- **高层和低层模型独立训练**：彼此不了解对方的能力，可能导致高层发布了低层无法执行的命令。未来应通过联合训练或在线反馈耦合。
- **依赖少量Prompt工程**：合成数据生成需要精心设计提示以产生有效示例，泛化性受限。
- **缺乏长期记忆**：高层模型无记忆机制，在需要长期上下文推理的任务中可能失败（文中承认）。
- **实验覆盖有限**：仅在三个具体任务上测试，未在更大范围或未知环境中评估。且每个任务单独训练高层策略，未验证多任务统一模型。
- **偏差风险**：训练数据可能偏向某些物品或场景，导致在分布外物品（如“bermuda triangle”）或罕见约束下失败。
- **物理限制**：低层策略有时会暂时忽略指令（如靠近奶酪时抓奶酪，尽管用户要求不加奶酪），由于训练数据中对象接近性形成的偏差。
- **对失败恢复未充分研究**：物品掉落等错误恢复能力弱，训练数据未包含对抗性干扰或纠正。
- **算力需求**：虽然推理可在消费级GPU上运行，但训练仍需要高端H100集群，对于普通实验室有一定门槛。

（完）
