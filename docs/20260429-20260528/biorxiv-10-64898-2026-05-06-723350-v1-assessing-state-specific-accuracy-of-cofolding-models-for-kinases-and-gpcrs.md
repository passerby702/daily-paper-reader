---
title: Assessing State-Specific Accuracy of Cofolding Models for Kinases and GPCRs
title_zh: 评估共折叠模型对激酶和GPCR的特定状态准确性
authors: "Obendorf, L., Doering, N. P., Knaus, P., Wolber, G."
date: 2026-05-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.06.723350v1.full.pdf"
tags: ["query:pocket-lig"]
score: 7.0
evidence: 基准测试共折叠模型的蛋白质-配体复合物预测
tldr: 在激酶和GPCR等构象状态关键的药靶中，AI共折叠模型虽能准确放置配体，但常错误预测整体蛋白构象状态。本研究基准测试了AlphaFold3、RosettaFold3、Boltz-2和Chai-1，发现局部配体RMSD低时，激酶活化环和GPCR胞内排布等状态标志仍常被误判。引入状态注释模板和过滤MSA对部分情况有所改善，但正构配体准确、别构配体普遍失效的盲点持续存在。研究揭示了构象脱耦这一根本局限，对状态选择性药物设计具有重要警示意义。
source: biorxiv
selection_source: fresh_fetch
motivation: 评估AI共折叠模型能否准确恢复激酶和GPCR的特定构象状态，以指导状态选择性药物设计。
method: 对AlphaFold3等四个共折叠模型，以激酶和GPCR为对象，比较配体RMSD与活化环、胞内排布等状态标记的预测准确性，并测试模板和MSA的影响。
result: 配体放置普遍准确，但构象状态常被错误预测；别构配体是所有模型的共同盲点，模板和MSA改善有限。
conclusion: 当前共折叠模型存在配体放置与构象状态恢复之间的脱耦，是根本性局限，影响基于结构的药物设计可靠性。
---

## 摘要
AI驱动的共折叠模型已成为预测蛋白质-配体复合物的强大工具，但配体放置是否忠实地捕捉了动态蛋白质的构象状态仍不清楚。我们在此展示，共折叠能够自适应地重塑结合配体周围的结合口袋，但这种局部准确性经常与更广泛构象状态的恢复相脱节。我们以一组激酶和A类G蛋白偶联受体（GPCRs）——这些蛋白质家族的药理学依赖于明确的结构状态——为基准，评估了四个模型：AlphaFold3、RosettaFold3、Boltz-2和Chai-1。我们发现，即使配体的均方根偏差（RMSD）较低，关键的状态标记物，包括激酶活化环几何结构和GPCR胞内排布，也经常被错误预测。在选定的案例中，引入带有状态标注的模板和经过筛选的多序列比对（MSAs）可以改善构象恢复，但对其他案例影响甚微。此外，虽然正构配体的放置通常是可靠的，但别构配体在所有模型中都暴露出一个一致的盲点。这些发现确立了构象脱节是当前共折叠方法的一个根本限制，对状态选择性药物设计具有直接影响。

## Abstract
AI-driven cofolding models have emerged as powerful tools for predicting protein-ligand complexes, yet whether ligand placement faithfully captures the conformational states of dynamic proteins remains unclear. Here we show that cofolding adaptively remodels binding pockets around bound ligands, but that this local accuracy is frequently decoupled from recovery of the broader conformational state. We benchmark four models, AlphaFold3, RosettaFold3, Boltz-2, and Chai-1, against a set of kinases and class A G protein-coupled receptors (GPCRs), protein families whose pharmacology depends on well-defined structural states. We find that even when ligand root-mean-square deviation (RMSD) is low, critical state markers, including kinase activation-loop geometries and GPCR intracellular arrangements, are frequently mispredicted. Incorporating state-annotated templates and filtered multiple sequence alignments (MSAs) improves conformational recovery in selected cases, yet weakly impacts others. Furthermore, while orthosteric ligand placement is generally reliable, allosteric binders expose a consistent blind spot across all models. These findings establish conformational decoupling as a fundamental limitation of current cofolding approaches, with direct implications for state-selective drug design.