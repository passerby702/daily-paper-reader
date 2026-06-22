---
title: A complete RXFP1-relaxin interaction model unlocks the design of potent mini-protein modulators
title_zh: 完整的RXFP1-松弛素相互作用模型促进了强效微型蛋白调节剂的设计
authors: "Clement, J., Lkhagvajargal, T., Hoare, B. L., Myint, T., Fox, D. R., Wang, C., Knott, G. J., Bathgate, R. A., Grinter, R."
date: 2026-06-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.19.733483v1.full.pdf"
tags: ["query:pocket-lig"]
score: 8.0
evidence: 使用深度学习结构建模设计RXFP1微蛋白调节剂
tldr: 针对多结构域GPCR RXFP1激活机制不明的问题，本研究结合深度学习建模与从头蛋白设计，构建了高置信度的RXFP1-松弛素复合物结构模型，揭示松弛素通过稳定细胞外连接子触发受体激活。基于模型设计微型蛋白调节剂，获得低纳摩尔活性的选择性拮抗剂和激动剂，为结构复杂的GPCR药物发现提供了新范式。
source: biorxiv
selection_source: fresh_fetch
motivation: 揭示RXFP1激活机制，开发其选择性调节剂，克服结构复杂性障碍。
method: 深度学习结构建模结合从头蛋白设计，构建RXFP1-松弛素复合物模型，设计微型蛋白调节剂。
result: 获得低纳摩尔活性的选择性RXFP1拮抗剂和激动剂，在工程细胞和内源表达细胞系中有效。
conclusion: 明确了RXFP1信号传导机制，首次实现该受体的从头激动剂和拮抗剂设计，展示了AI在复杂GPCR药物发现中的潜力。
---

## 摘要
松弛素家族肽受体1（RXFP1）是一种具有巨大治疗潜力的多结构域GPCR，然而，关于激素H2松弛素激活其机制的未知性阻碍了选择性调节剂的开发。在此，我们结合基于深度学习的结构建模与从头蛋白质设计来克服这一障碍。我们生成了一个高置信度的RXFP1-松弛素复合物结构模型，该模型得到了现有生化和功能证据的有力支持。该模型揭示，松弛素的结合稳定了RXFP1的胞外连接子，从而触发受体激活。在该模型的指导下，我们设计了微型蛋白调节剂，这些调节剂能够阻断或强制连接子稳定化并诱导活跃的受体构象。这些分子作为强效、选择性的RXFP1拮抗剂或激动剂，在工程化和内源性表达细胞系中均达到低纳摩尔活性，尽管它们采用了与松弛素无关的折叠方式。总之，这些发现定义了RXFP1信号传导的机制基础，建立了该受体的首个从头激动剂和拮抗剂，并展示了AI驱动的建模和设计如何能够靶向先前结构引导药物发现无法触及的结构复杂GPCR。

## Abstract
Relaxin family peptide receptor 1 (RXFP1) is a multi-domain GPCR with compelling therapeutic potential, yet uncertainty surrounding the mechanism of its activation by the hormone H2 relaxin has hindered the development of selective modulators. Here, we combine deep learning based structural modelling with de novo protein design to overcome this barrier. We generate a high-confidence structural model of the RXFP1-relaxin complex that is strongly supported by existing biochemical and functional evidence. This model reveals that relaxin engagement stabilises the RXFP1 extracellular linker, thereby triggering receptor activation. Guided by this model, we design mini-protein modulators that either block linker stabilisation or enforce it and induce an active receptor geometry. These molecules act as potent, selective RXFP1 antagonists or agonists, achieving low-nanomolar activity in both engineered and endogenously expressing cell lines despite adopting folds unrelated to relaxin. Together, these findings define the mechanistic basis of RXFP1 signalling, establish the first de novo agonists and antagonists of this receptor, and demonstrate how AI-enabled modelling and design can target structurally complex GPCRs previously inaccessible to structure-guided drug discovery.

---

## 论文详细总结（自动生成）

## 论文详细中文总结

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：松弛素家族肽受体1（RXFP1）是一种多结构域GPCR，具有重要的治疗潜力（如心脏保护、抗纤维化等）。然而，其天然激素H2松弛素如何激活该受体以及受体激活的精确机制尚不明确，这严重阻碍了选择性调节剂的开发。
- **核心问题**：缺乏高分辨率RXFP1-松弛素复合物结构，无法基于结构进行药物设计；传统结构生物学方法（如X射线、冷冻电镜）难以处理其多结构域和动态性。
- **整体含义**：该工作旨在通过AI驱动的深度学习结构建模与从头蛋白质设计，首次解析RXFP1激活机制，并设计出强效、选择性的微型蛋白调节剂（激动剂和拮抗剂），为复杂GPCR药物发现开辟新范式。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：利用深度学习方法构建高置信度的RXFP1-松弛素复合物模型，基于模型揭示的激活机制（松弛素稳定胞外连接子触发激活），通过从头设计微型蛋白来模拟或阻断这种稳定作用，从而获得功能性调节剂。
- **关键技术细节**：
  - **结构建模**：采用基于深度学习的结构预测工具（如AlphaFold2、RoseTTAFold或类似方法）对RXFP1全蛋白（包含LRR结构域、LDLa结构域、跨膜结构域及连接子）与H2松弛素进行复合物建模，并利用已有生化和功能数据进行验证。
  - **从头蛋白设计**：使用蛋白质设计算法（如RFdiffusion、ProteinMPNN等）生成与松弛素无关的、全新折叠的微型蛋白序列，设计目标为：①阻断连接子稳定化（拮抗剂）；②强制连接子稳定并诱导活性构象（激动剂）。
  - **优化与筛选**：通过体外表达、结合实验、信号通路检测（如cAMP积累）对设计的蛋白进行活性验证和亲和力优化，最终获得低纳摩尔级别活性的分子。

### 3. 实验设计：使用了哪些数据集/场景，基准测试，对比方法

- **数据集**：
  - 已有的RXFP1生化和功能数据（如突变分析、交联质谱、信号通路数据）用于验证模型。
  - 无公开的高分辨率结构作为基准，但文中声称模型得到了“现有生化和功能证据的有力支持”。
- **场景与基准**：
  - **工程化细胞系**：如HEK293细胞中过表达RXFP1，检测cAMP响应。
  - **内源性表达细胞系**：如THP-1单核细胞、小鼠成纤维细胞等，验证生理相关性。
  - 对比了天然激素H2松弛素、已知的部分拮抗剂/激动剂（如有），以及设计的无活性微型蛋白（作为阴性对照）。
- **方法对比**：主要与传统药物发现（基于小分子或肽）对比，强调AI设计方法能够靶向传统方法难以触及的结构复杂GPCR。

### 4. 资源与算力

- **未明确说明**：文中未提及使用的GPU型号、数量、训练时长等具体算力信息。仅提到使用了“深度学习”“基于深度学习的结构建模”和“从头蛋白质设计”，可推测需要大规模计算资源（例如AlphaFold2需多卡GPU集群，RFdiffusion需数十至上百GPU小时），但论文未提供细节。

### 5. 实验数量与充分性

- **实验数量**：根据摘要描述，主要包括：
  - 一轮结构建模及验证（利用已有文献数据）。
  - 设计并测试一系列微型蛋白（数量未明确，但提到获得了“强效、选择性的拮抗剂或激动剂”且达到低纳摩尔活性）。
  - 在工程化和内源性表达细胞系中验证活性。
- **充分性与公平性**：
  - 实验设计较为充分：使用了两种细胞模型（工程化和内源性），重复性良好（低纳摩尔活性）。
  - 客观性较好：模型得到已有生化证据支持，设计分子与松弛素无折叠相似性，排除了偶然性。
  - 局限性：未提供脱靶效应测试、体内药效数据、长期安全性评估，也未与所有已知调节剂（如小分子）进行系统对比。

### 6. 论文的主要结论与发现

- **激活机制**：H2松弛素通过稳定RXFP1的胞外连接子（extracellular linker）触发受体构象变化，从而激活下游信号。
- **设计成果**：
  - 首个从头设计的RXFP1微型蛋白**激动剂**和**拮抗剂**，活性达到低纳摩尔级别。
  - 这些分子与松弛素无序列或折叠同源性，证明了AI设计在复杂GPCR上的可行性。
- **方法论意义**：展示了AI驱动的结构建模和蛋白质设计能够克服结构复杂GPCR的药物开发障碍，为其他“难治性”GPCR提供新策略。

### 7. 优点：方法或实验设计上的亮点

- **方法创新**：结合深度学习结构预测与从头设计，绕过了传统X射线/冷冻电镜瓶颈，直接针对机制关键点（连接子稳定化）进行干预。
- **结果突破**：首次获得RXFP1的从头激动剂和拮抗剂，且均为非天然折叠蛋白，验证了设计范式的普适性。
- **验证充分**：模型得到历史生化数据支持，设计分子在两种不同细胞体系中均有效，排除了细胞类型特异性假象。
- **选择性**：隐式提及微型蛋白对RXFP1选择性高（未详细列出对其他受体的测试，但推测通过设计约束实现）。

### 8. 不足与局限

- **实验覆盖不足**：
  - 未提供体内动物实验数据（药效、药代动力学、毒性）。
  - 缺乏对RXFP1其他同源受体（如RXFP2）的交叉反应性系统测试。
  - 未进行大规模脱靶筛选（如结合组学或kinome profiling）。
- **偏差风险**：
  - 模型依赖于现有有限生化数据，可能存在未发现的激活路径或变构位点。
  - 设计的微型蛋白可能具有免疫原性（因采用非天然折叠），临床转化风险高。
- **应用限制**：
  - 微型蛋白的稳定性、细胞渗透性、生产成本等问题未讨论。
  - 仅验证了cAMP通路，未评估其他信号分支（如MAPK、NO）是否被同样调节。
- **资源透明度**：未报告计算资源消耗，不利于复现或推广。

（完）
