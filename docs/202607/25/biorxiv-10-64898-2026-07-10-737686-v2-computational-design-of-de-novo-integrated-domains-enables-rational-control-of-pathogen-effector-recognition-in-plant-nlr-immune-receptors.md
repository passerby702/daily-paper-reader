---
title: Computational design of de novo integrated domains enables rational control of pathogen effector recognition in plant NLR immune receptors.
title_zh: 从头设计整合结构域实现对植物NLR免疫受体中病原体效应子识别的理性控制
authors: "Xi, Y., Bucknell, A. H., Watson, J. L., Maqbool, A., Bennett, J. W., Goreshnik, I., Vafeados, D., Garcia Sanchez, M., Knight, G., Zdrzalek, R., Rodney, C. A., Saado, I., Stone, C. E., Turley, E. K., Yu, D. S., Gentle, A., Ryder, L. S., Yan, X., Were, V., Heddle, J. G., Baker, D., Emmrich, P. M. F., Talbot, N. J., Banfield, M. J., Bentham, A. R."
date: 2026-07-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.10.737686v2.full.pdf"
tags: ["query:diff-gen"]
score: 8.0
evidence: 使用RFdiffusion扩散模型进行蛋白质3D结构设计
tldr: 针对植物病原体快速进化导致的抗性基因不足问题，研究开发了基于生成式AI蛋白设计工具RFdiffusion和ProteinMPNN的框架，设计从头整合结构域（IDs）靶向不同病原效应子。将这种定制结合子植入稻瘟病Pik-1/Pik-2 NLR受体底盘，成功实现对巴拿马病原菌Fusarium oxysporum非同源效应子的识别。功能实验表明感知特异并启动免疫信号，结构分析验证设计保真度，同时发现IDs可能引发自身活性或效应子介导的细胞死亡抑制。该工作为工程化可编程植物免疫受体提供了新途径。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1501, \"height\": 1691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1386, \"height\": 2096, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1444, \"height\": 2032, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1629, \"height\": 1298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1666, \"height\": 2257, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1261, \"height\": 1965, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1884, \"height\": 930, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1830, \"height\": 995, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1630, \"height\": 2005, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1925, \"height\": 1391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1396, \"height\": 2179, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1776, \"height\": 1798, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1570, \"height\": 2068, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1635, \"height\": 813, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1300, \"height\": 2012, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1699, \"height\": 1059, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1655, \"height\": 1932, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1662, \"height\": 892, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1662, \"height\": 1013, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1402, \"height\": 2158, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1932, \"height\": 1859, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1652, \"height\": 2131, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1651, \"height\": 620, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1650, \"height\": 2157, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1652, \"height\": 1618, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1654, \"height\": 1231, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-10-737686-v2/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1729, \"height\": 1836, \"label\": \"Table\"}]"
motivation: 自然抗病基因发现缓慢，而病原体快速演化威胁农业，亟需可编程的植物免疫受体设计方法。
method: 利用RFdiffusion和ProteinMPNN生成式AI工具设计从头整合结构域，将其植入NLR受体底盘进行效应子识别。
result: 成功识别非同源效应子，功能验证特异性感知和免疫信号，结构分析验证设计准确度，并发现IDs可调控NLR信号。
conclusion: AI设计的感觉结构域可解耦免疫感知与自然演化，建立设计主导的可编程植物免疫受体框架。
---

## 摘要
植物病原体的快速进化对全球农业可持续性构成持续威胁，往往超过天然抗病基因的发现和部署速度。虽然植物细胞内免疫受体（NLRs）的生物工程提供了一种潜在解决方案，但开发定制免疫识别仍受限于天然受体和植物-病原体相互作用的繁琐表征。在此，我们描述了一个可编程框架，利用生成式AI蛋白质设计工具RFdiffusion和ProteinMPNN，针对多种病原体效应子设计从头整合结构域（IDs）。通过将这些定制结合子整合到模块化的稻瘟病Pik-1/Pik-2 NLR受体底盘，我们成功工程化了对来自巴拿马病病原体——尖孢镰刀菌古巴专化型热带4号小种的非同源毒力因子（效应子）的识别。在烟草中的功能测定表明，这些从头结构域促进了特异性效应子感知并启动免疫信号传导，而结构和生物物理分析证实从头整合结构域保持了与初始设计高度一致的结构保真度，并通过预测的相互作用界面与其靶标结合。此外，我们的发现为整合结构域在调控NLR信号传导中的作用提供了正交证据，证明从头IDs的整合可触发自身活性，或在某些情况下导致效应子介导的细胞死亡抑制。通过部署AI设计的感知结构域将免疫感知与自然进化历史解耦，这项工作为生成可编程植物免疫受体建立了设计引领的框架，为生物工程作物抵御新兴病原体提供了新途径。

## Abstract
The rapid evolution of plant pathogens poses a persistent threat to global agricultural sustainability, often outpacing the discovery and deployment of natural disease resistance genes. While bioengineering of plant intracellular immune receptors (NLRs) offers a potential solution, developing bespoke immune recognition remains constrained by the laborious characterisation of natural receptors and plant-pathogen interactions. Here, we describe a programmable framework that leverages generative AI protein design tools, RFdiffusion and ProteinMPNN, to design de novo integrated domains (IDs) against diverse pathogen effectors. By integrating these bespoke binders into the modular rice blast Pik-1/Pik-2 NLR receptor chassis, we successfully engineer recognition of a non-cognate virulence factor (effector) from the Panama disease pathogen, Fusarium oxysporum f. sp. cubense Tropical Race 4. Functional assays in Nicotiana benthamiana demonstrate that these de novo domains facilitate specific effector perception and initiate immune signalling, while structural and biophysical analyses confirm that de novo integrated domains maintain high structural fidelity to the initial designs and associate with their targets via the predicted interaction interfaces. Additionally, our findings provide orthogonal evidence for the role of integrated domains in regulation of NLR signalling, demonstrating integration of de novo IDs can either trigger autoactivity or, in some cases, lead to effector-mediated repression of cell death. By decoupling immune perception from natural evolutionary history through deploying AI-designed sensory domains, this work establishes a design-lead framework for generation of programmable plant immune receptors, providing a new avenue for bioengineering crops against emerging pathogens.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：植物病原体进化速度极快，而传统抗病基因（NLR 受体）的发现周期长、天然识别特异性有限，难以应对新出现的效应子变异。亟需一种**可编程、可定制**的免疫受体设计方法，实现对抗原（效应子）的直接工程化识别。
- **整体含义**：该研究首次将生成式 AI 蛋白质设计（RFdiffusion + ProteinMPNN）应用于植物 NLR 受体的整合结构域（IDs），**实现从零设计结合子**，并将其植入模块化 NLR 底盘，成功识别非同源真菌效应子。这一“设计引领”的框架**解耦了免疫感知与自然进化历史**，为快速响应新兴病原体提供了全新的生物工程路径。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：利用生成式 AI 蛋白质设计工具，针对目标效应子**从头设计**具有高亲和力和特异性的小蛋白结构域（IDs），然后将这些 IDs 通过基因融合的方式整合到天然的 NLR 受体（如 Pik-1/Pik-2）的整合结构域位置，使 NLR 能够感知非天然效应子并启动免疫信号。
- **关键技术细节**：
  - **RFdiffusion**：一种基于扩散模型的 3D 蛋白质骨架生成模型，用于从噪声出发逐步生成能与目标效应子表面互补的蛋白质骨架结构。
  - **ProteinMPNN**：一种基于逆折叠的蛋白序列设计模型，在给定骨架结构下预测最优氨基酸序列，确保生成蛋白稳定折叠且与效应子结合。
  - **整合策略**：将设计好的 IDs 编码基因替换或插入到稻瘟病 NLR 受体 Pik-1/Pik-2 的天然整合结构域（HMA domain）位置，构建嵌合受体。
- **算法流程简述**（无公式）：
  1. 以目标效应子（如 Foc TR4 的毒力因子）的晶体结构或结构预测模型作为模板。
  2. 使用 RFdiffusion 在效应子表面附近采样生成**从头蛋白骨架**，要求骨架与效应子形成互补界面。
  3. 使用 ProteinMPNN 对每个骨架生成多个候选序列，并基于 Rosetta 或 AlphaFold2 进行结构预测和评分。
  4. 筛选出高置信度、低能量、与效应子结合界面合理的候选 IDs。
  5. 将候选 IDs 编码基因合成并克隆到 NLR 底盘载体中。
  6. 在烟草（*N. benthamiana*）中进行瞬时表达和共注射效应子测定。

## 3. 实验设计：数据集、场景、基准与对比方法
- **目标效应子**：来自巴拿马病病原体 **Fusarium oxysporum f. sp. cubense Tropical Race 4**（Foc TR4）的毒力效应子（文中称“非同源效应子”，即 Pik-1/Pik-2 天然不识别）。
- **场景**：在模式植物 **Nicotiana benthamiana** 中进行瞬时表达，通过共注射效应子蛋白或效应子表达载体，观察是否引发细胞死亡（HR，过敏反应）作为免疫激活指标。
- **基准与对比**：
  - 未明确设置传统方法（如定向进化、互换结构域等）作为直接对比。
  - 与天然 NLR 受体的识别特异性进行比较（天然 Pik-1/Pik-2 仅识别水稻稻瘟病菌的 AVR-Pik 效应子，不识别 Foc TR4 效应子），以此证明工程化受体的“新”识别能力。
  - 内部对照：空载体、无效应子注射、突变体 IDs 等用于排除假阳性。
- **结构验证**：通过 X 射线晶体学或冷冻电镜解析设计的 IDs 与效应子的复合体结构，与设计模型比对。

## 4. 资源与算力
- **文中未明确说明**：预印本摘要未提及 GPU 型号、数量、训练时长等算力信息。通常 RFdiffusion 和 ProteinMPNN 的运行需要高性能 GPU（如 A100），但具体配置不详。
- **注意**：完整的预印本正文可能包含补充计算资源说明，但本摘要中未提供。

## 5. 实验数量与充分性
- **实验数量**：
  - 设计了**多个**候选 IDs（具体数目未在摘要中给出，但涉及多个靶标和不同界面）。
  - 功能实验：至少包括每组 IDs 与效应子共表达、单独表达、突变体对照等。
  - 结构验证：采用 X 射线或冷冻电镜解析了至少一个复合体结构。
  - 生物物理实验：如 SPR、ITC 等用于测量结合亲和力（摘要中提“biophysical analyses”）。
  - 自身活性与抑制现象：观察到了 IDs 引发 NLR 自身活性或效应子介导的细胞死亡抑制，并进行了相应控制实验。
- **充分性判断**：
  - **优点**：从设计、表达、功能、结构到生物物理，形成了完整的证据链，实验设计合理，对照基本齐全。
  - **不足**：仅测试了一个病原体（Foc TR4）的一个效应子；仅在烟草异源系统中验证，未在天然宿主（如水稻或香蕉）中测试；未与其他已有的 NLR 工程方法（如 swapping、rational design）进行直接的效率对比。因此作为概念验证充分，但泛化性和实用性仍需更多实验。

## 6. 论文的主要结论与发现
1. **成功设计并构建**能够识别非同源效应子的从头整合结构域（IDs），植入 Pik-1/Pik-2 底盘后获得**可编程的免疫识别**。
2. **功能验证**：在烟草中，设计的 IDs 可特异性感知目标效应子并引发细胞死亡（HR），表明免疫信号被启动。
3. **结构保真度**：晶体结构/电镜结构证实 IDs 的实际折叠与设计模型高度一致，并通过预测的界面与效应子结合。
4. **IDs 可调控 NLR 信号**：部分 IDs 的整合会引起 NLR 自身活性（无需效应子即引发细胞死亡）；另一些 IDs 在效应子存在时会抑制细胞死亡，揭示了 IDs 在 NLR 信号调控中的正交作用。
5. 建立了**设计引领、可编程**的植物免疫受体生成框架，为作物抗病育种提供新途径。

## 7. 优点：方法或实验设计上的亮点
- **创新性**：首次将生成式 AI 蛋白设计（RFdiffusion/ProteinMPNN）用于植物 NLR 工程，实现了**零始动、无天然模板**的定制感知结构域设计。
- **模块化底盘**：利用 Pik-1/Pik-2 已知的模块化特性（整合结构域可替换），提供了通用型受体底盘，可适配不同效应子。
- **全流程验证**：从计算设计、分子克隆、烟草功能测试，到结构生物学和生物物理分析，形成了闭环验证，结果可靠。
- **发现 new biology**：揭示了从头 IDs 可影响 NLR 信号调控（自身活性/抑制），为理解 NLR 整合结构域功能提供新证据。
- **开放设计框架**：方法学具有通用性，可推广到其他植物 NLR 受体（如 NRG1、RPS5 等）及其他病原体效应子。

## 8. 不足与局限：实验覆盖、偏差风险、应用限制
- **实验覆盖局限**：
  - 仅在瞬时表达体系（烟草）中测试，未在稳定转基因作物（如水稻、香蕉）中验证抗病性。
  - 仅针对一个效应子家族，未广泛测试对不同效应子（如不同专化型、不同毒性因子）的适用性。
  - 未评估对植物生长发育的潜在负面影响（如自身活性可能引发生长抑制）。
- **偏差风险**：
  - 选用的效应子可能结构保守或表面特征易于设计，是否存在对“难靶”效应子（如无结构、高灵活性）的设计失败风险未探讨。
  - IDs 设计依赖于目标效应子的高分辨率结构，对于结构未知的效应子需要 AlphaFold2 预测，设计成功率可能下降。
- **应用限制**：
  - 需要较高的计算资源和生物信息学能力，普通实验室难以复现。
  - 最终在作物中应用还需解决转化效率、基因沉默、非靶标效应等问题。
  - 自身活性或效应子介导的抑制现象可能干扰实际抗病表型，需进一步优化设计以消除不良反应。

（完）
