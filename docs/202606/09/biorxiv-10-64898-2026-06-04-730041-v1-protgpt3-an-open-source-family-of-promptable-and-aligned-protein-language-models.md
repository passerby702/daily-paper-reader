---
title: "ProtGPT3: an Open-source family of Promptable and Aligned Protein Language Models"
title_zh: ProtGPT3：一个开源的可提示与对齐的蛋白质语言模型家族
authors: "Garibbo, M., Boxo Corominas, G., Stocco, F., Illanes Vicioso, R., Middendorf, L., Ferruz, N."
date: 2026-06-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.04.730041v1.full.pdf"
tags: ["query:diff-gen"]
score: 7.0
evidence: 用于蛋白质分子生成的生成式蛋白质语言模型
tldr: 生成式蛋白质语言模型在探索序列空间方面表现优异，但可控生成目标功能家族仍是挑战。ProtGPT3系列模型（112M-10B参数）支持单序列和MSA提示，通过对齐技术优化模型行为，并采用少样本提示实现无需微调的灵活控制。实验表明对齐降低低复杂度序列生成，少样本提示在脱氟酶设计中比微调更高效，且MSA模型实验验证成功。开源模型及Feynman-Kac推理程序为可控蛋白质设计提供新范式。
source: biorxiv
selection_source: fresh_fetch
motivation: 生成式蛋白质语言模型难以可靠控制生成序列朝向目标功能家族，需探索对齐方法和提示控制技术。
method: 构建ProtGPT3系列模型（112M-10B参数），包括单序列和MSA提示模型；采用序列复杂度与结构置信度对齐，并与少样本提示对照微调。
result: 对齐减少低复杂度生成；少样本提示在脱氟酶设计中优于微调，MSA模型实验验证可溶表达且成功率更高。
conclusion: 开源ProtGPT3系列结合对齐与提示控制，为蛋白质设计提供可扩展的生成方法，并引入Feynman-Kac推理程序。
---

## 摘要
生成式蛋白质语言模型(pLMs)能够探索广阔的蛋白质设计序列空间，但可靠地控制生成朝向所需功能家族仍具挑战性。尽管蛋白质生成总体上遵循自然语言处理的趋势，但有两个方向仍未充分探索：针对设计目标优化模型行为的对齐方法，以及无需微调即可在推理时基于提示的控制。我们推出ProtGPT3，这是一个开源的蛋白质语言模型家族，参数量从1.12亿到100亿不等，并与Hugging Face生态系统集成。该套件包括单序列和多序列比对(MSA)可提示模型，支持灵活的生成条件设置。在不同模型规模和控制设置下，我们系统地比较了监督微调和基于同源序列的少样本提示。类似于大型语言模型(LLMs)通常与用户意图对齐，我们使用跨蛋白质组的序列复杂性和结构置信度指标，研究单序列模型中的训练后对齐。我们发现，对齐减少了低复杂性生成，同时保留了序列多样性。此外，我们证明，对于受控生成，少样本提示是监督微调的一种更具竞争力且更可扩展的替代方案。在一个低数据量的脱氟酶案例研究中，ProtGPT3-MSA取得了比微调基线更高的计算成功率，并产生了实验验证后可溶且表达的设计。最后，我们通过引入基于同源序列的费曼–卡克推理过程来引导蛋白质生成朝向目标，探索了MSA模型中推理时计算的潜力。我们在https://huggingface.co/collections/AI4PD/protgpt3-family 上公开提供我们的模型。

## Abstract
Generative protein language models (pLMs) enable exploration of vast sequence spaces for protein design, but reliably controlling generation toward desired functional families remains challenging. While protein generation has broadly followed trends in NLP, two directions remain underexplored: alignment methods that optimize model behavior toward design objectives, and prompting-based control at inference time without fine-tuning. We introduce ProtGPT3, an open-source family of protein language models spanning 112M to 10B parameters and integrated with the Hugging Face ecosystem. The suite includes both single-sequence and multiple sequence alignment (MSA)-promptable models, enabling flexible conditioning for generation. Across model scales and control settings, we systematically compare supervised fine-tuning and few-shot prompting using homologous sequences. Analogous to how large language models (LLMs) are routinely aligned with user intent, we study post-training alignment in single-sequence models using sequence-complexity and structure-confidence metrics across the proteome. We find that alignment reduces low-complexity generations while preserving sequence diversity. Furthermore, we show that few-shot prompting is a competitive and more scalable alternative to supervised fine-tuning for controlled generation. In a low-data defluorinase case study, ProtGPT3-MSA achieved higher computational success rates than fine-tuned baselines and produced designs that were soluble and expressed following experimental validation. Finally, we explore the potential of inference-time compute in MSA models by introducing a homolog-based Feynman--Kac inference procedure for steering protein generation toward desired targets. We make our models publicly available at https://huggingface.co/collections/AI4PD/protgpt3-family .