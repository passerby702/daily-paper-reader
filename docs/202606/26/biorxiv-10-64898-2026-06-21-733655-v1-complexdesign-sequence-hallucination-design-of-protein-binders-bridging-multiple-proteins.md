---
title: "ComplexDesign: sequence-hallucination design of protein binders bridging multiple proteins"
title_zh: ComplexDesign：桥接多个蛋白质的蛋白质结合子的序列幻影设计
authors: "Xu, J., Ren, M., Qi, N., Zhang, X., He, Z., Yu, C., Bu, D."
date: 2026-06-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.21.733655v1.full.pdf"
tags: ["query:pocket-lig"]
score: 7.0
evidence: 幻觉设计桥接多蛋白的结合子，靶标感知的序列优化
tldr: "多链蛋白复合物设计需同时满足链折叠与界面形成，现有方法在处理三聚体、四聚体及桥接两个靶蛋白的binder时能力有限。ComplexDesign采用基于hallucination的结构预测引导序列优化，通过特殊掩蔽机制探索靶蛋白相对排列，实现多链协同设计。在二聚体、三聚体和四聚体无条件设计中成功率超50%，并在10对靶蛋白中成功设计出8个高置信度三元复合物。该方法为多链蛋白设计，特别是桥接双靶点的binder设计，提供了有效工具。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法难以同时满足多链蛋白复合物的折叠与界面形成，尤其在三聚体、四聚体及桥接双靶蛋白的binder设计中灵活性不足。
method: ComplexDesign利用结构预测引导的序列优化进行hallucination，并引入掩蔽机制探索靶蛋白的相对排列，实现多链的协同折叠与界面形成。
result: "在无条件二聚体、三聚体和四聚体设计中成功率超50%，优于现有方法；在10对靶蛋白中成功为8对设计出高置信度三元复合物。"
conclusion: ComplexDesign是一种有效的多链蛋白设计方法，特别适用于设计桥接两个靶蛋白的binder。
---

## 摘要
动机：设计多链蛋白质复合体需要协调组分蛋白质的折叠与其界面的形成。然而，现有方法在同时满足这些要求方面的能力仍然有限，特别是对于三聚体和四聚体复合体。作为一个重要的实际场景，设计一个将两个靶标蛋白质桥接成三元复合体的结合子需要两个靶标相对排列的灵活性，这给现有设计方法带来了额外挑战。结果：我们提出了ComplexDesign，一种基于幻影的多链蛋白质设计方法。ComplexDesign进行结构预测引导的序列优化，以同时折叠每个蛋白质链并形成将它们结合在一起的链间相互作用。为了提供适当排列这些靶标蛋白质所需的灵活性，ComplexDesign引入了一种专门的掩蔽机制，使其能够探索可能的相对排列，而不是局限于预定义的排列。在具有不同链长度的全面基准测试中，ComplexDesign在二聚体、三聚体和四聚体的无条件设计上优于现有方法，实现了超过50%的高设计成功率，支持其多链复合体设计能力。此外，在多靶标结合子设计案例中，ComplexDesign为10个靶标对中的8个产生了高置信度、自洽的三元复合体。这些结果确立了ComplexDesign作为多链蛋白质设计有效工具的地位，对于设计桥接两个靶标蛋白质的结合子尤其有用。可用性和实现：ComplexDesign的源代码将在发表后公开。

## Abstract
Motivation: Designing multichain protein complexes requires coordinating the folding of component proteins with the formation of their interfaces. The existing methods, however, remain limited in their ability to satisfy these requirements simultaneously, especially for trimeric and tetrameric complexes. As an important practical scenario, designing a binder that bridges two target proteins into a ternary complex requires flexibility in the relative arrangement of the two targets, adding an additional challenge to existing design methods. Results: We present ComplexDesign, a hallucination-based approach for multichain protein design. ComplexDesign performs structure-prediction-guided sequence optimization to simultaneously fold each protein chain and form inter-chain interactions that bind them together. To provide the flexibility required to appropriately arrange these target proteins, ComplexDesign introduces a specialized masking mechanism that enables exploration of possible relative arrangements rather than being limited to the predefined ones. Across a comprehensive set of benchmarks with various chain lengths, ComplexDesign outperformed existing methods in the unconditional design of dimers, trimers, and tetramers, achieving a high design success rate exceeding 50%, supporting its capability for multichain complex design. Furthermore, in the case of multi-target binder design, ComplexDesign produced high-confidence, self-consistent ternary complexes for 8 out of 10 target pairs. These results establish ComplexDesign as an effective tool for multichain protein design, with particular utility for designing binders that bridge two target proteins. Availability and implementation: The source code of ComplexDesign will be made publicly available upon publication.