---
title: Assessing State-Specific Accuracy of Cofolding Models for Kinases and GPCRs
title_zh: 评估激酶和GPCR协同折叠模型的状态特异性准确性
authors: "Obendorf, L., Doering, N. P., Knaus, P., Wolber, G."
date: 2026-05-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.06.723350v1.full.pdf"
tags: ["query:pocket-lig"]
score: 8.0
evidence: 基准测试蛋白质-配体复合物预测的共折叠模型
tldr: AI共折叠模型预测蛋白-配体复合物时，局部配体位置准确但常与整体蛋白构象状态脱钩。本研究以激酶和GPCR为对象，系统评估了四种共折叠模型恢复状态特异性标记物的能力。结果显示，即使配体RMSD低，关键构象特征频繁误判，别构配体为普遍盲点。该发现揭示了共折叠方法的基本局限，对状态选择性药物设计提供重要警示。
source: biorxiv
selection_source: carryover_cache
motivation: 评估共折叠模型在预测配体结合时是否能准确恢复蛋白的功能构象状态，尤其针对具有明确状态依赖药理的激酶和GPCR。
method: 对AlphaFold3、RosettaFold3、Boltz-2和Chai-1四种模型，在激酶和A类GPCR体系中进行共折叠预测，分析配体RMSD及状态标记物如激活环与胞内区几何。
result: 发现配体RMSD低时关键构象状态仍常误预测；正构配体预测较准，别构配体在所有模型中均暴露出盲点；模板和MSA引入仅对部分实例有改善。
conclusion: 共折叠模型存在构象解耦这一根本局限，直接影响基于状态的药物设计，未来需发展能耦合局部与整体构象的预测方法。
---

## 摘要
AI驱动的协同折叠模型已成为预测蛋白质-配体复合物的强大工具，但配体放置是否忠实地捕获动态蛋白的构象状态仍不清楚。我们在此展示，协同折叠会在结合配体周围自适应重塑结合口袋，但这种局部准确性常常与更广泛构象状态的恢复相脱耦。我们对AlphaFold3、RosettaFold3、Boltz-2和Chai-1四个模型在一组激酶和A类G蛋白偶联受体（GPCR）上进行了基准测试，这些蛋白家族的药理特性依赖于明确的结构状态。我们发现，即使配体均方根偏差（RMSD）较低，关键状态标志物，包括激酶激活环几何结构和GPCR胞内排列，也常被错误预测。纳入状态注释模板和经过滤的多序列比对（MSA）在部分情况下改善了构象恢复，但对其他情况影响甚微。此外，虽然正构配体放置总体可靠，别构结合剂在所有模型中均暴露出一个持续的盲点。这些发现确立了构象脱耦为当前协同折叠方法的一个根本性局限，对状态选择性药物设计具有直接影响。

## Abstract
AI-driven cofolding models have emerged as powerful tools for predicting protein-ligand complexes, yet whether ligand placement faithfully captures the conformational states of dynamic proteins remains unclear. Here we show that cofolding adaptively remodels binding pockets around bound ligands, but that this local accuracy is frequently decoupled from recovery of the broader conformational state. We benchmark four models, AlphaFold3, RosettaFold3, Boltz-2, and Chai-1, against a set of kinases and class A G protein-coupled receptors (GPCRs), protein families whose pharmacology depends on well-defined structural states. We find that even when ligand root-mean-square deviation (RMSD) is low, critical state markers, including kinase activation-loop geometries and GPCR intracellular arrangements, are frequently mispredicted. Incorporating state-annotated templates and filtered multiple sequence alignments (MSAs) improves conformational recovery in selected cases, yet weakly impacts others. Furthermore, while orthosteric ligand placement is generally reliable, allosteric binders expose a consistent blind spot across all models. These findings establish conformational decoupling as a fundamental limitation of current cofolding approaches, with direct implications for state-selective drug design.