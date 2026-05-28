---
title: "From APOE Genetics to AI-Designed Drug Candidates: An Integrated Pipeline for Oral, Brain-Penetrant ACAT1 Inhibitors in Alzheimer's Disease"
title_zh: 从APOE遗传学到AI设计的候选药物：一条用于阿尔茨海默病的口服、脑渗透性ACAT1抑制剂的集成管线
authors: "Agarwal, S., Popert, R., Agapow, P., Ruff, C., Gupta, S."
date: 2026-05-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.21.727002v1.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 使用深度生成模型的整合管线AI设计治阿尔茨海默病的候选药物。
tldr: 阿尔茨海默病缺乏口服疾病修饰疗法，APOEε4等位基因导致胆固醇代谢异常是关键病理机制。本文整合遗传学机制与AI驱动的分子生成方法，构建了一条从靶点识别到候选药物设计的管线，旨在开发口服脑渗透性ACAT1抑制剂。通过深度生成模型设计新颖分子，并评估其药理学性质，为阿尔茨海默病药物开发提供了创新策略。
source: biorxiv
selection_source: fresh_fetch
motivation: 使用深度生成模型的整合管线AI设计治阿尔茨海默病的候选药物。
method: 方法与实现细节请参考摘要与正文。
result: 结果与对比结论请参考摘要与正文。
conclusion: 总体而言，该工作在所述任务上展示了有效性，并提供了可复用的思路或工具。
---

## 摘要
全球超过5500万痴呆症患者目前尚无口服疾病修饰疗法可用。阿尔茨海默病(AD)仍是神经病学中最紧迫的未满足需求之一，近期遗传学证据估计，72-93%的AD负担可归因于常见的APOE等位基因变异。从机制上讲，APOE ε4亚型会损害脑内胆固醇转运，促进小胶质细胞中胆固醇酯的积累；这些富含脂质的细胞会丧失吞噬清除β-淀粉样蛋白和自噬介导的磷酸化tau降解的能力，将单一上游代谢紊乱与AD的两大标志性病理联系起来。ACAT1/SOAT1是脑内主要的胆固醇酯化酶，是一个有吸引力的治疗靶点：抑制该酶可减少胆固醇酯的形成，恢复小胶质细胞对Aβ的清除，降低Aβ的产生，并通过自噬促进tau降解，这一多模式机制是目前已获批疗法所不具备的。然而，以往的ACAT抑制剂项目存在亚型非选择性、过度的亲脂性以及缺乏中枢神经系统优化等局限性。针对这些限制，我们提出CuraGenAI药物发现平台，用于设计口服、脑渗透性的ACAT1靶向小分子候选物。该管线将基于支架约束的生成化学与跨越30多项标准的多目标ADMET优化相结合。从大约600万个生成的分子中，经过多阶段筛选，获得了约7300个经中枢神经系统优化的候选物，其预测的口服脑渗透特性与以往的ACAT临床化合物截然不同。三个提名的先导候选物显示预测的血脑屏障透过概率>0.93，具有有利的中枢神经系统类药物理化特性，以及稳定的ACAT1结合构象，并被优先用于合成和体外验证。

## Abstract
For more than 55 million people living with dementia worldwide, no oral disease-modifying treatment is currently available. Alzheimer's disease (AD) remains one of the most urgent unmet needs in neurology, with recent genetic evidence estimating that 72-93% of AD burden is attributable to common APOE allelic variation. Mechanistically, the APOE {varepsilon}4 isoform impairs cholesterol transport in the brain, promoting cholesteryl ester accumulation in microglia; these lipid-laden cells lose phagocytic capacity for amyloid-{beta} clearance and autophagy-mediated degradation of phosphorylated tau, linking a single upstream metabolic disruption to both hallmark pathologies of AD. ACAT1/SOAT1, the brain's predominant cholesterol-esterifying enzyme, is an attractive therapeutic target: its inhibition reduces cholesteryl ester formation, restoring microglial A{beta} clearance, reducing A{beta} production, and promoting tau degradation via autophagy, supporting a multimodal mechanism not addressed by currently approved therapies. However, prior ACAT inhibitor programs were limited by isoform non-selectivity, excessive lipophilicity, and lack of CNS optimization. Addressing these constraints, we present the CuraGenAI Drug Discovery Platform for the design of oral, brain-penetrant ACAT1-targeted small-molecule candidates. The pipeline integrates scaffold-constrained generative chemistry with multi-objective ADMET optimization across more than 30 criteria. From approximately 6 million generated molecules, multi-stage filtering yielded approximately 7,300 CNS-optimized candidates with predicted oral brain-penetrant profiles distinct from prior ACAT clinical compounds. Three nominated lead candidates showed predicted BBB probabilities >0.93, favorable CNS drug-like physicochemical profiles, and stable ACAT1 binding poses, and are prioritized for synthesis and in vitro validation.