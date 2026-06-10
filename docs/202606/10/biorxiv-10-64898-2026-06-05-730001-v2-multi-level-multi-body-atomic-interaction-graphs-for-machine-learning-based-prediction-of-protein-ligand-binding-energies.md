---
title: "Multi-level, multi-body atomic interaction graphs for machine learning-based prediction of protein-ligand binding energies"
title_zh: 用于基于机器学习的蛋白质-配体结合能预测的多层级、多体原子相互作用图
authors: "Le, T. T. H., Nguyen, B. T., Vo, H., Nguyen, N. H., Nguyen, D. D."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.05.730001v2.full.pdf"
tags: ["query:pocket-lig"]
score: 6.0
evidence: 多层次原子交互图用于蛋白质-配体结合预测
tldr: 准确预测蛋白质-配体结合亲和力是药物设计的关键。传统评分函数复杂度高且泛化能力有限。本文提出GMI-Score，利用图表示建模多层次多体原子相互作用，融合成对与三体特征。在多个基准数据集上达到最高0.877的皮尔逊相关系数，并保持对数据泄漏和真实对接条件的鲁棒性。该方法为药物设计提供了高效准确的预测工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统评分函数计算复杂度高且泛化能力不足，亟需高效准确的结合能预测方法。
method: 构建多层次多体原子相互作用图，融合成对与三体特征，采用特征融合策略保持模型简洁。
result: 在PDBbind等数据集上Pearson相关系数达0.877，优于现有方法，且鲁棒性强。
conclusion: GMI-Score为药物设计提供准确鲁棒且泛化性强的结合能预测工具。
---

## 摘要
精确预测结合亲和力对于理性药物设计和发现至关重要。传统计算方法通常依赖复杂的评分函数，这些函数包含大量物理和化学描述符，导致计算需求高且有时泛化能力有限。在这项工作中，我们提出了一种新颖的评分函数，利用基于图的表示来建模多层级、多体原子相互作用。我们的方法构建了全面的相互作用图，其中包含成对和三重原子特征，有助于捕捉对结合亲和力预测至关重要的协作空间模式。通过采用特征融合策略，GMI-Score在保持模型简单性的同时提高了准确性。在多个数据集（如PDBbind v2013、PDBbind v2016、PDBbind v2020、CSAR-NRC-HiQ和PDBbind-Redocked）上的广泛评估表明，我们的模型持续优于最先进的评分函数，达到高达0.877的皮尔逊相关系数。此外，在严格的数据泄露控制和真实的对接条件下，它仍保持强大的预测能力，突显了其稳健性和泛化能力。

## Abstract
Accurate prediction of binding affinity is crucial for rational drug design and discovery. Traditional computational methods often rely on complex scoring functions that incorporate a multitude of physical and chemical descriptors, leading to high computational demands and sometimes limited generalizability. In this work, we propose a novel scoring function that models multi-level, multi-body atomic interactions using graph-based representations. Our method constructs comprehensive interaction graphs that incorporate both pairwise and triplet-wise atomic features that help capture cooperative spatial patterns essential for binding affinity prediction. By employing a feature fusion strategy, GMI-Score maintains model simplicity while enhancing accuracy. Extensive evaluation across multiple datasets, such as PDBbind v2013, PDBbind v2016, PDBbind v2020, CSAR-NRC-HiQ, and PDBbind-Redocked, demonstrates that our model consistently outperforms state-of-the-art scoring functions, achieving Pearson correlation coefficients up to 0.877. Furthermore, it retains strong predictive power under strict data leakage controls and realistic docking conditions to highlight its robustness and generalizability.