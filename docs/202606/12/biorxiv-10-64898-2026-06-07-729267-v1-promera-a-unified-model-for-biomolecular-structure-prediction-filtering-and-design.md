---
title: "Promera: a unified model for biomolecular structure prediction, filtering, and design"
title_zh: Promera：用于生物分子结构预测、筛选和设计的统一模型
authors: "Jing, B., Bafna, M., Diaz, D. J., Klivans, A. R., Berger, B."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.07.729267v1.full.pdf"
tags: ["query:pocket-lig"]
score: 7.0
evidence: 生物分子结构设计与过滤，与蛋白-配体相关但非小分子
tldr: 生成模型在生物分子结构预测与设计中应用广泛，但现有模型在过滤设计结合物方面能力不足，且设计方法缺乏可控性。Promera统一了全原子结构预测与可控设计，其置信度指标在过滤结合物时比现有模型更准确，共折叠性能优于OpenFold3-p2等开源模型。作为设计模型，Promera通过预测掩码序列并支持表位、互补位和模板约束生成结合物，纳米抗体设计成功率与反向传播方法相当，并成功展示了针对汉坦病毒糖蛋白的表位靶向和β2肾上腺素能受体的活性态稳定。最后，提出了共折叠模型的缩放定律，为性能提升指明方向。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有结构预测模型过滤能力不足，设计方法缺乏可控性，亟需统一模型提升过滤与可控设计能力。
method: Promera是一种统一全原子结构预测与可控设计的生成模型，通过预测掩码序列并支持表位、互补位和模板约束来实现可控设计。
result: Promera在过滤和共折叠性能上超越开源模型，纳米抗体设计成功率与反向传播方法相当，并成功应用于表位靶向与GPCR活性态稳定。
conclusion: 提出了共折叠模型的缩放定律，为未来性能改进提供了路径。
---

## 摘要
生成模型已成为建模和设计生物分子结构的主要工具。然而，尽管这些工具在结构预测准确性上有所提升，但它们在筛选设计结合物（一个关键应用）方面的能力仍然不足；而设计方法则更关注于无约束的结合物生成，而非可控设计所支持的功能。我们提出了Promera，一个统一生成模型，它结合了全原子结构预测与改进的筛选和可控设计。我们发现，Promera的置信度指标在从小蛋白和纳米抗体中筛选结合物方面更为准确，同时其共折叠性能在治疗相关类别上超越了流行的开源模型（OpenFold3-p2, Boltz-2）。作为一个设计模型，Promera通过预测掩码的蛋白质序列并可选地加入表位、互补位和模板约束来生成结合物。值得注意的是，在共折叠置信度筛选评估下，我们的纳米抗体设计达到了基于反向传播技术（mBER）的计算机模拟成功率。我们进一步提供了两个计算机模拟演示，展示我们设计方法的多功能能力：针对安第斯汉坦病毒糖蛋白的VHH表位靶向，以及β2肾上腺素能GPCR的活性态稳定。最后，我们提出了一个共折叠模型的缩放定律，为性能进一步提升指明了方向。

## Abstract
Generative models have become staple tools for modeling and designing biomolecular structures. However, although these tools have improved in structural prediction accuracy, their ability to filter designed binders---an essential use case---remains insufficient; whereas design methods have focused more on unconstrained binder generation rather than capabilities enabled by controllable design. We introduce Promera, a unified generative model that combines all-atom structure prediction with improved filtering and controllable design. We find that Promera's confidence metrics are more accurate for filtering binders from non-binders for both miniproteins and nanobodies, while its co-folding performance surpasses popular open-source models (OpenFold3-p2, Boltz-2) on therapeutically relevant categories. As a design model, Promera generates binders by predicting masked protein sequences with optional epitope, paratope, and template constraints. Remarkably, our nanobody designs match the in silico success rates from backprop-based techniques (mBER) when evaluated under co-folding confidence filters. We further provide two in silico demonstrations of the the versatile capabilities of our design method: epitope targeting of the Andes hantavirus glycoprotein with VHHs and active state stabilization of the beta-2 andrenergic GPCR. We conclude by proposing a scaling law for co-folding models, suggesting a path for further performance improvement.