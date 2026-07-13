---
title: Generative Drug Design in a Loop with dtSFM
title_zh: 基于dtSFM的循环生成式药物设计
authors: "Reddy, S. T."
date: 2026-07-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.731501v1.full.pdf"
tags: ["query:pocket-lig"]
score: 8.0
evidence: 基于靶标特异性基础模型的小分子药物生成
tldr: 小分子药物设计多依赖高通量筛选和化学直觉，缺乏定向进化机制。本文提出GenLoop闭环生成设计框架，基于药物-靶点特异性基础模型dtSFM生成分子，经AlphaFold3结构验证和化学信息学过滤后迭代选择优化。在12个靶点中，5个靶点的设计达到已批准药物的结构置信度（界面iPTM 0.93-0.98，PAE 0.8-2.0 Å），并成功应用于囊性纤维化跨膜传导调节因子和GLP-1受体家族的先导设计。该方法将定向进化引入小分子领域，为计算驱动药物发现开辟新路径。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1566, \"height\": 1142, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1523, \"height\": 1154, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1617, \"height\": 2432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1609, \"height\": 1254, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 344, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 343, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 339, \"height\": 339, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 427, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 433, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 338, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 339, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 338, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 343, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 337, \"height\": 338, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 339, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1604, \"height\": 1161, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1642, \"height\": 2464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1594, \"height\": 706, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 846, \"height\": 641, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1582, \"height\": 680, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1596, \"height\": 1004, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1622, \"height\": 902, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1598, \"height\": 803, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1593, \"height\": 685, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1653, \"height\": 1091, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1656, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1651, \"height\": 1711, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1652, \"height\": 461, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1672, \"height\": 481, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1640, \"height\": 736, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1635, \"height\": 2460, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1641, \"height\": 1549, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1672, \"height\": 445, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-10-731501-v1/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1716, \"height\": 671, \"label\": \"Table\"}]"
motivation: 将蛋白质工程的定向进化范式引入小分子药物设计，通过闭环迭代优化提升先导化合物的质量与新颖性。
method: 利用dtSFM生成目标条件分子，根据热力学兼容性评分重排，使用AlphaFold3进行结构验证，结合化学信息学过滤与迭代进化选择。
result: 在12个靶点中，5个靶点设计达到批准药置信度；针对CFTR和GLP-1受体家族设计出结构新颖的先导候选物，其中GLP-1设计获得23个中心口袋候选物，中位iPTM 0.89、PAE 1.95 Å。
conclusion: GenLoop通过计算热力学选择将定向进化应用于小分子设计，为后续湿实验验证奠定了基础。
---

## 摘要
由迭代的多样化、选择和反选择轮次组成的定向进化是现代蛋白质和抗体工程的基础，然而小分子药物设计仍然主要通过高通量筛选和药物化学直觉来推进。Transformer的softmax注意力在数学上等同于控制热平衡下分子结合的玻尔兹曼分布，这种同构性规定了一种序列原生的特异性基础模型（SFM）。该框架最近被应用于七个分子识别领域，并扩展为药物-靶标SFM（dtSFM），这是第一个将全尺寸编码器与生成式解码器配对的模型。此类模型能否在迭代和选择条件下被驱动以优化先导化合物，而不是仅采样一次，尚未得到证明。本文提出GenLoop，一种封闭的生成式药物设计循环，将单次生成转化为化学的定向进化。dtSFM生成靶标条件分子，并根据其热力学相容性分数对其重新排序。使用了正交的结构验证器AlphaFold 3，它与dtSFM没有共享架构或训练数据。化学信息学过滤器确保可开发性，并在结构验证的候选分子上进行生成式进化，选择预测的结合子并反选择针对脱靶化学。应用于跨越不同药理机制类别的十二个药物靶标，GenLoop产生了AlphaFold 3验证的设计，其中五个靶标达到了已批准药物的结构置信度，最佳设计的界面iPTM为0.93-0.98，PAE为0.8-2.0 Å，并且在九个靶标中解析了旁系同源选择性。随后进行了两项完整的疾病活动。对于囊性纤维化跨膜传导调节因子，GenLoop设计了九个经过可开发性过滤且结构新颖的先导候选分子（iPTM高达0.93，界面PAE为2.3 Å），靶向已批准药物Trikafta的所有三个正交位点。对于GLP-1受体家族，dtSFM设计了可调节的单、双和三重受体肠促胰岛素设计，产生了23个中心口袋候选分子，这些分子在结构上新颖，中位iPTM为0.89，界面PAE为1.95 Å。带有dtSFM的GenLoop通过计算热力学选择将定向进化引入小分子；湿实验室验证是直接的下一步。

## Abstract
Directed evolution consisting of iterative rounds of diversification, selection, and counter-selection, underlies modern protein and antibody engineering, yet small-molecule drug design still advances largely through high-throughput screening and medicinal-chemistry intuition. Transformer softmax attention is mathematically identical to the Boltzmann distribution that governs molecular binding at thermal equilibrium1, an isomorphism that prescribes a sequence-native Specificity Foundation Model (SFM)2. This framework was recently applied across seven molecular recognition domains3,4 and scaled into the drug-target SFM (dtSFM), the first to pair a full-scale encoder with a generative decoder5. Whether such a model can be driven, iteratively and under selection, to optimize leads rather than sample them once has not been shown. Here we present GenLoop, a closed generative drug design loop that turns single-pass generation into directed evolution of chemistry. dtSFM generates target-conditioned molecules and reranks them by their thermodynamic compatibility score. An orthogonal structural verifier, AlphaFold 3, is used that shares no architecture or training data with dtSFM. Cheminformatics filters enforce developability, and generative evolution is performed on the structurally verified candidates, selecting for predicted binders and counter-selecting against off-target chemistry. Applied across twelve drug targets spanning pharmacologically distinct mechanism classes, GenLoop produced AlphaFold 3-verified designs that reached the structural confidence of the approved drug for five of the twelve targets, with the best designs at interface iPTM 0.93-0.98 and PAE 0.8-2.0 [A], as well as resolving paralog selectivity across nine targets. Two full disease campaigns followed. For the cystic-fibrosis transmembrane conductance regulator, GenLoop designed nine developability-filtered and structurally novel lead candidates (iPTM up to 0.93, interface PAE 2.3 [A]) targeting all three orthogonal sites of the approved drug Trikafta. For the GLP-1 receptor family, dtSFM engineered tunable single-, dual-, and triple-receptor incretin designs, yielding 23 central-pocket candidates that are structurally novel at median iPTM 0.89 and interface PAE 1.95 [A]. GenLoop with dtSFM brings directed evolution to small molecules through computational-thermodynamic selection; wet-lab validation is the immediate next step.

---

## 论文详细总结（自动生成）

好的，以下是对论文《Generative Drug Design in a Loop with dtSFM》的详细中文总结。

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：当前小分子药物设计主要依赖于高通量筛选和药物化学家的经验直觉，这与蛋白质工程领域成熟的“定向进化”（迭代突变、选择和优化）范式形成对比。尽管近年来人工智能（如生成式模型和结构预测模型）取得了巨大进步，但如何将**定向进化的迭代优化思想**引入小分子生成设计中，以产生更高质量、更具选择性和可开发性的候选药物，仍是一个开放性问题。
- **研究动机**：本文建立在Transformer的softmax注意力机制与分子结合的热力学玻尔兹曼分布在数学上具有同构性的理论基础之上。据此开发的药物-靶标特异性基础模型（dtSFM）能够生成目标条件的分子。然而，单次生成（single-pass generation）存在局限：不同靶点的生成质量不一，且无法解决多靶点选择性、多口袋位点深度以及多药理学精细调控等复杂需求。
- **核心贡献**：本文提出**GenLoop**——一个封闭的迭代式药物设计循环。其核心思想是将**计算热力学选择**作为驱动力，使小分子设计过程模拟蛋白质的定向进化，从而将单次生成转化为一个多参数优化的迭代进化流程。

### 2. 论文提出的方法论

- **核心思想**：受蛋白质定向进化（生成库 -> 功能筛选 -> 反选择 -> 优化）的启发，GenLoop构建了一个由四个步骤组成的闭环系统，将生成式AI与结构验证和药物化学规则相结合。dtSFM执行“计算热力学”，其输出的分子因其与靶标的热力学相容性而具有高概率，而非简单的模式补全。
- **关键技术细节（GenLoop四步循环）**：
    1.  **生成 (Generate)**：使用dtSFM的条件化学解码器（27M参数），以目标蛋白质序列为条件，生成SMILES字符串形式的候选分子（默认温度为0.8）。
    2.  **重排 (Rerank)**：使用dtSFM编码器的“药物-靶标余弦相似度”分数对候选分子进行重新排序，筛选出与目标相关性强的前20%进行结构验证。
    3.  **验证 (Verify)**：使用与dtSFM**完全正交**的结构验证器**AlphaFold 3 (AF3)** 进行蛋白质-配体共折叠。输出界面预测TM分数（iPTM）和界面预测对齐误差（PAE）。并基于诱饵校准（decoy-calibrated）的阈值分类为“强 (STRONG)”、“中 (MODERATE)”和“弱 (WEAK)”三个置信度等级。
    4.  **进化优化 (Refine)**：对通过AF3验证的候选分子执行生成式进化优化，包括两种模式：
        - **生物等排诱变库**：从一个经过验证的母体支架出发，应用约80个药物化学的等排体替换规则（SMARTS），创建单点或组合的化学类似物库，类似于蛋白质工程中的深度诱变扫描或组合诱变。
        - **LoRA微调**：使用低秩适应（LoRA）技术对dtSFM解码器进行微调（仅增加0.68M可训练参数，占总参数的2.5%），结合“非似然损失”（unlikelihood loss），使解码器偏向于生成能成功装填到特定目标口袋的正样本，远离脱靶口袋或旁系同源蛋白的负样本。这是实现位点特异性和选择性的关键。
- **可开发性过滤**：在每个迭代轮次后，候选分子需通过一系列化学信息学过滤器，包括：Brenk报警过滤（去除反应性基团）、PAINS过滤、Lipinski五规则（Ro5）、定量类药性评估（QED）、可合成性评分（SA评分）、骨架新颖性（Bemis-Murcko）和结构新颖性（ECFP4 Tanimoto距离）。

### 3. 实验设计

- **数据集与场景**：实验涵盖了三个主要场景，旨在全面评估GenLoop的能力：
    1.  **广度筛选 (Breadth Screen)**：跨越12个药理学机制不同的药物靶标，包括激酶（ALK, BTK, JAK3, TYK2）、核受体（THRB）、补体蛋白酶（CFB）、蛋白-蛋白相互作用（MEN1）、磷酸酶（SHP2）、炎症小体（NLRP3）和B类GPCR（GCGR, GIPR, GLP1R）。
    2.  **深度设计 (Depth Campaign)**：针对**囊性纤维化跨膜传导调节因子（CFTR）**，模拟Trikafta三联疗法，设计靶向三个不同作用位点的先导化合物。
    3.  **多药理学设计 (Polypharmacology Campaign)**：针对**GLP-1受体家族**（GLP1R, GIPR, GCGR），设计具有可控单受体、双受体和三受体活性的分子。
- **基准 (Benchmark)**：论文主要以临床或处于研究阶段的药物分子（如lorlatinib, tirabrutinib, resmetirom, revumenib, Trikafta组分, danuglipron, orforglipron等）作为锚定点，对比GenLoop设计的分子在AF3结构置信度（iPTM, PAE）和化学新颖性（Tanimoto距离）上的表现。
- **对比方法**：未与当前的生成式模型（如DiffSBDD, Pocket2Mol, TargetDiff）进行直接对比。其核心对比是**单次生成**（dtSFM自身）与**闭环迭代生成**（GenLoop）的效果，并依赖AF3作为独立的结构评估标准。此外，使用了Boltz-2作为另一个独立的结构预测模型进行交叉验证。

### 4. 资源与算力

- **计算资源**：文章明确提到了计算基础设施：
    - **本地与HPC**：解码器采样、编码器重排等任务在ETH Zurich的Euler HPC集群上运行，使用单块NVIDIA A100 (40GB) GPU。
    - **大规模AF3共折叠**：超过15,000次AF3共折叠在瑞士国家超算中心（CSCS）的**ALPS超级计算机**上运行，该超算采用NVIDIA Grace Hopper Superchip（GH200）模块（H100 GPU + Grace ARM CPU）。
    - **LoRA微调**：计算轻量，可在消费级GPU（如NVIDIA TITAN RTX）上完成，仅需数分钟。

### 5. 实验数量与充分性

- **实验数量**：整个研究论文实验规模宏大，包含：
    - 12个靶标的广度筛选（产生了超过6万个候选分子和238次AF3验证）。
    - 9个靶标的旁系同源选择性分析（涉及41个旁系同源蛋白，205次共折叠）。
    - CFTR深度研究中对三个口袋进行设计的迭代优化，最终聚焦于9个先导化合物。
    - GLP-1R多药理学研究中基于6受体面板的选择性筛选和LoRA微调，最终产生19个设计分子。
    - 使用Boltz-2进行的正交结构验证和编码审计（Codex）。
- **充分性与公平性**：
    - **充分性**：实验设计非常全面，从“广度”到“深度”再到“选择性”，系统地证明了GenLoop在不同场景下的能力。实验采用了严谨的**诱饵校准（decoy calibration）** 来确定AF3的严格置信度阈值（STRONG gate），确保过滤掉假阳性。
    - **公平性**：**正交验证**是本文的一大亮点。dtSFM和AF3是两个*完全独立*的模型，没有共享架构或训练数据。这种双重验证极大地增强了结果的可靠性。编码审计（coding audit）也保证了结果的可重复性。
    - 潜在的偏差：AF3本身在预测某些靶标（如GLP-1R）上的小分子结合时，置信度较低（即使是临床药物），这可能导致GenLoop的设计虽然被AF3标注为WEAK，但实际可能有效。作者也明确指出了这一点。

### 6. 论文的主要结论与发现

1.  **GenLoop成功将定向进化引入小分子设计**：通过迭代生成、重排、验证和优化，单次生成无法解决的问题（如低产率靶标、多口袋、选择性）都可以通过迭代闭环解决。
2.  **在12个靶标广度筛选中的表现**：
    - 12个靶标中，有5个（BTK, THRB, CFB, MEN1, ALK）的设计达到了“STRONG”级别的结构置信度（iPTM 0.93-0.98, PAE 0.8-2.0 Å），与临床药物的置信度相当。
    - 3个目标（TYK2, NLRP3, GLP1R）的单次通过率为0%，但后续通过迭代进化（如GLP-1R深度研究）可以恢复。
3.  **成功实现旁系同源选择性**：在9个有相关旁系同源蛋白的靶标上，GenLoop设计的分子的选择性轮廓与临床药物一致，在某些靶标上甚至更优。
4.  **解决多口袋深度问题（CFTR）**：GenLoop能够成功设计出靶向Trikafta所有三个正交作用位点的结构新颖先导化合物。通过LoRA微调，成功将“深口袋”（位点C）的占据率从7.5%提升至36%。
5.  **实现可调多药理学（GLP-1R家族）**：通过选择性感知的迭代进化和位点导向的LoRA微调，GenLoop设计出的分子能够实现单（GLP1R）、双（GLP1R+GCGR）和三（GLP1R+GIPR+GCGR）受体激动活性的可控调节，且所有设计分子的中位iPTM=0.89，PAE=1.95 Å，表明其结构模型高度可信。

### 7. 优点

- **创新性高的方法论**：首次将“定向进化”的迭代思想以纯计算的形式应用于小分子设计，建立了“生成-选择-优化”的闭环，与蛋白质工程的实验范式高度契合。
- **坚实的理论基础**：基于Transformer注意力与玻尔兹曼分布的数学同构性，为模型的行为提供了热力学层面的解释（“计算热力学”），而非仅凭经验。
- **严谨的正交验证体系**：dtSFM负责“计算”结合打分，AF3负责“结构”验证。两者相互独立，交叉确认，极大增强了预测结果的可靠性。同时，还采用了Boltz-2和编码审计进行双重、三重保证。
- **实验设计全面且有深度**：广度（12靶标）、深度（多口袋CFTR）、选择性（旁系同源/多药理学GLP-1R）三位一体的实验设计，系统性地展现了方法论的强大和通用性。
- **开放性与可重复性**：所有代码、模型权重、数据、图表和审计记录均已开源发布，并提供了一个“Vibe Coding”启动提示，让实验生物学家无需编程经验也可尝试运行，极大地降低了使用门槛。

### 8. 不足与局限

- **完全基于计算预测，缺乏湿实验验证**：这是论文作者自己明确指出的最大局限。所有结果均基于AF3结构预测。虽然验证模型之间相互独立，但仍存在系统性偏差，最终需要湿实验（如结合亲和力、功能活性测试）来证实。这是“直接的下一步”。
- **AF3自身对某些靶标预测的盲区**：对于GLP-1R这类GPCR，即使是已知的临床药物（如danuglipron），AF3的预测置信度也较低（WEAK）。这可能导致GenLoop设计的一些高质量分子因AF3评分低而被过早淘汰。
- **单次生成产率不均匀**：在广度筛选中，12个靶标中有3个的单次生成为零STRONG，表明基础生成器dtSFM对不同靶标的覆盖存在差异，严重依赖后续的迭代优化来弥补。这暴露了dtSFM本身训练的覆盖不足。
- **未与最新方法直接对比**：论文未与当前主流的结构基生成模型（如DiffSBDD, Pocket2Mol, TargetDiff）进行定量的基准测试。无法直接评估GenLoop在已知任务上相比现有方法的优劣，尽管其“定向进化”的范式是全新的。
- **模型训练数据覆盖限制**：未能成功设计靶向orforglipron变构位点（与danuglipron中心口袋相距35 Å）的设计，作者承认这是dtSFM训练语料库中结构上下文覆盖不足所致。模型的泛化能力受限于其训练数据的多样性。
- **化学空间中存在“模式塌陷”**：在深度研究和多药理学研究中，发现部分设计分子存在特定的人工痕迹。例如，GLP-1R深度研究中的大部分设计（12/19）保留了终端羟肟酸基团，这是一种已知的Brenk结构报警。虽然该基团是手性中心，但在优化阶段仍需进一步改进，这表明GenLoop在突破初始锚定分子的化学空间方面存在局限。

（完）
