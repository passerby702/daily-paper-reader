---
title: "HalluDesign-NA: Extending HalluDesign for De Novo Nucleic Acid Design"
title_zh: "HalluDesign-NA: 将HalluDesign扩展到从头核酸设计"
authors: "Fang, M., Wang, Z., Cao, L."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.730767v1.full.pdf"
tags: ["query:diff-gen"]
score: 6.0
evidence: 深度学习从头核酸设计
tldr: AlphaFold3虽能预测核酸结构，但从头设计结构化核酸仍是难题。本文扩展HalluDesign框架，融入NA-MPNN进行序列优化与迭代共设计。在ssDNA、ssRNA及适配体任务中，pLDDT和ipTM等置信度分数一致提升。该框架支持序列长度、对称性及蛋白环境约束，为功能核酸设计提供新途径。
source: biorxiv
selection_source: fresh_fetch
motivation: AlphaFold3预测核酸结构能力强，但从头设计功能性核酸仍缺乏有效方法。
method: 扩展HalluDesign框架，集成NA-MPNN进行核酸序列优化，实现序列-结构迭代共优化。
result: 在ssDNA、ssRNA和适配体设计中，pLDDT与ipTM置信度分数均显著提升。
conclusion: HalluDesign-NA支持多种约束下的从头核酸设计，加速生物技术及医学应用。
---

## 摘要
AlphaFold3彻底改变了生物分子结构和相互作用的预测，包括核酸的原子级建模。然而，从头设计结构化和功能性核酸仍然是一个重大挑战。在这里，我们通过整合用于核酸序列优化与设计的NA-MPNN，将HalluDesign框架扩展到核酸设计。这一新框架HalluDesign-NA实现了序列-结构的迭代协同优化，促进了核酸的从头设计。在单链DNA、单链RNA和适配体设计任务上的计算基准测试表明，置信度分数（pLDDT、ipTM）持续提升，支持在序列长度、对称性和蛋白质结构背景等多种约束下进行从头核酸设计的可行性。我们预计HalluDesign-NA将加速功能性核酸的从头设计，用于生物技术和医学应用。HalluDesign-NA的源代码可在https://github.com/MinchaoFang/HalluDesign_NA获取。

## Abstract
AlphaFold3 has revolutionized the prediction of biomolecular structures and interactions, including atomic-level modeling of nucleic acids. However, the de novo design of structured and functional nucleic acids remains a significant challenge. Here, we extend our HalluDesign framework to nucleic acid design by integrating NA-MPNN for nucleic acid sequence optimization and design. This new framework, HalluDesign-NA, enables iterative sequence-structure co-optimization, facilitating the de novo design of nucleic acids. Computational benchmarking across ssDNA, ssRNA, and aptamer design tasks demonstrates consistent improvements in confidence scores (pLDDT, ipTM), supporting the feasibility of de novo nucleic acid design under various constraints, such as sequence length, symmetry, and protein structure context. We anticipate that HalluDesign-NA will accelerate the de novo design of functional nucleic acids for applications in biotechnology and medicine. The source code for HalluDesign-NA is available at https://github.com/MinchaoFang/HalluDesign_NA.