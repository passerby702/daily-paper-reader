---
title: "IDPForge: Deep Learning of Proteins with Global and Local Regions of Disorder"
title_zh: IDPForge：包含全局和局部无序区域的蛋白质深度学习
authors: "De Castro, S., Zhang, O., Liu, Z. H., Forman-Kay, J. D., Head-Gordon, T."
date: 2026-06-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.25.714313v2.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 用于无序蛋白构象系综生成的变压器蛋白质语言扩散模型
tldr: 现有蛋白结构预测方法对 intrinsically disordered proteins/regions (IDPs/IDRs) 的构象系综预测置信度低。本文提出 IDPForge，利用 transformer 蛋白语言扩散模型直接生成全原子 IDP/IDR 构象系综，同时保持折叠域结构。该方法无需序列特异性训练、粗粒化反向变换或系综重新加权，生成的构象与 NMR 和 SAXS 实验数据高度一致，并可选配实验约束偏置。IDPForge 作为开源工具，将促进含内在无序蛋白的整合结构研究。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法对无序蛋白构象预测置信度低，且需要序列特异性训练或后处理。
method: 利用 transformer 蛋白语言扩散模型直接生成全原子 IDP/IDR 构象系综，保持折叠域，无需额外训练。
result: 生成的系综与 NMR 和 SAXS 实验数据吻合，无需后处理，可选实验约束偏置。
conclusion: IDPForge 为含内在无序蛋白的整合结构研究提供新工具，开源可用。
---

## 摘要
尽管机器学习已经以惊人的准确性预测了折叠蛋白质基态的结构，但固有无序蛋白质和区域（IDPs/IDRs）由多样且动态的结构系综定义，而AlphaFold和RoseTTAFold等算法对其预测的置信度较低。我们提出了一种新的机器学习方法IDPForge（固有无序蛋白质、折叠与无序区域生成器），它利用Transformer蛋白质语言扩散模型来创建全原子IDP系综和保持折叠结构域的IDR无序系综。IDPForge不需要序列特异性训练、从粗粒化表示的反向转换，也不需要系综重新加权，因为通常创建的IDP/IDR构象系综与NMR和SAXS溶液实验数据吻合良好，并且如果需要，还提供了使用实验约束进行偏置的选项。我们设想具有这些多样化能力的IDPForge将促进含有内在无序蛋白质的综合和结构研究，并作为开源资源供普遍使用。

## Abstract
Although machine learning has transformed protein structure prediction of folded protein ground states with remarkable accuracy, intrinsically disordered proteins and regions (IDPs/IDRs) are defined by diverse and dynamical structural ensembles that are predicted with low confidence by algorithms such as AlphaFold and RoseTTAFold. We present a new machine learning method, IDPForge ({I}ntrinsically {D}isordered {P}rotein, {FO}lded and disordered {R}egion {GE}nerator), that exploits a transformer protein language diffusion model to create all-atom IDP ensembles and IDR disordered ensembles that maintains the folded domains. IDPForge does not require sequence-specific training, back transformations from coarse-grained representations, nor ensemble reweighting, as in general the created IDP/IDR conformational ensembles show good agreement with bot NMR and SAXS solution experimental data, and options for biasing with experimental restraints are provided if desired. We envision that IDPForge with these diverse capabilities will facilitate integrative and structural studies for proteins that contain intrinsic disorder, and is available as an open source resource for general use.