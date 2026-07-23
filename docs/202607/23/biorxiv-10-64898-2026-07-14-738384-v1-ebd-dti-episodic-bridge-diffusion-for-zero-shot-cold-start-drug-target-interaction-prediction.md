---
title: "EBD-DTI: Episodic Bridge Diffusion for Zero-Shot Cold-Start Drug-Target Interaction Prediction"
title_zh: "EBD-DTI: 面向零样本冷启动药物-靶标相互作用预测的片段桥接扩散"
authors: "Liu, J., Le, J., Wei, C., Liu, M., Yin, Z."
date: 2026-07-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.14.738384v1.full.pdf"
tags: ["query:pocket-lig"]
score: 6.0
evidence: 生成模型用于蛋白-配体相互作用预测，采用扩散方法
tldr: "药物-靶标相互作用预测中，针对完全未见实体（冷启动）的零样本推理是难题。现有图方法依赖全局扩散或需少量样本，序列方法忽略拓扑。EBD-DTI提出情景式冷启动训练，在每轮随机掩码训练实体模拟冷启动，并通过桥接扩散从最近邻居获取上下文，实现无需任何已知交互的零样本预测。在BioSNAP等三个基准上，严格零样本评估下性能领先，情景训练使AUC提升最高12%。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738384-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 781, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738384-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1759, \"height\": 581, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-14-738384-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 874, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-14-738384-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1797, \"height\": 527, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-14-738384-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1793, \"height\": 524, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-14-738384-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 500, \"height\": 414, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-14-738384-v1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 588, \"height\": 806, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-14-738384-v1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1428, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-14-738384-v1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 833, \"height\": 469, \"label\": \"Table\"}]"
motivation: 解决图模型在零样本冷启动场景下无法泛化到完全未见实体的问题，避免全局扩散或需已知样本的局限。
method: 采用情景式冷启动训练，每轮随机掩码部分实体作为伪冷启动，结合桥接条件局部子图与多跳扩散传递邻居信息。
result: "在BioSNAP、BindingDB、DrugBank上严格零样本评估，性能优于或匹敌SOTA，情景训练提升AUC达12%。"
conclusion: EBD-DTI为图模型提供有效的零样本冷启动推理框架，无需任何已知交互即可预测新药物或蛋白的靶标。
---

## 摘要
预测完全未见过的药物或蛋白质的药物-靶标相互作用（DTI）——冷启动问题——仍然是计算药物发现中的关键挑战。基于序列的方法自然支持零样本泛化，但它们常常忽略关系拓扑，而现有的基于图的方法要么依赖于模糊归纳与直推评估边界的全局扩散，要么在测试时需要少量已知相互作用样本（少样本）。我们提出了EBD-DTI，这是一个在基于图的DTI模型中实现零样本推理的框架，无需对未见实体有任何已知相互作用。关键创新是片段式冷启动训练：在每个训练周期，随机选择一部分训练实体进行掩码，并将其视为伪冷启动，迫使模型通过显式梯度监督学习冷启动推理。桥接条件局部子图结合多跳扩散，为冷实体提供来自其最近观测邻居的关系上下文。在三个基准（BioSNAP、BindingDB和DrugBank）上的实验表明，在严格的零样本评估下，EBD-DTI达到了与最先进方法竞争或更优的性能，其中片段式训练将AUC提升了高达12%。

## Abstract
Predicting drug-target interactions (DTI) for entirely unseen drugs or proteins---the cold-start problem---remains a critical challenge in computational drug discovery. While sequence-based methods naturally support zero-shot generalization, they often ignore relational topology, and existing graph-based approaches either rely on global diffusion that blurs the boundary between inductive and transductive evaluation or require a few known interaction samples at test time (few-shot). We present EBD-DTI, a framework that enables zero-shot inference in graph-based DTI models without requiring any known interactions for unseen entities. The key innovation is episodic cold-start training: at each epoch, a random subset of training entities is masked and treated as pseudo-cold, forcing the model to learn cold-start inference with explicit gradient supervision. A bridge-conditioned local subgraph, together with multi-hop diffusion, provides cold entities with relational context from their nearest observed neighbors. Experiments on three benchmarks (BioSNAP, BindingDB, and DrugBank) demonstrate that EBD-DTI achieves competitive or superior performance compared to state-of-the-art methods under strict zero-shot evaluation, with episodic training improving AUC by up to 12%.