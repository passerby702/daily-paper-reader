---
title: "Multi-level, multi-body atomic interaction graphs for machine learning-based prediction of protein-ligand binding energies"
title_zh: 基于多层次、多体原子相互作用图的蛋白质-配体结合能机器学习预测
authors: "Le, T. T. H., Nguyen, B. T., Vo, H., Nguyen, N. H., Nguyen, D. D."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.05.730001v2.full.pdf"
tags: ["query:pocket-lig"]
score: 6.0
evidence: 多层级原子相互作用图用于蛋白质-配体结合预测
tldr: 药物设计中蛋白-配体结合亲和力的精确预测至关重要。传统方法依赖复杂评分函数，计算成本高且泛化性有限。本文提出GMI-Score，用图表示建模多层次、多体原子相互作用，捕获配对和三元组空间特征。在多个数据集上Pearson相关系数最高达0.877，一致优于现有方法，且在数据泄漏控制和真实对接条件下表现稳健。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统评分函数计算成本高、泛化性差，需设计能有效捕获高阶原子相互作用的轻量级评分模型。
method: 构建多层级多体原子交互图，融合配对与三元组特征，通过特征融合策略保持模型简洁性。
result: 在PDBbind v2013等五个数据集上Pearson系数最高0.877，均优于现有评分函数。
conclusion: 统一图框架系统捕获高阶交互，提升预测准确性与鲁棒性，适用于规模化分子建模。
---

## 摘要
准确预测结合亲和力对于合理药物设计与发现至关重要。传统计算方法通常依赖于整合大量物理与化学描述符的复杂评分函数，导致计算需求高且泛化能力有时受限。本文提出了一种新颖的评分函数，利用基于图的表示对多层次、多体原子相互作用进行建模。该方法构建了包含成对和三体原子特征的综合性相互作用图，有助于捕捉对结合亲和力预测至关重要的协同空间模式。通过采用特征融合策略，GMI-Score在保持模型简洁性的同时提高了准确性。在多个数据集（如PDBbind v2013、PDBbind v2016、PDBbind v2020、CSAR-NRC-HiQ和PDBbind-Redocked）上的广泛评估表明，我们的模型始终优于最先进的评分函数，皮尔逊相关系数最高达到0.877。此外，在严格的数据泄漏控制和真实对接条件下，它仍保持强大的预测能力，凸显了其鲁棒性和泛化能力。

科学贡献：在本研究中，我们提出了一种评分方法，在统一的图框架内系统地捕捉高阶原子相互作用，实现了化学信息学评分函数的概念性转变。该方法在重新对接和保留数据集上始终优于现有方法并展现出强大的有效性，证明了其在大规模分子建模应用和开放化学信息学工作流程中的实用性。

## Abstract
Accurate prediction of binding affinity is crucial for rational drug design and discovery. Traditional computational methods often rely on complex scoring functions that incorporate a multitude of physical and chemical descriptors, leading to high computational demands and sometimes limited generalizability. In this work, we propose a novel scoring function that models multi-level, multi-body atomic interactions using graph-based representations. Our method constructs comprehensive interaction graphs that incorporate both pairwise and triplet-wise atomic features that help capture cooperative spatial patterns essential for binding affinity prediction. By employing a feature fusion strategy, GMI-Score maintains model simplicity while enhancing accuracy. Extensive evaluation across multiple datasets, such as PDBbind v2013, PDBbind v2016, PDBbind v2020, CSAR-NRC-HiQ, and PDBbind-Redocked, demonstrates that our model consistently outperforms state-of-the-art scoring functions, achieving Pearson correlation coefficients up to 0.877. Furthermore, it retains strong predictive power under strict data leakage controls and realistic docking conditions to high-light its robustness and generalizability.

Scientific ContributionIn this study, we present a scoring methodology that systematically captures higher-order atomic interactions within a unified graph framework, making a conceptual shift in cheminformatics scoring functions. Its consistent outperformances of existing methods and strong validity under redocked and withheld atascenarios demonstrate its utility for broad-scale molecular modeling applications and open heminformaticsworkflows.