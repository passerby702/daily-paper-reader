---
title: "CCK* (Convex Closure K*): A Suite of Algorithms for De Novo L- and D-peptide Design"
title_zh: "CCK*（凸闭包K*）：用于从头设计L型和D型肽的算法套件"
authors: "Childs, H., McBride, A. C., Donald, B. R."
date: 2026-06-01
pdf: "https://www.biorxiv.org/content/10.1101/2025.11.21.689740v2.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 使用统一计算框架进行从头L-和D-肽设计
tldr: "L-和D-肽设计在药物开发中具有重要价值，但D-肽缺乏进化背景和结构数据，传统方法难以应用于其从头设计。为此提出CCK*套件，整合SCOPE、MONTAGE和ARISE三个算法，利用几何凸包、几何哈希和K*算法实现无手性偏好的设计。在六个从头设计任务中成功生成同手性和异手性复合物序列。该框架首次统一支持L-和D-肽设计，扩展了可设计手性空间。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有L-肽设计方法依赖数据和深度学习，无法直接用于D-肽；需要同时支持两种手性的统一框架。
method: "CCK*套件包含三个算法：SCOPE通过几何凸包生成接触图，MONTAGE基于几何哈希和K*算法筛选骨架，ARISE使用图论迭代分配残基。"
result: "在六个从头设计任务中，CCK*成功实现了同手性保留和手性反转的设计，验证了异源手性复合物的可行性。"
conclusion: "CCK*为L-和D-肽设计提供了统一计算框架，通过融合几何与统计方法克服了数据限制，拓展了肽药物设计空间。"
---

## 摘要
L型肽及其镜像对应物D型肽的计算设计是药物设计中的一个活跃领域。肽类治疗剂具有卓越的结构多样性和高结合特异性，而D型肽还额外提供了诸如抗蛋白酶水解等关键优势。从头设计D型肽的进展受到缺乏进化背景和有限结构数据的阻碍，而这两者正是广泛用于L型肽设计的深度学习方法的基石。因此，一个能够同时设计L型和D型肽的鲁棒框架应当将数据驱动推理与基于第一性原理的物理建模相结合。在此，我们介绍一个统一的计算框架，支持L型和D型肽的从头设计，从而扩展了跨越两个手性空间的可达设计空间。凸闭包K* (CCK*) 是一套对手性无关的算法：SCOPE、MONTAGE和ARISE。SCOPE使用几何作为化学能量学的代理，计算旋转异构体状态的凸包表示，以快速生成多序列蛋白质接触图。MONTAGE结合几何哈希与K*算法，根据支架对序列设计的适合性来生成和排序主链支架。ARISE是一种基于K*的序列设计算法，它在无向图中执行迭代残基分配，以设计高亲和力的肽序列。我们将完整的CCK*套件应用于六个从头设计任务，对同手性和异手性复合物中的手性保持和手性反转设计进行基准测试。

## Abstract
The computational design of L-peptides and their mirror-image counterparts, D-peptides, is an active area in drug design. Peptide therapeutics offer exceptional structural diversity and high binding specificity, while D-peptides additionally confer critical advantages such as proteolytic resistance. Progress in de novo D-peptide design has been hindered by the absence of evolutionary context and limited structural data, both of which underpin the deep learning methods widely used in L-peptide design. Consequently, a robust framework capable of designing both L- and D-peptides should integrate data-driven inference with first-principles, physics-based modeling. Here, we introduce a unified computational framework that supports de novo design of both L- and D-peptides, thereby expanding the accessible design space across both chiral spaces. Convex Closure K* (CCK*) is a suite of chirality-agnostic algorithms: SCOPE, MONTAGE, and ARISE. SCOPE uses geometry as a proxy for chemical energetics, computing convex hull representations of rotameric states to rapidly generate multi-sequence protein contact maps. MONTAGE employs geometric hashing in conjunction with the K* algorithm to generate and rank backbone scaffolds according to their suitability for sequence design. ARISE is a K*-based sequence design algorithm that performs iterative residue assignment in an undirected graph to design high-affinity peptide sequences. We apply the full CCK* suite to six de novo design tasks, benchmarking chirality-preserving and chirality-inverting designs in both homochiral and heterochiral complexes.