---
title: Diffusion-based stimulus optimization reveals functional organization across higher visual cortex
title_zh: 基于扩散模型的刺激优化揭示高级视觉皮层的功能组织
authors: "Henderson, M. M., Luo, A. F., Park, S., Tarr, M. J., Wehbe, L."
date: 2026-05-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.12.724119v1.full.pdf"
tags: ["query:diff-gen"]
score: 6.0
evidence: 使用预训练扩散模型生成fMRI刺激，将扩散模型应用于神经科学
tldr: 传统神经影像实验受刺激多样性限制，难以精细表征高级视觉皮层功能组织。本文验证了先前开发的BrainDiVE工具，利用预训练图像扩散模型结合fMRI编码模型梯度生成能强烈激活特定脑区的自然图像。新被试实验证实扩散优化刺激有效揭示功能区域差异，为视觉神经科学研究提供新方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 使用预训练扩散模型生成fMRI刺激，将扩散模型应用于神经科学。
method: 方法与实现细节请参考摘要与正文。
result: 结果与对比结论请参考摘要与正文。
conclusion: 总体而言，该工作在所述任务上展示了有效性，并提供了可复用的思路或工具。
---

## 摘要
描述人类高级视觉皮层精细功能组织仍然是一个核心挑战，因为传统的神经影像学实验限制了可以采样的刺激多样性。在先前的工作中，我们通过开发一种新型数据驱动工具“BrainDiVE”（Luo等人，2023年）来应对这一挑战，该工具能够合成预测可强烈激活特定脑区的自然图像。BrainDiVE利用预训练的图像扩散模型，并由可图像计算的功能磁共振成像编码模型梯度引导。在此，我们通过生成预测能最大限度激活不同功能感兴趣区的图像，并在功能磁共振成像研究中呈现给新参与者（n = 12），对BrainDiVE进行了实验验证。模型生成的图像在目标脑区引发了稳健的、空间特异性的反应，产生的类别选择性显著高于自然图像，验证了该方法能够捕捉人类腹侧视觉皮层中可泛化的神经调谐特性。我们进一步表明，针对特定脑区的图像夸大了特定的低级和中级图像统计特征集，提示类别选择性区域调谐于特征空间中的连续方向。此外，我们通过差异性地激活两个面孔选择性区域——枕叶面孔区（OFA）和梭状回面孔区（FFA），展示了精细的实验控制，为这些区域编码面孔的不同方面提供了额外证据。最后，我们在枕叶场所区（OPA）内识别出一个从后到前的功能梯度，提示基于场景属性（如距离和室内-室外位置）的地形组织。这些发现增进了我们对类别选择性区域的表征结构的理解，并为探索人类视觉皮层中的神经选择性引入了一种新范式。

## Abstract
Characterizing the fine-grained functional organization of human higher visual cortex remains a central challenge, as traditional neuroimaging experiments constrain the diversity of stimuli that can be sampled. In prior work we addressed this challenge by developing a novel data-driven tool, termed "BrainDiVE" (Luo et al. 2023), which synthesizes naturalistic images predicted to strongly activate specific brain regions. BrainDiVE leverages pretrained image diffusion models guided by gradients from an image-computable fMRI encoding model. Here, we experimentally validated BrainDiVE by generating images predicted to maximally activate different functional regions of interest and then presenting them to new participants (n=12) in an fMRI study. The model-generated images elicited robust, spatially specific responses in the targeted brain regions, producing significantly greater category selectivity than natural images, validating the methods ability to capture generalizable neural tuning properties in human ventral visual cortex. We further showed that region-targeted images exaggerate specific sets of low-level and mid-level image statistics, suggesting that category-selective regions are tuned to continuous directions in feature space. Moreover, we demonstrated fine-grained experimental control by differentially activating two face-selective regions, the occipital face area (OFA) and fusiform face area (FFA), providing additional evidence that these regions encode distinct aspects of faces. Finally, we identify a posterior-to-anterior functional gradient within the occipital place area (OPA), suggesting topographic organization based on scene properties such as distance and indoor-outdoor location. These findings enhance our understanding of the representational structure of category-selective regions and introduce a new paradigm for probing neural selectivity in human visual cortex.