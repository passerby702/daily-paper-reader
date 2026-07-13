---
title: A generalisable framework to inject distance information into Alphafold-like structure predictors
title_zh: 一种向类AlphaFold结构预测器注入距离信息的通用框架
authors: "Mirabello, C., Wallner, B., Orekhov, V., Nystedt, B., Pearce, N."
date: 2026-07-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.02.736010v1.full.pdf"
tags: ["query:pocket-lig"]
score: 7.0
evidence: 向结构预测器注入距离先验改善了蛋白质-配体复合物预测，支持口袋感知生成
tldr: 针对AlphaFold类结构预测器难以灵活注入外部距离先验的问题，提出通用框架通过偏置pair representation在distogram中产生期望特征，进而影响结构预测。方法可用于采样替代构象、整合NMR NOESY数据、提升蛋白-蛋白及蛋白-配体复合物预测成功率。在AlphaFold 2和OpenFold3上验证有效，开源可用。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736010-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1270, \"height\": 1676, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736010-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1319, \"height\": 1495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736010-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1361, \"height\": 1244, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-736010-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1349, \"height\": 1327, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-02-736010-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1353, \"height\": 526, \"label\": \"Table\"}]"
motivation: 现有结构预测方法虽成功，但常需补充外部距离先验，缺乏通用注入机制。
method: 通过偏置pair representation，使distogram产生期望特征，从而将距离信息注入预测流程。
result: 成功实现替代状态采样、NMR NOESY数据整合及复合物预测性能提升。
conclusion: 提出一种通用可迁移的注入框架，适用于多种AlphaFold类模型，拓展了结构预测的应用范围。
---

## 摘要
结构预测方法现已能成功地从序列预测三维结构。然而，通常仍需要向这些方法补充关于结构中成对距离的外部先验信息。我们提出了一种通用方法，通过偏置成对表示以在距离图中产生理想特征，从而将先验信息注入类AlphaFold结构预测器，这些特征随后会反映在结构中。我们展示了该方法的应用：通过选择性推拉移动氨基酸对来采样替代状态；将NMR NOESY数据与结构预测整合；以及提高蛋白质-蛋白质和蛋白质-配体复合物预测的成功率。我们证明该方法既适用于AlphaFold 2，也适用于AlphaFold 3的复现版本（OpenFold3）。

resTrain是开源的，可在GitHub上作为Colab笔记本供所有用户使用：github.com/clami66/resTrain

## Abstract
Structure prediction methods are now highly successful at predicting three-dimensional structures from sequence. However, it is still often desirable to supplement these methods with additional external priors on pairwise distances in the structures. We present a general method for injecting prior information into AlphaFold-like structure predictors by biasing the pair representation to produce desirable features in the distogram, which are then reflected in the structures. We demonstrate this approach to: sample alternate states by selectively pushing or pulling mobile amino acid pairs; integrate NMR NOESY data with structure prediction; and improve the success of protein-protein and protein-ligand complex prediction. We demonstrate that this approach is applicable both to AlphaFold 2 and a reproduction of AlphaFold 3 (OpenFold3).

resTrain is open source, available to all users on GitHub and as a Colab notebook: github.com/clami66/resTrain