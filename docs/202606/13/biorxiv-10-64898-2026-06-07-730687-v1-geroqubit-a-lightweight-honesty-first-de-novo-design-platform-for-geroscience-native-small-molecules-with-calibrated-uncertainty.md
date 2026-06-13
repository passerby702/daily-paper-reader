---
title: "GeroQubit: a lightweight, honesty-first de-novo design platform for geroscience-native small molecules with calibrated uncertainty"
title_zh: GeroQubit：一个轻量级、诚实优先的衰老科学原生小分子从头设计平台，带有校准的不确定性
authors: "k, D., Swetha, H."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.07.730687v1.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 从头小分子生成平台，具有校准的不确定性
tldr: 计算分子生成模型常因过度自信而缺乏可信度。GeroQubit提出一种无需GPU的从头设计平台，按目标×组织×衰老标志模型组织分子，并明确披露每个信号的基线缺陷。其分子以反应优先方式生成，确保合成路线可验证；ADMET优化为多目标帕累托问题。在1940个结合剂回顾中达0.945 AUC，但报告在新颖骨架时性能降至0.62。该方法通过诚实呈现弱信号和失败案例，提供决策有用的输出。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有计算分子生成可信度不足，需一个诚实披露局限性的平台。
method: 按目标×组织×衰老标志组织分子，反应优先确保合成可验证，k-NN加置信区间评估功效，多目标帕累托优化ADMET。
result: 1940个结合剂回顾AUC 0.945，骨架新颖时降至0.62，功效信号弱（rho~0.145）。
conclusion: 诚实披露弱信号与失败案例，提供决策有用的老年科学分子设计工具。
---

## 摘要
计算分子生成已超越其自身的可信度。我们提出GeroQubit，一个无GPU的从头设计平台，该平台沿着靶点×组织×标志模型组织候选分子，并将每个信号及其测量基线一并报告。我们将组织衰老特征读数视为一个机制性结构先验，并明确披露其未经寿命验证，仅通过结构到寿命的k-NN呈现功效，该方法的弱但真实的信号（留一法rho约0.145）被包裹在经验校准的共形区间内（90%目标，实测覆盖90.3%）。在针对诱饵的约1,940个ChEMBL配体的保留回顾性恢复中，评分达到ROC-AUC 0.945，在1%时富集约20倍（BEDROC 0.91），并通过了骨架不相交分割测试——但我们报告其在真正新颖的化学类型上退化为接近随机（AUC 0.62）。分子采用反应优先组装，因此每个候选分子都带有已验证的合成路线和原子级合成子溯源；ADMET作为多目标帕累托问题处理。我们公开披露的弱信号和困难案例的失败并非缺陷，而是该领域批评者自身所要求的诚实、对决策有用的输出。

## Abstract
Computational molecule generation has outpaced its own credibility. We present GeroQubit, a GPU-free de-novo design platform that organizes candidates along a target x tissue x hallmark model and reports every signal alongside its measured baseline. We treat our tissue aging-signature readout as a mechanistic structural prior that we explicitly disclose is not validated against lifespan, and we surface efficacy only through a structure-to-lifespan k-NN whose weak but real signal (leave-one-out rho ~ 0.145) is wrapped in empirically-calibrated conformal intervals (90% target, 90.3% measured coverage). On a held-out retrospective recovery of ~1,940 ChEMBL binders against decoys, the score reaches ROC-AUC 0.945 with ~20x enrichment at 1% (BEDROC 0.91) and survives a scaffold-disjoint split - yet we report that it collapses to near-random (AUC 0.62) on genuinely novel chemotypes. Molecules are assembled reaction-first, so every candidate carries a verified synthetic route and atom-level synthon provenance; ADMET is handled as a multi-objective Pareto problem. We frame the disclosed weak signals and the hard-case failures not as flaws but as the honest, decision-useful output the field's own critics demand.