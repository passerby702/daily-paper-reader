---
title: "BoltzProt-1: Towards Efficient De Novo Binder Design with Good Developability"
title_zh: BoltzProt-1：面向高效且具有良好的可开发性的从头结合剂设计
authors: "Ucar, T., Bates, J., Fu, Y., Shi, W., Stark, H., Nava, D., Cavalleri, L., Wohlwend, J., Corso, G., Passaro, S."
date: 2026-06-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.23.733997v1.full.pdf"
tags: ["query:diff-gen"]
score: 6.0
evidence: 使用生成模型进行从头结合剂设计
tldr: "设计针对新蛋白靶点的结合剂是计算药物发现的长期挑战。本文提出BoltzProt-1管道，融合改进的生成模型BoltzGen和新蛋白互作预测模型BoltzPPI，用后者取代传统置信度排序提升纳米抗体筛选。在10个新靶点，确认命中率从3.3%提升至8.0%；在10个文献靶点中获得7/10筛选命中，超越Chai-2的6/10。可开发性方面，58%确认结合子通过稳定性等全部标准，优于BoltzGen的40%和临床阶段VHH的21%，证明其高效且具备良好开发前景。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有蛋白结合剂设计方法命中率低且可开发性差，亟需改进生成模型和排序策略以提升效率。
method: 提出BoltzProt-1管道，融合改进的BoltzGen生成模型和新互作预测模型BoltzPPI，用于纳米抗体排序。
result: "10个新靶点命中率从3.3%升至8.0%；10个文献靶点7/10命中，优于Chai-2；58%确认结合子通过所有可开发性标准。"
conclusion: BoltzProt-1有效提升命中率和可开发性，是计算药物发现中高效实用的结合剂设计工具。
---

## 摘要
针对新型蛋白质靶点设计结合剂仍是计算药物发现中的核心挑战。在此，我们介绍BoltzProt-1，一个用于生成蛋白质结合剂（包括纳米抗体）的流水线，其具有更高的命中率和良好的可开发性。其核心是BoltzGen生成模型的改进迭代版本以及一种新的蛋白质-蛋白质相互作用预测模型BoltzPPI。使用BoltzPPI（而非BoltzGen的标准结构预测置信度指标）对纳米抗体（VHH）设计进行排序，在10个新靶点上将已确认结合剂的命中率从3.3%提升至8.0%。在先前文献中使用的另外10个靶点上进行评估，BoltzProt-1流水线在10个靶点中的7个上获得了纳米抗体筛选命中，超过了Chai-2此前报告的10个靶点中的6个。最后，从稳定性、聚集性、纯度、多特异性和疏水性方面评估BoltzProt-1设计的纳米抗体的可开发性，发现其58%的已确认结合剂通过了所有标准，超过了BoltzGen（40%）和临床阶段的VHH对照（21%）。

## Abstract
Designing binders against novel protein targets remains a central challenge in computational drug discovery. Here we introduce BoltzProt-1, a pipeline for generating protein binders, including nanobodies, with improved hit rates and favorable developability properties. At its core lie a refined iteration of BoltzGen's generative model and a novel protein-protein interaction prediction model, BoltzPPI. Employing BoltzPPI instead of BoltzGen's standard structure-prediction confidence metrics to rank nanobody (VHH) designs increases the confirmed-binder hit rate from 3.3% to 8.0% across 10 novel targets. Assessed on 10 additional targets used in prior literature, the BoltzProt-1 pipeline obtains nanobody screening hits for 7 of 10 targets, surpassing the 6 of 10 previously reported by Chai-2. Finally, evaluating the developability of BoltzProt-1-designed nanobodies in terms of stability, aggregation, purity, polyspecificity and hydrophobicity reveals that 58% of its confirmed binders pass every criterion, exceeding both BoltzGen (40%) and clinical-stage VHH controls (21%).