---
title: Objective curriculum-guided design of multi-property proteins
title_zh: 基于目标课程引导的多特性蛋白质设计
authors: "Liu, L., Zhao, J., Xie, X., Xu, S., Ren, M., Zhang, X., He, Z., Liu, F., Yu, C., Wang, K., Wang, X., Liang, X., Ye, X., Bu, D., Zhou, H."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.25.727596v1.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 使用课程引导框架进行蛋白质设计，属于分子生成任务
tldr: 设计同时具备多生化特性的功能蛋白仍具挑战，因属性常相互冲突。现有方法一次性联合优化并大量筛选，效率低。本文提出OCDesign，基于目标课程原理，分阶段有序引入目标，每轮通过计算生成、帕累托优选和实验验证。以蛋白A为例，从溶解度与结构一致性逐步过渡至结合亲和力与耐碱性，用更少湿实验实现了多属性蛋白设计，证明目标顺序是高维设计空间可达性的关键。
source: biorxiv
selection_source: fresh_fetch
motivation: 蛋白质设计需同时优化多属性，但它们常冲突，一次性优化并筛选罕见可行设计成本高。
method: 提出OCDesign框架，按课程顺序分阶段引入目标，每轮计算生成候选序列，评估多属性，基于帕累托最优选择，并实验验证新引入目标的作用。
result: 以蛋白A为模型，一次性优化失败，而分阶段课程用更少湿实验成功设计出同时具备溶解性、结构一致性、结合亲和力和耐碱性的蛋白。
conclusion: OCDesign提供实用策略，通过有序组织多目标提升设计效率，揭示目标顺序是高维空间可达性的决定因素。
---

## 摘要
设计同时具备多种生化特性的功能性蛋白质仍是一项重大挑战，因为关键蛋白质特性（如溶解度、稳定性、结合亲和力与化学耐受性）往往相互依赖甚至相互冲突。当前方法通常试图一次性联合优化多个功能目标，随后进行大规模筛选以识别稀缺的可实现设计。在此，我们引入 OCDesign，一个基于目标课程引导的多特性蛋白质设计框架。OCDesign 基于目标课程原则，即引入目标的顺序可以塑造功能解的可及性。在 OCDesign 的每个设计轮次中，通过计算机模拟生成候选序列，评估多种特性，基于帕累托最优权衡进行选择，并进行实验验证，每个实验阶段测试课程中新引入目标的作用。以抗体结合蛋白 A 为模型系统，我们展示一次性优化无法产生功能性设计，而分阶段课程——从溶解度和结构一致性到结合亲和力，再到耐碱性——能够通过显著减少的湿实验次数，设计出具备多种所需特性的蛋白质。这些结果确立了 OCDesign 作为一种实用的计算-实验策略，用于组织和整合蛋白质设计中的多个目标，并表明目标排序是高维设计空间中可及性的关键决定因素。

## Abstract
Designing functional proteins that simultaneously possess multiple biochemical properties remains a significant challenge, as key protein properties, such as solubility, stability, binding affinity, and chemical resistance, are often interdependent or even conflicting. Current approaches typically attempt to jointly optimize multiple functional objectives in one shot, followed by extensive screening to identify rare feasible designs. Here, we introduce OCDesign, an objective curriculum-guided framework for multi-property protein design. OCDesign is based on the objective curriculum principle, which states that the order in which objectives are introduced can shape the accessibility of functional solutions. In each design round of OCDesign, candidate sequences are generated in silico, assessed across multiple properties, selected based on Pareto-optimal trade-offs, and experimentally validated, with each experimental stage testing the role of the newly introduced objective within the curriculum. Using antibody-binding protein A as a model system, we show that one-shot optimization fails to yield functional designs, whereas a staged curriculum--progressing from solubility and structural consistency to binding affinity, and then to alkaline resistance--enables the design of proteins possessing multiple desired properties through substantially fewer wet-lab experiments. These results establish OCDesign as a practical computational-experimental strategy for organizing and integrating multiple objectives in protein design, and suggest that objective ordering is a key determinant of accessibility in high-dimensional design spaces.