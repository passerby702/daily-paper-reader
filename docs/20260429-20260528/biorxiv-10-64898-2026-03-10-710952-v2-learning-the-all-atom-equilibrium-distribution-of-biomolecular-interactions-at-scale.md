---
title: Learning the All-Atom Equilibrium Distribution of Biomolecular Interactions at Scale
authors: "Wang, Y., Xu, Y., Li, W., Yu, H., Tan, W., Li, S., Huang, Q., Chen, N., Wu, X., Wu, Q., Liu, K."
date: 2026-04-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.10.710952v2.full.pdf"
tags: ["query:pocket-lig"]
score: 7.0
evidence: 用于采样蛋白-配体相互作用平衡分布的生成框架
tldr: 虽然AlphaFold等模型在静态结构预测上取得突破，但准确捕捉全原子平衡分布仍是挑战，主要因分子动力学模拟成本高。AnewSampling采用商空间生成框架与超1500万构象的大规模蛋白-配体轨迹数据，实现全原子高保真采样。在ATLAS基准上一致超越先前方法，并与真实MD统计对齐；在CDK2系统中成功恢复配体与侧链的耦合运动。这有望在密集型模拟前快速探索构象景观，阐明基本生物物理机制，加速功能性生物分子设计。
source: biorxiv
selection_source: fresh_fetch
motivation: 捕捉全原子平衡分布对于理解生物分子功能至关重要，但MD模拟成本过高，现有生成方法无法高保真复现。
method: 提出AnewSampling，基于商空间生成框架，利用自整理的1500万构象蛋白-配体轨迹数据库。
result: 在ATLAS基准上显著超越先前方法，并与真实MD紧密对齐；在CDK2中克服采样难点，恢复耦合运动。
conclusion: AnewSampling实现了全原子平衡分布高保真采样，可加速构象探索和功能分子设计。
---

## Abstract
Biomolecular functions are governed by dynamic conformational ensembles rather than static structures. While models like AlphaFold have revolutionized static structure prediction, accurately capturing the equilibrium distribution of all-atom biomolecular interactions remains a significant challenge due to the high computational cost of molecular dynamics (MD). We present AnewSampling, a transferable generative foundation framework designed for the high-fidelity sampling of all-atom equilibrium distributions, which is the first model to faithfully reproduce MD at the all-atom level. It uses a quotient-space generative framework to ensure mathematical consistency and leverages the largest self-curated database of protein-ligand trajectories to date, with over 15 million conformations. Statistically, AnewSampling consistently outperforms all prior generative methods on the ATLAS monomer benchmark, and the all-atom capabilities of AnewSampling enable close statistical alignment with ground-truth MD for evaluating atomic biomolecular interactions in protein-ligand dynamics. Furthermore, AnewSampling successfully recovers coupled ligand and side-chain motions in CDK2 systems, overcoming a major sampling hurdle inherent to conventional MD. AnewSampling enables rapid exploration of conformational landscapes prior to intensive simulations, elucidating fundamental biophysical mechanisms and accelerating the broader design of functional biomolecules.