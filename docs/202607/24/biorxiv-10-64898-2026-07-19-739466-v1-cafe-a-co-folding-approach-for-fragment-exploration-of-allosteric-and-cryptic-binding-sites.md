---
title: "CAFE: A Co-folding Approach for Fragment Exploration of Allosteric and Cryptic Binding Sites"
title_zh: CAFE：用于变构和隐秘结合位点片段探索的共折叠方法
authors: "Purnomo, J. C., Sun, K., Head-Gordon, T."
date: 2026-07-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.19.739466v1.full.pdf"
tags: ["query:pocket-lig"]
score: 8.0
evidence: 利用共折叠探索变构结合位点的片段
tldr: 共折叠模型在变构药物发现中受限于正构位点偏好，即使片段筛选也无法避免记忆效应。CAFE通过引入竞争性正构阻断剂（如激酶中的ADP），迫使片段探索变构和隐性位点。在Boltz-2模型上，CAFE显著增加变构位点发现，结合自由能强于或等于晶体结构，并识别传统方法漏检的隐性口袋。该方法无需额外训练，从推理层面提升了共折叠模型在变构与隐性位点药物发现中的实用性。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1622, \"height\": 595}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1491, \"height\": 1316}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1411, \"height\": 430}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1612, \"height\": 1207}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1598, \"height\": 1112}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1377, \"height\": 1211}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1668, \"height\": 1216}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1367, \"height\": 481}]"
motivation: 共折叠模型对正构配体存在系统偏好，限制变构位点发现；片段筛选也因记忆效应默认结合正构位点。
method: CAFE在共折叠协议中加入竞争性正构阻断剂，阻止片段占据正构位点，迫使其探索变构和隐性口袋。
result: CAFE在激酶等蛋白上大幅增加变构位点探索，结合自由能强于晶体结构，并发现多个未知隐性口袋。
conclusion: CAFE为无需训练的推理时协议，有效克服共折叠模型局限，推动变构与隐性位点药物发现。
---

## 摘要
共折叠模型在变构药物发现中具有巨大潜力，但由于其对正构配体结合的系统性偏差而严重受限。尽管片段筛选已被提出用于变构结合位点发现，但我们表明共折叠模型仍存在记忆问题，即化学上更简单的片段也默认结合到典型的正构结合位点。为克服这些限制，我们引入了CAFE（用于片段探索的共折叠方法），这是一种共折叠协议，利用竞争性正构阻断剂将片段引导至非典型位点，如本文中通过Boltz-2共折叠模型所示。使用ADP作为激酶家族的正构阻断剂，我们发现CAFE显著增加了片段的变构结合位点探索，且具有显著强的绝对结合自由能，达到或超过已知晶体学构象的自由能，而无需对Boltz-2预测进行事后优化。我们还表明，CAFE识别出常规口袋预测工具未检测到的隐秘结合口袋，其中一些在热力学上比变构或正构口袋更有利。为展示通用性，我们将CAFE应用于使用I型正构阻断剂的激酶蛋白、使用已知正构配体作为阻断剂的RAS-MAPK信号通路中的非激酶蛋白，以及使用片段库进行虚拟筛选以发现选择性结合变构和隐秘结合位点的新片段。CAFE确立了正构阻断和片段筛选作为一种无需训练、推理时的协议，有助于克服当前共折叠模型的一些局限性，同时提升其在变构和隐秘结合药物发现中的巨大潜力。

## Abstract
Co-folding models hold immense potential for allosteric drug discovery, but have been severely hampered by their systematic bias toward orthosteric ligand binding. While fragment screening has been proposed for allosteric binding site discovery, we show that co-folding models still suffer from memorization in which chemically simpler fragments also default to canonical orthosteric binding sites. To overcome these limitations, we introduce CAFE (Co-folding Approach for Fragment Exploration), a co-folding protocol that uses competitive orthosteric blockers to divert fragments into non-canonical sites as illustrated here with the Boltz-2 co-folding model. Using ADP as an orthosteric blocker for the kinase family, we find CAFE substantially increases the allosteric binding site exploration for fragments, with notably strong absolute binding free energies that match or exceed those of known crystallographic poses, without post-hoc refinement of the Boltz-2 prediction. We also show that CAFE identifies cryptic binding pockets undetected by conventional pocket prediction tools, some of which are more thermodynamically favorable than the allosteric or orthosteric pockets. To demonstrate generality, we apply CAFE using Type I orthosteric blockers for kinase proteins, known orthosteric ligands as blockers for non-kinase proteins in the RAS-MAPK signaling pathway, and for virtual screening campaigns using fragment libraries for new fragments that selectively engage allosteric and cryptic binding sites. CAFE establishes orthosteric blocking and fragment screening as a training-free, inference-time protocol that helps overcome some of the limitations of current co-folding models while elevating their great promise for allosteric and cryptic binding drug discovery.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将基于您提供的论文内容，对其进行结构化、深入、客观的总结。

---

### 论文《CAFE: 一种用于变构和隐秘结合位点片段探索的共折叠方法》详细中文总结

#### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：当前先进的蛋白质-配体共折叠模型（如AlphaFold3、Boltz-2）在变构药物发现中展现出巨大潜力，但它们普遍存在一个系统性偏差：模型在预测配体结合位点时，会强烈倾向于已知的、训练数据（如PDB数据库）中更常见的正构（orthosteric）结合位点。这种“记忆效应”导致模型难以准确预测变构（allosteric）或隐秘（cryptic）结合位点，甚至化学结构简单的片段也会“默认”结合到正构位点。
*   **研究动机**：开发一种**无需重新训练或微调模型**，仅在推理阶段（inference-time）就能克服共折叠模型正构位点偏好的方法，以使其能够有效地用于变构和隐秘结合位点的发现和药物筛选。
*   **整体含义**：通过将实验化学中“活性位点占据下的晶体浸泡”（active-site-occupied crystal soaking）逻辑转化为计算协议，论文提出了一种简单、通用且有效的策略，将共折叠模型的固有缺陷转化为其探索“未知”位点的强大驱动力。

#### 2. 论文提出的方法论
*   **核心思想**：在共折叠模型的输入中，强制加入一个已知的、与目标蛋白正构位点紧密结合的**竞争性正构阻断剂**。该阻断剂在模型的联合扩散过程中物理性地占据了正构位点，从而迫使测试的“片段”探针无法进入该位点，只能探索蛋白质表面的其他区域，包括变构和隐秘位点。
*   **关键技术细节（CAFE协议流程）**：
    1.  **片段库构建**：使用BRICS（Breaking of Retrosynthetically Interesting Chemical Substructures）方法对已知的正构或变构配体进行单次断裂，生成化学片段库，并确保片段分子量≥150 Da且含有≥8个重原子。
    2.  **阻断剂选择**：对于激酶家族，使用腺苷二磷酸（ADP）作为通用阻断剂，因为它能稳定地占据ATP结合位点。对于非激酶靶点，则选择其特异性的正构配体（如PTP1B的肽段、KRAS的GDP）。也可使用共晶的I型小分子抑制剂作为阻断剂。
    3.  **共折叠推理**：将蛋白质序列、片段SMILES和正构阻断剂分子一同作为输入，通过Boltz-2模型进行联合结构预测。每个片段生成10个独立的扩散样本作为分析集合。
    4.  **位点定位分析**：根据预测片段和已知参考配体的质心（COM）距离，将片段归类为正构位点（d_ortho ≤ 5.0 Å）、变构位点（d_allo ≤ 5.0 Å）或隐秘位点（不属于前两者）。
    5.  **热力学验证**：对预测的变构/隐秘位点的片段构象，直接进行**绝对结合自由能（ABFE）计算**，无需对Boltz-2输出的结构进行任何后处理优化，以评估其结合的热力学可行性。ABFE使用双解耦（double-decoupling）方法，结合AMBER力场和MBAR分析。

#### 3. 实验设计
*   **数据集与场景**：
    *   **主要靶点**：选取了5个代表性人类激酶（AKT2, CDK2, CHEK1, CSNK2A1, MAPK14）和2个非激酶靶点（PTP1B, KRAS），涵盖不同PDB数据覆盖率和折叠拓扑。
    *   **片段来源**：
        1.  **验证用片段**：从22个I型正构抑制剂和21个变构配体的共晶结构中通过BRICS分解得到232个片段（116正构来源，116变构来源）。
        2.  **筛选用片段**：从Enamine High Fidelity Fragment Library中筛选出300个化学多样性的片段。
    *   **基准与对比**：
        *   **主要对比**：使用ADP/配体阻断剂与不使用阻断剂（无阻断）条件下的片段定位分布对比。
        *   **置信度评估**：对比Boltz-2模型自身的ipTM置信度分数与基于几何距离的定位分析结果。
        *   **隐秘位点评估**：将CAFE发现的隐秘位点与专用口袋预测工具P2Rank和FPocket的预测结果进行交叉比对。
        *   **热力学验证**：对比CAFE预测构象与晶体学参考构象的ABFE计算结果。

#### 4. 资源与算力
*   论文中并未明确说明具体使用的GPU型号、数量以及共折叠和ABFE计算总的耗时。文中只提到使用了美国国家能源研究科学计算中心（NERSC）的计算资源。因此，**无法给出具体的算力统计**。

#### 5. 实验数量与充分性
*   **实验数量**：实验非常充分且系统。
    *   在7个靶点蛋白上进行了基础验证，评估了非正构位点探索率。
    *   对5个激酶靶点，使用232个片段进行了详细的交叉测试。
    *   对30个片段-激酶复合物进行了ABFE计算，直接对比了预测与晶体结构的热力学质量。
    *   识别并分析了14个隐秘位点，并对其中的2个（CDK-A017, CDK-A026）进行了深入的ABFE分析。
    *   对300个来自Enamine的商业片段进行了完整的虚拟筛选流程，并最终对107个候选片段进行了ABFE验证。
*   **充分性与公平性**：
    *   **充分性**：实验设计涵盖了多个靶点家族、多种片段来源、多种阻断剂（ADP、Type I抑制剂），并进行了从定位分析到热力学验证的全流程评估，实验设计相当全面和深入。
    *   **公平性**：对比条件（有无阻断剂）设置清晰，控制变量良好。ABFE计算直接使用未经优化的原始模型输出，这既体现了方法的简洁性，也避免了潜在的数据后处理偏好。然而，**缺乏与其他如AF2BIND等方法的直接对比**，是其公平性方面的一个不足。

#### 6. 论文的主要结论与发现
*   **CAFE通用有效**：CAFE能跨靶点（激酶和非激酶）显著提升片段探索非正构结合位点的能力。对于激酶，使用ADP阻断后，非正构位点探索率从平均11.7%跃升至85.0%。
*   **化学偏好可被覆盖**：片段本身的化学结构（如芳香环、氢键受体数目）会加剧其被正构位点“捕获”的倾向，但正构阻断剂的使用可以有效超越这种化学偏好。
*   **高质量变构构象**：CAFE发现的变构片段构象，其ABFE计算值与晶体学参考构象相当甚至更优，证明了其热力学可行性。这同时表明，Boltz-2模型的原始输出已经足够精确，无需额外优化即可用于后续计算。
*   **发现隐秘口袋**：CAFE能发现P2Rank和FPocket等传统静态几何方法无法检测到的隐秘结合口袋，且这些口袋对片段的结合热力学上甚至可能比已知的变构或正构位点更有利。
*   **指导性筛选**：通过结合正构和变构双阻断剂（double-blocker），可以进一步引导片段优先探索隐秘位点，实现了对结合位点的“可调式”筛选。
*   **筛选能力**：CAFE可以作为有效的虚拟筛选工具，从商业片段库中筛选出对变构或隐秘位点具有选择性结合能力的片段。

#### 7. 优点（方法或实验设计的亮点）
1.  **无需训练，即插即用**：CAFE是一个推理时协议，不依赖于昂贵的模型微调或重新训练，可以直接应用于现有和新一代的共折叠模型。
2.  **模型无关**：其核心思想和流程理论上可迁移到任何基于多链输入的共折叠模型（如AlphaFold3, RoseTTAFold All-Atom等），具有极高的普适性。
3.  **片段级物理合理性**：证明了即使是很小的片段，在Boltz-2的原始输出下也具有物理合理的结合几何，其ABFE值直接可信，省略了常规的结构优化步骤，简化了工作流。
4.  **同时发现口袋和配体**：CAFE不仅能发现隐秘口袋，还能作为探针的片段本身直接“命中”这些口袋。这意味着它实现了口袋发现与先导化合物发现的合二为一。
5.  **实验逻辑启发性**：将计算化学与经典实验化学（晶体浸泡）的逻辑相结合，思路新颖且简洁。

#### 8. 不足与局限
1.  **泛化性挑战**：对于PDB中结构高度同源的靶点（如CDK2），即使使用CAFE，片段主要聚集在隐秘位点而非已知的经典变构位点，表明对于特定靶点，CAFE的回溯能力（引导到已知功能位点）可能存在局限。
2.  **依赖模型能力**：CAFE的成功高度依赖于底层共折叠模型（这里是Boltz-2）的质量。如果模型本身对某类蛋白的结构预测严重不准确，CAFE的效果也会大打折扣。
3.  **阻碍剂依赖性**：需要一个已知的正构位点结合分子作为阻碍剂。这限制了其在缺乏任何已知配体的“全新”靶点上的直接应用。
4.  **无法替代置信度评估**：CAFE明确指出现有模型的ipTM等置信度指标不能用于区分正构和变构位点，必须依赖额外的几何距离打分，这增加了分析的复杂性。
5.  **缺乏实验验证**：虽然论文通过ABFE进行了热力学验证，但所有预测均停留在计算层面，**缺乏湿实验（如SPR、NMR或晶体学）的直接验证**，这是其在药物发现领域实用性的最大局限。
6.  **计算成本**：尽管无需训练，但大量的ABFE计算（30个片段 + 后续筛选的100多个片段）对GPU算力资源消耗巨大，这可能是其实际应用中的瓶颈。
7.  **比较基线有限**：实验设计中主要对比了“有/无阻断剂”，缺少与其他经典或前沿的变构位点/隐秘位点预测方法（如DynoDock、Temple等）的直接性能对比，使得其优势的定量化不够充分。

（完）
