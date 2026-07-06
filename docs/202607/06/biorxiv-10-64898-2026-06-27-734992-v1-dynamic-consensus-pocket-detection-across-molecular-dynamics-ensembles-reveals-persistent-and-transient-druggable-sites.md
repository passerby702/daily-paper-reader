---
title: Dynamic consensus pocket detection across molecular dynamics ensembles reveals persistent and transient druggable sites
title_zh: 跨分子动力学集合的动态一致性口袋检测揭示持久与瞬时可成药位点
authors: "Marigliani, G., Petrizzelli, F., Mangoni, M., Bianco, S. D., Orzella, I., Guzzi, P. H., Caputo, V., Biagini, T., Mazza, T."
date: 2026-07-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.27.734992v1.full.pdf"
tags: ["query:pocket-lig"]
score: 7.0
evidence: 综述并重用途口袋检测工具，使用深度学习，与口袋特异性分子生成相关
tldr: 传统药物研发假设单一结合位点，但蛋白质具有多个动态可药区域。本研究评估几何、能量和机器学习三类口袋检测工具在分子动力学构象集成上的一致性，结合HDBSCAN聚类、IoU分析和持久性评分。在GLUT1和Aldose还原酶上测试发现，不同算法捕获互补的口袋动力学特征，能量方法更敏感于瞬时隐式区域。提出共识框架以识别动态蛋白质中的持久和瞬时可药口袋。
source: biorxiv
selection_source: fresh_fetch
motivation: 突破“一药一靶”局限，识别蛋白质动态构象中的持久和瞬时隐式可药口袋。
method: 整合三类口袋检测工具，对分子动力学集成进行一致性分析、空间聚类、体积IoU和持久性评分。
result: 能量方法敏感于瞬时隐式区域，几何方法依赖预形成空腔，算法间互补覆盖口袋动态。
conclusion: 共识框架可鲁棒检测动态蛋白质系统中的保守和瞬时可药口袋，促进多靶点药物设计。
---

## 摘要
传统的“一药一靶”范式假设药物与单个特定结合位点相互作用。现代药理学已证明该定义过于简单，反之，认识到药物在复杂生物系统中发挥作用，并常与多个靶点相互作用。在此背景下，蛋白质不能被视为仅拥有单个功能性结合位点，而是动态实体，能够在多个区域容纳配体，包括瞬态和隐蔽口袋。在这项工作中，我们回顾并重新利用代表性的口袋检测工具，这些工具最初设计用于静态构象，涵盖了基于几何、基于能量以及机器/深度学习方法，评估它们在分子动力学衍生的构象集合上的一致性。以GLUT1蛋白作为动态转运蛋白模型、醛糖还原酶作为隐蔽口袋参考系统，我们结合工具间一致性、基于HDBSCAN的空间聚类、体积IoU分析以及时间持续性评分。结果表明，不同算法类别捕捉到口袋动力学的互补方面，其中基于能量的方法对瞬态隐蔽区域表现出更强的敏感性，而基于几何的方法更依赖于预先形成的空腔。本工作提出一个以共识为导向的框架，用于识别动态蛋白系统中保守和瞬态的可成药口袋。

## Abstract
The traditional "one drug, one target" paradigm assumes that drugs interact with a single specific binding site. Modern pharmacology has proven this definition overly simplistic and, instead, recognizes that drugs operate within complex biological systems and often interact with multiple targets. In this context, proteins cannot be viewed as possessing a single functional binding site, but rather as dynamic entities capable of accommodating ligands at multiple regions, including transient and cryptic pockets. Here, we review and repurpose representative pocket detection tools across geometry-based, energy-based, and machine/deep learning approaches, originally designed to work on static conformations, to evaluate their agreement on molecular dynamics-derived conformational ensembles. Using GLUT1 protein as a dynamic transporter model and Aldose reductase as a cryptic-pocket reference system, we combine inter-tool concordance, HDBSCAN-based spatial clustering, volumetric IoU analysis, and temporal persistence scoring. Our results show that different algorithmic classes capture complementary aspects of pocket dynamics, with energy-based methods showing stronger sensitivity to transient cryptic regions and geometry-based approaches depending more strongly on pre-formed cavities. This work proposes a consensus-oriented framework for identifying conserved and transient druggable pockets in dynamic protein systems.