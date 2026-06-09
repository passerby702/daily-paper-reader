---
title: Species- and Topic-aware Representation Learning for Antimicrobial Peptide Discovery
title_zh: 物种与主题感知的表示学习用于抗菌肽发现
authors: "Padi, S., Mondal, K., Kaur, N., Hoogerheide, D. P., Heinrich, F., Mihailescu, E., Klauda, J. B., Cardone, A., Keyrouz, W."
date: 2026-06-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.28.728246v1.full.pdf"
tags: ["query:pocket-lig"]
score: 6.0
evidence: 用于抗菌肽发现的生成模型，预测最小抑菌浓度
tldr: 抗菌素耐药性对全球健康构成重大挑战，迫切需要高效策略发现抗菌肽（AMP）。现有生成模型可产生大量候选序列，但实验室验证成本高、耗时长，因此需要准确预测最小抑菌浓度（MIC）。本文提出STAMP框架，通过物种条件与主题感知表示学习，整合蛋白质语言模型嵌入，实现跨物种的AMP活性统一预测。在三个基准数据集上，STAMP取得皮尔逊相关系数0.837、R²0.70的优异性能，并在大肠杆菌和表皮葡萄球菌上获得实验验证，为加速AMP发现与优化提供了可扩展的计算工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有生成模型产生大量抗菌肽候选序列，但实验验证成本高昂，亟需一个跨物种的MIC预测模型来高效筛选。
method: STAMP融合蛋白质语言模型嵌入，引入物种条件与主题感知表示，在单个模型中实现跨多个细菌物种的MIC统一预测。
result: 在三个基准数据集上，STAMP取得PCC 0.837、R²0.70，优于多个基线，并通过E.coli和S.epidermidis实验验证了实际应用性。
conclusion: STAMP作为可扩展的MIC预测框架，为加速AMP发现与优化提供了有效的计算工具。
---

## 摘要
抗菌药物耐药性构成一项重大全球健康挑战，需要高效策略来发现有效的抗菌肽（AMPs）。尽管最近生成模型能产生许多候选序列，但由于湿实验验证所有生成肽的成本高且耗时，因此迫切需要准确预测肽的效力（通常通过最小抑菌浓度MIC来衡量）。我们提出了STAMP，一种用于抗菌肽发现的物种与主题感知表示学习框架。这一统一的机器学习框架允许跨物种预测AMP活性。STAMP将蛋白质语言模型嵌入与物种条件及捕捉序列层面模式的主题感知表示相结合，使得单个模型能够跨多个细菌物种进行可泛化的预测。我们在三个基准数据集上评估了STAMP，包括两个已发表数据集和一个来自DBAASP的新整理数据集，系统性地处理了重复和不一致性。STAMP在这些数据集上展现出强大的预测性能，皮尔逊相关系数（PCC）达到0.837，R2为0.70，优于多个基线模型。重要的是，我们利用经实验验证对大肠杆菌和表皮葡萄球菌具有抗菌活性的肽进一步验证了预测模型，展示了其实际应用价值。此外，残基水平重要性分析揭示了决定抗菌活性的序列因素。综合来看，这些结果确立了STAMP作为可扩展的MIC预测框架，以及加速AMP发现与优化的有效计算工具。

## Abstract
Antimicrobial resistance poses a major global health challenge, necessitating efficient strategies to discover potent antimicrobial peptides (AMPs). While recent generative models can produce many candidate sequences, experimentally validating all generated peptides in wet labs is impractical due to the high costs and time involved in such measurements. As a result, there is a strong demand for accurate predictions of peptide efficacy, typically measured as the minimum inhibitory concentration (MIC). We introduce STAMP, a framework for Species- and Topic-aware Representation Learning in AMP Discovery. This unified machine learning framework allows for cross-species predictions of AMP activity. STAMP integrates protein language model embeddings with species conditioning and topic-aware representations that capture sequence-level patterns, enabling generalizable predictions across multiple bacterial species within a single model. We evaluated STAMP on three benchmark datasets, which include two previously published datasets and a newly curated dataset derived from DBAASP, addressing duplicates and inconsistencies systematically. STAMP achieved strong predictive performance across these datasets, demonstrating a Pearson correlation coefficient (PCC) of 0.837 and an R2 of 0.70, outperforming several baseline models. Importantly, we further validated our prediction model using peptides that were experimentally tested for their antimicrobial activity against E.coli. and S.epidermidis bacteria, demonstrating its real-world applicability. Furthermore, residue-level importance analyses provide insights into the sequence determinants governing antimicrobial activity. Together, these results establish STAMP as a scalable framework for MIC prediction and an effective computational tool for accelerating AMP discovery and optimization.