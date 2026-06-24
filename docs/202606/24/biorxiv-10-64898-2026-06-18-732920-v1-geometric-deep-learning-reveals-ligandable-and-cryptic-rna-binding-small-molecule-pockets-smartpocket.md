---
title: Geometric Deep Learning Reveals Ligandable and Cryptic RNA Binding Small Molecule Pockets (SMARTPocket)
title_zh: 几何深度学习揭示可配体结合与隐藏的RNA小分子结合口袋（SMARTPocket）
authors: "Thakare, R. H., Taghavi, A., Wang, J., Childs-Disney, J. L., Li, C., Disney, M. D., Li, Y."
date: 2026-06-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.732920v1.full.pdf"
tags: ["query:pocket-lig"]
score: 7.0
evidence: 几何深度学习预测RNA口袋，助力配体设计
tldr: RNA是重要但难靶向的药物靶标，缺乏可靠的小分子结合口袋预测方法。本文提出SMARTPocket，一种基于几何深度学习的全原子点云框架，利用超过11万蛋白质结合界面知识进行迁移学习，直接从RNA三维结构预测口袋。在多个基准测试中，SMARTPocket显著优于现有方法，并能识别隐秘口袋，在SARS-CoV-2移码元件和RNA适配体上验证了有效性。该工作为基于结构的RNA口袋识别提供了通用工具，有望加速RNA靶向药物发现。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有RNA小分子结合口袋预测方法准确性低，且缺乏足够实验数据支撑。
method: 提出SMARTPocket，将RNA表示为全原子点云，使用图神经网络并通过迁移学习从大量蛋白质结合界面预训练。
result: 在四个单链和三个扩展基准测试中均优于现有方法，能发现隐秘口袋，并在SARS-CoV-2移码元件和RNA适配体上复现实验验证的结合位点。
conclusion: SMARTPocket为基于结构的RNA药物发现提供了通用的口袋识别框架，可提升对接效率和准确性。
---

## 摘要
RNA是重要的治疗靶点，然而识别可配体结合的小分子结合口袋仍是RNA靶向药物发现的主要障碍。本文介绍了SMARTPocket，一种直接从三维结构预测RNA-小分子结合口袋的原子级几何深度学习框架。SMARTPocket将RNA表示为全原子点云，并利用来自超过11万个蛋白质结合界面结构的迁移学习，以克服实验解析RNA-配体复合物数量有限的问题。在四个已建立的单链基准测试和三个更广泛的精心筛选基准测试中，SMARTPocket始终优于现有的RNA口袋预测器以及一般的生物分子建模方法。该模型在构象变化较小时可泛化至apo RNA结构，识别隐藏的可配体结合口袋，并重现SARS-CoV-2移码元件和经进化以结合小分子的RNA适配体中经实验验证的结合位点。与盲对接相比，SMARTPocket引导的对接进一步改善了近天然RNA-配体姿态的恢复和计算效率。这些结果表明，SMARTPocket是一个通用的框架，可用于基于结构的可配体RNA口袋识别，并加速RNA靶向小分子的发现。

## Abstract
RNAs are important therapeutic targets, however identifying ligandable small-molecule binding pockets remains a major barrier to RNA-targeted drug discovery. Here, SMARTPocket, an atomic-level geometric deep learning framework for predicting RNA-small molecule binding pockets directly from three-dimensional structure is introduced. SMARTPocket represents RNA as full-atom point clouds and uses transfer learning from more than 110,000 protein binding interface structures to overcome the limited number of experimentally elucidated RNA-ligand complexes. Across four established single-chain benchmarks and three broader curated benchmarks, SMARTPocket consistently outperforms existing RNA pocket predictors and general biomolecular modeling approaches. The model generalizes to apo RNA structures when conformational changes are modest, identifies cryptic ligandable pockets, and recapitulates experimentally validated binding sites in the SARS-CoV-2 frameshifting element and an RNA aptamer evolved to bind small molecules. SMARTPocket-guided docking further improves near-native RNA-ligand pose recovery and computational efficiency compared with blind docking. These results establish SMARTPocket as a generalizable framework for structure-based identification of ligandable RNA pockets and for accelerating discovery of RNA-targeted small molecules.