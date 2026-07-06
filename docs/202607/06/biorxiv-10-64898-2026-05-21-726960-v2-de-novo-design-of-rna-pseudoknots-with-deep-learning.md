---
title: De novo design of RNA pseudoknots with deep learning
title_zh: 基于深度学习的RNA假结从头设计
authors: "Townley, J., Kladwang, W., Baker, D., Blair, H. M., Choe, C., El Nesr, G., Favor, A., Fisker, E., Haack, D. B., He, S., Hingey, J., Huang, R., Huang, P.-S., Joshi, C. K., Karagianes, T. G., Kubaney, A., Lio, P., Mancino, A., Romano, J., Rudolfs, B., Spellmon, N., Toor, N., Verma, J., Wu, V., Yu, Z., Eterna players,, Das, R."
date: 2026-07-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.21.726960v2.full.pdf"
tags: ["query:diff-gen"]
score: 8.0
evidence: 利用深度学习生成AI从头设计RNA假结
tldr: RNA设计长期受限于3D结构预测的低准确性。本研究利用深度学习，通过设计假结二级结构来生成复杂RNA。基于RNet模型，在Eterna竞赛中，AI生成的分子在57个假结挑战中达到与人类专家相当的水平，并通过化学图谱和冷冻电镜验证了其准确折叠。结果表明，无需攻克3D预测难题，也能实现困难RNA的设计。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有RNA设计受制于3D结构预测精度不足，需要新方法绕过这一瓶颈。
method: 使用基于化学作图数据预训练的RNet模型，从头设计假结二级结构，并通过优化序列实现稳定折叠。
result: AI在57个假结竞赛盲测中与人类专家匹敌，生成的分子形成有序3D折叠，其非经典三级相互作用未在设计时建模。
conclusion: RNA设计可以不依赖精确的3D结构预测，仅通过二级结构设计和深度学习即可完成复杂任务。
---

## 摘要
RNA设计一直受到3D结构预测精度有限的阻碍。在这里，我们展示了通过精确的假结二级结构从头设计，可以利用当前的深度学习工具生成复杂的RNA结构。在一项涉及57个假结的Eterna竞赛中，生成式AI方法在解决大多数盲挑战方面与经验丰富的人类设计师相当，通过单核苷酸分辨率化学映射、补偿性诱变和冷冻电镜进行评估。具有精确二级结构的AI生成分子形成了有序的3D折叠，并由设计过程中未建模的非规范三级相互作用稳定。成功得益于基于先前化学映射数据训练的RNet基础模型，这表明一些困难的RNA设计任务可能无需先解决RNA 3D结构预测即可处理。

## Abstract
RNA design has been hindered by the limited accuracy of 3D structure prediction. Here, we show that intricate RNA structures can be generated with current deep learning tools through accurate de novo design of pseudoknot secondary structures. In an Eterna competition involving 57 pseudoknots, generative AI methods matched experienced human designers in solving most blind challenges, evaluated by single-nucleotide-resolution chemical mapping, compensatory mutagenesis, and cryogenic electron microscopy. AI-generated molecules with accurate secondary structures formed well-ordered 3D folds stabilized by noncanonical tertiary interactions not modeled during design. Success was guided by an RNet foundation model trained on prior chemical mapping data, suggesting that some difficult RNA design tasks may be tractable without first solving RNA 3D structure prediction.

---

## 论文详细总结（自动生成）

### 论文详细中文总结

#### 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：RNA 的从头设计长期受限于现有计算工具在三维（3D）结构预测上的低准确性，特别是对于复杂拓扑结构（如假结）的设计，远落后于蛋白质设计领域。
- **整体含义**：本研究证明，通过聚焦于二级结构（假结）的精准设计，并利用基于大规模化学图谱数据训练的深度学习模型（RNet），可以在不依赖精准 3D 结构预测的前提下，自动化设计出复杂、稳定且三维折叠有序的 RNA 假结。这为 RNA 功能设计（核酶、适体等）开辟了新路径。

#### 2. 论文提出的方法论
- **核心思想**：绕过 3D 预测瓶颈，以二级结构（假结配对模式）为设计目标，使用深度学习模型在序列空间进行探索与优化，并通过训练好的神经网络（RNet）预测化学图谱（SHAPE），将其作为可实验验证的反馈信号。
- **关键技术细节**：
    - **RNet 基础模型**：在约 100 万条 RNA 的 SHAPE 化学图谱数据上训练，能准确预测给定序列的二级结构相关反应性，被用作设计过滤与评分函数。
    - **多个 AI 设计框架**：
        - **MPNN-fixbb**：消息传递神经网络，在固定 3D 骨架（由模板或建模提供）上设计序列，类似 ProteinMPNN。
        - **gRNAde**：几何深度学习，进行 3D RNA 逆折叠，也有无需 3D 输入的无模型变体。
        - **Struct2SeQ**：基于深度 Q 强化学习的方法，完全由 RNet 模型引导设计。
        - **codesign-RFdiff**：结合坐标和序列的协同设计方法。
    - **设计流程**：给定目标假结二级结构 → AI 方法生成候选序列 → RNet 预测 SHAPE 反应性，计算与目标二级结构的一致性（OpenKnot 分数） → 过滤高分段进行实验验证（SHAPE 实验、补偿性诱变 M2R-seq、冷冻电镜结构解析）。
- **算法流程**：无显式公式，流程为“目标二级结构 → 序列生成（深度学习） → RNet 评分筛选 → 实验验证”。

#### 3. 实验设计
- **数据集与场景**：
    - **Eterna OpenKnot 竞赛**：共 57 个假结设计目标，分为 4 轮（Round 1-4）。
        - **Round 1/2**：17 个目标，来自 PDB 天然 RNA 3D 结构（11 个）和 Eterna 参与者提出的复杂合成结构（6 个），先进行未经反馈的设计（Round 1），再结合 RNet 反馈进行改进（Round 2）。
        - **Round 3/4**：各 20 个新目标，来源包括 PDB 结构（减少至 5 个）、Pseudobase 天然假结（5 个）、Eterna 提出结构（10 个），Round 4 目标长度达 117–240 nt。
    - **基准与对比方法**：
        - **人类基线**：Eterna 人类专家。
        - **AI 方法**：Rosetta、Rosetta-LoRes、3DRNA、gRNAde（及其无 3D 变体）、MPNN-RFdiff、MPNN-fixbb、codesign-RFdiff、Struct2SeQ、Struct2SeQ-SHAPE。
- **评估指标**：
    - **OpenKnot 分数**：基于 SHAPE 反应性与目标二级结构一致性的百分比（阈值>90 为成功）。
    - **M2R-seq 补偿性诱变**：验证单碱基对是否正确形成（通过双突变恢复效应，采用 Rescue Factor 和茎恢复率）。
    - **冷冻电镜（Cryo-EM）**：对成功设计中最高分辨率的三款（Struct2SeQ-SHAPE、MPNN-fixbb、gRNAde）进行 3D 结构解析。

#### 4. 资源与算力
- **明确提及**：Acknowledgments 部分提到 NVIDIA DGX Cloud 和 NSF NAIRR Pilot（分配 ID: NAIRR240281）为 Struct2SeQ 在 Round 4 提供工程支持。
- **未明确说明**：论文未给出具体 GPU 型号、数量、训练时长等详细算力信息。

#### 5. 实验数量与充分性
- **实验规模**：
    - 总共 57 个设计目标（4 轮），每个目标由多个 AI 方法与人类设计提交，涉及约 50,000 条序列（含单/双突变）。
    - SHAPE 实验覆盖所有设计的化学图谱。
    - M2R-seq 实验覆盖 Round 3 所有 20 个目标，每目标至少测试一个人类与每个 AI 方法的顶级设计。
    - Cryo-EM 聚焦于 Round 3 的一个代表性目标（P20，Kissing Multiloops），成功解析了 3 个 AI 设计（分辨率 2.9–4.8 Å）和 1 个二聚体结构。
- **充分性与公平性**：
    - **充分**：采用了多轮、多来源（天然、合成、长链）的盲测设计，使用独立且正交的验证手段（SHAPE + M2R-seq + Cryo-EM），统计检验（配对二项检验）显示多数 AI 方法间差异不显著。
    - **公平**：Round 1/2 中 AI 方法表现不佳，经 RNet 指导后 Round 2/3/4 迅速提升，部分方法（如 Struct2SeQ-SHAPE）在 Round 4 表现显著更优，但文中指出其有额外开发时间。整体对比在统一平台和同一目标集合上进行，透明度高。
    - **局限性**：仅一个目标（P20）进行了 Cryo-EM 验证，结构多样性有限；P16 等目标所有方法均失败，说明设计空间仍存在难题。

#### 6. 论文的主要结论与发现
- AI 方法（特别是结合 RNet）在不到一年时间内，达到了与人类专家相当甚至更优的从头设计假结能力，在 57 个目标中超过 95% 达到成功标准（OpenKnot >90）。
- 补偿性诱变（M2R-seq）证实绝大多数设计形成的碱基对准确，未出现严重替代配对。
- 冷冻电镜揭示 AI 设计的假结形成了与预测不一致但更为有序的 3D 折叠，并出现了未在设计中显式建模的非规范三级相互作用（如碱基三联体、非规范配对）。
- **关键发现**：RNA 复杂结构的可靠设计可以绕过精准 3D 结构预测，仅通过二级结构层面的深度学习（基于化学图谱训练）即可实现，这为 RNA 功能设计提供了新策略。

#### 7. 优点
- **方法先进**：首次将多种深度学习（MPNN、GNN、强化学习）成功应用于 RNA 假结的从头实验验证，创新性地利用大规模化学图谱数据训练模型（RNet）替代 3D 预测。
- **实验严谨**：结合大规模 SHAPE 图谱、高吞吐量补偿诱变（M2R-seq）和高分辨率结构解析（Cryo-EM），多维度验证设计准确性，显著提升了可信度。
- **开放科学**：所有数据（SHAPE 图谱、3D 结构、代码）均公开，Eterna 平台实现人机协作，具有高可重复性。
- **实用性**：AI 方法可在无 3D 结构情况下运行，降低了 RNA 设计的入口门槛，同时证明了跨长度（长达 240 nt）的设计能力。

#### 8. 不足与局限
- **3D 预测缺失**：虽然成功避开了 3D 预测瓶颈，但非规范三级相互作用未能显式设计，可能限制对复杂功能（如催化、配体结合）的精准控制。
- **验证范围有限**：Cryo-EM 仅详细分析了单一目标（P20）的三个 AI 设计，且仅有一个结构获高分辨率（2.9 Å），难以代表所有设计目标的折叠普适性。
- **失败案例**：仍有目标（如 P16）无法成功设计，表明某些复杂假结亚类仍构成挑战。
- **模型依赖风险**：RNet 训练数据来自 Eterna 历史实验，可能存在对某些 RNA 结构类型（如高度无序、含配体等）的偏差。
- **算力细节缺失**：未提供完整的训练与推理算力信息，限制了复现的精确估计。
- **统计显著性**：多数 AI 方法间差异不显著，最优方法可能取决于具体目标，尚无可通用的单一最优框架。

（完）
