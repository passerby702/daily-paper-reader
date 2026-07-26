---
title: "CAFE: A Co-folding Approach for Fragment Exploration of Allosteric and Cryptic Binding Sites"
title_zh: CAFE：一种用于别构和隐秘结合位点片段探索的共折叠方法
authors: "Purnomo, J. C., Sun, K., Head-Gordon, T."
date: 2026-07-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.19.739466v1.full.pdf"
tags: ["query:pocket-lig"]
score: 6.0
evidence: 探索变构结合位点的方法，与口袋特异性分子生成相关
tldr: 共折叠模型在别构药物发现中潜力巨大，但存在系统性偏向正构配体结合的问题，即使进行片段筛选也因记忆效应而受限。CAFE通过引入竞争性正构阻断剂（如激酶中使用ADP），迫使片段探索别构和隐蔽结合位点，无需后处理即可获得强结合自由能，并发现传统工具未检出的隐蔽口袋。该方法作为无需训练的推理时协议，显著提升了共折叠模型在别构和隐蔽位点药物发现中的实用性。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1622, \"height\": 595}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1491, \"height\": 1316}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1411, \"height\": 430}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1612, \"height\": 1207}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1598, \"height\": 1112}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1377, \"height\": 1211}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1668, \"height\": 1216}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1367, \"height\": 481}]"
motivation: 共折叠模型因偏向正构配体结合而难以发现别构位点，片段筛选也受记忆效应限制。
method: CAFE使用竞争性正构阻断剂（如ADP）与片段共折叠，迫使片段探索非经典位点。
result: 在激酶家族中，CAFE显著增加了别构位点探索，结合自由能媲美晶体结构，并发现了隐蔽口袋。
conclusion: CAFE作为训练无关的推理协议，有效克服了共折叠模型的偏见，拓展了别构药物发现能力。
---

## 摘要
共折叠模型在别构药物发现方面具有巨大潜力，但一直因其对正构配体结合的系统性偏差而受到严重阻碍。虽然片段筛选已被提出用于别构结合位点的发现，但我们表明共折叠模型仍然存在记忆化问题，其中化学结构更简单的片段也默认结合到典型的正构结合位点。为了克服这些限制，我们引入了CAFE（片段探索的共折叠方法），这是一种利用竞争性正构阻断剂将片段引导至非典型位点的共折叠协议，如使用Boltz-2共折叠模型所展示的那样。以ADP作为激酶家族的正构阻断剂，我们发现CAFE显著增加了片段对别构结合位点的探索，其绝对结合自由能非常强，与已知晶体学姿态匹配或超越，且无需对Boltz-2预测进行事后优化。我们还表明，CAFE能够识别传统口袋预测工具无法检测到的隐秘结合口袋，其中一些在热力学上比别构或正构口袋更有利。为了证明其通用性，我们将CAFE应用于使用I型正构阻断剂针对激酶蛋白、已知正构配体作为阻断剂针对RAS-MAPK信号通路中的非激酶蛋白，以及使用片段库进行虚拟筛选以发现能够选择性结合别构和隐秘结合位点的新片段。CAFE确立了正构阻断和片段筛选作为一种无需训练、推理时使用的协议，有助于克服当前共折叠模型的一些局限性，同时提升它们在别构和隐秘结合药物发现中的巨大潜力。

## Abstract
Co-folding models hold immense potential for allosteric drug discovery, but have been severely hampered by their systematic bias toward orthosteric ligand binding. While fragment screening has been proposed for allosteric binding site discovery, we show that co-folding models still suffer from memorization in which chemically simpler fragments also default to canonical orthosteric binding sites. To overcome these limitations, we introduce CAFE (Co-folding Approach for Fragment Exploration), a co-folding protocol that uses competitive orthosteric blockers to divert fragments into non-canonical sites as illustrated here with the Boltz-2 co-folding model. Using ADP as an orthosteric blocker for the kinase family, we find CAFE substantially increases the allosteric binding site exploration for fragments, with notably strong absolute binding free energies that match or exceed those of known crystallographic poses, without post-hoc refinement of the Boltz-2 prediction. We also show that CAFE identifies cryptic binding pockets undetected by conventional pocket prediction tools, some of which are more thermodynamically favorable than the allosteric or orthosteric pockets. To demonstrate generality, we apply CAFE using Type I orthosteric blockers for kinase proteins, known orthosteric ligands as blockers for non-kinase proteins in the RAS-MAPK signaling pathway, and for virtual screening campaigns using fragment libraries for new fragments that selectively engage allosteric and cryptic binding sites. CAFE establishes orthosteric blocking and fragment screening as a training-free, inference-time protocol that helps overcome some of the limitations of current co-folding models while elevating their great promise for allosteric and cryptic binding drug discovery.