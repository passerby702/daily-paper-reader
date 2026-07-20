---
title: A Glycan-Aware Diffusion Model for Carbohydrate and Glycoprotein Structure Prediction
title_zh: 一种面向碳水化合物和糖蛋白结构预测的糖链感知扩散模型
authors: "Sundar, K., Yang, H."
date: 2026-07-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.16.738959v1.full.pdf"
tags: ["query:diff-gen"]
score: 6.0
evidence: 扩散模型用于生物分子结构预测，与分子生成相关
tldr: 现有生物分子扩散模型难以处理聚糖的分支拓扑、构象灵活性和立体化学规则。为此，我们提出SweetFold，将糖类表示为伪聚合物并引入糖类专用架构与立体化学监督。在单糖、寡糖、凝集素和糖蛋白基准上，SweetFold显著提升结构预测指标，同时保持蛋白质性能不变。这证明化学局部表示和监督可将扩散模型成功扩展到糖类化学领域。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738959-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1873, \"height\": 1206, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738959-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 944, \"height\": 1115, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738959-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1879, \"height\": 1397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738959-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1866, \"height\": 1250, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738959-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1859, \"height\": 1582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738959-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1712, \"height\": 1181, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738959-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 496, \"height\": 128, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738959-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 340, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738959-v1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1664, \"height\": 815, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-16-738959-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1712, \"height\": 401, \"label\": \"Table\"}]"
motivation: 现有扩散模型无法同时处理聚糖的分支拓扑、构象灵活性和严格立体化学规则。
method: SweetFold将糖类表示为伪聚合物，结合糖类专用架构、立体化学监督和糖中心训练课程。
result: 在单糖、寡糖、凝集素和糖蛋白基准上，SweetFold结构指标优于基线，且蛋白质性能不变。
conclusion: 化学局部表示和监督可有效将扩散模型扩展到糖类结构预测。
---

## 摘要
生物分子扩散模型现可预测蛋白质和异质复合物，但糖链仍具挑战性，因其分支拓扑、构象灵活性和严格立体化学规则必须同时捕获。我们开发了SweetFold，它是Boltz-1x的糖链感知适配版本，用于自由糖链、糖蛋白和蛋白质-糖链复合物的结构预测。SweetFold将糖链表示为伪聚合物而非通用配体，保留了单糖身份、异头状态、糖苷键连接和原子级立体化学。我们将这种表示与糖链特定架构、立体化学监督以及以糖为中心的训练课程相结合。在单糖、寡糖、凝集素和糖蛋白基准测试中，与基线全原子扩散模型相比，SweetFold改善了结构指标，同时保持了仅蛋白质基准的性能。这些结果表明，化学局域化的表示和监督可以将生物分子扩散模型扩展到碳水化合物化学。

## Abstract
Biomolecular diffusion models can now predict proteins and heterogeneous complexes, but glycans remain difficult because their branched topology, conformational flexibility, and strict stereochemical rules must be captured simultaneously. We developed SweetFold, a glycan-aware adaptation of Boltz-1x for the structure prediction of free glycans, glycoproteins, and protein-glycan complexes. SweetFold represents glycans as pseudo-polymers rather than generic ligands, preserving monosaccharide identity, anomeric state, glycosidic connectivity, and atom-level stereochemistry. We pair this representation with glycan-specific architecture, stereochemical supervision, and a sugar-centric training curriculum. Across monosaccharide, oligosaccharide, lectin, and glycoprotein benchmarks, SweetFold improves structural metrics relative to baseline all-atom diffusion models while retaining protein-only benchmark performance. These results show that chemically localized representation and supervision can extend biomolecular diffusion models to carbohydrate chemistry.