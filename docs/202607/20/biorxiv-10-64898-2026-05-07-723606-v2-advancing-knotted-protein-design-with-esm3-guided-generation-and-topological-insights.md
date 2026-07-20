---
title: "Advancing Knotted Protein Design with ESM3: Guided Generation and Topological Insights"
title_zh: 利用ESM3推进打结蛋白设计：引导生成与拓扑洞察
authors: "Marsalkova, E., Simecek, P."
date: 2026-07-14
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.07.723606v2.full.pdf"
tags: ["query:diff-gen"]
score: 6.0
evidence: 使用ESM3引导生成打结蛋白质设计
tldr: "蛋白质拓扑结构（如打结蛋白质）是检验生成模型表征能力的理想探针。本文利用多模态语言模型ESM3，通过拓扑感知引导解码生成打结蛋白质，成功率高达89%，远超未引导方法（~0.5%）。但人工结的置信度指标（pLDDT/pTM）低于真实结，需谨慎解释。鲁棒性分析显示，平均改变84%序列才破坏结，且结构漂移先于拓扑破坏，表明拓扑比特定三维结构更鲁棒。该工作为理解生成模型如何表征罕见全局结构特征提供了新视角。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-05-07-723606-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 901, \"height\": 938, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-05-07-723606-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1662, \"height\": 717, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-05-07-723606-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1351, \"height\": 773, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-05-07-723606-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1522, \"height\": 955, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-05-07-723606-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1499, \"height\": 1137, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-05-07-723606-v2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1517, \"height\": 952, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-05-07-723606-v2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1716, \"height\": 557, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-05-07-723606-v2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1278, \"height\": 423, \"label\": \"Table\"}]"
motivation: 现有蛋白质语言模型对复杂拓扑特征的捕获能力未知，以罕见打结蛋白质为探针，检验模型对全局结构表示的理解。
method: 使用ESM3模型，结合拓扑感知的引导解码策略，生成打结蛋白质结构，并与未引导扩散方法对比。
result: "引导解码使打结成功率从~0.5%提升至89%；人工结置信度低于真实结；破坏结需平均改变84%序列，且拓扑在结构漂移后仍保持。"
conclusion: 打结蛋白质可作为有效探针，揭示生成模型对稀有全局结构特征的表示能力，并表明拓扑鲁棒性优于具体三维构象。
---

## 摘要
多模态蛋白质语言模型已经改变了蛋白质设计，但它们捕捉复杂拓扑特征的能力仍知之甚少。我们以打结蛋白（一种主链形成非平凡拓扑结的稀有结构）为测试案例，利用生成式蛋白质语言模型ESM3来探测这一能力。拓扑感知的引导解码显著富集了ESM3输出中的打结拓扑结构，产生的结构中89%被分类为打结（95%置信区间：81-94%），而基于无引导扩散的方法仅为约0.5%。置信度分析显示，新生成的人工结在同一流程下评估时，其ESM3 pLDDT和pTM低于真实打结蛋白，这提示在独立验证前应谨慎地将生成示例视为模型样本。相反，对真实打结蛋白的鲁棒性分析具有高置信度：平均而言，在结断裂前必须改变84%的蛋白质序列，且损失遵循尖锐阈值而非逐渐退化。引人注目的是，结构漂移在拓扑破坏之前就已显著累积，表明拓扑比特定的三维结构更鲁棒。这些发现将打结蛋白定位为探究生成式蛋白质模型如何表征稀有全局结构特征的有用探针。

## Abstract
Multimodal protein language models have transformed protein design, yet their capacity to capture complex topological features remains poorly understood. We use knotted proteins, rare structures in which the backbone forms a nontrivial topological knot, as a test case to probe this capacity using ESM3, a generative protein language model. Topology-aware guided decoding strongly enriches ESM3 outputs for knotted topologies, producing structures classified as knotted at an 89% success rate (95% CI: 81- 94%), compared to ~0.5% for unguided diffusion-based approaches. A confidence analysis shows that freshly generated artificial knots have lower ESM3 pLDDT and pTM than real knotted proteins evaluated under the same pipeline, motivating a cautious interpretation of generated examples as model samples pending independent validation. In contrast, the robustness analyses on real knotted proteins are high-confidence: on average 84% of the protein sequence must be altered before the knot breaks, and the loss follows a sharp threshold rather than gradual degradation. Strikingly, structural drift accumulates well before topological disruption, suggesting that topology is more robust than specific three-dimensional arrangement. These findings position knotted proteins as a useful probe of how generative protein models represent rare, global structural features.