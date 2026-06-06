---
title: "FlowTransOP: Distributional Translation of Omics Signatures via Constrained Deep Flow Matching"
title_zh: "FlowTransOP: 基于约束深度流匹配的组学特征分布迁移"
authors: "Meimetis, N., Magliacane, S., Hoang, T. N., Lauffenburger, D. A."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.27.728305v1.full.pdf"
tags: ["query:diff-gen"]
score: 6.0
evidence: 流匹配用于组学数据分布转换，与生成模型相关
tldr: 临床前模型观察难以推广到患者，现有方法无法处理特征不重叠且无配对样本的跨域翻译。提出FlowTransOP，通过深度流匹配在预对齐潜在空间中对齐领域分布，并用结构正则化保持条件相似性。在配对样本稀缺（<35对）或特征中等相关（r≤0.58）时优于需配对的方法。实现了无需直接对应关系的生物观察翻译，为可靠治疗推断提供工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决临床前模型与人类患者间特征不重叠且无配对样本的组学翻译难题。
method: 利用深度流匹配对齐预对齐潜在空间中的完整领域分布，并加入结构正则化保持转换后的条件相似性。
result: FlowTransOP在配对样本稀少或跨域特征中等相关时优于需配对的金标准方法，且保持竞争力。
conclusion: FlowTransOP实现无需直接对应关系的跨域组学翻译，有望提高临床转化成功率。
---

## 摘要
来自临床前模型的观察很少能推广到人类患者，导致许多临床试验失败。现有方法大多无法处理具有非重叠特征和无配对样本的领域。在此，我们开发了FlowTransOP，用于在无需一对一特征映射和配对数据的情况下跨此类领域迁移生物观测，同时为四种迁移场景下的模型选择提供指导。我们使用流匹配在预对齐的潜在空间中对齐完整领域分布，并引入结构正则化项，使得变换后相似条件保持接近。FlowTransOP在与需要配对样本的金标准方法竞争时仍具竞争力，但当配对数稀少（<35对）或跨域特征仅中度相关（r<=0.58）时，其性能更优。总体而言，当直接对应关系不可用时，FlowTransOP可在临床前模型与患者之间迁移扰动，实现可靠的治疗推断。作为概念验证，我们在ARCHS4上训练了基础的小鼠-人类转录组图谱，并将其应用于肝脏疾病预测。

## Abstract
Observations from pre-clinical models rarely generalize to human patients, leading to many failures in clinical trials. Most existing methods cannot handle domains with non-overlapping features and no paired samples. Here, we developed FlowTransOP to translate biological observations across such domains without requiring 1-to-1 feature mappings and paired data, while providing a guideline for model selection across four translational regimes. We use flow matching to align full domain distributions in a pre-aligned latent space, with a structural regularization term that keeps similar conditions proximate after transformation. FlowTransOP remains competitive with gold-standard approaches requiring paired samples, but outperforms them when pairs become scarce (<35 pairs) or when cross-domain features are only moderately correlated (r<=0.58). Overall, FlowTransOP can translate perturbations between pre-clinical models and patients when direct correspondences are unavailable, enabling reliable therapeutic inference. As a proof-of-concept, we trained a foundational mouse-human transcriptomic map on ARCHS4 and applied it to liver disease predictions.