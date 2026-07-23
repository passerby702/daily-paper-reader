---
title: ProteinSketch translates spatial intuition into protein design with bimanual interaction in VR
title_zh: ProteinSketch：通过VR中的双手交互将空间直觉转化为蛋白质设计
authors: "Ma, D., Lee, J., Lee, H., Lee, S.-H., Oh, Y. G., Kim, Y.-e., Jin, T., Sutthiwanna, S., Lee, S.-J., Jeon, W., Ahn, J., Cho, R., Park, H., Jeong, S., Bae, S.-H., Kim, H. M."
date: 2026-07-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.19.739460v1.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 扩散模型用于蛋白质三维结构生成
tldr: 蛋白质设计面临人类对三维结构控制有限的问题。ProteinSketch通过双手VR交互让用户直接绘制骨架和体积包络，转化为扩散模型约束，实现实时细化与拓扑构建。体积条件化控制各向异性几何，经冷冻电镜验证，并用于设计功能结合子及扩展结合子表面。该人机协作框架融合空间直觉与生成式AI，实现形状定向的蛋白质设计。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739460-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1799, \"height\": 1840, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739460-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1820, \"height\": 1741, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739460-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1803, \"height\": 2267, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739460-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1789, \"height\": 1732, \"label\": \"Figure\"}]"
motivation: 现有生成式AI蛋白质设计缺乏对三维结构的直观控制，需要人机交互框架。
method: 基于RFdiffusion的VR平台，用户双手绘制骨架和包络作为约束，实时细化生成蛋白质。
result: 体积约束实现高保真各向异性几何控制，并成功设计功能结合子及扩展复杂分子环境中的结合表面。
conclusion: ProteinSketch整合人类空间推理与生成式AI，实现空间定向、形状控制的蛋白质结构与功能设计。
---

## 摘要
基于生成式人工智能的蛋白质设计能够为所需功能创建多样化的结构，但人类设计师对三维架构的控制有限。我们开发了ProteinSketch，这是一个双手操作的虚拟现实平台，在该平台中，沉浸式的主链草图和体积包络被直接创建并转化为用于基于扩散的蛋白质生成的约束条件。基于RFdiffusion的实时细化实现了用户指定蛋白质拓扑的交互式探索和构建。草图包络的体积条件化实现了对各向异性几何形状的高保真控制，并通过冷冻电镜得到确认。这些用户定义的体积约束使得功能结合体的设计以及将现有的微型结合体扩展到在复杂分子环境中使用常规方法难以触及的表面成为可能。这种人机协作框架将人类空间推理与生成式人工智能相结合，实现对蛋白质结构和功能的空间定向、形状控制设计。

## Abstract
Generative AI-based protein design can create diverse structures for desired functions but offers human designers limited control over three-dimensional architectures. We developed ProteinSketch, a bimanual virtual reality platform in which immersive backbone sketches and volumetric envelopes are directly created and translated into constraints for diffusion-based protein generation. RFdiffusion-based real-time refinement enabled interactive exploration and construction of user-specified protein topologies. Volumetric conditioning of sketched envelopes enabled high-fidelity control of anisometric geometries, confirmed by cryo-electron microscopy. These user-defined volumetric constraints enabled functional-binder design and extension of pre-existing minibinders to surfaces otherwise difficult to access within complex molecular environments using conventional design approaches. This collaborative human-AI framework integrates human spatial reasoning with generative AI for spatially directed, shape-controlled design of protein structure and function.