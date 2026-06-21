---
title: From Scarce Functional Labels to Label-Aware Generation in Homologous Protein Families
title_zh: 从稀缺功能标签到同源蛋白家族中的标签感知生成
authors: "Rosset, L., Weigt, M., Zamponi, F."
date: 2026-06-19
pdf: "https://www.biorxiv.org/content/10.1101/2025.07.22.665933v2.full.pdf"
tags: ["query:diff-gen"]
score: 6.0
evidence: 使用深度学习生成蛋白质序列，基于ESM2嵌入
tldr: 同源蛋白家族中功能标签稀缺限制了功能注释和蛋白设计。本文提出两阶段轻监督策略，先比较one-hot、RBM和ESM2等序列表示在减少系统发育泄漏下的标签预测，发现ESM2不优于简单基线。再利用推断标签训练标签感知RBM生成条件序列。结果表明准确传播的稀缺标签可支持标签感知设计，且需系统发育感知评估方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 蛋白质工程中，同源家族内功能标签稀缺，亟需有效方法实现细粒度功能注释和标签感知序列生成。
method: "两阶段轻监督策略：第一阶段用不同表示（one-hot, RBM, ESM2）预测标签，第二阶段用推断标签训练标签感知RBM生成序列。"
result: ESM2嵌入未优于家族特异性RBM或one-hot；标签数量和质量决定条件生成可靠性，准确传播的稀缺标签有效。
conclusion: 稀缺标注可支持标签感知蛋白设计，需采用系统发育感知评估避免高估性能。
---

## 摘要
从序列数据中准确注释和控制蛋白质功能仍然是蛋白质工程中的主要挑战，特别是在大型同源家族中功能标签稀缺的情况下。在这里，我们研究了一种用于细粒度功能注释和标签感知序列生成的两阶段轻监督策略。首先，我们比较了几种序列表示方法，包括独热编码、受限玻尔兹曼机（RBM）和基于ESM2的蛋白质语言模型嵌入，用于从有限监督中预测家族内特异性标签。通过使用明确减少系统发育泄漏的训练/测试分割，我们表明基于ESM2的表示并不系统地优于家族特异性RBM嵌入甚至简单的独热基线。其次，我们利用推断的注释来训练一个注释感知的RBM，能够根据规定的标签生成人工同源物。在几个蛋白质家族中，我们量化了可用标签的数量和质量如何决定条件生成的可靠性。我们的结果表明，当稀缺注释被准确传播时，它们可以支持标签感知的蛋白质设计，同时也强调了系统发育感知评估对于评估同源家族内功能注释方法的重要性。

## Abstract
Accurately annotating and controlling protein function from sequence data remains a major challenge in protein engineering, especially when functional labels are scarce within large homologous families. Here, we study a two-stage light-supervision strategy for fine-grained functional annotation and label-aware sequence generation. First, we compare several sequence representations, including one-hot encodings, Restricted Boltzmann Machines (RBMs), and ESM2-based protein language model embeddings, for predicting intra-family specificity labels from limited supervision. By using train/test splits that explicitly reduce phylogenetic leakage, we show that ESM2-based representations do not systematically outperform family-specific RBM embeddings or even simple one-hot baselines in this regime. Second, we use the inferred annotations to train an annotation-aware RBM capable of generating artificial homologs conditioned on prescribed labels. Across several protein families, we quantify how the number and quality of available labels determine the reliability of conditional generation. Our results show that scarce annotations can support label-aware protein design when they are accurately propagated, while also highlighting the importance of phylogeny-aware evaluation for assessing functional annotation methods within homologous families.