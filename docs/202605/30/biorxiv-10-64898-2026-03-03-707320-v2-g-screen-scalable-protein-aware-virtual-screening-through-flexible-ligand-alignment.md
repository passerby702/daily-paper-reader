---
title: "G-screen: Scalable Protein-Aware Virtual Screening through Flexible Ligand Alignment"
title_zh: G-screen：通过柔性配体比对实现可扩展的蛋白感知虚拟筛选
authors: "Jung, N., Park, H., Yang, J., Seok, C."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.03.707320v2.full.pdf"
tags: ["query:pocket-lig"]
score: 7.0
evidence: 蛋白感知虚拟筛选用于基于结构的配体发现
tldr: 虚拟筛选中，传统配体方法快速但忽略蛋白结构，而对接方法建模蛋白质-配体相互作用却计算成本高昂。G-screen框架利用参考复合物结构，通过灵活全局对齐（G-align）快速产生配体构象，并基于药效团交互进行蛋白感知评估，无需完整对接。在DUD-E、LIT-PCBA、MUV基准集上，G-screen取得与代表性方法相当的区分能力和早期富集，同时维持毫秒级每分子速度。作为中间策略，它可在具有参考复合物结构时高效预筛超大型化学库。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有虚拟筛选方法难以同时实现可靠的蛋白质感知建模和高通量计算，尤其对超大化学空间。
method: 利用参考蛋白-配体复合物，G-align执行灵活全局对齐生成配体姿态假设，再结合蛋白感知药效团交互进行快速评分。
result: 在多个公共数据集上表现出竞争性的鉴别力和早期富集，每分子运行时间达毫秒级，支持多线程。
conclusion: 提供一种实用的可扩展替代方案，介于传统配体筛选和全对接之间，适用于有参考复合物结构的超大规模过滤。
---

## 摘要
虚拟筛选长期以来一直是合理配体发现的核心计算工具，能够从大型化学库中系统性地优先筛选候选分子。尽管显式考虑蛋白质-配体相互作用的对接及相关方法经过数十年的发展和完善，但实现可靠的蛋白感知相互作用建模和计算可扩展性仍然是一个开放挑战，尤其是在超大型化学空间中。基于配体的方法快速且稳健，但未显式纳入蛋白质结构，而基于对接的方法虽能更直接地模拟蛋白质-配体相互作用，但计算成本显著更高。在此，我们提出了 G-screen，一个免费且可扩展的蛋白感知虚拟筛选框架，适用于当有一个实验确定或预测的参考蛋白质-配体复合物结构可用的情况。G-screen 并非执行计算密集型的全对接与显式构象采样和优化，而是利用柔性全局比对算法 (G-align) 快速生成比对引导的构象假设。随后，利用从参考复合物中提取的蛋白感知药效团相互作用对生成的比对构象进行评估，实现显式的原子级相互作用分析，同时保留了基于配体的比对方法的可扩展性和稳健性。在 DUD-E、LIT-PCBA 和 MUV 数据集上的基准测试表明，G-screen 相对于代表性的基于配体和基于对接的方法，在区分能力和早期富集方面具有竞争力，同时在多线程执行下保持每分子毫秒级的运行时间。这些结果使 G-screen 成为一种实用且可扩展的中间策略，介于传统的基于配体的虚拟筛选和计算密集型的对接工作流程之间，用于在有参考复合物结构可用时高效地过滤超大型化学库。G-screen 和 G-align 分别免费提供于 https://github.com/seoklab/gscreen 和 https://github.com/seoklab/galign。

## Abstract
Virtual screening has long been a central computational tool for rational ligand discovery, enabling the systematic prioritization of candidate molecules from large chemical libraries. Although docking and related approaches that explicitly account for protein-ligand interactions have been developed and refined over several decades, achieving both reliable protein-aware interaction modeling and computational scalability remains an open challenge, particularly for ultra-large chemical spaces. Ligand-based methods are fast and robust but do not explicitly incorporate protein structure, whereas docking-based approaches model protein-ligand interactions more directly at substantially higher computational cost. Here, we present G-screen, a freely available and scalable protein-aware virtual screening framework designed for cases in which an experimentally determined or predicted reference protein-ligand complex structure is available. Rather than performing computationally intensive full docking with explicit pose sampling and optimization, G-screen rapidly generates alignment-guided pose hypotheses using a flexible global alignment algorithm (G-align). The resulting aligned poses are subsequently evaluated using protein-aware pharmacophore interactions derived from the reference complex, enabling explicit atomic-level interaction analysis while retaining the scalability and robustness of ligand-based alignment methods. Benchmarking on DUD-E, LIT-PCBA, and MUV datasets demonstrates that G-screen achieves competitive discrimination and early enrichment relative to representative ligand-based and docking-based methods, while maintaining millisecond-scale per-molecule runtimes under multi-threaded execution. These results position G-screen as a practical and scalable intermediate strategy between conventional ligand-based virtual screening and computationally intensive docking workflows for efficiently filtering ultra-large chemical libraries when a reference complex structure is available. G-screen and G-align are freely available at https://github.com/seoklab/gscreen and https://github.com/seoklab/galign, respectively.