---
title: A control-validated pan-proteome deep-learning pipeline nominates GPR35 as a candidate target of the orphan bacterial metabolite ligiamycin A
title_zh: 一种经对照验证的全蛋白质组深度学习流程将GPR35鉴定为孤儿细菌代谢物ligiamycin A的候选靶点
authors: "Martin, J."
date: 2026-07-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.01.735807v1.full.pdf"
tags: ["query:pocket-lig"]
score: 6.0
evidence: 深度学习管道用于天然产物靶标预测，支持结构感知的配体设计
tldr: 大多数微生物天然产物生物活性靶点未知，限制其开发。本文提出一个开源、控制验证的计算管道，结合全蛋白质组深度学习药物-靶标相互作用模型（图神经网络配体编码器、ESM-2蛋白语言模型编码器、双向交叉注意力）与偏差校正排名及控制锚定分子对接。应用于2022年报道的天然产物ligiamycin A，预测其相互作用集中于A类GPCR，经已知药物losartan校正偏差后，孤儿受体GPR35成为首要候选。结构对接验证GPR35特异性，对接分数与已知激动剂zaprinast相当。最终提出GPR35作为可实验验证的靶点，并发布可重用工作流。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决天然产物靶点未知问题，开发可重用且控制验证的计算方法。
method: 构建全蛋白质组DTI模型（GNN+ESM-2+交叉注意力），结合偏差校正排名与控制锚定分子对接。
result: ligiamycin A优先靶向孤儿受体GPR35，对接分数-8.1 kcal/mol（对照-8.3，非结合物-5.5），其他候选被排除。
conclusion: 提出GPR35为实验验证靶点，并发布开源工作流。
---

## 摘要
大多数具有记录生物活性的微生物天然产物缺乏已鉴定的分子靶点，这限制了它们的开发。我们提出了一种开放、经过对照验证的计算流程，用于天然产物靶点假说生成。该流程结合了全蛋白质组深度学习药物-靶点相互作用（DTI）模型（一个图神经网络配体编码器、一个ESM-2蛋白质语言模型编码器以及双向交叉注意力）、偏差校正排序和对照锚定分子对接。将其应用于ligiamycin A（一种2022年描述的链霉菌/无色杆菌共培养产生的十氢萘-氨基-马来酰亚胺，尚无报道的靶点），我们发现该化合物预测的相互作用主要由A类G蛋白偶联受体主导。使用一种已知靶点的药物（氯沙坦），我们识别并校正了原始模型中的频繁命中偏差；校正后，突出的候选物一致为A类GPCR，以孤儿受体GPR35为首。在三个候选物上使用匹配的阳性和阴性对照进行基于结构的对接，专门证实了GPR35：ligiamycin A在激动剂口袋处的得分与已知GPR35激动剂zaprinast相当（-8.1 vs -8.3 kcal/mol；非结合物下限-5.5），而FFAR1被排除，组胺H2结果不确定。我们提出GPR35作为优先考虑、可实验验证的靶点，并将该工作流程作为可重用工具发布。该结果是一个需要实验验证的计算假说。

## Abstract
Most microbial natural products with documented bioactivity lack an identified molecular target, which limits their development. We present an open, control-validated computational pipeline for natural-product target hypothesis generation. It combines a pan-proteome deep-learning drug-target interaction (DTI) model (a graph neural-network ligand encoder, an ESM-2 protein language-model encoder, and bidirectional cross-attention) with bias-corrected ranking and control-anchored molecular docking. Applying it to ligiamycin A, a 2022-described Streptomyces/Achromobacter co-culture decalin-amino-maleimide with no reported target, we find that the predicted interactions of the compound are dominated by class-A G-protein-coupled receptors. Using a drug with a known target (losartan) we identify and correct a frequent-hitter bias in the raw model; after correction the standout candidates are uniformly class-A GPCRs, led by the orphan receptor GPR35. Structure-based docking with matched positive and negative controls across three candidates corroborates GPR35 specifically: ligiamycin A scores comparably to the known GPR35 agonist zaprinast at the agonist pocket (-8.1 vs -8.3 kcal/mol; non-binder floor -5.5), whereas FFAR1 is excluded and histamine H2 is inconclusive. We propose GPR35 as a prioritized, experimentally testable target and release the workflow as a reusable tool. The result is a computational hypothesis that requires experimental validation.