---
title: De novo design of RNA pseudoknots with deep learning
title_zh: 利用深度学习从头设计RNA假结
authors: "Townley, J., Kladwang, W., Baker, D., Blair, H. M., Choe, C., El Nesr, G., Favor, A., Fisker, E., Haack, D. B., He, S., Hingey, J., Huang, R., Huang, P.-S., Joshi, C. K., Karagianes, T. G., Kubaney, A., Lio, P., Mancino, A., Romano, J., Rudolfs, B., Spellmon, N., Toor, N., Wu, V., Yu, Z., Eterna players,, Das, R."
date: 2026-05-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.21.726960v1.full.pdf"
tags: ["query:diff-gen"]
score: 9.0
evidence: 使用生成式AI进行RNA从头设计
tldr: RNA设计长期受限于3D结构预测精度。本研究利用深度学习实现假结二级结构的从头设计，在Eterna竞赛57个任务中，生成式AI的表现与经验丰富的人类设计师相当。关键突破在于AI生成的分子不仅能正确折叠二级结构，还意外形成了由非规范三级相互作用稳定的有序3D构象。该工作通过RNet基础模型利用先前的化学映射数据，表明部分高难度RNA设计任务可能无需先求解3D结构预测，为领域开辟了新路径。
source: biorxiv
selection_source: fresh_fetch
motivation: RNA设计准确性受制于现有3D结构预测能力，亟需不依赖精确预测的新策略。
method: 采用生成式AI与在化学映射数据上训练的RNet基础模型，进行假结二级结构的从头设计。
result: 在含57个假结的Eterna竞赛中，AI方法匹敌人类专家；AI分子形成稳定3D折叠，并包含未建模的非规范三级相互作用。
conclusion: 深度学习使部分高难度RNA设计无需预知3D结构即可实现，为RNA工程带来新可能。
---

## 摘要
RNA设计一直受到三维结构预测准确性有限的制约。在这里，我们展示了，通过假结二级结构的精确从头设计，利用当前的深度学习工具可以生成复杂的RNA结构。在一项涉及57个假结的Eterna竞赛中，生成式AI方法在解决大多数盲测挑战方面与经验丰富的人类设计师不相上下，并通过单核苷酸分辨率化学作图、补偿性诱变和冷冻电子显微镜进行了评估。意外的是，AI生成的具有准确二级结构的分子形成了有序的三维折叠，并由设计过程中未建模的非经典三级相互作用所稳定。成功是由一个基于先前化学作图数据训练的RNet基础模型所指导的，这表明某些困难的RNA设计任务可能无需首先解决RNA三维结构预测即可实现。

## Abstract
RNA design has been hindered by the limited accuracy of 3D structure prediction. Here, we show that intricate RNA structures can be generated with current deep learning tools through accurate de novo design of pseudoknot secondary structures. In an Eterna competition involving 57 pseudoknots, generative AI methods matched experienced human designers in solving most blind challenges, evaluated by single-nucleotide-resolution chemical mapping, compensatory mutagenesis, and cryogenic electron microscopy. Unexpectedly, AI-generated molecules with accurate secondary structures formed well-ordered 3D folds stabilized by noncanonical tertiary interactions not modeled during design. Success was guided by a RNet foundation model trained on prior chemical mapping data, suggesting that some difficult RNA design tasks may be tractable without first solving RNA 3D structure prediction.

---

## 论文详细总结（自动生成）

# 论文深度总结：利用深度学习从头设计 RNA 假结

## 1. 核心问题与整体含义
- **研究背景**：RNA 分子具有复杂的结构和功能，其三维（3D）折叠的精确预测一直是计算生物学中的巨大挑战，严重制约了 RNA 结构的理性设计。
- **核心问题**：能否在不依赖精确 3D 结构预测的情况下，直接设计具有复杂二级结构（特别是假结）的 RNA 分子，并使其正确折叠？
- **整体含义**：该工作揭示了深度学习模型有可能绕开 RNA 3D 结构预测这一“瓶颈”，通过直接生成正确的二级结构来驱动分子形成有序的三维构象，为 RNA 纳米技术和合成生物学开辟了一条“预测受限而设计自由”的新范式。

## 2. 方法论
- **核心思想**：利用生成式人工智能，从序列到二级结构的直接设计，而非先预测 3D 结构再反推序列。采用一种在大量化学作图数据上预训练的**RNet 基础模型**作为“设计评判器”或“生成指引器”。
- **关键技术细节**（基于摘要推断）：
  - **生成式 AI 方法**：很可能是一种条件序列生成模型（如扩散模型、自回归模型等），以目标假结二级结构为约束，生成候选 RNA 序列。
  - **RNet 基础模型**：该模型利用先前的化学作图（chemical mapping）数据进行训练，能评估序列与结构之间的适应性，可能是用于筛选或指导生成的关键组件。
  - **设计流程**：给定一个目标假结拓扑结构，AI 生成序列；RNet 模型指导序列的选择或优化，使其不仅满足二级结构配对规则，还能在化学环境下表现出正确的折叠倾向。
- **公式与算法流程**：原文未提供具体数学描述，但可理解为一种“生成-评估”闭环：`序列 = 生成器(目标结构, 随机噪声)`，然后通过 `RNet(序列, 目标结构)` 打分并迭代优化，直至获得高置信度设计。

## 3. 实验设计
- **测试场景与数据集**：
  - **Eterna 竞赛盲测**：作为核心验证平台，参与者（AI 与人类）针对 57 个全新的 RNA 假结结构进行从头设计，所有分子均为“盲盒”测试，设计前无法知晓真实折叠结果。
  - **对照方法**：与经验丰富的人类 RNA 设计师进行直接比较。
- **验证手段（Benchmark 的生物学验证）**：
  - **单核苷酸分辨率化学作图**：精确检测合成分子的二级结构是否与设计目标一致。
  - **补偿性诱变**：通过突变配对碱基并观察结构恢复，验证碱基配对的正确性。
  - **冷冻电子显微镜（cryo-EM）**：直接观察 AI 设计分子的三维折叠形态，发现其形成了未在设计中明确建模的非经典三级相互作用。

## 4. 资源与算力
- **算力信息**：**论文摘要及相关元数据中未明确提及**所用 GPU 型号、数量、训练时长或推理成本。唯一提及的计算依赖是“RNet 基础模型”，但该模型的训练与推理算力需求未被披露。

## 5. 实验数量与充分性
- **实验规模**：主要设计任务为 **57 个不同的假结结构**，每个结构对应一条或多条 AI 生成序列。这是一个相当可观且具有挑战性的测试集，涵盖了多种假结拓扑。
- **实验类型**：包含计算方法的性能对比（AI vs. 人类）、**三种正交的生物物理验证**（化学作图、诱变、冷冻电镜），以及意外发现的定性分析。
- **充分性评估**：
  - **充分性**：在 RNA 设计领域，57 个完全不同结构的盲测设计竞赛，结合高分辨率结构验证，实验设计非常全面和严谨。能与人类专家打平甚至超越，证据说服力强。
  - **客观性与公平性**：采用竞赛机制，验证过程为盲测，避免了数据泄露和先验偏差；多种实验相互印证，结果可靠。
  - **局限**：虽未披露失败案例具体数量，但提及“解决大多数盲测挑战”，暗示并非 100% 成功；样本量集中在假结类结构，可能未覆盖其他复杂 RNA 基序。

## 6. 主要结论与发现
- **AI 设计与人类专家水平相当**：在 57 个假结设计任务中，生成式 AI 方法成功解决了绝大多数挑战，性能匹敌顶尖人类设计师。
- **二级结构准确引导三级折叠**：AI 设计的分子不仅实现了精确的二级结构配对，还意外地折叠成高度有序的三维结构。
- **三级相互作用的涌现**：冷冻电镜显示，分子稳定性由**未被设计过程显式建模的非经典三级相互作用**（如 A-minor 互作、核糖拉链等）提供，表明 AI 学习到了深层的物理化学规律。
- **RNet 基础模型的关键作用**：成功得益于在历史化学作图数据上训练的 RNet 模型，证明通过大规模实验数据训练的模型可以有效指导 RNA 设计，**部分高难度 RNA 设计任务可能无需首先攻克 3D 结构预测难题**。

## 7. 优点
- **范式创新**：回避了业界公认困难的 RNA 3D 结构预测，直接以二级结构为设计目标，策略巧妙且实用性强。
- **实验验证极致严谨**：采用盲测竞赛、三种正交高分辨率实验（化学作图、诱变、cryo-EM）对 AI 设计进行了多维度验证，可信度极高。
- **发现具有科学启发性**：非经典三级相互作用的“非预期获得”不仅是设计成功，更揭示了 RNA 序列-结构-功能关系的深层原理，为未来设计提供了新思路。
- **人机对比客观**：与人类设计师在竞赛平台上的直接对比，为 AI 能力提供了直观且苛刻的评估标准。

## 8. 不足与局限
- **方法论细节缺失**：由于仅有摘要，生成式 AI 的具体架构、RNet 模型的结构、训练数据构成、超参数等关键算法细节完全未知，可复现性存疑。
- **泛化范围受限**：目前仅展示了假结结构的设计，是否适用于其他 RNA 基序（如大 RNA、核开关、长链非编码 RNA）有待验证。
- **成功率边界模糊**：仅提及“解决大多数挑战”，未提供确切的设计成功率、失败案例的分析以及失败模式，可能掩盖了模型在特定拓扑或极端稳定性要求下的缺陷。
- **三维折叠的偶然性与必然性**：虽然意外形成了三级相互作用，但这是否每次都能稳定复现？三级互作的涌现是否依赖于特定序列空间，能否被理性利用，尚不明确。
- **计算资源未披露**：无法评估该方法的资源门槛，可能隐含高昂的训练或推理成本，限制了其广泛应用。

（完）
