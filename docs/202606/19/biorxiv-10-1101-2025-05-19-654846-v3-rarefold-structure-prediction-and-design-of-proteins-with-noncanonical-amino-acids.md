---
title: "RareFold: Structure prediction and design of proteins with noncanonical amino acids"
title_zh: RareFold：含有非标准氨基酸的蛋白质结构预测与设计
authors: "Li, Q., Daumiller, D., Zuo, F., Marcotte, H., Pan-Hammarstrom, Q., Bryant, P."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.1101/2025.05.19.654846v3.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 用于含有非天然氨基酸的蛋白质结构预测与设计的深度学习方法
tldr: 现有蛋白质结构预测和设计局限于20种标准氨基酸，无法处理非标准氨基酸（ncAA）。RareFold将每个残基作为独立token，学习跨化学多样性的原子相互作用模式，实现对含ncAA蛋白质的统一建模。基于此的EvoBindRare设计出针对核糖核酸酶A的线性/环肽结合剂，亲和力达低微摩尔（KD约2-9微摩尔），与天然配体相当。氢氘交换质谱证实结合界面，且在人源类器官模型上未检测到免疫激活，扩展了深度学习蛋白质设计至非标准化学空间。
source: biorxiv
selection_source: fresh_fetch
motivation: 扩展蛋白质设计至非标准氨基酸，突破传统20种氨基酸的限制。
method: 将每个残基作为独立token，学习跨化学多样性的原子相互作用模式，统一建模标准与非标准氨基酸。
result: 设计出针对核糖核酸酶A的线性/环肽，亲和力低微摩尔，经氢氘交换质谱验证结合界面。
conclusion: RareFold实现了对含非标准氨基酸蛋白质的可编程设计，拓宽了蛋白质工程的化学空间。
---

## 摘要
蛋白质结构预测与设计传统上局限于20种标准氨基酸。将非标准氨基酸（ncAAs）纳入这一化学空间对于工程化具有新颖化学和功能特性的蛋白质至关重要。然而，现有方法无法泛化至化学性质多样的残基类型。在此，我们提出RareFold，一种用于预测和设计包含20种标准氨基酸及29种非标准氨基酸蛋白质的深度学习架构。通过将每个残基表示为独立令牌，RareFold学习跨化学多样性序列空间的上下文相关原子相互作用模式，从而在统一框架内对非标准化学性质进行建模。我们将该能力应用于EvoBindRare，一种用于从头设计线性和环状肽配体的生成式框架，其高效实现相比现有架构大幅降低了计算需求。通过设计针对核糖核酸酶A的配体，我们展示了其性能，在预测界面中产生了含有非标准氨基酸的新型线性和环状肽，具有低微摩尔亲和力（KD≈2-9 μM），与天然配体（KD≈2 μM）相当。氢-氘交换质谱证实，设计肽段在与预测结合界面一致的区域与靶标结合。此外，在人源类器官模型中的免疫原性分析显示无检测到的免疫激活。通过将基于深度学习的蛋白质设计拓展至非标准化学空间，RareFold实现了对扩展氨基酸字母表的可编程访问，并拓宽了从头蛋白质工程的范围。

## Abstract
Protein structure prediction and design have traditionally been confined to the 20 canonical amino acids. Expanding this chemical space to include non-canonical amino acids (ncAAs) is essential for engineering proteins with novel chemical and functional properties. However, existing methods are not designed to generalise across chemically diverse residue types. Here, we present RareFold, a deep learning architecture for structure prediction and design of proteins containing the 20 canonical amino acids and 29 ncAAs. By representing each residue as an independent token, RareFold learns context-dependent atomic interaction patterns across chemically diverse sequence spaces, enabling modelling of non-standard chemistries within a unified framework. We apply this capability in EvoBindRare, a generative framework for de novo design of linear and cyclic peptide binders with an efficient implementation that substantially reduces computational requirements compared to existing architectures. We demonstrate its performance by designing binders against Ribonuclease A, yielding novel linear and cyclic peptides incorporating ncAAs within predicted interfaces with low-micromolar affinities (KD [~]2-9 M), comparable to the native ligand (KD [~]2 M). Hydrogen-deuterium exchange mass spectrometry confirms that the designed peptides engage the target at regions consistent with predicted binding interfaces. In addition, immunogenicity profiling in human-derived organoid models shows no detectable immune activation. By extending deep learning-based protein design to non-canonical chemical spaces, RareFold enables programmable access to expanded amino acid alphabets and broadens the scope of de novo protein engineering.