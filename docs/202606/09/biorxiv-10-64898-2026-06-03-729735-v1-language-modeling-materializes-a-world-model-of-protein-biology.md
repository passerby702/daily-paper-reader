---
title: Language Modeling Materializes a World Model of Protein Biology
title_zh: 语言建模实现了蛋白质生物学的世界模型
authors: "Candido, S., Hayes, T., Derry, A., Rao, R., Lin, Z., Verkuil, R., Wu, B. Z., Lee, J. S., Bruguera, E. S., Keval, J. A., Kopylov, M., Pak, J. E., Wu, W., Thomas, N., Mataraso, S., Hsu, A., Trotman-Grant, A. C., Fatras, K., dos Santos Costa, A., Badkundri, R., Akin, H., Oktay, D., Deaton, J., Montabana, E., Sitwala, H., Yu, Y., Wiggert, M., Carlin, D. A., Goering, A. W., Blazejewski, T., Sandora, M., Hla, M., Jia, T. Z., Kloker, L. H., Sofroniew, N. J., Uehara, M., Pannu, J., Bachas, S., Liu, D. S., Sercu, T., Rives, A."
date: 2026-06-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.03.729735v1.full.pdf"
tags: ["query:pocket-lig"]
score: 6.0
evidence: 使用语言模型学习蛋白质表示，在纳米摩尔结合亲和力发现中取得高实验成功率，与口袋配体生成相关
tldr: 蛋白质生物学极为复杂，实验方法难以全面表征。本文提出用语言建模学习蛋白质的统一通用表示，并基于此开发了结构预测模型，在抗体-靶标等生物分子复合物预测上超越现有方法。简单搜索即可获得纳摩尔级结合亲和力的蛋白质，实验成功率很高。语言模型表示空间呈现系统层次，生成了包含68亿序列和11亿结构的蛋白质生物学图谱，揭示了已知与未知的联系。语言建模成为表示蛋白质生物学、跨越原子级到进化级尺度的强大基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 蛋白质生物学远超实验表征能力，急需能虚拟实验的准确数字表示。
method: 采用语言建模学习蛋白质通用表示，并基于此构建结构预测模型。
result: 复合物预测超越现有方法，搜索获纳摩尔级结合蛋白；生成68亿序列和11亿结构图谱。
conclusion: 语言建模可有效表示蛋白质生物学，跨越原子级到进化级尺度。
---

## 摘要
蛋白质是生命的基础。其生物学的全部范围超出了我们在物理实验室中通过实验方法进行表征的能力。准确的数字表示可以通过虚拟实验加速蛋白质生物学的发现。我们提出语言建模来学习统一且通用的表示，这些表示可以扩展到所有的蛋白质生物学。基于这些表示，我们开发了一个结构预测模型，在生物分子复合物预测的基准测试中超越了现有方法的性能，包括抗体与其靶标的相互作用。一个简单的搜索程序在发现对微型蛋白和单链抗体具有纳摩尔结合亲和力的蛋白质方面取得了很高的实验成功率，这对治疗设计至关重要。对语言模型表示空间中概念的研究揭示了一个系统性的组织，与通过经验科学发展的蛋白质还原论理解相一致。利用这一组织，我们生成了一个全面的蛋白质生物学图谱，包含超过68亿个序列和11亿个预测结构，识别了已知和未知生物学之间的联系。总的来说，这表明语言建模是表示蛋白质生物学的强大基础，跨越从原子水平预测和设计蛋白质相互作用，到识别不同粒度和抽象层次蛋白质的性质，再到跨越数十亿年进化联系蛋白质之间的图谱规模。

## Abstract
Proteins are fundamental to life. The full extent of their biology is beyond our ability to characterize with experimental approaches in the physical laboratory. Accurate digital representations could accelerate the discovery of protein biology through virtual experiments. We propose language modeling to learn unified and general representations that can be scaled to all of protein biology. Building on these representations, we develop a structure prediction model that exceeds the performance of established methods for biomolecular complex prediction across benchmarks, including for the interactions of antibodies with their targets. A simple search procedure yields high experimental success rates for the discovery of proteins with nanomolar binding affinities for both miniproteins and single-chain antibodies, a modality critical for therapeutic design. Study of the concepts in the language models representation space reveals a systematic organization aligned with the reductionist understanding of proteins developed through empirical science. Leveraging this organization, we generate a comprehensive map of protein biology encompassing over 6.8 billion sequences and 1.1 billion predicted structures, identifying connections across known and unknown biology. As a whole, this shows language modeling as a powerful substrate for representing the biology of proteins, operating across scales from the prediction and design of protein interactions at the atomic level, to identifying properties of proteins at different levels of granularity and abstraction, to the scale of mapping connections between proteins across billions of years of evolution.