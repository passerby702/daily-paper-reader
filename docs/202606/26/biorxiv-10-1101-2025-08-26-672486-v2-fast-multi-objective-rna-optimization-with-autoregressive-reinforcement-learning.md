---
title: Fast Multi-objective RNA Optimization with Autoregressive Reinforcement Learning
title_zh: 基于自回归强化学习的快速多目标RNA优化
authors: "Huang, J., Feng, N., Bai, H., Fang, Y., Liu, X., Wang, S., Yan, J., Shen, H.-B., Qiu, Z., Yuan, Y., Hu, R., Pan, X."
date: 2026-06-20
pdf: "https://www.biorxiv.org/content/10.1101/2025.08.26.672486v2.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 自回归强化学习用于RNA序列优化
tldr: mRNA疫苗开发中密码子优化至关重要，但现有工具效率低、多样性差且难以多目标优化。提出RNAJog框架，采用自回归生成与强化学习联合优化最小自由能、密码子适应指数和GC含量。在模拟和湿实验中，RNAJog对长序列优化速度比LinearDesign快两个数量级，用于流感HA mRNA疫苗使小鼠抗体滴度提升约10倍。该框架支持生物约束，如最小化m6A修饰基序以提升翻译效率和RNA稳定性。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有密码子优化工具计算效率低、序列多样性差，且缺乏通用多目标优化能力。
method: 提出RNAJog，结合自回归生成模型与强化学习，无需标注数据即可联合优化MFE、CAI和GC含量。
result: RNAJog对长序列优化速度比LinearDesign快两个数量级，用于流感疫苗mRNA设计使小鼠抗体滴度提升约10倍。
conclusion: RNAJog是一种高效、通用、支持生物约束的多目标RNA优化框架。
---

## 摘要
密码子优化在mRNA疫苗开发中至关重要，而现有工具在计算效率、序列多样性和通用性方面存在局限。为应对这些挑战，我们开发了RNAJog（基于自回归生成模型的RNA联合优化），该框架将自回归生成与强化学习相结合，以优化密码子序列的最小自由能、密码子适应指数和GC含量，甚至能够在无需标注训练数据的情况下进行序列设计。计算机模拟和湿实验评估均证实了RNAJog的有效性和高效性，在长RNA序列上的速度比传统算法（LinearDesign）快两个数量级，且在针对小鼠的流感病毒血凝素mRNA疫苗设计中，抗体滴度相比野生型mRNA提高了约10倍。RNAJog还支持序列优化的生物学约束。利用这一特性，我们在Bmp2编码序列中最小化了m6A修饰基序，以增强翻译效率和RNA稳定性，并在细胞实验中得到了验证。

## Abstract
Codon optimization is essential in mRNA vaccine development, while existing tools face limitations in the computational efficiency, sequence diversity and universality. To address these challenges, we develop RNAJog (RNA Joint Optimization with autoregressive Generative model), a framework integrating autoregressive generation with reinforcement learning to optimize codon sequences for minimum free energy (MFE), codon adaptation index (CAI) and GC content, even enabling sequence design without requiring annotated training data. Evaluations in both in silico and wet-lab experiments have confirmed RNAJogs effectiveness and efficiency, with two orders of magnitude faster than traditional algorithm (LinearDesign) for long RNA sequence and about a 10-fold increase in antibody titer compared to the wild-type mRNA for Influenza virus hemagglutinin (HA) mRNA vaccine design in mouse. RNAJog also supports biological constraints for sequence optimization. Using this feature, we minimized m6A modification motifs in Bmp2 coding sequence for enhancing the translational efficiency and RNA stability, which are validated in cell-based experiments.