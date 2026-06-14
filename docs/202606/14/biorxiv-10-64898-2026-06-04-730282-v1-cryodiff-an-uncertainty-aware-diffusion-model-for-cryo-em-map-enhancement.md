---
title: "CryoDiff: An uncertainty-aware diffusion model for Cryo-EM map enhancement"
title_zh: "CryoDiff: 一种用于冷冻电镜图谱增强的不确定性感知扩散模型"
authors: "Wen, B., He, B., Cheng, Y., Zhou, S., Han, R., Zhang, F."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.04.730282v1.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 扩散模型用于增强3D冷冻电镜图谱
tldr: "冷冻电镜图受噪声和信号衰减影响，现有后处理方法过平滑且缺乏置信度估计。CryoDiff采用多步扩散过程逐步去噪恢复高分辨率特征，并通过蒙特卡洛采样导出体素级置信度。实验表明，CryoDiff在FSC0.5指标上平均提升0.356Å，应用于ModelAngelo模型构建时完整度提高5.5%。该方法首次实现了地图增强与不确定性估计的联合建模，显著提升了结构解析的准确性和可解释性。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有cryo-EM后处理方法过平滑且无法提供可靠置信度估计，限制地图可解释性。
method: 提出CryoDiff，基于扩散模型的多步去噪框架，利用蒙特卡洛采样得到体素级不确定性估计。
result: "CryoDiff在FSC0.5指标上平均提升0.356Å，且ModelAngelo模型完整度提高5.5%。"
conclusion: 首次将扩散模型用于cryo-EM图增强与不确定性联合建模，有效提升结构解析精度。
---

## 摘要
冷冻电子显微镜(cryo-EM)能够实现大型大分子复合物的高分辨率结构测定。然而，冷冻电镜图谱的可解释性常常受到大量背景噪声和信号衰减的阻碍，这些因素掩盖了结构细节。尽管现有的后处理方法可以部分缓解这些伪影，但它们通常存在过度平滑的问题，并且缺乏可靠的信度估计。在此，我们提出CryoDiff，一种用于冷冻电镜图谱增强的不确定性感知扩散模型。CryoDiff采用多步扩散过程，逐步去噪并恢复高分辨率结构特征。重要的是，CryoDiff结合了从蒙特卡罗采样导出的体素级信度度量。它将图谱增强和体素级不确定性估计统一在一个基于扩散的生成框架中，这是首次在冷冻电镜图谱增强中实现这种联合建模的方法。在综合实验中，CryoDiff在图谱-模型相关性和图谱可解释性方面显著优于现有方法，将平均FSC0.5指标相较于最先进方法提升了0.356 [Å]。当应用于使用ModelAngelo进行从头模型构建时，CryoDiff进一步将模型完整度提高了5.5%，超过了竞争方法所达到的提升。

## Abstract
Cryogenic electron microscopy (cryo-EM) enables high-resolution structural determination of large macromolecular complexes. However, the interpretability of cryo-EM maps is often hindered by substantial background noise and signal attenuation, which obscure structural details. Although existing post-processing methods can partially mitigate these artifacts, they typically suffer from over-smoothing and lack reliable confidence estimation. Here, we present CryoDiff, an uncertainty-aware diffusion model for cryo-EM map enhancement. CryoDiff employs a multi-step diffusion process to progressively denoise and restore high-resolution structural features. Importantly, CryoDiff incorporates a voxel-wise confidence metric derived from Monte Carlo sampling. It unifies map enhancement and voxel-level uncertainty estimation within a diffusion-based generative framework, representing the first approach to achieve such joint modeling for cryo-EM map enhancement. In comprehensive experiments, CryoDiff markedly out-performs existing methods in both map-model correlation and map interpretability, improving the average FSC0.5 metric by 0.356 [A] over state-of-the-art approaches. When applied to de novo model building with ModelAngelo, CryoDiff further increases model completeness by 5.5%, exceeding the gains achieved by competing method.