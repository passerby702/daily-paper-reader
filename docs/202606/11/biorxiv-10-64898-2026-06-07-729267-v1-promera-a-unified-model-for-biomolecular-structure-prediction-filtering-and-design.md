---
title: "Promera: a unified model for biomolecular structure prediction, filtering, and design"
title_zh: Promera：一个用于生物分子结构预测、筛选和设计的统一模型
authors: "Jing, B., Bafna, M., Diaz, D. J., Klivans, A. R., Berger, B."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.07.729267v1.full.pdf"
tags: ["query:pocket-lig"]
score: 7.0
evidence: 生物分子结构预测、过滤与设计的统一生成模型
tldr: 生物分子结构预测与设计面临过滤准确率不足和可控设计能力有限的问题。Promera统一模型结合全原子结构预测与改进的过滤及可控设计，其置信度指标在区分迷你蛋白和纳米抗体结合物上更准确，协同折叠性能超越开源模型。作为设计模型，它通过掩码序列预测生成结合物，可施加表位、互补位和模板约束。纳米抗体设计在计算机上达到与反向传播方法相当的成功率，并展示了靶向病毒糖蛋白和稳定GPCR的应用。最后提出协同折叠模型的缩放定律。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有生成模型在结构预测中过滤设计产物的能力不足，且设计方法缺乏可控性，需要统一模型同时提升预测、过滤和可控设计性能。
method: 提出Promera，一个基于全原子表示的统一生成模型，联合训练结构预测与序列设计，支持掩码序列预测和可选的表位、互补位及模板约束。
result: Promera的置信度指标在区分结合物与非结合物上更优，协同折叠性能在治疗相关类别上超过OpenFold3-p2和Boltz-2；纳米抗体设计在计算机上达到与反向传播方法相当的成功率。
conclusion: Promera统一了预测、过滤与可控设计，展示了在病毒糖蛋白靶向和GPCR稳定化中的应用潜力，并提出了协同折叠模型的缩放定律指导未来改进。
---

## 摘要
生成模型已成为建模和设计生物分子结构的主要工具。然而，尽管这些工具在结构预测准确性上有所提升，它们在筛选设计结合物（一个至关重要的用例）方面的能力仍然不足；而设计方法则更多关注无约束的结合物生成，而非可控设计所赋予的能力。我们介绍了Promera，一个统一的生成模型，它将全原子结构预测与改进的筛选和可控设计相结合。我们发现，Promera的置信度指标在从小蛋白和纳米抗体中筛选结合物与非结合物时更为准确，同时其共折叠性能在治疗相关类别上超越了流行的开源模型（OpenFold3-p2，Boltz-2）。作为设计模型，Promera通过预测被掩盖的蛋白质序列（可选表位、互补位和模板约束）来生成结合物。值得注意的是，我们的纳米抗体设计在共折叠置信度筛选评估下，与基于反向传播技术（mBER）的计算成功率相匹配。我们进一步通过两个计算演示展示了设计方法的多样能力：针对安第斯汉坦病毒糖蛋白的VHH表位靶向，以及β-2肾上腺素能GPCR的活性态稳定化。最后，我们提出了一个共折叠模型的缩放定律，指明了进一步提升性能的路径。

## Abstract
Generative models have become staple tools for modeling and designing biomolecular structures. However, although these tools have improved in structural prediction accuracy, their ability to filter designed binders---an essential use case---remains insufficient; whereas design methods have focused more on unconstrained binder generation rather than capabilities enabled by controllable design. We introduce Promera, a unified generative model that combines all-atom structure prediction with improved filtering and controllable design. We find that Promera's confidence metrics are more accurate for filtering binders from non-binders for both miniproteins and nanobodies, while its co-folding performance surpasses popular open-source models (OpenFold3-p2, Boltz-2) on therapeutically relevant categories. As a design model, Promera generates binders by predicting masked protein sequences with optional epitope, paratope, and template constraints. Remarkably, our nanobody designs match the in silico success rates from backprop-based techniques (mBER) when evaluated under co-folding confidence filters. We further provide two in silico demonstrations of the the versatile capabilities of our design method: epitope targeting of the Andes hantavirus glycoprotein with VHHs and active state stabilization of the beta-2 andrenergic GPCR. We conclude by proposing a scaling law for co-folding models, suggesting a path for further performance improvement.