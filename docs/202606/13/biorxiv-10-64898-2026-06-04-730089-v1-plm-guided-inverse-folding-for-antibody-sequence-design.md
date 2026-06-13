---
title: pLM-Guided Inverse Folding for Antibody Sequence Design
title_zh: pLM引导的抗体序列设计逆向折叠
authors: "Noske, V., Koulischer, F., Marchal, K., Demeester, T."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.04.730089v1.full.pdf"
tags: ["query:pocket-lig"]
score: 7.0
evidence: 基于结构的抗体序列逆折叠，与条件于蛋白质口袋结构的分子生成相关
tldr: 逆折叠从三维结构预测氨基酸序列是蛋白质设计的基础任务，但抗体结构数据稀缺导致模型训练受限且易过拟合。本文提出一种无需训练的加权集成方法，结合通用逆折叠模型ProteinMPNN与抗体语言模型IgLM的预测，充分利用序列数据。在抗体和纳米抗体结构上评估，该方法显著提升氨基酸恢复率，接近抗体专用模型AntiFold，同时生成序列多样性更高。即使已用抗体结构微调的AbMPNN也受益，表明语言模型指导能补充结构微调，产生更自然且满足结构约束的序列。
source: biorxiv
selection_source: fresh_fetch
motivation: 为缓解抗体逆折叠训练数据稀缺问题，需要在不增加结构数据的情况下利用大量序列信息，提升模型性能。
method: 提出训练自由加权集成方法，结合通用逆折叠模型ProteinMPNN与抗体语言模型IgLM的预测，无需额外训练。
result: 在抗体和纳米抗体上，氨基酸恢复率大幅提升，接近AntiFold，生成序列多样性更高，且微调模型AbMPNN也受益。
conclusion: 语言模型指导能够有效补充结构微调，产生更自然且满足结构约束的抗体序列。
---

## 摘要
逆向折叠，即从三维结构预测氨基酸序列，是计算蛋白质设计的基础任务，然而受限于结构数据的稀缺性，模型训练受限且存在过拟合风险。标准方法是在抗体等特定领域结构数据集上微调通用逆向折叠模型，但此类数据依然昂贵。为使逆向折叠模型能更充分地利用丰富的序列数据，我们提出将通用蛋白质逆向折叠模型ProteinMPNN与抗体特异性语言模型IgLM相结合，在推理时通过无需训练的加权集成方法整合其预测结果。在抗体和纳米抗体结构上的评估表明，该方法显著提高了氨基酸恢复率，优于单独使用ProteinMPNN，接近AntiFold等抗体特异性模型的性能，同时生成了更多样化的序列。即使是已在抗体结构上微调的模型（AbMPNN），也能从语言模型引导中获益，表明该方法补充了结构微调，并生成了更自然且仍满足结构约束的序列。

## Abstract
Inverse folding, predicting amino acid sequences from three-dimensional structures, is a foundational task in computational protein design, yet it is hindered by the scarcity of structural data, which limits model training and risks overfitting. The standard approach fine-tunes general inverse folding models on domain-specific structural datasets like antibodies, but such data remain expensive. To enable inverse folders to benefit more from abundant sequence data, we propose combining ProteinMPNN, a general protein inverse folding model, with IgLM, an antibody-specific language model, via a training-free weighted ensemble of their predictions at inference time. Evaluated on antibody and nanobody structures, our results show that this approach substantially improves amino acid recovery over ProteinMPNN alone, approaching the performance of antibody-specific models like AntiFold while generating more diverse sequences. Even models already fine-tuned on antibody structures (AbMPNN) benefit from language model guidance, demonstrating that it complements structural fine-tuning and leads to more natural-looking sequences that still satisfy structural constraints.