---
title: "A Drug-Target Specificity Foundation Model for Off-target Prediction, Repurposing, and Generative Design"
title_zh: 一种用于脱靶预测、药物重定位和生成式设计的药物-靶标特异性基础模型
authors: "Reddy, S. T."
date: 2026-06-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.08.730844v1.full.pdf"
tags: ["query:pocket-lig"]
score: 7.0
evidence: 具有生成设计能力的药物-靶标特异性基础模型
tldr: "现有方法依赖实验筛选或结构预测来判定药物-靶点结合特异性，计算成本高。本文提出dtSFM基础模型，利用Transformer注意力机制与玻尔兹曼分布的数学同构性，直接从序列计算热力学结合亲和力。在71万对实测相互作用上训练，编码器实现95%靶点检索和89%药物检索召回率，脱靶筛选将已知脱靶排在前0.6%；解码器针对16个靶点生成分子，71%的候选结构置信度与获批药物相当。该模型将计算热力学无缝融入脱靶预测、重定位和分子生成，为药物发现提供序列原生方案。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法依赖实验或结构预测，效率低且泛化差。需从序列直接推断药物-靶点结合特异性。
method: "基于Transformer注意力与玻尔兹曼分布的数学同构性，构建编码器-解码器架构，在714,747个药物-蛋白相互作用上训练，用AlphaFold 3结构验证。"
result: "编码器靶点检索recall@10达95%，脱靶中位数排名前0.6%；解码器为16靶点生成分子，71%候选AlphaFold 3结构置信度达标，最佳iPTM 0.95-0.99。"
conclusion: dtSFM实现了从序列到热力学特异性的直接计算，覆盖脱靶预测、重定位和生成设计，实验验证是下一步关键。
---

## 摘要
分子识别——即小分子与哪种蛋白质结合以及具有怎样的选择性——决定了每种治疗药物的有效性、安全性和发现过程，然而结合特异性仍然通过实验筛选或先预测三维结构的计算方法来确定。Transformer的softmax注意力机制在数学上同构于热平衡下支配分子结合的玻尔兹曼分布，这一恒等式规定了一种单一的序列原生架构：特异性基础模型（Specificity Foundation Model，SFM），它直接从序列计算分子结合兼容性作为热力学量。该框架最近在六个分子识别领域作为原型编码器实现。本文报道了小分子药物-靶标蛋白质SFM（dtSFM）作为首个将全尺寸编码器与生成式解码器配对的实例，该模型在由714,747个实测药物-蛋白质相互作用（涵盖522,776种化合物和22,964种蛋白质）组成的公开数据上训练。在整个过程中，我们使用AlphaFold 3作为正交结构验证器来验证结合预测，该验证器与dtSFM没有共享任何架构、训练数据或表示基础。仅凭这一个dtSFM模型，我们展示了药物发现的三种序列原生应用：脱靶预测、药物重定位和生成式设计。dtSFM编码器在分布内分别以95%和89%的top-10召回率检索药物的靶标和靶标的药物。在药物到靶标方向上，它在蛋白质组规模上筛选脱靶靶点，将临床激酶抑制剂的已记录脱靶靶点排名中位数为4,910个基因中的第30位——即筛选结果的前0.6%（通过化学蛋白质组学面板验证）。在靶标到药物方向上，它针对三个免疫学靶标对全部522,776个化合物的文库进行排序，识别出46个通过AlphaFold 3结构门控的新候选化合物。dtSFM交叉注意力解码器为16个靶标生成了新颖分子，1,200个设计候选物中的850个（71%）与获批药物的AlphaFold 3结构置信度相匹配（iPTM >= 0.9且界面PAE <= 1.67埃），最佳候选物达到iPTM 0.95-0.99和界面PAE 0.79-1.37埃。dtSFM将计算热力学引入到分子识别影响药物发现的每个阶段；实验湿实验验证是下一步的紧迫任务。

## Abstract
Molecular recognition - which small molecule binds which protein, and with what selectivity - governs the efficacy, safety, and discovery of every therapeutic, yet binding specificity is still determined by experimental screening or by computational methods that first predict three-dimensional structure. Transformer softmax attention is mathematically isomorphic to the Boltzmann distribution governing molecular binding at thermal equilibrium, an identity that prescribes a single sequence-native architecture: the Specificity Foundation Model (SFM), which computes molecular binding compatibility as a thermodynamic quantity directly from sequence. The framework was recently realized as prototype encoders across six molecular-recognition domains. Here we report the small molecule drug-target protein SFM (dtSFM) as the first instance to pair a full-scale encoder with a generative decoder, trained on publicly available data consisting of 714,747 measured drug-protein interactions spanning 522,776 compounds and 22,964 proteins. Throughout, we verify binding predictions with AlphaFold 3 as an orthogonal structural verifier that shares no architecture, training data, or representational basis with dtSFM. From this single dtSFM model we demonstrate the three sequence-native applications of drug discovery: off-target prediction, repurposing, and generative design. The dtSFM encoder retrieves a drug's target, and a target's drug, at 95% and 89% recall-at-10 in distribution, respectively. In the drug-to-target direction it screens off-targets at proteome scale, ranking the documented off-targets of clinical kinase inhibitors at a median of 30th out of 4,910 genes - the top 0.6% of the screen - when validated against a chemoproteomic panel. In the target-to-drug direction it ranks the full 522,776-compound library against three immunology targets, identifying 46 novel candidates that pass AlphaFold-3 structural gating. The dtSFM cross-attentive decoder generates novel molecules for 16 targets, 850 of 1,200 (71%) designed candidates match the AlphaFold 3 structural confidence of the approved drug (iPTM >= 0.9 and interface PAE <= 1.67 angstroms), with the best candidates reaching iPTM 0.95-0.99 and interface PAE 0.79-1.37 angstroms. dtSFM brings computational thermodynamics to every stage where molecular recognition shapes drug discovery; experimental wet-lab validation is the immediate next step.