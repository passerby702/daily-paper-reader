---
title: AlphaFold3 for Structure-guided Ligand Discovery
title_zh: AlphaFold3用于结构指导的配体发现
authors: "Menon, K., Davasam, A., Chen, G., Bryant, C., Deng, Z., Lam, B., Yang, C., Barcelos, D., Liu, F., Alon, A., Lyu, J."
date: 2026-06-12
pdf: "https://www.biorxiv.org/content/10.64898/2025.12.04.692352v2.full.pdf"
tags: ["query:pocket-lig"]
score: 8.0
evidence: 蛋白质-配体复合物预测AlphaFold3虚拟筛选
tldr: "AlphaFold3在配体发现中的表现受限于训练集相似性和数据偏差，在回顾性富集中优于DOCK3但存在过拟合，在无偏差实验数据中整体富集不如DOCK3；前瞻性筛选σ2受体命中率13%低于DOCK3的两倍，但能产生近原生姿态。AF3是深度学习结构引导配体发现的补充工具，而非替代。"
source: biorxiv
selection_source: fresh_fetch
motivation: 系统评估AlphaFold3在结构引导配体发现中的真实性能，与经典分子对接对比。
method: 在DUDE-Z、三个实验数据集和σ2受体前瞻性筛选中，对比AF3与DOCK3的富集与命中率。
result: "AF3在DUDE-Z上富集更优但受偏差影响；实验数据中DOCK3整体富集更强；前瞻性命中率13%，低于DOCK3的两倍。"
conclusion: AF3是深度学习配体发现的起点，可作为对接的互补工具而非替代。
---

## 摘要
用于蛋白质结构预测的深度学习方法，如AlphaFold2（AF2）和RosettaFold（RF），已经改变了结构生物学并加速了下游生物学发现。更新的模型，包括AlphaFold3（AF3）和RosettaFold All-Atom（RFAA），将这一能力扩展到蛋白质-配体共折叠，使得能够直接从序列和配体输入预测结合复合物。这一进展提出了这样的可能性：这些模型不仅可以作为结构预测器，还可以作为基于AI的分子对接引擎用于虚拟筛选。然而，它们对配体发现的真正影响仍不清楚，并且在许多情况下存在争议。在这里，我们系统评估了AF3共折叠在中心任务（与小分子发现相关）中的表现，并与传统的分子对接进行比较。首先，对活性物质与诱饵的回顾性富集显示，AF3在DUDE-Z中的43个药物靶标上优于基于物理的对接程序DOCK3；然而，这一优势很大程度上是由计算诱饵集固有的隐藏配体仅偏差驱动的。相比之下，在三个大型实验数据集（sigma-2受体（σ2）、D4多巴胺受体（D4）、AmpC β-内酰胺酶（AmpC））中，包含超过2500个经过测试的分子，没有这种偏差，DOCK3实现了更强的整体富集，而AF3主要贡献于早期富集。其次，在AF3训练和验证截止之后沉积的超过8000个蛋白质-配体复合物上的样本外姿势重现显示，AF3的准确性强烈依赖于训练集的相似性，表明模型更多地是记忆原子位置，而不是学习分子识别的一般原理。最后，在针对AF3训练集新奇的σ2受体的首次前瞻性头对头筛选中，AF3实现了13%的命中率，并直接从筛选中识别出一个13 nM的结合物。然而，与平行的DOCK3活动相比，AF3的命中率低了两倍，尽管在前五个命中中产生了相似的亲和力分布。σ2受体与最有效的AF3衍生命中物结合的晶体结构证实AF3产生了近乎天然的配体姿势。因此，AF3代表了基于深度学习的结构指导配体发现的开始：一种互补工具，而非传统对接的替代品，在实际应用中既可作为筛选引擎，也可作为提高命中率的对接后滤波器。更广泛地说，这项工作为评估下一代深度学习共折叠模型并量化它们对小分子发现的影响建立了框架。

## Abstract
Deep-learning methods for protein structure prediction, such as AlphaFold2 (AF2) and RosettaFold (RF), have transformed structural biology and accelerated downstream biological discovery. More recent models, including AlphaFold3 (AF3) and RosettaFold All-Atom (RFAA), extend this capability to protein-ligand co-folding, enabling direct prediction of bound complexes from sequence and ligand inputs. This advance has raised the possibility that such models could function not only as structure predictors but also as AI-based molecular docking engines for virtual screening. Yet their true impact on ligand discovery remains unclear and, in many cases, controversial. Here, we systematically assess AF3 co-folding across tasks central to small-molecule discovery compared to conventional molecular docking. First, retrospective enrichment of actives over decoys showed that AF3 outperforms the physics-based docking program DOCK3 across 43 drug targets in DUDE-Z; however, this advantage is largely driven by hidden ligand-only biases inherent to computational decoy sets. In contrast, in three large experimental datasets (the sigma-2 receptor ({sigma}2), the D4 dopamine receptor (D4), AmpC {beta}-lactamase (AmpC)) with over 2,500 tested molecules that lack such biases, DOCK3 achieved stronger overall enrichment, while AF3 contributed mainly to early enrichment. Second, out-of-sample pose reproduction on >8,000 protein-ligand complexes deposited after the AF3 training and validation cutoff showed that AF3 accuracy is strongly dependent on training-set similarity, indicating that the model memorizes atomic positions more than learning general principles of molecular recognition. Finally, in the first prospective head-to-head screen against the {sigma}2 receptor, novel to AF3's training set, AF3 achieved a 13% hit rate and identified a 13 nM binder directly from the screen. However, compared with the parallel DOCK3 campaign, AF3 delivered a two-fold lower hit rate, despite yielding a similar affinity distribution among the top five hits. A crystal structure of the {sigma}2 receptor bound to the most potent AF3-derived hit confirmed that AF3 produced a near-native ligand pose. AF3 therefore represents the beginning of deep-learning-based structure-guided ligand discovery: a complementary tool rather than a replacement for conventional docking, with practical applications both as a screening engine and as a post-docking filter that improves hit rates. More broadly, this work establishes a framework for evaluating next-generation deep-learning co-folding models and quantifying their impact on small-molecule discovery.

---

## 论文详细总结（自动生成）

好的，这是根据您提供的论文内容生成的结构化、深入、客观的中文总结。

### 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：以 AlphaFold3 (AF3) 为代表的深度学习蛋白质-配体共折叠模型，能否作为高效的分子对接引擎，用于实际的、结构引导的先导化合物发现？与经典的物理原理分子对接（如 DOCK3）相比，其真实表现如何？
- **研究动机**：AF3 等模型可以直接从序列和配体输入预测结合复合物结构，这引发了其直接作为AI对接引擎进行虚拟筛选的广泛期待。然而，其在实际配体发现中的价值尚不明确，甚至存在争议。
- **整体含义**：本文旨在通过系统的回顾性、样本外和前瞻性实验，客观评估 AF3 在配体发现中的优势和局限性。研究结果表明，AF3 并非传统对接的替代品，而是一个有互补价值的工具，尤其适合作为早期富集指标或对接后过滤器。

### 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将 AF3 共折叠方法应用于虚拟筛选的核心任务：富集（区分活性分子与非活性分子）、姿势重现（预测正确的结合模式）和前瞻性命中发现。通过与传统对接方法 DOCK3 进行全面的头对头比较，揭示 AF3 的真实性能边界。
- **关键技术细节**：
    1.  **Template-based AF3 co-folding**：为了加速预测（从~20分钟降低到~2分钟），研究者向 AF3 提供实验结构的蛋白质模板，避免耗时的多序列比对（MSA）。这使大规模筛选成为可能。
    2.  **AF3 评分指标**：使用 AF3 输出的两个置信度指标作为筛选排序依据：
        - **ipTM (interface predicted Template Modeling score)**：衡量预测的蛋白质-配体界面的置信度，越高越好。
        - **mPAE (mean Predicted Aligned Error)**：衡量模型的不确定性，越低越好。
    3.  **Ligand-only pTM**：仅输入配体SMILES，不提供任何蛋白质信息，用于检测计算基准（如DUDE-Z）中存在的配体化学偏差。
    4.  **物理合理性验证**：使用 **PoseBusters** 框架过滤掉具有化学或结构不合理（如键角应变、空间冲突）的预测复合物，确保富集信号不是由伪影驱动。
    5.  **交互指纹分析**：使用 **LUNA** 工具计算蛋白质-配体相互作用指纹（PLIF），评估 AF3 预测的复合物是否恢复了关键的生物学相互作用（如氢键、盐桥、π-π堆积），而不仅仅是位置上的接近。
    6.  **相似性指标**：使用多种指标量化预测配体/口袋与 AF3 训练集分子的相似性，检验模型泛化能力：
        - **2D 相似性**：基于 Morgan 指纹的 Tanimoto 系数 (Tc)。
        - **3D 相似性**：使用 OpenEye ROCS 的 ComboROCS 分数，衡量分子形状和化学特征的3D叠加。
        - **口袋相似性**：使用 APoc 的 PS-Score，衡量结合口袋的几何和序列相似性。
        - **组合指标**：将 3D 相似性与口袋相似性相乘（ComboROCS × PS-Score），作为最有效的“记忆效应”预测因子。
    7.  **Boltz-2 重打分**：使用更新的 AF3 复现模型 Boltz-2 的亲和力预测模块（binding likelihood 和 log10(IC50)）对前瞻性筛选结果进行重打分。

### 实验设计：数据集、基准测试与对比方法

- **数据集与基准测试**：
    1.  **DUDE-Z 基准**：包含43个药物靶标的标准对接基准，每个靶标有实验活性分子和性质匹配的诱饵。用于评价**回顾性富集**和**样本内姿势重现**。
    2.  **大型实验测试集**：来自先前大规模对接活动，无化学偏差的三大数据集：
        - **σ2 受体 (σ2)**、**D4 多巴胺受体 (D4)**、**AmpC β-内酰胺酶 (AmpC)**。共包含超过 2500 个经过实验测试的分子。
    3.  **样本外测试集**：作者自行构建，包含 AF3 训练和验证截止日期后（2023年1月至2024年12月）沉积的 **8,076 个**蛋白质-配体复合物晶体结构，用于评估 **样本外泛化能力**。
    4.  **前瞻性筛选**：对 **σ2 受体**（为AF3训练集不可见的新靶标）进行头对头筛选，从 **69 万个** Enamine 在库分子（单阳离子）中筛选命中分子。

- **对比方法**：
    - **AF3**（主要方法）: 使用 ipTM 和 mPAE 作为评分指标。
    - **DOCK3**（基准方法）: 经典的基于物理的分子对接程序，使用其能量评分。
    - **Ligand-only AF3**: 作为消融实验，验证偏差影响。
    - **ComboROCS**: 评估 3D 形状和化学特征相似性对富集的影响。
    - **Boltz-2**: 作为前瞻性重打分方法。

### 资源与算力

- **前瞻性 σ2 受体筛选**（AF3 vs. DOCK3）：
    - **AF3**：共消耗 **23,000 GPU 小时** (使用 A100 GPU)。
    - **DOCK3**：共消耗 **673 CPU 小时**（使用普通硬件）。
    - **综合效率差距**：AF3 的计算成本是 DOCK3 的约 6,700 倍（考虑硬件价格差异和运行时长）。
- **AF3 模型训练**：文中提及类似模型训练需约 **128块 A100 (80GB) GPU 运行一个月**，估计云端花费约 **40万美元**。
- **AF3 单次预测**：有模板时约 2 分钟，无模板时约 20 分钟。

### 实验数量与充分性

- **实验数量**：非常充分，涵盖了配体发现的各个关键步骤：
    - **回顾性**：在DUDE-Z的43个靶标上进行了富集和姿势重现测试。
    - **大实验数据集**：在3个大型、无偏的靶标验证集（σ2, D4, AmpC）上评估了富集。
    - **泛化性**：在超过8,000个复杂结构上进行了大规模的样本外姿势重现和交互重建分析，并深入探讨了训练集相似性的影响。
    - **前瞻性**：完成了一项完整的前瞻性头对头筛选，包括购买、测试和晶体结构验证。
- **充分性与公平性**：
    - **充分**：实验设计全面，从回顾性到前瞻性，从简单基准到真实实验数据，覆盖了模型评估的多个维度。
    - **客观公平**：
        - 主动揭示了DUDE-Z基准中存在的**数据偏差（ligand-only bias）**，证明AF3在该基准上的优势是误导性的，并使用了无偏的实验数据集进行校正，体现了严谨性。
        - 在前瞻性筛选中对两种方法的命中选择过程（多样性聚类、过滤标准等）保持一致，保证了比较的公平性。
        - 公开了所有代码和数据集（如Github链接），有利于复现和后续研究。

### 论文的主要结论与发现

1.  **AF3 在回顾性基准上的优势具有欺骗性**：在 DUDE-Z 上，AF3 的富集效果优于 DOCK3，但这一优势主要归因于**配体独特的化学偏差**。仅使用配体信息的 AF3 (ligand-only pTM) 也能取得相当好的结果，证明 AF3 并未真正“理解”蛋白质-配体相互作用。
2.  **在无偏实验数据上，DOCK3 整体表现更强**：在σ2、D4 和 AmpC 三个大型实验数据集上，DOCK3 的整体富集（AUC）显著优于 AF3。但 AF3 在**早期富集**（如 logAUC、EF10）上表现更好，表明其更适合作为**对接后重打分过滤器**。
3.  **AF3 存在严重的“死记硬背”而非“理解”问题**：在超过 8000 个新复合物上的测试表明，AF3 的姿势预测成功率**强烈依赖于预测分子与训练集中分子的 3D 形状和口袋相似性**。对于新颖的配体和口袋，AF3 经常能正确放置口袋，但配体姿势错误，且即使姿势正确，关键的生物学**相互作用网络也常常未能复现**（62%的案例PLIF恢复不达标）。
4.  **前瞻性筛选中，AF3 的命中率更低，但能产生高亲和力分子和正确姿势**：
    - **命中率**：AF3 为 **13%**，远低于 DOCK3 的 **25%**。
    - **亲和力**：尽管命中率低，但 AF3 顶部命中的亲和力分布与 DOCK3 相当（最佳为 13 nM vs 32 nM）。
    - **结构验证**：通过 X 射线晶体学证实，AF3 对最佳命中分子的预测姿势与实验晶体结构高度一致（配体重原子RMSD为1.8 Å），证明了其在确定真实活性的结合模式方面的可靠性。其局限性在于**评分和排序**能力，而非“建模”能力。
5.  **总体结论**：AF3 是深度学习结构引导配体发现的**开端**，是一个**互补工具而非替代品**。它在早期富集和重打分方面有潜力，但受限于训练集依赖、高昂计算成本和整体较低的命中率，无法撼动物理对接（如 DOCK3）在当前大规模筛选中的主导地位。

### 优点：方法或实验设计上的亮点

- **系统性评估**：从多个维度（富集、姿势、泛化、前瞻性）系统评估了 AF3，结论全面且具有说服力。
- **揭示数据偏差**：精准识别并量化了DUDE-Z等计算基准的隐藏偏差，为深度学习方法的基准测试提供了重要警示。
- **严格的泛化性测试**：构建了大规模样本外数据集，并通过多种相似性指标揭示了AF3的“记忆”本质，结论扎实。
- **前瞻性头对头验证**：完成了真正的前瞻性筛选，并辅以晶体结构验证，使研究结论具有很高的实际指导价值。
- **清晰的定位**：研究并未简单否定AF3，而是客观地指出了其优势和局限性，并提出了具体的应用场景（如对接后过滤器），具有很强的实用性。
- **公开资源**：公开了模型评估的数据集和代码，促进了该领域的可重复性研究。

### 不足与局限：包括实验覆盖、偏差风险、应用限制

- **靶标多样性有限**：前瞻性筛选仅针对 σ2 受体（单阳离子结合蛋白），可能无法代表 AF3 在所有靶标类型上的表现。对于结合大分子、柔性配体的靶标，AF3 可能表现更好，但受限于商用常规类药分子库，难以测试。
- **计算成本过高**：AF3 的 GPU 成本是 DOCK3 的数千倍，这使其无法像物理对接那样应用于>10^7 级别的超大规模库筛选，限制了其实际应用规模。
- **训练集依赖性**：AF3 对训练集相似性高度依赖，这构成其核心局限。对于结构新颖的靶标或化学型，其预测能力会急剧下降。作者将此归因于“空间位置记忆”而非“物理规律学习”，暗示了模型架构上的根本性问题。
- **评分指标与亲和力不相关**：AF3的置信度指标（ipTM, mPAE）与实验结合亲和力（Ki）的相关性很弱，表明其不适合用于预测活性强度。
- **前瞻性命中率低**：尽管能产生正确姿势，但其筛选的命中率仅为物理对接的一半，说明其作为一种独立的虚拟筛选引擎，效率不高。
- **测试环境与真实药物发现的差异**：前瞻性筛选使用了相对较小的在库库库，而成功的大规模对接通常依赖于更大的、按需合成的虚拟库。AF3目前无法处理后者。

（完）
