---
title: "F.A.D.E. (Fully Agentic Drug Engine): A Conversational AI Platform for Drug Discovery"
title_zh: F.A.D.E.（全自主药物引擎）：面向药物发现的对话式AI平台
authors: "Kantorow, J., Mani, N., Mohanraj, N. R., Zong, X."
date: 2026-06-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.20.733481v1.full.pdf"
tags: ["query:diff-gen"]
score: 6.0
evidence: 药物发现平台，涉及分子生成
tldr: 药物发现成本高昂、周期长且失败率高，现有计算工具碎片化并需专业知识。本文提出F.A.D.E.多代理开源平台，通过自然语言查询即可自动进行结构预测、结合口袋检测、配体生成和亲和力评估，生成候选药物。在EGFR和CRBP1靶标上验证，EGFR生成的候选QED达0.85，优于共晶配体0.46，显著降低了计算药物发现的专业门槛。
source: biorxiv
selection_source: fresh_fetch
motivation: 降低药物发现中高级计算方法的专业知识壁垒，整合碎片化流程为端到端自动化流水线。
method: 采用三分支层次架构，根据靶标结构数据可用性自适应选择路径，集成结构预测、结合口袋检测、等变扩散配体生成和亲和力估计。
result: 在EGFR靶标上生成候选药物QED达0.85，对比共晶配体0.46；在CRBP1上也生成可药性化合物。
conclusion: F.A.D.E.能从自然语言输入可靠生成多种蛋白质类别的可合成、类药先导化合物。
---

## 摘要
药物发现仍然是制药管线中成本最高、时间最密集的工作之一，平均每款药物的开发成本超过23亿美元，研发周期超过十年，且临床试验的失败率超过90%。尽管计算方法已拓展了可搜索的化学空间，但当前的管线仍然支离破碎，且对于缺乏深厚跨学科专业知识的研究人员而言，这些工具基本难以使用。本文提出F.A.D.E.（全自主药物引擎），一个多智能体、开源平台，可将自然语言查询转化为潜在的候选药物，从而大幅降低进入高级计算药物发现的专业知识门槛。F.A.D.E.采用三分支层级架构，可根据任何蛋白质靶点可用结构数据的水平进行自适应调整，将结构预测、结合口袋检测、基于等变扩散的从头配体生成以及结合亲和力估计整合到单一自动化管线中。我们通过两个结构不同的靶点验证了F.A.D.E.：表皮生长因子受体激酶结构域（EGFR）（一个成熟的肿瘤学靶点）和细胞视黄醇结合蛋白1（CRBP1）（一种参与视黄醇代谢的脂质结合蛋白）。对于EGFR，我们的生成候选分子QED评分为0.85，而共晶参考配体为0.46，表明预测药物相似性显著提升。两个靶点的结果均证实，F.A.D.E.能够仅通过简单的自然语言输入，可靠地生成不同蛋白质类别中化学可处理的、类药性的先导化合物。

## Abstract
Drug discovery remains one of the costliest and most time-intensive endeavors in the pharmaceutical pipeline, with average development costs exceeding $2.3 billion per drug, timelines spanning more than a decade, and attrition rates above 90% in clinical trials. While computational methods have expanded the searchable chemical space, current pipelines remain fragmented and largely inaccessible to researchers without deep interdisciplinary expertise. Here we present F.A.D.E. (Fully Agentic Drug Engine), a multi-agent, open-source platform that converts natural language queries into potential drug candidates, substantially lowering the expertise barrier to advanced computational drug discovery. F.A.D.E. employs a three-branch hierarchical architecture that adapts to the level of available structural data for any protein target, integrating structure prediction, binding pocket detection, equivariant diffusion-based de novo ligand generation, and binding affinity estimation into a single automated pipeline. We validate F.A.D.E. on two structurally distinct targets: the epidermal growth factor receptor kinase domain (EGFR), a well-established oncology target, and cellular retinol-binding protein 1 (CRBP1), a lipid-binding protein involved in retinoid metabolism. For EGFR, our generated candidates achieved QED scores of 0.85 compared to 0.46 for the co-crystallised reference ligand, demonstrating marked improvement in predicted drug-likeness. Results across both targets confirm that F.A.D.E. can reliably generate chemically tractable, drug-like hit compounds across diverse protein classes from simple natural language input.