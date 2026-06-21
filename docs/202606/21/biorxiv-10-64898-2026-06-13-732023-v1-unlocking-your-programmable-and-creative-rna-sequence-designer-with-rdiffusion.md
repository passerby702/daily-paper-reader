---
title: Unlocking Your Programmable and Creative RNA Sequence Designer with RDiffusion
title_zh: 解锁您的可编程和创造性RNA序列设计师RDiffusion
authors: "Wang, J., Dong, J., Li, T., Yang, L., yin, J., Chen, J., Dong, Y., Li, J., Tan, C."
date: 2026-06-13
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.13.732023v1.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 基于扩散的RNA序列设计生成模型
tldr: RNA序列空间浩瀚，现有知识仅触及冰山一角。本文提出RDiffusion，一种基于扩散的生成模型，可依据功能、结构、结合蛋白等条件从头设计RNA序列。在多项设计任务中，RDiffusion在成功率和多样性上超越所有基线，并作为RNA基础模型在下游任务上取得最优性能。针对骨关节炎，利用RDiffusion从数据驱动筛选流程中设计新型miRNA候选序列，有望加速RNA工程在健康、药物和基因编辑中的应用。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有RNA序列设计方法局限于已知空间，难以探索多样性并满足特定功能需求，亟需统一生成模型。
method: RDiffusion是基于扩散的生成框架，以功能、二级/三级结构、结合蛋白等为条件，指导新RNA序列生成。
result: RDiffusion在多种RNA设计任务中成功率和序列多样性超越所有基线，并作为基础模型在下游任务上达到最优。
conclusion: RDiffusion提供统一的RNA设计方法，加速可编程RNA工程，对人类健康、药物开发和基因编辑工具产生深远影响。
---

## 摘要
作为中心法则的基石，RNA既见证又积极塑造了三十亿年的进化历程。在这漫长的时间尺度上，出现了令人惊叹的RNA分子多样性，其执行的功能远远超出了信息传递的传统角色。在后基因组时代，虽然我们已经收录了数千万个非编码RNA序列并功能注释了数百万个，但这些知识仅触及了庞大而神秘的RNA序列空间的表面。在此，我们介绍RDiffusion，一个旨在广泛探索这个RNA宇宙的综合性生成模型。RDiffusion是一个基于扩散的框架，以多种生物学特征为条件——例如期望的功能、家族类型、二级结构、三级结构或结合蛋白——可以指导生成符合特定规格的新型RNA序列。我们在广泛的RNA设计任务上评估了RDiffusion，发现它不仅在设计成功率和序列多样性上超越了所有基线方法，而且在下游任务上达到了最先进的性能，作为一个强大的RNA基础模型。为了将RDiffusion转化为疾病应用，我们以骨关节炎（OA）为首要范例，利用RDiffusion通过定制的数据驱动种子选择和筛选流水线进行新型miRNA序列的从头设计。虽然这些设计候选物目前正在进行严格的生物学实验验证，最终的评估数据将在正式发表时全面整合并呈现。通过提供统一的RNA设计方法，我们预期RDiffusion将加速RNA的可编程工程——对人类健康、药物开发和基因编辑工具产生深远影响，同时也为RNA相关下游任务的表示学习建立新标准。

## Abstract
As a cornerstone of the central dogma, RNA has both witnessed and actively shaped three billion years of evolution. Over this vast timescale, a remarkable diversity of RNA molecules has emerged, executing functions that extend far beyond traditional roles in information transfer. In the post-genomic era, while we have cataloged tens of millions of non-coding RNA sequences and functionally annotated millions, this knowledge merely scratches the surface of the vast and enigmatic RNA sequence space. Here, we introduce RDiffusion, a comprehensive generative model designed to extensively explore this RNA universe. RDiffusion is a diffusion-based framework that, conditioned on diverse biological features, such as desired function, family type, secondary structure, tertiary structure, or binding proteins--can guide the generation of novel RNA sequences tailored to specific specifications. We evaluate RDiffusion across a broad spectrum of RNA design tasks and find that it not only surpasses all baseline methods in design success rate and sequence diversity but also achieves state-of-the-art performance on downstream tasks, functioning as a powerful RNA foundation model. To translate RDiffusion into disease applications, we targeted osteoarthritis (OA) as a prime paradigm, utilizing the RDiffusion to perform de novo design of novel miRNA sequences guided by a customized, data-driven seed selection and screening pipeline. While these designed candidates are currently undergoing rigorous biological experimental validations, the finalized evaluation data will be comprehensively integrated and presented upon formal publication. By providing a unified approach to RNA design, we anticipate that RDiffusion will accelerate the programmable engineering of RNA--with profound implications for human health, drug development, and gene-editing tools, while also establishing a new standard for representation learning on RNA-related downstream tasks.