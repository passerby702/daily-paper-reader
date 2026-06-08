---
title: "An Agentic Platform for Drug Repurposing Unified across Molecular, Phenotypic, and Clinical Scales"
title_zh: 一个跨分子、表型和临床尺度统一的药物重定位智能平台
authors: "Wang, C., El Moussaoui, M., Zhang, D., Prabhakaraalva, P., Merzliakov, S., Lu, R. J.-H., Zaman, N., Chakraborty, G., Huang, K.-l."
date: 2026-06-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.19.719462v2.full.pdf"
tags: ["query:pocket-lig"]
score: 6.0
evidence: 基于扩散的亲和力预测用于药物-靶标结合，属于口袋-配体主题
tldr: "药物重定位缺乏跨分子、表型和临床尺度的统一验证。LinkD框架通过扩散模型预测结合亲和度，结合选择性打分和分子对接，整合960细胞系敏感性及CRISPR数据，并利用1150万人的临床记录，实现多证据层协同。LinkD-Bind在BindingDB、Davis和KIBA的9项评测中8项排名第一，冷启动场景增益最大；LinkD-Select恢复95.3%已知靶点；LinkD-Pheno识别34个新药-基因对，前50候选含约85%已知靶点；基于人群数据，β-阻滞剂普萘洛尔和卡维地洛降低5年前列腺癌风险，经分子对接和细胞实验验证。平台提供自然语言查询，可广泛生成重定位假设。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有药物重定位方法依赖单一证据，缺乏跨分子、表型、临床尺度的统一验证与多证据整合。
method: 方法包括扩散亲和预测(LinkD-Bind)、选择性对接打分(LinkD-Select)、表型验证(LinkD-Pheno)和临床数据分析，统一多尺度证据。
result: "在9个评测中8个第一，恢复95.3%已知靶点，识别34个新药-基因对，人群分析证实β-阻滞剂降低前列腺癌风险。"
conclusion: LinkD通过多证据层协同实现高精度药物重定位，其在线平台支持自然语言查询，可有效生成新的重定位机会。
---

## 摘要
药物重定位为新疗法提供了一条有效途径，但现有计算方法依赖于单一证据链，且很少在不同生物尺度上得到验证。我们提出了LinkD，一个集成框架，统一了基于扩散的亲和力预测、蛋白质组范围选择性评分、表型验证和群体尺度临床证据。LinkD-Bind预测了14,981种药物与20,385个人类靶标之间的结合，在BindingDB、Davis和KIBA的9项评估中8项排名第一，在冷启动条件下增益最大。LinkD-Select通过结合选择性评分和分子对接，恢复了95.3%的已知药物-靶标对。LinkD-Pheno整合了960种癌细胞系的药物敏感性和CRISPR依赖性数据，识别出34个新的药物-基因对，并在前50个候选物中恢复了约85%的已知靶标。在来自西奈山和英国生物银行的1150万人中，LinkD优先推荐的β受体阻滞剂普萘洛尔（HR 0.82）和卡维地洛尔（HR 0.92）相对于美托洛尔降低了5年前列腺癌发病率，并通过ADRB2对接和LNCaP生长抑制得到证实。LinkD-Agent能够有效协调所有证据层，现已部署在公开可用的网络平台上（https://linkd-agent.onrender.com/），使广泛用户能够通过自然语言查询获得新的药物重定位机会。

## Abstract
Drug repurposing offers an effective path to new therapies, yet existing computational approaches rely on a single line of evidence and are rarely validated across biological scales. We present LinkD, an integrated framework that unifies diffusion-based affinity prediction, proteome-wide selectivity scoring, phenotypic validation, and population-scale clinical evidence. LinkD-Bind predicts binding across 14,981 drugs and 20,385 human targets, ranking first in 8 of 9 BindingDB, Davis, and KIBA evaluations, with the largest gains under cold-start conditions. LinkD-Select recovers 95.3% of known drug-target pairs by combining selectivity scoring and molecular docking. LinkD-Pheno integrates drug-sensitivity and CRISPR dependency data across 960 cancer cell lines, identifying 34 novel drug-gene pairs and recovering ~85% of known targets among the top 50 candidates. Across 11.5 million individuals from Mount Sinai and UK Biobank, LinkD-prioritized {beta}-blockers propranolol (HR 0.82) and carvedilol (HR 0.92) reduced 5-year prostate cancer incidence relative to metoprolol, corroborated by ADRB2 docking and LNCaP growth inhibition. LinkD-Agent, which can effectively orchestrate all evidence layers, is served on a publicly available web platform (https://linkd-agent.onrender.com/), enabling a wide range of users to derive new drug repurposing opportunities through natural language queries.