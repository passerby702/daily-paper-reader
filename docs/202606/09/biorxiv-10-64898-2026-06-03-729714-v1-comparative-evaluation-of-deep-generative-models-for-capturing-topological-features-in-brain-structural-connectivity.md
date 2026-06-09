---
title: Comparative Evaluation of Deep Generative Models for Capturing Topological Features in Brain Structural Connectivity
title_zh: 深度生成模型捕获大脑结构连接拓扑特征的比较评估
authors: "Kumada, C., Hiroyasu, T., Hiwa, S."
date: 2026-06-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.03.729714v1.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 评估DDPM用于脑连接生成
tldr: 脑结构连接数据稀缺制约机器学习，深度生成模型用于数据增强但捕获拓扑特征能力未知。本研究比较VAE、WGAN-GP与DDPM在合成及真实数据上的生成质量，发现WGAN-GP表现最平衡稳定，而所有模型难以严格复现全局约束（如平面性）。建议将WGAN-GP作为基线，并需结合结构约束以提升生成忠实度。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究不同深度生成模型在脑结构连接生成中捕获复杂拓扑特征的能力差异。
method: 系统比较VAE、WGAN-GP和DDPM，基于图论指标和邻接矩阵可视化评估合成与真实数据生成质量。
result: WGAN-GP表现最稳定；VAE与DDPM在特定指标良好但敏感于数据特性；所有模型均难以复制平面性等全局约束。
conclusion: WGAN-GP可作为平衡基线，标准生成模型需结合结构约束以提升脑网络生成忠实度。
---

## 摘要
结构连接（SC）数据对于脑网络分析至关重要，但基于SC的机器学习常常受限于数据可用性不足，阻碍了模型的泛化能力和鲁棒性。尽管使用深度生成模型进行数据增强已引起越来越多的关注，但不同模型如何捕获SC数据的复杂拓扑特征仍不清楚。为了阐明深度生成模型在SC生成方面的学习特性，本研究比较了三种代表性模型：变分自编码器（VAE）、带梯度惩罚的Wasserstein GAN（WGAN-GP）和去噪扩散概率模型（DDPM）。我们使用已知特征的人工合成数据集和真实SC数据系统评估了这些模型。通过图论指标比较和生成邻接矩阵的视觉检查来评估生成质量。WGAN-GP在数据集和指标上表现出相对稳定的性能，在不同评估设置下没有严重退化。相比之下，VAE和DDPM在特定方面表现良好，但对数据特征更为敏感。这些发现表明，WGAN-GP可作为未来SC数据增强研究中最平衡的基线，而VAE和DDPM可能根据目标应用和感兴趣的结构特性发挥作用。此外，由于所有模型都难以完全再现平面性等严格的全局约束，我们的结果表明，标准生成模型可能不足以捕获SC数据的复杂拓扑特征。这凸显了将期望的结构属性纳入训练或生成过程的重要性。

## Abstract
Structural connectivity (SC) data are crucial for brain network analysis, but SC-based machine learning often suffers from limited data availability, hindering model generalization and robustness. Although data augmentation using deep generative models has attracted increasing attention, it remains unclear how different models capture the complex topological features of SC data. To clarify the learning characteristics of deep generative models for SC generation, this study compares three representative models: variational autoencoder (VAE), Wasserstein GAN with gradient penalty (WGAN-GP), and denoising diffusion probabilistic models (DDPM). We systematically evaluated these models using both synthetic datasets with known characteristics and real-world SC data. Generation quality was assessed using graph-theoretic metric comparisons and visual inspection of the generated adjacency matrices. WGAN-GP showed relatively stable performance across datasets and metrics, without severe performance degradation across evaluation settings. In contrast, VAE and DDPM performed well in specific aspects but were more sensitive to data characteristics. These findings suggest that WGAN-GP may serve as the most balanced baseline for future SC data augmentation studies, whereas VAE and DDPM may be useful depending on the target application and structural properties of interest. Furthermore, because all models struggled to fully reproduce strict global constraints such as planarity, our results suggest that standard generative models may be insufficient to capture the complex topological features of SC data. This highlights the importance of incorporating the desired structural properties into the training or generation process.