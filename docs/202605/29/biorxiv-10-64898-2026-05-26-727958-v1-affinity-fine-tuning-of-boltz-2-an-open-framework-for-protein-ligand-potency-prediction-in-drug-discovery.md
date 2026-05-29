---
title: "Affinity Fine-Tuning of Boltz-2: An Open Framework for Protein-Ligand Potency Prediction in Drug Discovery"
title_zh: Boltz-2的亲和力微调：药物发现中蛋白质-配体效力预测的开放框架
authors: "Amini, S., Sciabola, S., Wang, Y."
date: 2026-05-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.26.727958v1.full.pdf"
tags: ["query:pocket-lig"]
score: 6.0
evidence: 提出一个开源框架，对Boltz-2进行蛋白质-配体亲和力预测微调，辅助先导化合物优化
tldr: Boltz-2通过共折叠结构实现准确亲和力预测，但其缺乏公开训练方案，限制了在药物发现项目中的应用。我们提出一个开放框架，通过仅微调亲和力预测模块，利用项目特异性实验数据来提升模型。在两个内部研究中，包括多靶点回顾性基准测试和最大1700个配体的单靶点研究，微调Boltz-2在相关性上均超越现成模型，在某些情况下与自由能微扰（FEP）方法性能相当。通过发布此框架，我们希望使社区能够将Boltz-2适配到各自的靶点和数据，加速先导优化。
source: biorxiv
selection_source: fresh_fetch
motivation: Boltz-2虽准确但缺少公开训练方案，难以融入不断产生新实验数据的先导优化流程。
method: 我们开发了一个开放框架，仅微调Boltz-2的亲和力预测组件，使用项目特定实验数据。
result: 微调后模型在相关性上优于原生模型，在多靶点和单靶点1700配体研究中表现优异，甚至可与FEP媲美。
conclusion: 发布此开放框架，使研究人员能针对自身靶点和数据定制Boltz-2，提升先导优化效率。
---

## 摘要
Boltz-2通过利用共折叠的蛋白质-配体结构实现了准确的结合亲和力预测，但由于缺乏公开的训练方案，其在活性药物发现项目中的应用受到限制，这些项目在先导化合物优化过程中不断产生新的实验测量数据和同系配体系列。我们提出了一个Boltz-2亲和力微调的开放框架，表明仅使用项目特定的实验数据调整亲和力预测组件，就能使模型在先导化合物优化中更具实用性。我们通过两项内部研究评估了该方法：一项针对基于物理和机器学习基线的多靶标回顾性基准研究，以及一项包含多达1700个配体的大规模单一靶标研究。在两种情境下，微调后的Boltz-2相比开箱即用模型提高了相关性，并在某些情况下达到了与自由能微扰（FEP）方法相当的性能。通过发布该框架，我们旨在帮助社区将Boltz-2适配至其药物发现项目中的特定靶标和数据。代码可在以下链接获取：https://github.com/molecularinformatics/Boltz2_affinity

## Abstract
Boltz-2 has enabled accurate binding affinity prediction by leveraging co-folded protein-ligand structures, but the absence of a public training recipe has limited its use in active drug discovery projects, where new experimental measurements and congeneric ligand series continually arrive during lead optimization. We present an open framework for affinity fine-tuning of Boltz-2, showing that adapting only the affinity prediction components with project-specific experimental data can make the model substantially more useful for lead optimization. We evaluate the approach in two internal studies: a multi-target retrospective benchmark against physics-based and machine learning baselines, and a large single-target study with up to 1,700 ligands. In both settings, fine-tuned Boltz-2 improves correlation over the off-the-shelf model, and in some cases reaches performance competitive with free energy perturbation (FEP) methods. By releasing this framework, we aim to enable the community to adapt Boltz-2 to the specific targets and data of their own drug discovery campaigns. The code is available at: https://github.com/molecularinformatics/Boltz2_affinity