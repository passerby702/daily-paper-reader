---
title: "The YTHDC1 glutamate-rich domain docks to the ADAR1 Zα Domain, linking the N6-methyladenosine modification of pre-mRNAs to dsRNA editing"
title_zh: YTHDC1谷氨酸丰富结构域停靠至ADAR1 Zα结构域，将前体mRNA的N6-甲基腺苷修饰与dsRNA编辑联系起来
authors: "Gromak, D., Shaytan, A. K., Herbert, A., Poptsova, M."
date: 2026-07-12
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.08.737312v1.full.pdf"
tags: ["query:pocket-lig"]
score: 8.0
evidence: 基于扩散模型的蛋白质口袋结合子生成
tldr: ADAR1通过编辑dsRNA避免炎症反应，但其如何被招募至前体RNA尚不清楚。本研究采用AI驱动蛋白质设计策略，预测并验证YTHDC1的谷氨酸富集区与ADAR1 Zα结构域通过电荷互补机制结合，dsRNA作为共锚定支架稳定复合物。该发现将m6A修饰与RNA编辑两大系统直接关联，为自身免疫病和癌症的靶向干预开辟新途径。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737312-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1662, \"height\": 853, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737312-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1522, \"height\": 1109, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737312-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1571, \"height\": 1131, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737312-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1635, \"height\": 1187, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737312-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1611, \"height\": 971, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737312-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1640, \"height\": 1028, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737312-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1575, \"height\": 1167, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737312-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1549, \"height\": 978, \"label\": \"Figure\"}]"
motivation: 探索ADAR1编辑前体RNA的招募机制，揭示m6A修饰与dsRNA编辑的系统间联系。
method: 结合RFdiffusion与ProteinMPNN生成合成结合子，经多阶段BLASTp和ColabFold筛选，AlphaFold3建模确定YTHDC1为候选。
result: YTHDC1的poly-E区（199-254）通过电荷互补模拟Z-RNA磷酸骨架插入ADAR1 Zα口袋，dsRNA共锚定二元复合物，动力学模拟稳定性<3Å。
conclusion: YTHDC1招募ADAR1p150至转录相关YT小体，促进内含子前体的共转录编辑，联通了RNA修饰与编辑通路。
---

## 摘要
双链RNA编辑酶ADAR1的p150亚型通过保守的翼状螺旋-转角-螺旋Z结构域结合Z-DNA和Z-RNA。在此，我们描述了一种逆向计算设计策略来绘制Z的蛋白质相互作用因子。我们使用RFdiffusion和ProteinMPNN生成约10,000个针对Z识别表面优化的合成结合物，然后将其序列作为结构模板，通过BLASTp搜索人类蛋白质组。通过ColabFold pDockQ对来自298个蛋白质的约1,200个候选区域进行多阶段筛选，鉴定出79个候选蛋白用于高分辨率AlphaFold3建模，揭示了m6A读取器YTHDC1为排名最高的相互作用因子。AlphaFold3预测，YTHDC1的一个富含谷氨酸的poly-E无序区域（残基199-254）通过一种模拟Z-RNA磷酸骨架的电荷互补机制停靠到Z的基本识别口袋中。微秒级分子动力学模拟证实了二元ADAR1p150-YTHDC1复合物的稳定性，Z-poly-E界面在整个模拟过程中保持RMSD低于3 Å。三元复合物模拟表明，dsRNA作为共锚定支架，稳定了两种蛋白质在催化休眠构象中的同时结合。YTHDC1定位于与转录相关的YT小体，其中新生RNA经历m6A修饰，而负超螺旋促进Z-DNA形成，表明YTHDC1招募ADAR1p150以促进剪接前含内含子底物的编辑。

简短陈述：ADAR1可以在RNA生成后对其进行编辑，改变其携带的信息并移除可激活炎症反应的双链RNA。通过AI驱动的蛋白质设计，我们发现ADAR1与YTHDC1（一种识别新生成自身RNA的蛋白质）发生物理相互作用。这种相互作用使ADAR能够在RNA生成时对其进行编辑。这两个基本RNA修饰系统之间的意外联系为理解和潜在靶向由RNA转录本错误编辑驱动的自身免疫性疾病和癌症开辟了新途径。

## Abstract
The p150 isoform of the double-stranded RNA editing enzyme ADAR1 binds Z-DNA and Z-RNA through the conserved winged helix-turn-helix Z domain. Here, we describe an inverse computational design strategy to map protein interactors of Z. We used RFdiffusion and ProteinMPNN to generate [~]10,000 synthetic binders optimized for the Z recognition surface, then used their sequences as structural templates for BLASTp searches against the human proteome. Multi-stage screening of [~]1,200 candidate regions from 298 proteins via ColabFold pDockQ identified 79 candidates for high-resolution AlphaFold3 modeling, which revealed the m6A reader YTHDC1 as the top-ranked interactor. AlphaFold3 predicts that a glutamate-rich poly-E disordered region of YTHDC1 (residues 199-254) docks into the basic recognition pocket of Z through a charge-complementary mechanism that mimics the phosphate backbone of Z-RNA. Microsecond molecular dynamics simulations confirmed stability of the binary ADAR1p150-YTHDC1 complex, with the Z-poly-E interface maintaining RMSD below 3 [A] throughout. Ternary complex simulations showed that dsRNA acts as a co-anchoring scaffold stabilizing simultaneous engagement of both proteins in a catalytically dormant conformation. YTHDC1 localizes to transcription-associated YT bodies where nascent RNAs undergo m6A modification and negative supercoiling promotes Z-DNA formation, suggesting that YTHDC1 recruits ADAR1p150 to promote editing of intron-containing substrates prior to splicing.

Short StatementADAR1 can edit RNAs after they are made, changing the message they carry and removing double-stranded RNAs that can activate inflammatory responses. Using AI-driven protein design, we discovered that ADAR1 physically interacts with YTHDC1, a protein that recognizes newly made self-RNAs. The interaction allows ADAR to edit RNAs as they are made. This unexpected connection between two fundamental RNA modification systems opens new avenues for understanding and potentially targeting autoimmune disorders and cancers driven by the mis-editing of RNA transcripts.