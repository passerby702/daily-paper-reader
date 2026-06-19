---
title: "Controlling metal-carbonate phase, form, and function through de novo protein design"
title_zh: 通过从头蛋白质设计控制金属碳酸盐的相、形态与功能
authors: "Kwon, P. S., Li, X., Yu, L. T., Pyles, H., Lewis, T. H., Weidle, C., Borst, A. J., Bodinger, C. C., Kang, A., Nguyen, H., Mendoza, J., Carr, K. D., Coventry, B., Hsia, Y., Molnar, Z., Li, D., Zhang, B., Cossairt, B. M., Zhang, S., Bera, A. K., De Yoreo, J., Baker, D."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.730916v1.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 微调扩散模型用于控制矿化的蛋白质设计
tldr: 生物矿化通过蛋白质控制无机晶体，但天然蛋白难以应用。本研究利用深度学习设计可重构二维蛋白质阵列，模板化方解石纳米晶；通过改进RFdiffusion2设计选择性形成文石的蛋白质架构；进一步设计晶格匹配的蛋白质模板，促进碳酸钴形成，其中D3笼组装体在内部生成均质碳酸钴，作为碱性水分解电催化剂。
source: biorxiv
selection_source: fresh_fetch
motivation: 天然生物矿化蛋白常无序、异质或难溶，难以指导工程材料设计，需探索从头设计方法。
method: 基于RFdiffusion2微调重复蛋白骨架，设计可调控碳酸钙多晶型及碳酸钴形貌的蛋白质界面与笼组装体。
result: 实现了方解石纳米晶模板、选择性文石形成、碳酸钴可控生长，D3笼-碳酸钴杂化材料展现电催化活性。
conclusion: 深度学习设计蛋白质-矿物复合材料，可精确控制无机相、形态与功能，拓展至电催化应用。
---

## 摘要
生物矿化使得生命系统能够通过蛋白质及其他生物分子控制无机晶体的位置、取向和多晶型，从而构建杂化材料。尽管经过数十年的研究，这些过程背后的分子原理仍难以在工程材料中加以利用，部分原因是天然生物矿化蛋白通常具有内在无序性、异质性或不溶性。在此我们展示，从头设计的蛋白质界面可以组装成可重构的二维阵列，这些阵列作为方解石纳米晶的模板。通过在重复蛋白支架上微调RFdiffusion2，我们进一步实现了蛋白质结构的设计，这些结构在成核条件下选择性形成文石——碳酸钙的一种亚稳态多晶型，而其他条件下则会导致相混合。超越生物系统中存在的无机物，我们展示了晶格匹配的蛋白质设计能够模板化碳酸钴的形成：平坦的螺旋重复蛋白界面促进无约束生长，而可溶的D3笼状组装体则产生限制在笼内的更均匀的碳酸钴纳米晶。这些蛋白质笼-碳酸钴杂化材料可作为碱性水分解的电催化剂。我们的结果展示了基于深度学习的方法在解锁蛋白质-矿物复合物的结构与功能活性方面的潜力。

## Abstract
Biomineralization enables living systems to construct hybrid materials by controlling the location, orientation, and polymorph of inorganic crystals with proteins and other biomolecules. Despite decades of study, the molecular principles underlying these processes remain difficult to harness in engineered materials, in part because native biomineralization proteins are often intrinsically disordered, heterogeneous, or insoluble. Here we show that de novo designed protein interfaces can be assembled into reconfigurable two-dimensional arrays which template calcite nanocrystals. By fine-tuning RFdiffusion2 on repeat protein scaffolds, we further enable the design of protein architectures which selectively form aragonite, a metastable polymorph of calcium carbonate, in nucleation conditions that otherwise result in a mixture of phases. Extending beyond inorganics found in biological systems, we show that lattice-matched protein designs template cobalt carbonate formation: a flat helical repeat protein interface promotes unconfined growth, whereas soluble D3 cage assemblies yield more homogenous cobalt carbonate nanocrystals confined to the interior of the cage. These protein-cage cobalt carbonate hybrid materials function as electrocatalysts for alkaline water splitting. Our results demonstrate the potential of deep learning-based methods to unlock the structural and functional activity of protein-mineral composites.