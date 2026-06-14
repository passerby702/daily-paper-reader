---
title: "Promera: a unified model for biomolecular structure prediction, filtering, and design"
title_zh: Promera：用于生物分子结构预测、筛选和设计的统一模型
authors: "Jing, B., Bafna, M., Diaz, D. J., Klivans, A. R., Berger, B."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.07.729267v1.full.pdf"
tags: ["query:pocket-lig"]
score: 8.0
evidence: 统一的生物分子结构预测与设计生成模型
tldr: 现有生成式模型在生物分子结构预测中过滤能力不足，且设计方法缺乏可控性。Promera统一模型结合全原子结构预测与改进的过滤，其置信度指标在区分迷你蛋白和纳米体的结合子与非结合子上更准确，协同折叠性能超越OpenFold3-p2和Boltz-2。设计时通过预测掩码序列并可选约束表位、互补位和模板，纳米体设计的计算机成功率媲美基于反向传播的mBER方法。该模型还展示了表位靶向和GPCR活性态稳定的应用，并提出协同折叠模型的缩放定律以指导改进。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有生成式模型在结构预测中过滤能力不足，且设计方法缺乏可控性，难以有效筛选设计好的结合子。
method: 提出统一生成模型Promera，结合全原子结构预测与改进的过滤，通过预测掩码序列并引入表位、互补位及模板约束实现可控设计。
result: Promera的置信度指标在过滤中更准确，协同折叠性能优于OpenFold3-p2和Boltz-2，纳米体设计成功率媲美基于反向传播的mBER方法。
conclusion: 展示了Promera在表位靶向和GPCR活性态稳定中的应用，并提出协同折叠模型的缩放定律，指引未来性能提升。
---

## 摘要
生成模型已成为建模和设计生物分子结构的主要工具。然而，尽管这些工具在结构预测精度上有所改进，但它们在筛选设计的结合物（一个重要的应用场景）方面的能力仍然不足；而设计方法更侧重于无约束结合物生成，而非可控设计所赋予的能力。我们引入了Promera，一个统一的生成模型，它将全原子结构预测与改进的筛选和可控设计相结合。我们发现，Promera的置信度指标在从非结合物中筛选结合物方面（无论是微型蛋白还是纳米抗体）更为准确，同时其协同折叠性能在治疗相关的类别上超越了流行的开源模型（OpenFold3-p2, Boltz-2）。作为一种设计模型，Promera通过预测掩蔽的蛋白质序列来生成结合物，并可选地施加表位、互补位和模板约束。值得注意的是，在协同折叠置信度过滤器的评估下，我们的纳米抗体设计与基于反向传播技术（mBER）的计算模拟成功率相匹配。我们进一步通过两个计算模拟示例展示了我们设计方法的多功能性：使用VHH靶向安第斯汉坦病毒糖蛋白的表位，以及β-2肾上腺素能GPCR的活性态稳定。最后，我们提出了协同折叠模型的标度律，指出了进一步提升性能的路径。

## Abstract
Generative models have become staple tools for modeling and designing biomolecular structures. However, although these tools have improved in structural prediction accuracy, their ability to filter designed binders---an essential use case---remains insufficient; whereas design methods have focused more on unconstrained binder generation rather than capabilities enabled by controllable design. We introduce Promera, a unified generative model that combines all-atom structure prediction with improved filtering and controllable design. We find that Promera's confidence metrics are more accurate for filtering binders from non-binders for both miniproteins and nanobodies, while its co-folding performance surpasses popular open-source models (OpenFold3-p2, Boltz-2) on therapeutically relevant categories. As a design model, Promera generates binders by predicting masked protein sequences with optional epitope, paratope, and template constraints. Remarkably, our nanobody designs match the in silico success rates from backprop-based techniques (mBER) when evaluated under co-folding confidence filters. We further provide two in silico demonstrations of the the versatile capabilities of our design method: epitope targeting of the Andes hantavirus glycoprotein with VHHs and active state stabilization of the beta-2 andrenergic GPCR. We conclude by proposing a scaling law for co-folding models, suggesting a path for further performance improvement.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义

- **研究动机**：当前生成式模型在生物分子结构预测方面虽有进展，但在实际应用中存在两大短板——① 筛选（filtering）设计出的结合物（binders）时能力不足；② 设计方法侧重于无约束的结合物生成，缺乏可控性（如指定表位、互补位、模板等约束）。
- **整体意义**：作者提出一个统一的生成模型 **Promera**，将全原子结构预测、高效筛选与可控设计整合到单一框架中，旨在提升治疗性生物分子（如微型蛋白、纳米抗体）的设计效率和预测可靠性。

## 2. 方法论

- **核心思想**：统一模型同时实现结构预测、结合物筛选与可控设计,通过预测掩码（masked）蛋白质序列来生成结合物，并可选地引入表位（epitope）、互补位（paratope）和模板（template）约束。
- **关键技术细节**：
  - 结构预测：采用全原子（all-atom）协同折叠（co-folding）方式，预测复合物结构并输出置信度指标。
  - 筛选改进：Promera的置信度指标比现有模型更准确地从非结合物中筛选出结合物（针对微型蛋白和纳米抗体）。
  - 设计模块：通过掩码预测缺失的蛋白质序列，在生成过程中可施加表位（靶标上的对接区域）、互补位（抗体上的结合区域）和模板（现有结构）约束，实现可控设计。
  - 缩放定律（scaling law）：提出协同折叠模型的性能随数据/模型规模变化的规律，为未来改进提供指导。
- **公式/算法流程**（文本未提供具体数学公式，此处文字描述）：
  - 输入靶标结构（可选）和部分序列信息。
  - 模型对复合体进行全原子协同折叠，输出结构坐标和每个残基的置信度分数。
  - 对于设计任务，掩码待设计的序列（如纳米抗体），模型根据靶标表位、互补位约束和模板结构预测完整序列及复合物结构。
  - 通过置信度过滤（co-folding confidence filter）评估设计成功与否。

## 3. 实验设计

- **数据集与场景**：
  - 筛选实验：区分结合子与非结合子（binders vs non-binders）——使用微型蛋白（miniproteins）和纳米抗体（nanobodies）作为测试对象。
  - 协同折叠性能基准：治疗相关的蛋白质类别（具体类别未列出，可能包括GPCR、病毒糖蛋白等）。
  - 设计实验：纳米抗体设计（未明确数据源）、两个计算模拟示例——① VHH靶向安第斯汉坦病毒糖蛋白表位；② β-2肾上腺素能GPCR活性态稳定。
- **基准（benchmark）方法**：
  - 协同折叠对比方法：OpenFold3-p2、Boltz-2（开源模型）。
  - 纳米抗体设计对比方法：mBER（基于反向传播的计算机模拟技术）。
- **对比指标**：置信度指标在结合子筛选中的准确率；协同折叠性能在治疗相关类别上的超越程度；设计成功率（通过协同折叠置信度过滤器评估）。

## 4. 资源与算力

- **文中说明**：摘要和元数据中**未明确提及**使用的GPU型号、数量、训练时长等信息。
- **补充说明**：可能是由于摘要篇幅所限，完整论文中可能会在Methods部分披露，但当前提供的内容中无相关数据。

## 5. 实验数量与充分性

- **实验数量**：
  - 三个主要方面：筛选（2种分子类型）、协同折叠（对比2种开源模型）、设计（对比mBER + 2个实际应用案例）。整体实验组数中等。
  - 消融实验：未明确提及，但文中提到“可选地施加表位、互补位和模板约束”，可能隐含了约束条件的消融比较，但摘要未展开。
- **充分性评估**：
  - 筛选实验：用了两种代表性结合物类别（微型蛋白和纳米抗体），覆盖度较好。
  - 协同折叠：在“治疗相关类别”上超越，但未说明具体类别数量，可能不够全面。
  - 设计：仅对比了mBER一种方法（且是计算机模拟成功率），缺乏与其他生成模型（如ProteinMPNN、RFdiffusion等）的对比。
  - 实际应用示例只有两个，且为计算模拟验证，缺乏湿实验验证。
  - 总体而言，实验设计在关键任务上给出了定量结果，但**覆盖范围有限，缺少消融和更广泛基准**，充分性中等。

## 6. 主要结论与发现

- Promera的置信度指标在区分结合子与非结合子上比现有模型**更准确**。
- Promera在协同折叠性能上**优于**OpenFold3-p2和Boltz-2（在治疗相关类别上）。
- 纳米抗体设计的**计算机模拟成功率**与基于反向传播的mBER方法**相匹配**。
- 展示了表位靶向（VHH+安德斯汉坦病毒）和GPCR活性态稳定两个应用场景的可行性。
- 提出协同折叠模型的**缩放定律**，指出通过扩大数据/模型可进一步提升性能。

## 7. 优点

- **统一框架**：同一个模型同时支持结构预测、筛选和设计，减少了多模型转换的复杂度。
- **可控性增强**：通过表位、互补位、模板约束实现有目标的生成，比纯无约束生成更实用。
- **筛选改进**：置信度指标专门针对结合物筛选优化，解决了现有预测模型在此任务上的不足。
- **开源对比**：与当前最受欢迎的开源模型（OpenFold3-p2、Boltz-2）进行直接比较，具有较大参考价值。
- **实际场景验证**：选择了治疗相关的纳米抗体靶向和GPCR稳定两个有代表性的计算示例。

## 8. 不足与局限

- **缺乏湿实验验证**：所有结果均基于计算机模拟（in silico），未通过实验（如酵母展示、SPR等）验证设计出的结合物。
- **基准方法有限**：设计任务仅对比了mBER，未与ProteinMPNN、AlphaFold设计、RFdiffusion等其他流行生成模型比较。
- **消融实验缺失**：未明确分析各约束（表位、互补位、模板）的独立贡献。
- **性能基准细节不透明**：“治疗相关类别”具体包括哪些？是否涵盖所有重要类别？可能引入选择偏差。
- **算力资源未披露**：无法评估方法的可复现性和大规模应用的资源需求。
- **评分仅8.0**（来自元数据）：表明作者自身认为尚有一定不足，可能实验规模或近期可验证性有限。
- **数据集来源不明**：训练数据、测试数据的具体划分未说明。

（完）
