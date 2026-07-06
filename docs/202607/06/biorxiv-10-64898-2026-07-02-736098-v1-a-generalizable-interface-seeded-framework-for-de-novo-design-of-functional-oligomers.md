---
title: A generalizable interface-seeded framework for de novo design of functional oligomers
title_zh: 一个通用的界面种子框架用于从头设计功能寡聚体
authors: "Chim, H. Y., Idris, M. O., Rieger, D., Schlegel, P., Goldbach, N. M., Juanatey, M. A., Mallik, B. B., Buckley, S., Basak, S., Georgeon, S., Lau, K., Pojer, F., Kaysser, L., Tinnefeld, P., Schoeder, C. T., Correia, B. E., Khmelinskaia, A."
date: 2026-07-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.02.736098v1.full.pdf"
tags: ["query:diff-gen"]
score: 8.0
evidence: 基于AI的生成方法用于从头设计功能性寡聚体，采用深度学习进行分子生成
tldr: 蛋白质寡聚体在生物系统中普遍且功能关键，但从头设计可控组装响应外源刺激的寡聚体仍具挑战。本文提出基于AI的界面种子生成方法，从分离相互作用模块设计响应性同源寡聚体。实验验证设计高度准确并探索新拓扑，可对化学触发物条件性寡聚化或磷酸化驱动可逆构象变化。进一步功能化实现配体依赖膜结合和磷酸化控制基因调控，为复杂调控生物合成系统提供通用设计框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法无法高效设计可响应外源刺激可控组装的蛋白质寡聚体，限制生物系统调控工程。
method: 采用AI生成方法结合界面种子策略，从分离模块设计响应性同源寡聚体。
result: 实验验证设计高度准确，获得新拓扑；实现化学触发条件寡聚和磷酸化驱动可逆构象变化。
conclusion: 该框架通用设计响应性蛋白复合物，为生物合成系统复杂调控机制工程开辟新可能。
---

## 摘要
蛋白质寡聚体在生物系统中普遍存在且对功能至关重要。然而，从头设计能够响应外源刺激并可控组装的寡聚体仍然具有挑战性。在这里，我们提出了一种基于AI的生成方法，利用界面种子策略从分离的相互作用模块设计响应性同源寡聚体。经实验验证的设计高度准确，并探索了自然界中不存在的新拓扑结构。我们展示了设计能够通过条件性寡聚化有效响应其化学触发物，或通过可逆寡聚化响应磷酸化驱动的构象变化。我们进一步功能化了我们的响应性组装体，构建了配体依赖的膜结合系统和磷酸化控制的基因调控开关。我们的框架能够实现响应性蛋白质复合物的通用设计，为工程化具有复杂调控机制的生物合成系统开辟了新的可能性。

## Abstract
Protein oligomers are ubiquitous in biological systems and essential for function. However, the de novo design of oligomers that controllably assemble in response to exogenous stimuli remains challenging. Here, we present an AI-based generative approach that leverages an interface-seeded strategy for designing responsive homo-oligomers from isolated interaction modules. Experimentally validated designs are highly accurate and explore new-to-nature topologies. We show that designs effectively respond to their chemical triggers with conditional oligomerization or to phosphorylation-driven conformational changes with reversible oligomerization. We further functionalized our responsive assemblies to build ligand-dependent membrane binding systems and phosphorylation-controlled gene regulatory switches. Our framework enables the generalizable design of responsive protein complexes, opening novel possibilities for the engineering of biosynthetic systems with sophisticated regulatory mechanisms.

---

## 论文详细总结（自动生成）

# 中文论文总结

## 一、论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：蛋白质寡聚体广泛存在于天然生物系统中并执行关键功能，但现有的从头设计方法难以生成能够响应外源刺激（如金属离子、小分子、磷酸化）而可控组装的功能性寡聚体。过去的设计多聚焦于静态、非条件性组装，而自然界中蛋白质却能够动态响应环境信号并改变寡聚状态以调控细胞过程。
- **整体含义**：本文旨在建立一个通用、模块化的接口种子框架，利用已验证的蛋白质-蛋白质相互作用（PPI）作为“种子”，通过AI生成方法将其嵌入到满足目标对称性（C3、C4、C5）的新型蛋白支架中，从而构建响应性同源寡聚体。该框架的成功将进一步推动蛋白质工程在合成生物学、生物传感、智能纳米材料等领域的应用，使蛋白设计向“即插即用”的模块化方向迈进。

## 二、方法论：核心思想、关键技术细节、流程

### 核心思想
- **接口种子策略**：从已验证的、可响应特定刺激的PPI中提取相互作用模块（interface seed），将其对称化后作为设计约束，再利用深度学习模型生成与目标对称性兼容的全新蛋白骨架，从而复用已有PPI构建可控寡聚体。

### 关键技术细节
1. **对称性条件化骨架生成**：
   - 在RFdiffusion中新增对称性基序支架模块，可将interface seed随机旋转（旋转自由度）并放置在指定径向距离范围内，然后启动扩散轨迹。
   - 扩散过程中，motif的径向位置由去噪残基的质心引导，以促进紧密堆积的骨架生成。
2. **序列设计**：
   - 使用SolubleMPNN进行序列设计，同时保留interface seed中的关键残基。
3. **计算验证**：
   - 使用AlphaFold2（单体及复合物）和AlphaFold3（复合物）预测结构，根据ipTM、pLDDT等指标筛选高置信度设计。
4. **负向筛选**：
   - 针对可能形成错误对称性的设计（如C4设计形成C5），比较同一设计在目标对称性与替代对称性下的AF3预测置信度，保留只有目标结构高置信的设计。

### 算法流程（文字描述）
1. 提取已验证的、响应性PPI的相互作用界面（interface seed），确定其关键残基。
2. 将该种子按照目标对称性（例如C3）进行多重复制与对称排列。
3. 随机旋转种子（采样旋转自由度）并置于初始径向距离范围内。
4. 利用RFdiffusion进行去噪生成，期间通过质心引导调整径向位置，产出大量候选骨架。
5. 对生成的骨架进行结构聚类，去除冗余；计算界面质量指标（rpx score, 埋藏溶剂可及表面积）。
6. 使用SolubleMPNN设计序列，同时固定种子残基。
7. 用AlphaFold2/AF3对设计进行结构预测与反向验证，筛选pLDDT、ipTM等指标优异的设计。
8. 对于响应性设计，额外比较有/无刺激条件下的AF3预测，确保组装仅在刺激存在时高置信。
9. 对入选设计进行实验表达、纯化、SEC、SEC-MALS、结晶或冷冻电镜结构测定。

## 三、实验设计：数据集/场景、基准、对比方法

### 数据集与场景
- **场景1：无条件的必需寡聚体设计**
  - 使用LHD101和LHD29两个从头设计的异源二聚体作为非响应性PPI种子，设计C3、C4、C5对称的寡聚体。
- **场景2：金属离子（Cu²⁺）响应性寡聚体**
  - 种子来源于工程化细胞色素中的Cu²⁺依赖性同源二聚体PPI。
- **场景3：小分子（胆酸CHD、Venetoclax LBM、黄体酮P4）响应性寡聚体**
  - 种子分别来源于CHD依赖性异源二聚体、LBM响应的BCL2-迷你结合子界面、P4响应的抗体-迷你结合子界面。
- **场景4：可逆磷酸化响应性寡聚体**
  - 种子来源于一个从头设计的磷酸化开关，该开关通过磷酸化暴露隐蔽结合位点，进而与结合肽形成PPI。
- **功能性应用验证（细胞实验）**：
  - 膜结合：将Cu²⁺或CHD响应性寡聚体融合到MTS和GFP，观察在支持脂双层上的定位变化。
  - 转录调控：将磷酸化响应性三聚体PO18s融合到HSF1的DBD和VP64反式激活域，在HEK293T细胞中测定HSE驱动的分泌型NanoLuc活性。

### 基准（Benchmark）
- 非正式基准：与经典dock-and-design方法的对比（文中图S1显示dock方法在多样性及成功率上的局限）。
- 结构比对：使用FoldSeek搜索PDB，TM-score≤0.56（obligate设计）或更低（响应性设计），表明设计在结构上具有新颖性。
- 晶体结构与设计模型比对：RMSD Cα<2.4Å。
- SEC-MALS分子量与理论值对比：误差较小。

### 对比方法
- **dock-and-design方法**（Sheffler et al. 2023）：在固定蛋白骨架基础上对接形成对称寡聚体，但作者发现该方法生成的对称类型单一且成功率低。
- 本研究的**接口种子方法**在不同对称性、不同响应机制下均获得成功，展示了更好的通用性。

## 四、资源与算力

- **论文未明确说明**所使用的GPU型号、数量及训练时长。
- 文中仅提到计算资源来自Leibniz超级计算中心的Linux集群和AI系统，并感谢相关支持。
- 涉及的深度学习模型（RFdiffusion、AlphaFold2/3）均为已有框架，作者可能使用了较少的训练/推理卡时，但在高通量生成骨架和序列设计阶段需要一定的GPU资源。

## 五、实验数量与充分性

### 实验数量
- **无条件设计**：27个C3、21个C4、12个C5设计进入实验。63/64成功表达，18/63分子量完全匹配设计，4个组装体获得晶体结构。
- **金属响应**：16个Cu²⁺设计，4/16显示金属依赖组装。
- **小分子响应**：16个CHD设计 → 3/5活性设计；14个LBM设计 → 1个经第二轮优化后成功（LBM10）；7个P4设计 → 均未观察到响应。
- **磷酸化响应**：19个C3+8个C4设计，20个可溶，12/20表现混合状态；通过SSM优化后获得PO5s和PO18s，实现可逆磷酸化响应。
- **结构测定**：共获得多个寡聚体的晶体结构（LHD类C3/C4、MC11、CHD04、LBM10、PO5），以及CHD04的冷冻电镜结构。
- **功能实验**：膜结合实验（两种响应系统）和转录激活实验（多种PO18s变体、对照、不同刺激条件）。

### 充分性与客观性判断
- **充分性**：实验覆盖了从非响应到金属、多种小分子、可逆磷酸化等多种响应机制，并延伸至下游功能，设计规模与结构验证较为丰富。
- **客观性**：实验设计包括了多种对照（如无刺激对照、突变对照、已知阳性对照等）；失败案例也有明确描述（如P4无响应、LBM需多轮优化）。
- **公平性**：与dock方法进行了对比（虽然篇幅有限）；使用了统一的实验流程（表达、SEC、MALS）。但未与其他同类AI方法（如其他基于生成模型的寡聚体设计）进行详细比较，这或许是本文的一个局限。

## 六、论文的主要结论与发现

1. **接口种子策略成功实现了从单一PPI种子生成多样化的、具有新型拓扑结构的寡聚体**：不同对称性（C3、C4、C5）均获得实验验证，晶体结构高度吻合设计模型。
2. **该方法可扩展至非连续、响应性PPI种子**：实现了Cu²⁺、胆酸、Venetoclax刺激下的条件性寡聚化。
3. **首次实现了从头设计的可逆磷酸化依赖性寡聚体**：通过单点突变（L→A）降低本底结合后，成功构建了由激酶/磷酸酶控制的开关，并可引入氧化还原双输入控制。
4. **设计的响应性组装体可在细胞环境下执行功能**：膜结合实验展示了刺激依赖的膜定位；转录激活实验表明磷酸化响应三聚体可被细胞内PKA激活，实现基因表达调控。
5. **设计几何偏好分析**：成功的环状寡聚体倾向于界面“扭转”适中，与天然蛋白中观察到的几何偏向性类似，可为未来设计提供指导。

## 七、优点：方法或实验设计上的亮点

- **通用性与模块化**：仅需一个已验证的PPI种子，即可生成多种对称性、多种响应机制的寡聚体，降低了从头设计响应性组装体的门槛。
- **结合最新AI工具**：利用RFdiffusion进行骨架生成、SolubleMPNN设计序列、AlphaFold系列进行反向验证，形成高效的计算-实验闭环。
- **双输入控制**：在磷酸化响应设计中引入二硫键锁，实现“磷酸化+还原”两输入控制，是去新设计中的突破。
- **结构验证充分**：对多个设计进行了晶体结构和冷冻电镜解析，直接证实设计准确性。
- **功能应用展示**：将设计扩展至膜定位和基因转录，展示了实际生物学应用潜力，增加了论文的实用价值。
- **开源与数据共享**：所有设计模型、脚本和数据已在GitHub及PDB/EMDB公开，便于后续使用和复现。

## 八、不足与局限

- **成功率仍有提升空间**：即使经过多轮优化，部分响应系统（如黄体酮、LBM初始轮次）几乎无成功设计，说明对拓扑采样的约束仍不够灵活。
- **依赖种子完整性**：本方法要求PPI种子的结构已知且可拆解，对于高度动态或结构未解析的PPI难以应用。
- **规模化局限**：目前生成的骨架尺寸较小（多小于200残基），对于更大对称寡聚体的生成能力有限（文中也承认“current design protocol relies on the ability of generative models in producing large designable backbones”）。
- **可重复性与固有问题**：某些设计在结晶条件下出现非预期对称性（如PI56），说明预测模型可能高估目标状态的热力学优势；状态之间的能量差可能过小，导致结晶/溶液中出现多构象。
- **未与最新的端到端生成方法对比**：如直接使用RFdiffusion或ProteinMPNN从头生成整个寡聚体，或使用其他基于扩散的复合物设计方法，文中仅与dock方法对比，缺乏同类方法的横向比较。
- **算力资源未透明报告**：无法评估方法的计算成本。

（完）
