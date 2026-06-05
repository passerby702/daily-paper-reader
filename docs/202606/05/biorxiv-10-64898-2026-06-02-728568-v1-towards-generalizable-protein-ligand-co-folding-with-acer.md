---
title: Towards Generalizable Protein-ligand Co-folding with ACER
title_zh: 迈向具有ACER的可泛化蛋白质-配体共折叠
authors: "Vithayapalert, N., Grisoni, F."
date: 2026-06-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.02.728568v1.full.pdf"
tags: ["query:pocket-lig"]
score: 7.0
evidence: 蛋白质-配体共折叠与口袋探索
tldr: 蛋白质-配体共折叠模型（如AlphaFold-3）在变构或结构新颖靶点上泛化性差，常错误定位配体。ACER框架无需重新训练，通过系统探索替代结合口袋并利用姿态排名提升准确性，高效发现非普遍口袋。在变构靶点和新型复合物上，ACER显著提高口袋发现率和配体姿态准确性，成功建模训练集中未充分代表的界面。该方法通过改进采样动力学增强泛化性，为药物设计提供实用工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有共折叠模型泛化性不足，尤其对变构或结构新颖靶点的配体结合界面预测不准确。
method: ACER框架无需重新训练，通过探索替代结合口袋并基于口袋排序优化配体姿态。
result: 在变构靶点和结构新颖复合物上，口袋发现率和配体姿态准确性显著提升。
conclusion: 改进采样动力学可增强共折叠模型泛化性，无需额外训练数据。
---

## 摘要
预测蛋白质-配体复合物结构是药物发现的核心挑战。尽管AlphaFold-3等最新共折叠模型能够实现准确的结构预测，但它们未能泛化到探索不足的结合界面——系统性地错误放置配体，尤其对于变构或结构新颖的靶标。为解决这一差距，我们提出了ACER（通过口袋探索和姿势排序的自适应共折叠），这是一个无需训练的框架，它(a)使共折叠模型能够系统地探索替代结合口袋，并且(b)利用发现的口袋提高姿势准确性。我们的方法无需先验专家知识即可高效发现非主流口袋。ACER在变构靶标和结构新颖的复合物上提高了口袋发现和姿势准确性，成功地对训练集中代表性不足或缺失的结合界面进行建模。我们的结果展示了改进的采样动态如何在不重新训练的情况下增强共折叠模型的泛化能力。

## Abstract
Predicting protein-ligand complex structures is a central challenge in drug discovery. While recent co-folding models such as AlphaFold-3 achieve accurate structure prediction, they fail to generalize to underexplored binding interfaces - systematically misplacing ligands, particularly for allosteric or structurally novel targets. To address this gap, we present ACER (A daptive Co-folding via pocket E xploration and pose R anking), a training-free framework that (a) enables co-folding models to systematically explore alternative binding pockets, and (b) leverages the discovered pockets to increase pose accuracy. Our method enables the efficient discovery of non-prevalent pockets without prior expert knowledge. ACER improves pocket discovery and pose accuracy on allosteric targets and structurally novel complexes, successfully modeling binding interfaces that are under-represented or absent from the training set. Our results demonstrate how improved sampling dynamics enhance the generalisability of co-folding models without retraining.