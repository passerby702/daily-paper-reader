---
title: "Multi-level, multi-body atomic interaction graphs for machine learning-based prediction of protein-ligand binding energies"
title_zh: 基于多层次、多体原子相互作用图的机器学习预测蛋白质-配体结合能
authors: "Le, T. T. H., Nguyen, B. T., Vo, H., Nguyen, N. H., Nguyen, D. D."
date: 2026-06-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.05.730001v1.full.pdf"
tags: ["query:pocket-lig"]
score: 7.0
evidence: 蛋白质-配体结合能预测，支持配体设计评估
tldr: 蛋白-配体结合亲和力预测是药物设计的关键。传统评分函数计算复杂、泛化性差。本文提出GMI-Score，通过构建多层次多体原子交互图，融合成对与三元特征，实现高精度预测。在多个基准数据集上Pearson相关系数达0.877，且具备强鲁棒性，为药物筛选提供有效工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统评分函数依赖复杂物理化学描述符，计算成本高且泛化能力有限，亟需高效准确的预测方法。
method: 构建多层次多体原子交互图，融合成对和三元原子特征，采用特征融合策略保持模型简洁性。
result: 在PDBbind v2013等数据集上Pearson相关系数最高0.877，优于现有方法，且通过严格数据泄露和对接测试。
conclusion: GMI-Score在预测精度和泛化性上显著提升，为理性药物设计提供可靠评分函数。
---

## 摘要
准确预测结合亲和力对于理性药物设计和发现至关重要。传统计算方法通常依赖于整合大量物理和化学描述符的复杂打分函数，导致计算需求高且有时泛化能力有限。本文提出了一种新颖的打分函数，利用基于图的表示对多层次、多体原子相互作用进行建模。我们的方法构建了全面的相互作用图，融合了成对和三体原子特征，有助于捕捉对结合亲和力预测至关重要的协同空间模式。通过采用特征融合策略，GMI-Score在保持模型简洁性的同时提高了准确性。在多个数据集（如PDBbind v2013、PDBbind v2016、PDBbind v2020、CSAR-NRC-HiQ和PDBbind-Redocked）上的广泛评估表明，我们的模型始终优于最先进的打分函数，Pearson相关系数高达0.877。此外，在严格的数据泄漏控制和实际对接条件下，该模型仍保持强大的预测能力，凸显其鲁棒性和泛化能力。

## Abstract
Accurate prediction of binding affinity is crucial for rational drug design and discovery. Traditional computational methods often rely on complex scoring functions that incorporate a multitude of physical and chemical descriptors, leading to high computational demands and sometimes limited generalizability. In this work, we propose a novel scoring function that models multi-level, multi-body atomic interactions using graph-based representations. Our method constructs comprehensive interaction graphs that incorporate both pairwise and triplet-wise atomic features that help capture cooperative spatial patterns essential for binding affinity prediction. By employing a feature fusion strategy, GMI-Score maintains model simplicity while enhancing accuracy. Extensive evaluation across multiple datasets, such as PDBbind v2013, PDBbind v2016, PDBbind v2020, CSAR-NRC-HiQ, and PDBbind-Redocked, demonstrates that our model consistently outperforms state-of-the-art scoring functions, achieving Pearson correlation coefficients up to 0.877. Furthermore, it retains strong predictive power under strict data leakage controls and realistic docking conditions to highlight its robustness and generalizability.