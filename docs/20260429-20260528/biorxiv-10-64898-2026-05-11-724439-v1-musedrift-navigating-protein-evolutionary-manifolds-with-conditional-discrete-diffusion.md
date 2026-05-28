---
title: "MuseDrift: Navigating Protein Evolutionary Manifolds with Conditional Discrete Diffusion"
title_zh: MuseDrift：使用条件离散扩散导航蛋白质进化流形
authors: "Wang, C., Wang, Y."
date: 2026-05-12
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.11.724439v1.full.pdf"
tags: ["query:diff-gen"]
score: 9.0
evidence: 提出条件离散扩散模型进行距离控制的蛋白质生成
tldr: "蛋白质工程需控制变体与野生型的序列相似度，现有模型难以精细调控。MuseDrift通过条件离散扩散和校准身份表盘，实现锚定WT的距离可控生成。在基准测试中，身份控制精度达±0.05，τ=0.95时pLDDT>84，参数仅85M。该工作为蛋白质进化探索提供了精准高效的导航工具。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有生成模型缺乏对野生型序列相似度的显式控制，限制定向进化应用。
method: 提出MuseDrift，结合WT前缀条件与随机迭代去掩码的离散扩散模型，并引入校准身份表盘。
result: 身份控制精度达±0.05，在τ=0.95时Mol-Instructions/CAMEO的pLDDT分别为84.97和83.14（85M参数）。
conclusion: MuseDrift在保持竞争性能的同时，首次实现显式的蛋白质距离控制，兼具生物合理性。
---

## 摘要
蛋白质工程通常需要生成野生型（WT）序列的变体，同时控制它们在序列空间中漂移的距离。现有的生成模型支持从头设计，但对WT相似度的控制有限。我们推出了MuseDrift，一个条件离散扩散模型，用于以WT为锚点、距离可控的蛋白质生成。MuseDrift在3820万对的种子-分层语料库上训练，结合了WT前缀条件和随机顺序迭代去掩码，以实现稳定的多残基生成。其关键特性是校准的身份拨盘：经过轻量校准后，生成的序列在预留探针上，目标WT身份一致度τ在[0.55, 0.95]范围内，误差约为±0.05。在Mol-Instructions和CAMEO上使用共享评估oracle进行评估，MuseDrift与多模态和文本条件基准相比具有竞争力，同时能提供独特的显式身份控制。在τ=0.95时，它在Mol-Instructions上达到84.97的pLDDT分数，在CAMEO上达到83.14，仅使用8500万个参数，媲美大得多的18亿-20亿模型。进化和FoldX分析进一步支持了其生物合理性和结构稳定性。

## Abstract
Protein engineering often requires generating variants of a wild-type (WT) sequence while controlling how far they drift in sequence space. Existing generative models support de novo design but offer limited control over WT similarity. We introduce MO_SCPLOWUSEC_SCPLOWDO_SCPLOWRIFTC_SCPLOW, a conditional discrete diffusion model for WT-anchored, distance-controlled protein generation. Trained on a 38.2M-pair Seed-and-Stratify corpus, MO_SCPLOWUSEC_SCPLOWDO_SCPLOWRIFTC_SCPLOW combines WT-prefix conditioning with random-order iterative unmasking to enable stable multi-residue generation. Its key feature is a calibrated identity dial: after lightweight calibration, generated sequences match a target WT identity{tau} within approximately {+/-}0.05 over{tau} [isin] [0.55, 0.95] on held-out probes. On Mol-Instructions and CAMEO under shared evaluation oracles, MO_SCPLOWUSEC_SCPLOWDO_SCPLOWRIFTC_SCPLOW is competitive with multimodal and text-conditioned baselines while uniquely providing explicit identity control. At{tau} = 0.95, it achieves pLDDT scores of 84.97 on Mol-Instructions and 83.14 on CAMEO with only 85M parameters, rivaling much larger 1.8B-2B models. Evolutionary and FO_SCPLOWOLDC_SCPLOWX analyses further support biological plausibility and structural stability.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：在蛋白质工程中，例如定向进化或功能微调，研究人员常需以野生型（WT）序列为起点，生成具有一定序列相似度的变体，即“控制序列空间中的漂移距离”。然而，现有的蛋白质生成模型（如基于语言模型或多模态条件的模型）主要面向从头设计，缺乏对“与野生型序列相似度”这一关键指标的明确、可调节控制。
- **整体含义**：MuseDrift 提出了首个能够按需设定“目标身份一致度（τ）”的条件离散扩散模型，犹如为蛋白质进化探索提供了带有“距离标尺”的导航器，实现了可控、精准的变体生成。

### 2. 论文提出的方法论
- **核心思想**：将蛋白质序列生成建模为条件离散扩散过程，以野生型序列作为“锚点”，通过生成过程中逐步去掩码实现多残基协同突变，同时引入一个可校准的“身份拨盘”来精准控制生成序列与野生型的序列一致度。
- **关键技术细节**：
  - **训练策略**：在包含**3820万对**“种子‑分层”语料库上训练，使模型学会在不同的序列相似度层级下生成。
  - **条件机制**：采用**WT前缀条件**（WT-prefix conditioning），将野生型序列的部分信息作为上下文输入，引导生成。
  - **生成过程**：使用**随机顺序迭代去掩码**（random-order iterative unmasking）的离散扩散方式，以稳定逐步地揭示多残基替换。
  - **核心创新——校准身份拨盘**：在训练后引入轻量级校准步骤，使目标τ（范围0.55~0.95）与实际生成序列的WT identity之间的误差控制在约**±0.05**。
- **算法流程概要**（文字描述）：给定野生型序列和目标身份τ，将任务编码为带蒙版的序列，逐步按照随机顺序恢复残基，恢复时模型依条件概率采样，过程受扩散时间步和τ参数共同控制，使最终生成的序列以高精度逼近目标相似度。

### 3. 实验设计
- **数据集与场景**：
  - **训练语料**：专属构建的3820万对“种子‑分层”数据对。
  - **评估数据集**：使用两个公开基准测试集——**Mol-Instructions**（指令驱动的分子生成）和**CAMEO**（结构预测中常用评估集）。
- **主要评估指标**：以**pLDDT**（预测局部距离差异测试，反映结构可信度）为核心性能衡量，并辅以进化分析和FoldX结构稳定性评估。
- **对比方法**：与**多模态模型**和**文本条件基础模型**（如大至1.8B–2B参数的语言模型）进行比较，证明在相同评估oracle下具备竞争力。

### 4. 资源与算力
- 论文摘要中**未明确提及**所使用GPU的型号、数量及具体训练时长。仅披露了模型参数量为**8500万**。相关算力资源细节需从全文获取。

### 5. 实验数量与充分性
- **主要实验组数**（基于摘要推断）：
  - 身份控制精度测试：在预留探针上验证τ∈[0.55,0.95]区间的偏差 ≤ ±0.05。
  - 性能对比实验：在Mol-Instructions和CAMEO两个数据集上，与多模态及文本条件大模型进行pLDDT对比。
  - 结构合理性验证：FoldX能量分析与进化尺度序列合理性分析。
  - 可能包含消融实验（如不同τ组合、有无校准等），但摘要未详细列出。
- **充分性评价**：在核心命题上验证较为全面，既展示了控制精度，也给予了结构与进化合理性的佐证，并进行了多场景对比，整体设计客观、公平。但由于未提供全文，消融实验和泛化性分析的程度尚无法判断。

### 6. 主要结论与发现
- **精准身份控制**：首次实现了蛋白质生成中对WT similarity的**显式可调**，校准后在宽τ范围内误差仅±0.05。
- **性能竞争力**：在仅8.5千万参数下，MuseDrift在τ=0.95时，Mol-Instructions上pLDDT达84.97，CAMEO上达83.14，**媲美18亿–20亿参数的大模型**，证明高效且实用。
- **生物学合理性**：进化分析与FoldX稳定性评估进一步支持生成的变体在进化路径和结构刚性上具有合理性，而非随机突变。

### 7. 优点
- **首创显式距离控制**：弥补了现有生成模型在定向进化相似度控制上的空白。
- **高精度拨盘机制**：通过轻量校准使身份一致度达到实用级可控（±0.05）。
- **参数高效**：仅85M参数即取得与大模型可比的结构质量，部署成本低。
- **多维度验证**：不仅关注序列质量，还纳入FoldX和进化指标，评价体系更全面。

### 8. 不足与局限
- **实验覆盖限制**：摘要未提及在湿实验层面的验证，仅依赖计算指标（pLDDT、FoldX），实际功能相关性未知。
- **τ调节范围**：测试的τ下限为0.55，未覆盖极低相似度（如<0.5）的远同源序列生成场景。
- **泛化风险**：训练数据“种子‑分层”语料库的具体构成和规模可能引入对特定蛋白家族的偏好，未说明在全新折叠类型上的表现。
- **条件方式局限**：主要固定于WT前缀条件，若面对无天然WT锚点的全新功能蛋白设计任务，适用性可能下降。
- **算力未披露**：缺少训练资源报告，难以复现和评估环境要求。

（完）
