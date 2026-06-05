---
title: Vibe Coding Specificity Foundation Models
title_zh: 氛围编码特异性基础模型
authors: "Reddy, S. T."
date: 2026-06-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.04.730134v1.full.pdf"
tags: ["query:pocket-lig"]
score: 6.0
evidence: 分子结合特异性预测基础模型
tldr: "分子识别决定结合特异性，但传统方法依赖实验或专用工具，缺乏通用性。利用Transformer注意力与玻尔兹曼分布数学同一性，提出物理衍生序列架构，在六个领域训练SFM。在512候选池中检索，R@1从27.7%到98.0%，数据效率比视觉语言模型高约十万倍。无需结构信息即可跨领域预测结合兼容性，且可由非编程专家用vibe coding构建。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有结合特异性预测方法依赖实验筛选或专用工具，缺乏跨模态通用性。
method: 基于Transformer注意力与玻尔兹曼分布同一性，构建双序列编码器、对称对比学习和物理温度的SFM架构。
result: "六种SFM在512候选池中跨模态检索R@1达27.7%-98.0%，数据效率比视觉语言模型高约十万倍。"
conclusion: SFM作为物理衍生的序列原生模型，可在无结构信息下增强各分子识别领域实验与计算流程。
---

## 摘要
分子识别——决定哪种试剂结合哪个靶标——支配着适应性免疫、基因调控、信号转导、RNA沉默、酶催化以及治疗药物的选择性。确定结合特异性仍依赖于实验筛选或领域特定的计算工具，而这些工具无法在不同结合模式间通用。Transformer的softmax注意力机制在数学上与支配分子结合的玻尔兹曼分布相同。这一恒等式，结合分子识别系统的五个条件，规定了用于跨模态结合预测的单一神经网络架构：双序列编码器、对称对比学习和一个可学习的物理温度。特异性基础模型（SFM）是这种源自物理学的序列到序列架构的一个实例，它将任意试剂-靶标序列对映射为结合兼容性分数，从而在分子识别领域实现双向检索，无需结构信息。首个用于抗体-抗原结合的SFM展示出比同类视觉语言模型高出约10万倍的数据效率。本文报告了六个分子识别领域的SFM——转录因子-DNA、酶-底物、肽-MHC、CRISPR gRNA-脱靶基因组DNA、microRNA-mRNA靶标以及小分子药物-靶标蛋白——使用相同的架构无需修改，并仅使用公开数据进行训练。通过从512个候选池中进行跨模态检索评估（随机基线为0.2%），六个领域内分布内的R@1范围从27.7%到98.0%。mir-SFM以98.0%的R@1检索miRNA靶标，包括约80%的已验证相互作用，而种子匹配工具无法发现这些相互作用。mhcSFM在训练中未出现的稀有HLA等位基因上达到95.4%的R@1。将crisprSFM应用于CRISPR脱靶预测，其精确度从仅靠汉明距离的33.2%提高到94.0%。所有六个SFM均由一位没有编程经验的领域专家使用氛围编码（自然语言指导的AI编码代理）构建，数值声明由独立的正交AI审计员验证。这些结果确立了SFM作为一类源自物理学、序列原生的模型，增强了分子识别领域的实验和计算工作流程。

## Abstract
Molecular recognition - the determination of which agent binds which target - governs adaptive immunity, gene regulation, signal transduction, RNA silencing, enzyme catalysis, and the selectivity of therapeutics. Determining binding specificity remains dependent on experimental screening or domain-specific computational tools that do not generalize across binding modalities. Transformer softmax attention is mathematically identical to the Boltzmann distribution governing molecular binding. This identity, together with five conditions of molecular recognition systems, prescribes a single neural network architecture for cross-modal binding prediction: dual sequence encoders, symmetric contrastive learning, and a learned physical temperature. A Specificity Foundation Model (SFM) is an instance of this physics-derived, sequence-to-sequence architecture that maps any agent-target sequence pair to a binding compatibility score, enabling bidirectional retrieval across molecular recognition domains without requiring structural information. The first SFM for antibody-antigen binding demonstrated ~100,000-fold greater data efficiency than comparable vision-language models. Here we report six SFMs across six molecular recognition domains - transcription factor-DNA, enzyme-substrate, peptide-MHC, CRISPR gRNA-off-target genomic DNA, microRNA-mRNA target, and small molecule drug-target protein - using the identical architecture without modification and trained using publicly available data only. Evaluated by cross-modal retrieval from pools of 512 candidates (random baseline 0.2%), in-distribution R@1 ranges from 27.7% to 98.0% across the six domains. mir-SFM retrieves miRNA targets at 98.0% R@1, including the ~80% of validated interactions that seed-matching tools cannot find. mhcSFM achieves 95.4% R@1 on held-out rare HLA alleles absent from training. Applying crisprSFM to CRISPR off-target prediction improves precision to 94.0% compared to 33.2% from Hamming distance alone. All six SFMs were built by a domain expert with no programming experience using vibe coding - natural-language-directed AI coding agents - with numerical claims independently verified by an orthogonal AI auditor. These results establish SFMs as a physics-derived, sequence-native class of model that augments experimental and computational workflows across molecular recognition domains.