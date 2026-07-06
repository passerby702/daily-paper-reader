---
title: Pathogen context reshapes antimicrobial peptide generation
title_zh: 病原体背景重塑抗菌肽生成
authors: "You, S., Zhang, C., Han, Y., Jiang, Q., Guo, X., Li, M., Su, Y., Dong, X., Yang, M., Lu, H."
date: 2026-07-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.01.735178v1.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 利用深度学习的条件抗菌肽生成
tldr: 抗菌肽发现受限于如何从海量候选分子中选择针对特定病原体的少数分子，而传统生成器仅输出广谱序列。AMPHORA方法引入病原体上下文条件，将靶标类别、基因组特征及菌株描述文本作为生成模型的额外输入，使生成的肽序列具有病原体指向性。对比实验显示，对齐的病原体输入显著改变文库分布，菌株描述驱动序列突变而基因组特征影响结构预测，且物种水平分析揭示靶标依赖性富集。该工作证明病原体上下文条件化是重塑抗菌肽生成文库的有效新范式，有望提升精准抗菌药物开发效率。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统抗菌肽生成缺乏对特定病原体的靶向性，需要引入病原体上下文实现精准设计。
method: AMPHORA通过条件生成对抗网络，将病原体类别、基因组信息与菌株描述作为输入，引导序列生成。
result: 病原体上下文显著重塑生成文库，菌株描述主导序列变异，基因组特征影响结构性质，且保持高多样性。
conclusion: 病原体上下文条件化为抗菌肽生成提供新范式，有望提升靶向筛选效率。
---

## 摘要
抗菌肽发现的限制更多地来自于选择哪少数分子应针对特定病原体进行测试，而非可生成的分子数量。大多数肽生成器产生广谱抗菌样序列，并将靶标特异性留给下游过滤器。这里我们表明，病原体背景可以在生成过程中引入。AMPHORA 根据靶标类别、病原体基因组特征和菌株描述文本对肽原生生成器进行条件化。匹配、消融和打乱对照显示，对齐的病原体输入将生成的文库重塑，超越了粗略的活性标签，而全局打乱则削弱了这种效果。同噪声反事实表明，菌株描述驱动了更大的序列变化，而基因组特征更强地影响预测的结构特性。物种水平分析揭示了靶标依赖性富集。匹配的细菌输入也相对于仅类别生成改变了 APEX 预测的活性排名。生成的文库保持多样性，基本不记忆，并与预测的肽样结构特征兼容。总之，这些结果确立了病原体背景条件化作为计算文库重塑在抗菌肽生成中的新范式。

## Abstract
Antimicrobial peptide discovery is constrained less by the number of molecules that can be generated than by the choice of which few should be tested against a defined pathogen. Most peptide generators produce broadly antimicrobial-like sequences and leave target specificity to downstream filters. Here we show that pathogen context can be introduced during generation. AMPHORA conditions a peptide-native generator on target class, pathogen genome features and strain-description text. Matched, ablated and shuffled controls showed that aligned pathogen inputs redirected generated libraries beyond coarse activity labels, whereas global shuffling weakened this effect. Same-noise counterfactuals showed that strain descriptions drove larger sequence changes, whereas genome features more strongly affected predicted structural properties. Species-level analyses revealed target-dependent enrichment. Matched bacterial inputs also shifted APEX-predicted activity rankings relative to class-only generation. The resulting libraries remained diverse, largely non-memorizing and compatible with predicted peptide-like structural features. Together, these results establish pathogen-context conditioning as a new paradigm for computational library reshaping in antimicrobial peptide generation.