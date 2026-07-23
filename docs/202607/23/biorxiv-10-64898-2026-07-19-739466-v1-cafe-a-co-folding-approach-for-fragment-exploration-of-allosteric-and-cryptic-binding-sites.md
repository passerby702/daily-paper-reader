---
title: "CAFE: A Co-folding Approach for Fragment Exploration of Allosteric and Cryptic Binding Sites"
title_zh: CAFE：用于变构和隐性结合位点片段探索的共折叠方法
authors: "Purnomo, J. C., Sun, K., Head-Gordon, T."
date: 2026-07-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.19.739466v1.full.pdf"
tags: ["query:pocket-lig"]
score: 8.0
evidence: 共折叠协议用于变构和隐秘结合位点的片段探索
tldr: 共折叠模型倾向于正构位点，CAFE通过引入竞争性正构阻断剂将片段引导至变构和隐蔽位点，显著提升探索效果。使用ADP作为激酶阻断剂，CAFE发现的变构位点结合自由能匹配或超过晶体结构，并识别出传统工具未发现的隐蔽口袋。该方法在多种蛋白和虚拟筛选中通用，为变构药物发现提供了无需训练的推理协议。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1622, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1491, \"height\": 1316, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1411, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1612, \"height\": 1207, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1598, \"height\": 1112, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1377, \"height\": 1211, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1668, \"height\": 1216, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-19-739466-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1367, \"height\": 481, \"label\": \"Table\"}]"
motivation: 共折叠模型对正构位点存在系统性偏见，片段筛选受记忆化影响，难以发现变构位点。
method: 提出CAFE协议，在共折叠时引入正构阻断剂（如ADP）竞争结合，迫使片段探索非典型位点。
result: CAFE显著增加变构位点探索，结合自由能优异，匹配或超过晶体学数据，并发现新的隐蔽口袋。
conclusion: CAFE是一种无需训练、高效的正构阻断协议，增强了共折叠模型在变构和隐蔽药物发现中的应用。
---

## 摘要
共折叠模型在变构药物发现中具有巨大潜力，但因其对正构配体结合的系统性偏差而严重受限。虽然片段筛选已被提议用于发现变构结合位点，但我们发现共折叠模型仍存在记忆化问题，即化学结构更简单的片段也默认倾向结合经典正构位点。为克服这些限制，我们引入CAFE（片段探索的共折叠方法），这是一种利用竞争性正构阻断剂将片段引导至非经典位点的共折叠协议，此处以Boltz-2共折叠模型为例。使用ADP作为激酶家族的正构阻断剂，我们发现CAFE显著增加了片段的变构结合位点探索，其绝对结合自由能尤为强劲，与已知晶体学构象相当甚至更优，且无需对Boltz-2预测进行事后优化。我们还发现CAFE能识别出常规口袋预测工具无法检测的隐性结合口袋，其中一些在热力学上比变构或正构口袋更有利。为展示通用性，我们将CAFE应用于：使用I型正构阻断剂作用于激酶蛋白、使用已知正构配体作为RAS-MAPK信号通路中非激酶蛋白的阻断剂，以及利用片段库进行虚拟筛选以发现选择性结合变构和隐性位点的新片段。CAFE确立了正构阻断与片段筛选作为一种无需训练、基于推理时间的协议，有助于克服当前共折叠模型的部分局限性，同时提升其在变构与隐性结合药物发现中的巨大潜力。

## Abstract
Co-folding models hold immense potential for allosteric drug discovery, but have been severely hampered by their systematic bias toward orthosteric ligand binding. While fragment screening has been proposed for allosteric binding site discovery, we show that co-folding models still suffer from memorization in which chemically simpler fragments also default to canonical orthosteric binding sites. To overcome these limitations, we introduce CAFE (Co-folding Approach for Fragment Exploration), a co-folding protocol that uses competitive orthosteric blockers to divert fragments into non-canonical sites as illustrated here with the Boltz-2 co-folding model. Using ADP as an orthosteric blocker for the kinase family, we find CAFE substantially increases the allosteric binding site exploration for fragments, with notably strong absolute binding free energies that match or exceed those of known crystallographic poses, without post-hoc refinement of the Boltz-2 prediction. We also show that CAFE identifies cryptic binding pockets undetected by conventional pocket prediction tools, some of which are more thermodynamically favorable than the allosteric or orthosteric pockets. To demonstrate generality, we apply CAFE using Type I orthosteric blockers for kinase proteins, known orthosteric ligands as blockers for non-kinase proteins in the RAS-MAPK signaling pathway, and for virtual screening campaigns using fragment libraries for new fragments that selectively engage allosteric and cryptic binding sites. CAFE establishes orthosteric blocking and fragment screening as a training-free, inference-time protocol that helps overcome some of the limitations of current co-folding models while elevating their great promise for allosteric and cryptic binding drug discovery.

---

## 论文详细总结（自动生成）

好的，以下是对该论文的结构化、深入、客观的中文总结。

---

### 论文结构化总结：CAFE: 用于变构和隐性结合位点片段探索的共折叠方法

#### 1. 论文的核心问题与整体含义
-   **研究背景**：基于深度学习的共折叠模型（如AlphaFold3、Boltz-1/2）在蛋白质-配体复合物结构预测上表现出色，尤其能捕捉配体诱导的构象变化，对变构药物发现潜力巨大。
-   **核心问题**：共折叠模型存在严重的**系统性偏见（系统偏差）**，即训练数据中大量的正构位点复合物导致模型“死记硬背”，使配体（尤其是化学结构简单的片段）在预测时傾向于占据已知的正构位点，从而忽视了更具药物开发潜力的变构位点和隐性位点。传统的片段筛选方法也无法克服这一记忆化问题。
-   **整体意义**：本文提出的CAFE方法通过一种**无需额外训练**的推理策略，成功绕过了共折叠模型的正构位点偏见，将其转化为高效探索变构和隐性位点的强大工具，为AI驱动的变构药物发现提供了一种新颖、有效的范式。

#### 2. 论文提出的方法论
-   **核心思想**：借鉴实验晶体学中“浸泡”技术的思想，在共折叠过程的输入中，人为地引入一个**竞争性正构阻断剂**。该阻断剂会物理性地占据并封锁正构位点空间，迫使作为探针的片段在联合扩散过程中不得不去探索蛋白表面的其他非正构区域（变构位点或隐性位点）。
-   **关键技术细节**：
    1.  **共折叠模型**：使用**Boltz-2**作为推理引擎。
    2.  **阻断剂选择**：对激酶家族，选择**三磷酸腺苷（ADP）** 作为通用阻断剂（优于三磷酸腺苷（ATP）），因其在蛋白数据库（PDB）中更常见，构象收敛性更好。同样可使用I型小分子抑制剂。对于其他蛋白，则使用已知正构配体（如对蛋白酪氨酸磷酸酶1B（PTP1B）使用DADEpYL六肽，对KRAS使用GDP）。
    3.  **片段库构建**：使用BRICS算法对已知配体（正构/变构）进行分解，生成化学结构多样的片段。同时，也使用了商用的Enamine高保真片段库进行前瞻性筛查。
    4.  **流程**：将目标蛋白序列、片段SMILES和阻断剂（作为额外实体）一同输入Boltz-2进行共折叠。通过计算片段质心与正构、变构参考配体质心的距离，来判定片段是否成功定位到非正构位点。最后，对预测的构象进行结合自由能计算以评估其热力学可行性。
-   **公式与算法**：论文主要使用**ABFE**评估与比较，公式为：`ΔG_bind = -ΔG_complex + ΔG_solvent + ΔG_res + ΔG_Boresch`。相关计算未在正文详述，但基于标准双退耦方法。

#### 3. 实验设计
-   **数据集与场景**：
    -   **激酶家族**：选择5种不同PDB覆盖度的激酶：AKT2, CDK2, CHEK1, CSNK2A1, MAPK14。针对每个激酶，从已知的变构抑制剂共晶结构出发，通过BRICS分解得到116个变构源性片段和对应的正构配体片段。
    -   **非激酶靶点**：选择蛋白酪氨酸磷酸酶1B（PTP1B）和小GTP酶KRAS，以验证方法的泛化能力。
    -   **商业片段库**：使用300个Enamine高保真片段库片段进行前瞻性虚拟筛选。
-   **基准与评估指标**：
    -   **非正构探索率**：片段质心距离正构参考配体>5.0Å的预测样本比例，作为主要评估指标。
    -   **变构定位率**：片段质心距离变构参考配体<5.0Å的预测样本比例。
    -   **构象质量**：与晶体学参考配体坐标的重原子均方根偏差RMSD。
    -   **热力学有效性**：通过ABFE计算预测构象的结合自由能（ΔG_bind），并与晶体结构和正构位点构象进行比较。使用pTM和ipTM等模型置信度分数进行评估。
-   **对比方法**：主要对比了**无阻断剂的共折叠**作为基线。同时，也与两种传统静态口袋预测工具**P2Rank**和**FPocket**进行比较，以评估CAFE发现新口袋的能力。

#### 4. 资源与算力
-   论文未明确给出所使用GPU的具体型号、数量及训练时长等详细算力信息。
-   但文中提到，ABFE计算在一张GPU上运行，经典分子动力学（MD）模拟的生产阶段（production）为：复合物和溶剂腿各5.0纳秒，约束腿2.5纳秒。
-   由于CAFE是一种基于已有模型的推理策略，无需重新训练模型，因此主要的算力消耗来源于**大规模采样**以及后续的**ABFE计算**。

#### 5. 实验数量与充分性
-   **实验数量**：非常丰富，覆盖了多种场景：
    -   主实验：在5种激酶和2种非激酶上，评估了超过200个片段在不同阻断条件下的表现。
    -   力学能验证：对30个激酶-片段复合物进行了ABFE计算。
    -   隐蔽口袋分析：系统识别了14个非正构/非变作簇，并结合其他方法进行了比较。
    -   商业库筛选：对300个商业片段进行了前瞻性筛选，并对其中33个有利命中进行了深入验证（合成了ABFE在抑制剂下的稳定构象和切换回抑制剂的分析）。
-   **充分性与公平性**：实验设计较为全面、客观。
    -   考虑了PDB覆盖度不同的激酶，以验证方法的通用性。
    -   对比了有无阻断剂、不同类型阻断剂（ADP vs. I型抑制剂）。
    -   不仅评估了定位率，还通过ABFE验证了热力学可行性，并对比了变构位点与正构位点的结合能力。
    -   发现并讨论了模型置信度分数（ipTM）无法区分正构与变构位点这一关键局限性。
    -   不足之处：对照组中，对其他非激酶靶点（PTP1B，KRAS）的ABFE分析不够深入，主要依赖定位率分析。对隐蔽口袋的验证也仅到ABFE程度，缺乏实验验证。

#### 6. 论文的主要结论与发现
-   **CAFE有效克服共折叠模型的偏见**：引入ADP等正构阻断剂，可以将片段从正构位点显著重定向到非正构位点。在5个激酶中，平均非正构探索率从12%提高到85%以上。该方法对非激酶靶点同样有效。
-   **CAFE定位的变构构象具有高保真度和热力学可行性**：ABFE计算表明，CAFE生成的变构位点构象的结合自由能与晶体学参考结构相当或更优（21/30个复合物），证明无需事后结构优化。
-   **CAFE能够发现新的隐蔽口袋**：CAFE识别出了传统几何方法（P2Rank, FPocket）遗漏的隐性囊袋，这些囊袋对片段的结合可能在热力学上比正构或变构位点更有利。通过引入双阻断剂（正构+变构）可进一步提高隐蔽位点的发现率。
-   **CAFE具备前瞻性筛选能力**：在Enamine商业库的虚拟筛选中，CAFE成功识别出了31%的优先命中片段，且这些片段的变构/隐性位点结合能力是依赖于阻断剂存在的。

#### 7. 优点
-   **无需训练**：直接利用现有共折叠模型，无需额外的微调或训练，降低了应用门槛。
-   **机理清晰**：物理阻断策略直接、高效，从根源上解决了模型偏见问题。
-   **通用性强**：对激酶和非激酶靶点均有效，且对不同化学性质的片段和不同种类的阻断剂均有良好表现。
-   **多功能性**：不仅能发现已知变构位点，还能系统性地发现新的隐蔽口袋，兼具虚拟筛选能力。
-   **评估严谨**：结合了定位率、构象RMSD和热力学自由能（ABFE）等多维度评估，结论可靠。
-   **实践指导性强**：指出了模型置信度分数（ipTM）在变构位点识别中的局限性，并提供了可行的替代方案（中心质心几何距离评估）。

#### 8. 不足与局限
-   **完全依赖模型**：CAFE的最终表现高度依赖于所用共折叠模型（Boltz-2）本身的质量和泛化能力。对于PDB覆盖率极低或结构过于动态的靶点，CAFE可能表现不佳。
-   **缺乏实验验证**：尽管进行了严谨的ABFE计算，但所有发现的变构位点和隐性位点（尤其是新发现的）均未在体外或体内进行实验验证，其真正的成药性仍是未知数。
-   **阻断剂选择局限**：针对新靶点，必须已知其正构位点的强效配体才能作为阻断剂，这限制了其在完全未知靶点上的应用。虽然ADP对激酶是通用方案，但对非激酶不具普适性。
-   **计算成本**：虽然推理本身无需训练，但为了获得统计上可靠的结果，需要进行大规模采样（每个片段10次），且后续对成百上千个预测构象进行ABFE评估的计算开销仍然巨大。
-   **泛化范围需进一步探究**：虽然在少数非激酶靶点上进行了验证，但其性能可能对不同家族、不同结构类型的蛋白存在波动，需要更广泛的基准测试。
-   **与模型自身评估指标的冲突**：模型自身的置信度分数倾向于正构而改变，用户依赖默认指标会筛选出错误构象，这构成一个实务上的风险点，需要用户额外设置。

（完）
