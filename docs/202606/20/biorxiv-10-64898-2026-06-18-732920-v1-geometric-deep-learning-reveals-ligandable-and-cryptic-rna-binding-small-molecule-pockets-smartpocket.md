---
title: Geometric Deep Learning Reveals Ligandable and Cryptic RNA Binding Small Molecule Pockets (SMARTPocket)
title_zh: 几何深度学习揭示可配体结合和隐性的RNA结合小分子口袋（SMARTPocket）
authors: "Thakare, R. H., Taghavi, A., Wang, J., Childs-Disney, J. L., Li, C., Disney, M. D., Li, Y."
date: 2026-06-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.732920v1.full.pdf"
tags: ["query:pocket-lig"]
score: 7.0
evidence: 预测RNA可配体结合口袋，与口袋特异性分子生成相关
tldr: RNA是重要药物靶点，但识别可成药小分子结合口袋是主要障碍。SMARTPocket提出全原子点云几何深度学习框架，通过迁移学习从11万蛋白质界面结构预训练，精准预测RNA结合口袋。在多个基准测试中优于现有方法，能识别隐蔽口袋，并成功应用于SARS-CoV-2和RNA适配体。该框架加速了RNA靶向药物的发现。
source: biorxiv
selection_source: fresh_fetch
motivation: RNA是重要药物靶点，但缺乏识别可成药小分子结合口袋的有效方法，阻碍了RNA靶向药物发现。
method: SMARTPocket将RNA表示为全原子点云，采用迁移学习从大量蛋白质结合界面结构预训练，预测结合口袋。
result: 在多个基准测试中优于现有预测器，能识别隐蔽口袋，并成功应用于SARS-CoV-2和RNA适配体，提高对接效率。
conclusion: 建立了基于结构识别RNA可成药口袋的通用框架，加速RNA靶向小分子发现。
---

## 摘要
RNA是重要的治疗靶点，然而识别可配体结合的小分子口袋仍然是RNA靶向药物发现的主要障碍。本文介绍SMARTPocket，一种直接从三维结构预测RNA-小分子结合口袋的原子级几何深度学习框架。SMARTPocket将RNA表示为全原子点云，并利用来自超过11万个蛋白结合界面结构的迁移学习，以克服实验解析的RNA-配体复合物数量有限的问题。在四个已建立的单链基准和三个更广泛筛选的基准上，SMARTPocket一致优于现有的RNA口袋预测器和通用生物分子建模方法。该模型在构象变化适当时可推广至无配体RNA结构，识别隐性的可配体口袋，并在SARS-CoV-2移码元件和进化为结合小分子的RNA适配体中重现了实验验证的结合位点。与盲对接相比，SMARTPocket引导的对接进一步提高了近天然RNA-配体姿态恢复和计算效率。这些结果表明SMARTPocket是一个可推广的框架，用于基于结构识别可配体的RNA口袋，并加速RNA靶向小分子的发现。

## Abstract
RNAs are important therapeutic targets, however identifying ligandable small-molecule binding pockets remains a major barrier to RNA-targeted drug discovery. Here, SMARTPocket, an atomic-level geometric deep learning framework for predicting RNA-small molecule binding pockets directly from three-dimensional structure is introduced. SMARTPocket represents RNA as full-atom point clouds and uses transfer learning from more than 110,000 protein binding interface structures to overcome the limited number of experimentally elucidated RNA-ligand complexes. Across four established single-chain benchmarks and three broader curated benchmarks, SMARTPocket consistently outperforms existing RNA pocket predictors and general biomolecular modeling approaches. The model generalizes to apo RNA structures when conformational changes are modest, identifies cryptic ligandable pockets, and recapitulates experimentally validated binding sites in the SARS-CoV-2 frameshifting element and an RNA aptamer evolved to bind small molecules. SMARTPocket-guided docking further improves near-native RNA-ligand pose recovery and computational efficiency compared with blind docking. These results establish SMARTPocket as a generalizable framework for structure-based identification of ligandable RNA pockets and for accelerating discovery of RNA-targeted small molecules.