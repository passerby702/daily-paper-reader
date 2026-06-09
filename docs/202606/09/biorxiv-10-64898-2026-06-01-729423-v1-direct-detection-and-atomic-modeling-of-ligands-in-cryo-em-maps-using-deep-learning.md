---
title: Direct Detection and Atomic Modeling of Ligands in Cryo-EM Maps Using Deep Learning
title_zh: 利用深度学习在冷冻电镜图中直接检测和原子建模配体
authors: "Li, S., Jain, A., Kagaya, Y., Park, J. H., Kihara, D."
date: 2026-06-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.01.729423v1.full.pdf"
tags: ["query:pocket-lig"]
score: 7.0
evidence: 直接从冷冻电镜图中检测并原子建模配体，用于基于结构的药物发现
tldr: 冷冻电镜在药物发现中日益重要，但小分子配体的密度检测和原子建模仍是难点。现有方法依赖高质量结构和预设位点，不适用于早期解析。本文提出Emap2lig两阶段深度学习框架：Emap2lig-Find在低至5Å分辨率下检测配体密度，Emap2lig-Build利用扩散模型生成配体原子结构。该框架实现了从实验图谱直接进行配体发现和建模，适用于广泛分辨率范围。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法难以在低分辨率或未知位点的情况下自动检测并构建配体原子结构，亟需统一的自动化方案。
method: 提出两阶段框架：Emap2lig-Find基于深度学习检测配体密度；Emap2lig-Build采用扩散模型生成原子坐标。
result: Emap2lig-Find在约5Å分辨率仍有效，Emap2lig-Build可自动构建配体原子结构。
conclusion: Emap2lig提供了从冷冻电镜图谱直接进行配体发现与建模的统一方案，拓展了应用范围。
---

## 摘要
冷冻电子显微镜（cryo-EM）通过表征大分子与小分子配体之间的相互作用，已成为基于结构的药物发现中日益重要的工具。然而，配体密度的计算解释仍然具有挑战性，尤其是在配体位置未知或局部图谱分辨率有限的情况下。现有方法通常需要高分辨率的大分子结构和预定义的结合位点，这限制了它们在早期结构测定中的适用性。迄今为止，还没有方法能够直接从实验cryo-EM图中同时可靠地检测配体密度并随后重建配体原子结构。

在这里，我们提出了Emap2lig，一个两阶段深度学习框架，用于从cryo-EM图中自动检测和原子建模配体。Emap2lig-Find识别配体相关密度，并对分辨率低至约5 Å的图谱保持有效。Emap2lig-Build随后使用基于扩散的生成模型构建配体原子结构。结合起来，Emap2lig提供了一个统一的框架，适用于广泛分辨率范围内的配体发现和建模。

## Abstract
Cryogenic electron microscopy (cryo-EM) has become an increasingly important for structure-based drug discovery by enabling characterization of interactions between macromolecules and small-molecule ligands. However, computational interpretation of ligand density remains challenging, particularly when ligand locations are unknown or local map resolution is limited. Existing methods generally require well-resolved macromolecular structures and predefined binding sites, limiting their applicability during early-stage structure determination. To date, no approach has been able to both reliably detect ligand density and subsequently reconstruct ligand atomic structures directly from experimental cryo-EM maps.

Here, we present Emap2lig, a two-stage deep learning framework for automated ligand detection and atomic modeling directly from cryo-EM maps. Emap2lig-Find identifies ligand-associated densities and remains effective for maps at resolutions as low as [~]5 [A]. Emap2lig-Build subsequently uses a diffusion-based generative model to build atomic ligand structures. Together, Emap2lig provides a unified framework for ligand discovery and modeling across a broad range of resolutions.