# The Question-driven Literature Taxonomy for RAG

A question-driven reading guide to retrieval-augmented generation, organized by components, systems, agentic capabilities, evaluation, and open research.

**Edition:** 2026-09-11 · **Taxonomy baseline:** RAG survey v16 · **Language:** English

This catalogue accompanies *A Systematic Survey of Retrieval-Augmented Generation (RAG): Advances, Challenges and Future Directions*. It retains the established question taxonomy while adding a consistent bibliographic presentation for repository readers.

**Central research question:** How should RAG systems be designed and optimized to support diverse generative AI applications at scale over heterogeneous, evolving data under stated quality, latency, and cost requirements?

**Coverage:** 5 domains, 35 subcategories, 95 questions, and 497 distinct bibliographic records. The question-organized sections contain 411 distinct papers through 535 question–paper associations. Another 86 supporting records are listed separately because they have no inherited question-level assignment. The 619 uncited records in the larger survey bibliography are outside this catalogue.

<a id="contents"></a>

## Contents

- [How to use this catalogue](#how-to-use)
- [Taxonomy overview](#taxonomy-overview)
- [A. Component-level design](#domain-a)
  - [A1. Query and routing](#group-a1)
  - [A2. Datastore and knowledge lifecycle](#group-a2)
  - [A3. Retrieval and evidence-set construction](#group-a3)
  - [A4. Context assembly and provenance](#group-a4)
  - [A5. Evidence-conditioned generation](#group-a5)
  - [A6. Response quality and accountability](#group-a6)
- [B. System-level composition and optimization](#domain-b)
  - [B1. Composition, interfaces, and scheduling](#group-b1)
  - [B2. Cross-component optimization](#group-b2)
  - [B3. Learning, rewards, and credit](#group-b3)
  - [B4. Knowledge and deployment conditions](#group-b4)
- [C. Adaptive control, memory, and collaboration](#domain-c)
  - [C1. Agency and decision responsibility](#group-c1)
  - [C2. Planning, revision, and search control](#group-c2)
  - [C3. Memory roles, lifecycle, and reuse](#group-c3)
  - [C4. Delegation, communication, and reconciliation](#group-c4)
  - [C5. Runtime interfaces and observability](#group-c5)
  - [C6. Learning stateful control](#group-c6)
  - [C7. Matched capability comparisons](#group-c7)
- [D. Evaluation and evidence for claims](#domain-d)
  - [D1. Claim definition](#group-d1)
  - [D2. Evaluation objects](#group-d2)
  - [D3. Quality and operational dimensions](#group-d3)
  - [D4. Evaluation settings](#group-d4)
  - [D5. Metrics, judges, and interventions](#group-d5)
  - [D6. Benchmark and infrastructure portfolio](#group-d6)
  - [D7. Agentic capability evaluation](#group-d7)
  - [D8. Inherited common-protocol case study](#group-d8)
  - [D9. Uncertainty and reproducible reporting](#group-d9)
- [E. Open research and conditional scaling](#domain-e)
  - [E1. Adaptive control and interface validity](#group-e1)
  - [E2. Credit and portable policies](#group-e2)
  - [E3. Quality-preserving selective acquisition](#group-e3)
  - [E4. Source change and selective persistence](#group-e4)
  - [E5. Conditional multi-agent and swarm scaling](#group-e5)
  - [E6. Modality and domain transfer](#group-e6)
  - [E7. Integrity, privacy, and fairness](#group-e7)
  - [E8. Comparable evaluation infrastructure](#group-e8)
  - [E9. Native acquisition and reasoning interfaces](#group-e9)
- [Supporting literature without a question-level assignment](#supporting-literature)
- [Venue abbreviations](#venue-abbreviations)
- [Metadata and maintenance notes](#metadata-notes)

<a id="how-to-use"></a>

## How to use this catalogue

Start with a domain and subcategory, then select the question closest to your information need. Papers are sorted by recorded publication year (newest first) and then title within each question. A paper can occur under several questions; repeated entries are deliberate cross-listings, not additional distinct papers.

**Question types.** Q-1–Q-80 are *Focal questions* organizing existing mechanisms and trade-offs. Q-81–Q-95 are *Open research questions* organizing unresolved mechanisms and evaluation needs. This is not a solved/unsolved partition: some questions remain relevant across successive technical advances.

**Bibliographic convention.** Each entry gives its linked title, author list in source order, venue or dissemination outlet, and year. Full author lists are retained where supplied; institutional authors are identified as such. Findings, industry tracks, demonstrations, workshops, and companion proceedings remain distinct from main-conference papers. The year refers to the displayed record; when the event and publication years differ, the venue field makes that distinction explicit. An arXiv entry identifies the indexed preprint version, not a claim that no later publication exists.

**Association labels are separate from publication metadata.** They describe the existing review depth of one question–paper association, not the quality of the paper or proof that it answers the question:

| Label | Existing association-review status | Count |
| --- | --- | ---: |
| P | Inherited citation-position association; semantic role not independently re-adjudicated | 512 |
| C | Manuscript context reviewed; not an independent full-text verification | 19 |
| A | Primary abstract checked for this association; not full-text claim verification | 4 |

Five questions have no inherited local paper assignment: [Q-36](#q-36), [Q-54](#q-54), [Q-60](#q-60), [Q-71](#q-71), [Q-82](#q-82). Their empty lists are retained transparently; they do not imply an absence of relevant research.

<a id="taxonomy-overview"></a>

## Taxonomy overview

| Domain | Questions | Organizing perspective |
| --- | --- | --- |
| [A. Component-level design](#domain-a) | [Q-1](#q-1)–[Q-25](#q-25) | What information object is handled, and which local bottleneck limits useful evidence? |
| [B. System-level composition and optimization](#domain-b) | [Q-26](#q-26)–[Q-36](#q-36) | How do local decisions interact under task and resource constraints? |
| [C. Adaptive control, memory, and collaboration](#domain-c) | [Q-37](#q-37)–[Q-53](#q-53) | Which decisions require observation-conditioned control or coordinated state? |
| [D. Evaluation and evidence for claims](#domain-d) | [Q-54](#q-54)–[Q-80](#q-80) | What observations make an application, capability, or scaling claim defensible? |
| [E. Open research and conditional scaling](#domain-e) | [Q-81](#q-81)–[Q-95](#q-95) | Which unresolved mechanisms and conditions should future research test? |

Categories identify the primary location of a question, not mutually exclusive classes of papers. Graph structure, modality, domain, learning strategy, and deployment conditions can cut across these categories.

<a id="domain-a"></a>

## A. Component-level design

What information object is handled, and which local bottleneck limits useful evidence?

<a id="group-a1"></a>

### A1. Query and routing

Focus: Need ambiguity; evidence demand; selective routing.

Questions: [Q-1](#q-1) · [Q-2](#q-2) · [Q-3](#q-3) · [Q-4](#q-4) · [Q-5](#q-5) · [Q-6](#q-6).

<a id="q-1"></a>

#### Q-1. When should external evidence be acquired?

*Focal question.*

<!-- record: Marina2025LLM; question: Q-1; review: positional_only -->
- **[LLM-Independent Adaptive RAG: Let the Question Speak for Itself](<https://arxiv.org/abs/2505.04253>)**
  - Authors: Maria Marina; Nikolay Ivanov; Sergey Pletenev; Mikhail Salnikov; Daria Galimzianova; Nikita Krayko; Vasily Konovalov; Alexander Panchenko; Viktor Moskvoretskii.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: li2025etc; question: Q-1; review: positional_only -->
- **[Modeling Uncertainty Trends for Timely Retrieval in Dynamic RAG](<https://arxiv.org/abs/2511.09980>)**
  - Authors: Bo Li; Tian Tian; Zhenghua Xu; Hao Cheng; Shikun Zhang; Wei Ye.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Zhu2025RaDIO; question: Q-1; review: positional_only -->
- **[RaDIO: Real-Time Hallucination Detection with Contextual Index Optimized Query Formulation for Dynamic Retrieval Augmented Generation](<https://doi.org/10.1609/aaai.v39i24.34809>)**
  - Authors: Jia Zhu; Hanghui Guo; Weijie Shi; Zhangze Chen; Pasquale De Meo.
  - Venue / outlet: **AAAI** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: chen2025and; question: Q-1; review: positional_only -->
- **[When and How to Augment Your Input: Question Routing Helps Balance the Accuracy and Efficiency of Large Language Models](<https://doi.org/10.18653/v1/2025.findings-naacl.200>)**
  - Authors: Shufan Chen; He Zheng; Lei Cui.
  - Venue / outlet: **Findings of NAACL** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: jeong2024adaptive; question: Q-1; review: positional_only -->
- **[Adaptive-RAG: Learning to Adapt Retrieval-Augmented Large Language Models through Question Complexity](<https://doi.org/10.18653/v1/2024.naacl-long.389>)**
  - Authors: Soyeong Jeong; Jinheon Baek; Sukmin Cho; Sung Ju Hwang; Jong Park.
  - Venue / outlet: **NAACL (Long Papers)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: su2024dragin; question: Q-1; review: positional_only -->
- **[DRAGIN: Dynamic Retrieval Augmented Generation based on the Real-time Information Needs of Large Language Models](<https://aclanthology.org/2024.acl-long.702/>)**
  - Authors: Weihang Su; Yichen Tang; Qingyao Ai; Zhijing Wu; Yiqun Liu.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: asai2024selfrag; question: Q-1; review: positional_only -->
- **[Self-RAG: Learning to Retrieve, Generate, and Critique through Self-Reflection](<https://proceedings.iclr.cc/paper_files/paper/2024/hash/25f7be9694d7b32d5cc670927b8091e1-Abstract-Conference.html>)**
  - Authors: Akari Asai; Zeqiu Wu; Yizhong Wang; Avirup Sil; Hannaneh Hajishirzi.
  - Venue / outlet: **ICLR** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: jiang2023active; question: Q-1; review: positional_only -->
- **[Active Retrieval Augmented Generation](<https://doi.org/10.18653/v1/2023.emnlp-main.495>)**
  - Authors: Zhengbao Jiang; Frank Xu; Luyu Gao; Zhiqing Sun; Qian Liu; Jane Dwivedi-Yu; Yiming Yang; Jamie Callan; Graham Neubig.
  - Venue / outlet: **EMNLP** · Year: **2023**.
  - Association review: [P](#how-to-use).

<!-- record: lewis2020rag; question: Q-1; review: positional_only -->
- **[Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks](<https://papers.nips.cc/paper/2020/hash/6b493230205f780e1bc26945df7481e5-Abstract.html>)**
  - Authors: Patrick Lewis; Ethan Perez; Aleksandra Piktus; Fabio Petroni; Vladimir Karpukhin; Naman Goyal; Heinrich Küttler; Mike Lewis; Wen-tau Yih; Tim Rocktäschel; Sebastian Riedel; Douwe Kiela.
  - Venue / outlet: **NeurIPS** · Year: **2020**.
  - Association review: [P](#how-to-use).

<a id="q-2"></a>

#### Q-2. What type and granularity of evidence is required?

*Focal question.*

<!-- record: edge2024graphrag; question: Q-2; review: positional_only -->
- **[From Local to Global: A Graph RAG Approach to Query-Focused Summarization](<https://arxiv.org/abs/2404.16130>)**
  - Authors: Darren Edge; Ha Trinh; Newman Cheng; Joshua Bradley; Alex Chao; Apurva Mody; Steven Truitt; Dasha Metropolitansky; Robert Osazuwa Ness; Jonathan Larson.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: trivedi2023interleaving; question: Q-2; review: positional_only -->
- **[Interleaving Retrieval with Chain-of-Thought Reasoning for Knowledge-Intensive Multi-Step Questions](<https://doi.org/10.18653/v1/2023.acl-long.557>)**
  - Authors: Harsh Trivedi; Niranjan Balasubramanian; Tushar Khot; Ashish Sabharwal.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2023**.
  - Association review: [P](#how-to-use).

<!-- record: lewis2020rag; question: Q-2; review: positional_only -->
- **[Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks](<https://papers.nips.cc/paper/2020/hash/6b493230205f780e1bc26945df7481e5-Abstract.html>)**
  - Authors: Patrick Lewis; Ethan Perez; Aleksandra Piktus; Fabio Petroni; Vladimir Karpukhin; Naman Goyal; Heinrich Küttler; Mike Lewis; Wen-tau Yih; Tim Rocktäschel; Sebastian Riedel; Douwe Kiela.
  - Venue / outlet: **NeurIPS** · Year: **2020**.
  - Association review: [P](#how-to-use).

<a id="q-3"></a>

#### Q-3. What representation should express the information need?

*Focal question.*

<!-- record: Chen2026DeFuzzRAG; question: Q-3; review: positional_only -->
- **[DeFuzzRAG: Handling Fuzzy Time Expressions for Temporal Robustness in Retrieval-Augmented Generation](<https://doi.org/10.1609/aaai.v40i36.40276>)**
  - Authors: Ling-Chun Chen; Hsi-Wen Chen; Ming-Syan Chen.
  - Venue / outlet: **AAAI** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: liu2026qdrag; question: Q-3; review: positional_only -->
- **[Faithful in Steps: Improving Generalization and Citation in RAG via Query Decomposition](<https://doi.org/10.1609/aaai.v40i42.40879>)**
  - Authors: Yue Liu; Zhongying Ru; Shimin Di; Jipeng Zhang; Ruiyuan Zhang; Xiaofang Zhou.
  - Venue / outlet: **AAAI** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Jiao2026PruneRAG; question: Q-3; review: positional_only -->
- **[PruneRAG: Confidence-Guided Query Decomposition Trees for Efficient Retrieval-Augmented Generation](<https://doi.org/10.1145/3774904.3792103>)**
  - Authors: Shuguang Jiao; Xinyu Xiao; Yunfan Wei; Shuhan Qi; Chengkai Huang; Quan Z. Sheng; Lina Yao.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: rlqr2025; question: Q-3; review: positional_only -->
- **[Annotation-Free Reinforcement Learning Query Rewriting via Verifiable Search Reward](<https://arxiv.org/abs/2507.23242>)**
  - Authors: Sungguk Cha; DongWook Kim; Taeseung Hahn; Mintae Kim; Youngsub Han; Byoung-Ki Jeon.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: zhu2025convsearchr1; question: Q-3; review: positional_only -->
- **[ConvSearch-R1: Enhancing Query Reformulation for Conversational Search with Reasoning via Reinforcement Learning](<https://arxiv.org/abs/2505.15776>)**
  - Authors: Changtai Zhu; Siyin Wang; Ruijun Feng; Kai Song; Xipeng Qiu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Pogrebinsky2025Enhancing; question: Q-3; review: positional_only -->
- **[Enhancing Retrieval-Augmented Generation for Text Completion Through Query Selection](<https://doi.org/10.1145/3731120.3744610>)**
  - Authors: Idan Pogrebinsky; David Carmel; Oren Kurland.
  - Venue / outlet: **ICTIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: zhang2025imprag; question: Q-3; review: positional_only -->
- **[ImpRAG: Retrieval-Augmented Generation with Implicit Queries](<https://arxiv.org/abs/2506.02279>)**
  - Authors: Wenzheng Zhang; Xi Victoria Lin; Karl Stratos; Wen-tau Yih; Mingda Chen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Gabin2025Leveraging; question: Q-3; review: positional_only -->
- **[Leveraging Retrieval-Augmented Generation for Keyphrase Synonym Suggestion](<https://link.springer.com/chapter/10.1007/978-3-031-88711-6_20>)**
  - Authors: Jorge Gabín; Javier Parapar.
  - Venue / outlet: **ECIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Zhang2025Lexical; question: Q-3; review: positional_only -->
- **[Lexical Diversity-aware Relevance Assessment for Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2025.acl-long.1346>)**
  - Authors: Zhange Zhang; Yuqing Ma; Yulong Wang; Shan He; Tianbo Wang; Siqi He; Jiakai Wang; Xianglong Liu.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: su2025racqc; question: Q-3; review: positional_only -->
- **[RACQC: Advanced Retrieval-Augmented Generation for Chinese Query Correction](<https://doi.org/10.18653/v1/2025.findings-emnlp.36>)**
  - Authors: Jinbo Su; Lingzhe Gao; Wei Li; Shihao Liu; Haojie Lei; Xinyi Wang; Yuanzhao Guo; Ke Wang; Daiting Shi; Dawei Yin.
  - Venue / outlet: **Findings of EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Kim2025UniRAG; question: Q-3; review: positional_only -->
- **[UniRAG: A Unified RAG Framework for Knowledge-Intensive Queries with Decomposition, Break-Down Reasoning, and Iterative Rewriting](<https://doi.org/10.18653/v1/2025.findings-emnlp.1022>)**
  - Authors: Gun Il Kim; Jong Wook Kim; Beakcheol Jang.
  - Venue / outlet: **Findings of EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: li2025unirag; question: Q-3; review: positional_only -->
- **[UniRAG: Unified Query Understanding Method for Retrieval Augmented Generation](<https://doi.org/10.18653/v1/2025.acl-long.693>)**
  - Authors: Rui Li; Liyang He; Qi Liu; Zheng Zhang; Heng Yu; Yuyang Ye; Linbo Zhu; Yu Su.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: su2024dragin; question: Q-3; review: positional_only -->
- **[DRAGIN: Dynamic Retrieval Augmented Generation based on the Real-time Information Needs of Large Language Models](<https://aclanthology.org/2024.acl-long.702/>)**
  - Authors: Weihang Su; Yichen Tang; Qingyao Ai; Zhijing Wu; Yiqun Liu.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: jiang2023active; question: Q-3; review: positional_only -->
- **[Active Retrieval Augmented Generation](<https://doi.org/10.18653/v1/2023.emnlp-main.495>)**
  - Authors: Zhengbao Jiang; Frank Xu; Luyu Gao; Zhiqing Sun; Qian Liu; Jane Dwivedi-Yu; Yiming Yang; Jamie Callan; Graham Neubig.
  - Venue / outlet: **EMNLP** · Year: **2023**.
  - Association review: [P](#how-to-use).

<a id="q-4"></a>

#### Q-4. Where should evidence be acquired?

*Focal question.*

<!-- record: Zheng2025CoRAG; question: Q-4; review: positional_only -->
- **[CoRAG: Enhancing Hybrid Retrieval-Augmented Generation through a Cooperative Retriever Architecture](<https://doi.org/10.18653/v1/2025.findings-emnlp.872>)**
  - Authors: Zaiyi Zheng; Song Wang; Zihan Chen; Yaochen Zhu; Yinhan He; Liangjie Hong; Qi Guo; Jundong Li.
  - Venue / outlet: **Findings of EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Lee2024HybGRAG; question: Q-4; review: positional_only -->
- **[HybGRAG: Hybrid Retrieval-Augmented Generation on Textual and Relational Knowledge Bases](<https://arxiv.org/abs/2412.16311>)**
  - Authors: Meng-Chieh Lee; Qi Zhu; Costas Mavromatis; Zhen Han; Soji Adeshina; Vassilis N. Ioannidis; Huzefa Rangwala; Christos Faloutsos.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<a id="q-5"></a>

#### Q-5. Which retriever or retrieval combination should be used?

*Focal question.*

<!-- record: colbertv22022; question: Q-5; review: positional_only -->
- **[ColBERTv2: Effective and Efficient Retrieval via Lightweight Late Interaction](<https://doi.org/10.18653/v1/2022.naacl-main.272>)**
  - Authors: Keshav Santhanam; Omar Khattab; Jon Saad-Falcon; Christopher Potts; Matei Zaharia.
  - Venue / outlet: **NAACL** · Year: **2022**.
  - Association review: [P](#how-to-use).

<!-- record: KZ_SIGIR_2020; question: Q-5; review: positional_only -->
- **[ColBERT: Efficient and Effective Passage Search via Contextualized Late Interaction over BERT](<https://doi.org/10.1145/3397271.3401075>)**
  - Authors: Omar Khattab; Matei Zaharia.
  - Venue / outlet: **SIGIR** · Year: **2020**.
  - Association review: [P](#how-to-use).

<!-- record: karpukhin2020dense; question: Q-5; review: positional_only -->
- **[Dense Passage Retrieval for Open-Domain Question Answering](<https://doi.org/10.18653/v1/2020.emnlp-main.550>)**
  - Authors: Vladimir Karpukhin; Barlas Oguz; Sewon Min; Patrick Lewis; Ledell Wu; Sergey Edunov; Danqi Chen; Wen-tau Yih.
  - Venue / outlet: **EMNLP** · Year: **2020**.
  - Association review: [P](#how-to-use).

<a id="q-6"></a>

#### Q-6. Which generator and evidence interface should be used?

*Focal question.*

<!-- record: graphragrouter2026; question: Q-6; review: positional_only -->
- **[GraphRAG-Router: Learning Cost-Efficient Routing over GraphRAGs and LLMs with Reinforcement Learning](<https://arxiv.org/abs/2604.16401>)**
  - Authors: Dongzhe Fan; Chuanhao Ji; Zimu Wang; Tong Chen; Qiaoyu Tan.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: ong2025routellm; question: Q-6; review: positional_only -->
- **[RouteLLM: Learning to Route LLMs with Preference Data](<https://arxiv.org/abs/2406.18665>)**
  - Authors: Isaac Ong; Amjad Almahairi; Vincent Wu; Wei-Lin Chiang; Tianhao Wu; Joseph E. Gonzalez; M. Waleed Kadous; Ion Stoica.
  - Venue / outlet: **ICLR** · Year: **2025**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-a2"></a>

### A2. Datastore and knowledge lifecycle

Focus: Coverage; granularity; freshness; admissibility.

Questions: [Q-7](#q-7) · [Q-8](#q-8) · [Q-9](#q-9) · [Q-10](#q-10).

<a id="q-7"></a>

#### Q-7. Which knowledge should be available and admissible?

*Focal question.*

<!-- record: zerhoudi2026nuggetindex; question: Q-7; review: positional_only -->
- **[NuggetIndex: Governed Atomic Retrieval for Maintainable RAG](<https://sigir2026.org/en-AU/pages/program/accepted-papers>)**
  - Authors: Saber Zerhoudi; Michael Granitzer; Jelena Mitrović.
  - Venue / outlet: **SIGIR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: edge2024graphrag; question: Q-7; review: positional_only -->
- **[From Local to Global: A Graph RAG Approach to Query-Focused Summarization](<https://arxiv.org/abs/2404.16130>)**
  - Authors: Darren Edge; Ha Trinh; Newman Cheng; Joshua Bradley; Alex Chao; Apurva Mody; Steven Truitt; Dasha Metropolitansky; Robert Osazuwa Ness; Jonathan Larson.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<a id="q-8"></a>

#### Q-8. What should constitute a retrievable unit?

*Focal question.*

<!-- record: Lu2026HiChunk; question: Q-8; review: positional_only -->
- **[HiChunk: Evaluating and Enhancing Retrieval Augmented Generation with Hierarchical Chunking](<https://doi.org/10.18653/v1/2026.acl-long.1372>)**
  - Authors: Wensheng Lu; Keyu Chen; Zhifeng Shen; Ruizhi Qiao; Xing Sun.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: zhao2026qchunker; question: Q-8; review: positional_only -->
- **[QChunker: Learning Question-Aware Text Chunking for Domain RAG via Multi-Agent Debate](<https://doi.org/10.1145/3774904.3792433>)**
  - Authors: Jihao Zhao; Daixuan Li; Pengfei Li; Shuaishuai Zu; Biao Qin; Hongyan Liu.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Zhang2025cAST; question: Q-8; review: positional_only -->
- **[cAST: Enhancing Code Retrieval-Augmented Generation with Structural Chunking via Abstract Syntax Tree](<https://arxiv.org/abs/2506.15655>)**
  - Authors: Yilin Zhang; Xinran Zhao; Zora Zhiruo Wang; Chenyang Yang; Jiayi Wei; Tongshuang Wu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Wang2025Document; question: Q-8; review: positional_only -->
- **[Document Segmentation Matters for Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2025.findings-acl.422>)**
  - Authors: Zhitong Wang; Cheng Gao; Chaojun Xiao; Yufei Huang; Shuzheng Si; Kangyang Luo; Yuzhuo Bai; Wenhao Li; Tangjian Duan; Chuancheng Lv; Guoshan Lu; Gang Chen; Fanchao Qi; Maosong Sun.
  - Venue / outlet: **Findings of ACL** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Zhao2025MoC; question: Q-8; review: positional_only -->
- **[MoC: Mixtures of Text Chunking Learners for Retrieval-Augmented Generation System](<https://arxiv.org/abs/2503.09600>)**
  - Authors: Jihao Zhao; Zhiyuan Ji; Zhaoxin Fan; Hanyu Wang; Simin Niu; Bo Tang; Feiyu Xiong; Zhiyu Li.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Zhang2025SAGE; question: Q-8; review: positional_only -->
- **[SAGE: A Framework of Precise Retrieval for RAG](<https://doi.org/10.1109/icde65448.2025.00108>)**
  - Authors: Jintao Zhang; Guoliang Li; Jinyang Su.
  - Venue / outlet: **ICDE** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: tao2025sakirag; question: Q-8; review: positional_only -->
- **[SAKI-RAG: Mitigating Context Fragmentation in Long-Document RAG via Sentence-level Attention Knowledge Integration](<https://doi.org/10.18653/v1/2025.emnlp-main.63>)**
  - Authors: Wenyu Tao; Xiaofen Xing; Zeliang Li; Xiangmin Xu.
  - Venue / outlet: **EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: zhong2025mog; question: Q-8; review: positional_only -->
- **[Mix-of-Granularity: Optimize the Chunking Granularity for Retrieval-Augmented Generation](<https://arxiv.org/abs/2406.00456>)**
  - Authors: Zijie Zhong; Hanwen Liu; Xiaoya Cui; Xiaofan Zhang; Zengchang Qin.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<a id="q-9"></a>

#### Q-9. How should evidence and its relationships be organized for access?

*Focal question.*

<!-- record: Zhong2026Unified; question: Q-9; review: positional_only -->
- **[A Unified Framework for Context-Aware and Relation-Aware Graph Retrieval-Augmented Generation](<https://doi.org/10.1145/3774904.3792720>)**
  - Authors: Haoyang Zhong; Yifei Sun; Antong Zhang; Chunping Wang; Lei Chen; Yang Yang.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Wang2025ArchRAG; question: Q-9; review: positional_only -->
- **[ArchRAG: Attributed Community-based Hierarchical Retrieval-Augmented Generation](<https://doi.org/10.1609/aaai.v40i19.38619>)**
  - Authors: Shu Wang; Yixiang Fang; Yingli Zhou; Xilin Liu; Yuchi Ma.
  - Venue / outlet: **AAAI** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: cream2026; question: Q-9; review: positional_only -->
- **[CREAM: Continual Retrieval on Dynamic Streaming Corpora with Adaptive Soft Memory](<https://arxiv.org/abs/2601.02708>)**
  - Authors: HuiJeong Son; Hyeongu Kang; Sunho Kim; Subeen Ho; SeongKu Kang; Dongha Lee; Susik Yoon.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Liu2026Disco; question: Q-9; review: positional_only -->
- **[Disco-RAG: Discourse-Aware Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2026.acl-long.189>)**
  - Authors: Dongqi Liu; Hang Ding; Qiming Feng; Xurong Xie; Zhucun Xue; Chengjie Wang; Jian Li; Jiangning Zhang; Yabiao Wang.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Nishida2026Dissecting; question: Q-9; review: positional_only -->
- **[Dissecting GraphRAG: A Modular Analysis of Knowledge Structuring for Factoid Question Answering](<https://doi.org/10.1162/tacl.a.615>)**
  - Authors: Noriki Nishida; Rumana Ferdous Munne; Shanshan Liu; Narumi Tokunaga; Yuki Yamagata; Fei Cheng; Kouji Kozaki; Yuji Matsumoto.
  - Venue / outlet: **TACL** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Fan2026Do; question: Q-9; review: positional_only -->
- **[Do We Still Need GraphRAG? Benchmarking RAG and GraphRAG for Agentic Search Systems](<https://arxiv.org/abs/2604.09666>)**
  - Authors: Dongzhe Fan; Zheyi Xue; Siyuan Liu; Qiaoyu Tan.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Lien2026HyperRAG; question: Q-9; review: positional_only -->
- **[HyperRAG: Reasoning N-ary Facts over Hypergraphs for Retrieval Augmented Generation](<https://doi.org/10.1145/3774904.3792710>)**
  - Authors: Wen-Sheng Lien; Yu-Kai Chan; Hao-Lung Hsiao; Bo-Kai Ruan; Meng-Fen Chiang; Chien-An Chen; Yi-Ren Yeh; Hong-Han Shuai.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: zerhoudi2026nuggetindex; question: Q-9; review: positional_only -->
- **[NuggetIndex: Governed Atomic Retrieval for Maintainable RAG](<https://sigir2026.org/en-AU/pages/program/accepted-papers>)**
  - Authors: Saber Zerhoudi; Michael Granitzer; Jelena Mitrović.
  - Venue / outlet: **SIGIR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: hu2026erm; question: Q-9; review: positional_only -->
- **[RAG without Forgetting: Continual Query-Infused Key Memory](<https://arxiv.org/abs/2602.05152>)**
  - Authors: Yuntong Hu; Sha Li; Naren Ramakrishnan; Liang Zhao.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: kim2026thrag; question: Q-9; review: positional_only -->
- **[TH-RAG : Topic-Based Hierarchical Knowledge Graphs for Robust Multi-hop Reasoning in Graph-based RAG Systems](<https://doi.org/10.18653/v1/2026.acl-long.1740>)**
  - Authors: JungHyoun Kim; Soohyeong Kim; Seok Jun Hwang; Jeonghyeon Park; Yong Suk Choi.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: xiang2026graphragbench; question: Q-9; review: positional_only -->
- **[When to use Graphs in RAG: A Comprehensive Analysis for Graph Retrieval-Augmented Generation](<https://proceedings.iclr.cc/paper_files/paper/2026/hash/6c9e01d6cefbbf4cdd265032550e767f-Abstract-Conference.html>)**
  - Authors: Zhishang Xiang; Chuanjie Wu; Qinggang Zhang; Shengyuan Chen; Zijin Hong; Xiao Huang; Jinsong Su.
  - Venue / outlet: **ICLR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Wang2025CausalRAG; question: Q-9; review: positional_only -->
- **[CausalRAG: Integrating Causal Graphs into Retrieval-Augmented Generation](<https://arxiv.org/abs/2503.19878>)**
  - Authors: Nengbo Wang; Xiaotian Han; Jagdip Singh; Jing Ma; Vipin Chaudhary.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Hu2025Cog; question: Q-9; review: positional_only -->
- **[Cog-RAG: Cognitive-Inspired Dual-Hypergraph with Theme Alignment Retrieval-Augmented Generation](<https://arxiv.org/abs/2511.13201>)**
  - Authors: Hao Hu; Yifan Feng; Ruoxue Li; Rundong Xue; Xingliang Hou; Zhiqiang Tian; Yue Gao; Shaoyi Du.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Wang2025Cross; question: Q-9; review: positional_only -->
- **[Cross-Granularity Hypergraph Retrieval-Augmented Generation for Multi-hop Question Answering](<https://arxiv.org/abs/2508.11247>)**
  - Authors: Changjian Wang; Weihong Deng; Weili Guan; Quan Lu; Ning Jiang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: gutierrez2025hipporag2; question: Q-9; review: positional_only -->
- **[From RAG to Memory: Non-Parametric Continual Learning for Large Language Models](<https://arxiv.org/abs/2502.14802>)**
  - Authors: Bernal Jiménez Gutiérrez; Yiheng Shu; Weijian Qi; Sizhe Zhou; Yu Su.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: luo2025hypergraphrag; question: Q-9; review: positional_only -->
- **[HyperGraphRAG: Retrieval-Augmented Generation via Hypergraph-Structured Knowledge Representation](<https://arxiv.org/abs/2503.21322>)**
  - Authors: Haoran Luo; Haihong E; Guanting Chen; Yandan Zheng; Xiaobao Wu; Yikai Guo; Qika Lin; Yu Feng; Zemin Kuang; Meina Song; Yifan Zhu; Luu Anh Tuan.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: huang2025hirag; question: Q-9; review: positional_only -->
- **[Retrieval-Augmented Generation with Hierarchical Knowledge](<https://arxiv.org/abs/2503.10150>)**
  - Authors: Haoyu Huang; Yongfeng Huang; Junjie Yang; Zhenyu Pan; Yongqiang Chen; Kaili Ma; Hongzhi Chen; James Cheng.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Yang2025SuperRAG; question: Q-9; review: positional_only -->
- **[SuperRAG: Beyond RAG with Layout-Aware Graph Modeling](<https://arxiv.org/abs/2503.04790>)**
  - Authors: Jeff Yang; Duy-Khanh Vu; Minh-Tien Nguyen; Xuan-Quang Nguyen; Linh Nguyen; Hung Le.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: edge2024graphrag; question: Q-9; review: positional_only -->
- **[From Local to Global: A Graph RAG Approach to Query-Focused Summarization](<https://arxiv.org/abs/2404.16130>)**
  - Authors: Darren Edge; Ha Trinh; Newman Cheng; Joshua Bradley; Alex Chao; Apurva Mody; Steven Truitt; Dasha Metropolitansky; Robert Osazuwa Ness; Jonathan Larson.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: guo2024lightrag; question: Q-9; review: positional_only -->
- **[LightRAG: Simple and Fast Retrieval-Augmented Generation](<https://arxiv.org/abs/2410.05779>)**
  - Authors: Zirui Guo; Lianghao Xia; Yanhua Yu; Tu Ao; Chao Huang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<a id="q-10"></a>

#### Q-10. How should knowledge be built, updated, repaired, and withdrawn?

*Focal question.*

<!-- record: zhou2026meshrag; question: Q-10; review: positional_only -->
- **[Collision to Cognition: Hash-Driven Graph Construction for Efficient RAG](<https://doi.org/10.18653/v1/2026.acl-long.1156>)**
  - Authors: Chuang Zhou; Zheng Yuan; Linhao Luo; Zhaozhuo Xu; Yilin Xiao; Junnan Dong; Siyu An; di Yin; Xing Sun; Xiao Huang.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: fan2026minirag; question: Q-10; review: positional_only -->
- **[MiniRAG: A Lightweight RAG system with Small Language Models](<https://doi.org/10.18653/v1/2026.acl-long.1721>)**
  - Authors: Tianyu Fan; Jingyuan Wang; Xubin Ren; Chao Huang.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: zerhoudi2026nuggetindex; question: Q-10; review: positional_only -->
- **[NuggetIndex: Governed Atomic Retrieval for Maintainable RAG](<https://sigir2026.org/en-AU/pages/program/accepted-papers>)**
  - Authors: Saber Zerhoudi; Michael Granitzer; Jelena Mitrović.
  - Venue / outlet: **SIGIR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Huang2025How; question: Q-10; review: positional_only -->
- **[How to Mitigate Information Loss in Knowledge Graphs for GraphRAG: Leveraging Triple Context Restoration and Query-Driven Feedback](<https://arxiv.org/abs/2501.15378>)**
  - Authors: Manzong Huang; Chenyang Bu; Yi He; Xindong Wu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Huang2025KET; question: Q-10; review: positional_only -->
- **[KET-RAG: A Cost-Efficient Multi-Granular Indexing Framework for Graph-RAG](<https://doi.org/10.1145/3711896.3737012>)**
  - Authors: Yiqian Huang; Shiqi Zhang; Xiaokui Xiao.
  - Venue / outlet: **KDD (Vol. 2)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Kim2025ReGraphRAG; question: Q-10; review: positional_only -->
- **[ReGraphRAG: Reorganizing Fragmented Knowledge Graphs for Multi-Perspective Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2025.findings-emnlp.290>)**
  - Authors: Soohyeong Kim; Seok Jun Hwang; JungHyoun Kim; Jeonghyeon Park; Yong Suk Choi.
  - Venue / outlet: **Findings of EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: difallah2025wikirag; question: Q-10; review: positional_only -->
- **[WikiRAG: Revisiting Wikidata KGC Datasets with Community Updates and Retrieval-Augmented Generation](<https://doi.org/10.1145/3711896.3737444>)**
  - Authors: Djellel Difallah.
  - Venue / outlet: **KDD (Vol. 2)** · Year: **2025**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-a3"></a>

### A3. Retrieval and evidence-set construction

Focus: Matching; complementarity; retrieval cost.

Questions: [Q-11](#q-11) · [Q-12](#q-12) · [Q-13](#q-13).

<a id="q-11"></a>

#### Q-11. How should queries be matched to candidate evidence?

*Focal question.*

<!-- record: zhang2026flowrag; question: Q-11; review: positional_only -->
- **[FlowRAG: Continual Learning for Dynamic Retriever in Retrieval-Augmented Generation](<https://doi.org/10.1145/3774904.3792361>)**
  - Authors: Senlei Zhang; Tongjun Shi; Dandan Song; Luan Zhang; Shuhao Zhang; Xiaofei Liao; Hai Jin.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Chandra2026LURE; question: Q-11; review: positional_only -->
- **[LURE-RAG: Lightweight Utility-driven Reranking for Efficient RAG](<https://arxiv.org/abs/2601.19535>)**
  - Authors: Manish Chandra; Debasis Ganguly; Iadh Ounis.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Wu2026Optimizing; question: Q-11; review: positional_only -->
- **[Optimizing RAG Rerankers with LLM Feedback via Reinforcement Learning](<https://doi.org/10.18653/v1/2026.acl-long.1406>)**
  - Authors: Yuhang Wu; Xiangqing Shen; Fanfan Wang; Cangqi Zhou; Zhen Wu; Xinyu Dai; Rui Xia.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: zhou2026qafd; question: Q-11; review: positional_only -->
- **[Query-Aware Flow Diffusion for Graph-Based RAG with Retrieval Guarantees](<https://openreview.net/forum?id=n28wnc2QTc>)**
  - Authors: Zhuoping Zhou; Davoud Ataee Tarzanagh; Sima Didari; Wenjun Hu; Baruch Gutow; Oxana Verkholyak; Masoud Faraki; Heng Hao; Hankyu Moon; Seungjai Min.
  - Venue / outlet: **ICLR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: yu2026stem; question: Q-11; review: positional_only -->
- **[STEM: Structure-Tracing Evidence Mining for Knowledge Graphs-Driven Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2026.acl-long.329>)**
  - Authors: Peng Yu; En Xu; Bin Chen; Haibiao Chen; Yinfei Xu.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: liu2026parallax; question: Q-11; review: positional_only -->
- **[Think Parallax: Solving Multi-Hop Problems via Multi-View Knowledge-Graph-Based Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2026.acl-long.1226>)**
  - Authors: Jinliang Liu; Jiale Bai; Shaoning Zeng.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Mavromatis2025BYOKG; question: Q-11; review: positional_only -->
- **[BYOKG-RAG: Multi-Strategy Graph Retrieval for Knowledge Graph Question Answering](<https://arxiv.org/abs/2507.04127>)**
  - Authors: Costas Mavromatis; Soji Adeshina; Vassilis N. Ioannidis; Zhen Han; Qi Zhu; Ian Robinson; Bryan Thompson; Huzefa Rangwala; George Karypis.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Zheng2025CoRAG; question: Q-11; review: positional_only -->
- **[CoRAG: Enhancing Hybrid Retrieval-Augmented Generation through a Cooperative Retriever Architecture](<https://doi.org/10.18653/v1/2025.findings-emnlp.872>)**
  - Authors: Zaiyi Zheng; Song Wang; Zihan Chen; Yaochen Zhu; Yinhan He; Liangjie Hong; Qi Guo; Jundong Li.
  - Venue / outlet: **Findings of EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Maghakian2025Embedding; question: Q-11; review: positional_only -->
- **[Embedding-Free RAG](<https://doi.org/10.18653/v1/2025.findings-emnlp.1360>)**
  - Authors: Jessica Maghakian; Raunak Sinha; Max Schettewi; Gunkirat Kaur.
  - Venue / outlet: **Findings of EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: mavromatis2025gnnrag; question: Q-11; review: positional_only -->
- **[GNN-RAG: Graph Neural Retrieval for Efficient Large Language Model Reasoning on Knowledge Graphs](<https://doi.org/10.18653/v1/2025.findings-acl.856>)**
  - Authors: Costas Mavromatis; George Karypis.
  - Venue / outlet: **Findings of ACL** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: gumbel2025; question: Q-11; review: positional_only -->
- **[Gumbel Reranking: Differentiable End-to-End Reranker Optimization](<https://arxiv.org/abs/2502.11116>)**
  - Authors: Siyuan Huang; Zhiyuan Ma; Jintao Du; Changhua Meng; Weiqiang Wang; Jingwen Leng; Minyi Guo; Zhouhan Lin.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Guo2025HASH; question: Q-11; review: positional_only -->
- **[HASH-RAG: Bridging Deep Hashing with Retriever for Efficient, Fine Retrieval and Augmented Generation](<https://arxiv.org/abs/2505.16133>)**
  - Authors: Jinyu Guo; Xunlei Chen; Qiyang Xia; Zhaokun Wang; Jie Ou; Libo Qin; Shunyu Yao; Wenhong Tian.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Santra2025HF; question: Q-11; review: positional_only -->
- **[HF-RAG: Hierarchical Fusion-based RAG with Multiple Sources and Rankers](<https://doi.org/10.1145/3746252.3760942>)**
  - Authors: Payel Santra; Madhusudan Ghosh; Debasis Ganguly; Partha Basuchowdhuri; Sudip Kumar Naskar.
  - Venue / outlet: **CIKM** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Liu2025HopRAG; question: Q-11; review: positional_only -->
- **[HopRAG: Multi-Hop Reasoning for Logic-Aware Retrieval-Augmented Generation](<https://arxiv.org/abs/2502.12442>)**
  - Authors: Hao Liu; Zhengren Wang; Xi Chen; Zhiyu Li; Feiyu Xiong; Qinhan Yu; Wentao Zhang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: wang2025infogainrag; question: Q-11; review: positional_only -->
- **[InfoGain-RAG: Boosting Retrieval-Augmented Generation via Document Information Gain-based Reranking and Filtering](<https://arxiv.org/abs/2509.12765>)**
  - Authors: Zihan Wang; Zihan Liang; Zhou Shao; Yufei Ma; Huangyu Dai; Ben Chen; Lingtao Mao; Chenyi Lei; Yuqing Ding; Han Li.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Sun2025KERAG; question: Q-11; review: positional_only -->
- **[KERAG: Knowledge-Enhanced Retrieval-Augmented Generation for Advanced Question Answering](<https://arxiv.org/abs/2509.04716>)**
  - Authors: Yushi Sun; Kai Sun; Yifan Ethan Xu; Xiao Yang; Xin Luna Dong; Nan Tang; Lei Chen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Zhu2025Knowledge; question: Q-11; review: positional_only -->
- **[Knowledge Graph-Guided Retrieval Augmented Generation](<https://arxiv.org/abs/2502.06864>)**
  - Authors: Xiangrong Zhu; Yuexiang Xie; Yi Liu; Yaliang Li; Wei Hu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Liu2025MixRAG; question: Q-11; review: positional_only -->
- **[MixRAG : Mixture-of-Experts Retrieval-Augmented Generation for Textual Graph Understanding and Question Answering](<https://www.semanticscholar.org/paper/8c8fac22b0c1ede2eaacad82d5423c955299c094>)**
  - Authors: Lihui Liu; Jiayuan Ding; Subhabrata Mukherjee; Carl Yang.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: wang2025proprag; question: Q-11; review: positional_only -->
- **[PropRAG: Guiding Retrieval with Beam Search over Proposition Paths](<https://doi.org/10.18653/v1/2025.emnlp-main.317>)**
  - Authors: Jingjin Wang; Jiawei Han.
  - Venue / outlet: **EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: SPS_SIGIR_2025; question: Q-11; review: positional_only -->
- **[RankLLM: A Python Package for Reranking with LLMs](<https://dl.acm.org/doi/abs/10.1145/3726302.3730331>)**
  - Authors: Sahel Sharifymoghaddam; Ronak Pradeep; Andre Slavescu; Ryan Nguyen; Andrew Xu; Zijian Chen; Yilin Zhang; Yidi Chen; Jasper Xian; Jimmy Lin.
  - Venue / outlet: **SIGIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Lee2024HybGRAG; question: Q-11; review: positional_only -->
- **[HybGRAG: Hybrid Retrieval-Augmented Generation on Textual and Relational Knowledge Bases](<https://arxiv.org/abs/2412.16311>)**
  - Authors: Meng-Chieh Lee; Qi Zhu; Costas Mavromatis; Zhen Han; Soji Adeshina; Vassilis N. Ioannidis; Huzefa Rangwala; Christos Faloutsos.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: Xu2024List; question: Q-11; review: positional_only -->
- **[List-aware Reranking-Truncation Joint Model for Search and Retrieval-augmented Generation](<https://doi.org/10.1145/3589334.3645336>)**
  - Authors: Shicheng Xu; Liang Pang; Jun Xu; Huawei Shen; Xueqi Cheng.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: yoon2024listt5; question: Q-11; review: positional_only -->
- **[ListT5: Listwise Reranking with Fusion-in-Decoder Improves Zero-shot Retrieval](<https://arxiv.org/abs/2402.15838>)**
  - Authors: Soyoung Yoon; Eunbi Choi; Jiyeon Kim; Hyeongu Yun; Yireun Kim; Seung-won Hwang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: dsi2022; question: Q-11; review: positional_only -->
- **[Transformer Memory as a Differentiable Search Index](<https://arxiv.org/abs/2202.06991>)**
  - Authors: Yi Tay; Vinh Q. Tran; Mostafa Dehghani; Jianmo Ni; Dara Bahri; Harsh Mehta; Zhen Qin; Kai Hui; Zhe Zhao; Jai Gupta; Tal Schuster; William W. Cohen; Donald Metzler.
  - Venue / outlet: **arXiv (preprint)** · Year: **2022**.
  - Association review: [P](#how-to-use).

<a id="q-12"></a>

#### Q-12. Which combination of candidates supplies complementary evidence?

*Focal question.*

<!-- record: Cui2025CIRAG; question: Q-12; review: positional_only -->
- **[CIRAG: Retrieval-Augmented Language Model with Collective Intelligence](<https://doi.org/10.1145/3726302.3729921>)**
  - Authors: Chenxu Cui; Haihui Fan; Jinchao Zhang; Lin Shen; Bo Li; Weiping Wang.
  - Venue / outlet: **SIGIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Chen2025PathRAG; question: Q-12; review: positional_only -->
- **[PathRAG: Pruning Graph-based Retrieval Augmented Generation with Relational Paths](<https://arxiv.org/abs/2502.14902>)**
  - Authors: Boyu Chen; Zirui Guo; Zidan Yang; Yuluo Chen; Junze Chen; Zhenghao Liu; Chuan Shi; Cheng Yang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: lee2025setr; question: Q-12; review: positional_only -->
- **[Shifting from Ranking to Set Selection for Retrieval Augmented Generation](<https://doi.org/10.18653/v1/2025.acl-long.861>)**
  - Authors: Dahyun Lee; Yongrae Jo; Haeju Park; Moontae Lee.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-13"></a>

#### Q-13. How should retrieval utility, efficiency, and robustness be adapted?

*Focal question.*

<!-- record: shim2026ldar; question: Q-13; review: positional_only -->
- **[Beyond RAG vs. Long-Context: Learning Distraction-Aware Retrieval for Efficient Knowledge Grounding](<https://openreview.net/forum?id=c8CZWLy4T4>)**
  - Authors: Seong-Woong Shim; Myunsoo Kim; Jae Hyeon Cho; Byung-Jun Lee.
  - Venue / outlet: **ICLR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Liu2026Beyond; question: Q-13; review: positional_only -->
- **[Beyond Semantic Relevance: Counterfactual Risk Minimization for Robust Retrieval-Augmented Generation](<https://sigir2026.org/en-AU/pages/program/accepted-papers>)**
  - Authors: Peiyang Liu; Qiang Yan; Ziqiang Cui; Di Liang; Xi Wang; Wei Ye.
  - Venue / outlet: **SIGIR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Liu2026Rethinkinga; question: Q-13; review: positional_only -->
- **[Rethinking the Hidden Risk of Reranking: Achieving Risk-aware Reranking with Information Gain for RAG with LLMs](<https://doi.org/10.1145/3774904.3792085>)**
  - Authors: Zhizhao Liu; Zhihua Wen; Zhiliang Tian; Zhen Huang; Miaorong Zhu; Zimian Wei; Yifu Gao; Liang Ding; Dongsheng Li.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: sun2025dynamicrag; question: Q-13; review: positional_only -->
- **[DynamicRAG: Leveraging Outputs of Large Language Model as Feedback for Dynamic Reranking in Retrieval-Augmented Generation](<https://arxiv.org/abs/2505.07233>)**
  - Authors: Jiashuo Sun; Xianrui Zhong; Sizhe Zhou; Jiawei Han.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Jiang2025GainRAG; question: Q-13; review: positional_only -->
- **[GainRAG: Preference Alignment in Retrieval-Augmented Generation through Gain Signal Synthesis](<https://arxiv.org/abs/2505.18710>)**
  - Authors: Yi Jiang; Sendong Zhao; Jianbo Li; Haochun Wang; Bing Qin.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Qu2025Uplift; question: Q-13; review: positional_only -->
- **[Uplift-RAG: Uplift-Driven Knowledge Preference Alignment for Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2025.findings-emnlp.511>)**
  - Authors: Changle Qu; Sunhao Dai; Hengyi Cai; Yiyang Cheng; Jun Xu; Shuaiqiang Wang; Dawei Yin.
  - Venue / outlet: **Findings of EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: zhang2025utility; question: Q-13; review: positional_only -->
- **[Utility-Focused LLM Annotation for Retrieval and Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2025.emnlp-main.88>)**
  - Authors: Hengran Zhang; Minghao Tang; Keping Bi; Jiafeng Guo; Shihao Liu; Daiting Shi; Dawei Yin; Xueqi Cheng.
  - Venue / outlet: **EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-a4"></a>

### A4. Context assembly and provenance

Focus: Context budget; information loss; conflicting evidence.

Questions: [Q-14](#q-14) · [Q-15](#q-15) · [Q-16](#q-16) · [Q-17](#q-17).

<a id="q-14"></a>

#### Q-14. Which evidence should be retained within the available budget?

*Focal question.*

<!-- record: Chakraborty2025Principled; question: Q-14; review: positional_only -->
- **[Principled Context Engineering for RAG: Statistical Guarantees via Conformal Prediction](<https://link.springer.com/chapter/10.1007/978-3-032-21300-6_45>)**
  - Authors: Debashish Chakraborty; Eugene Yang; Daniel Khashabi; Dawn Lawrie; Kevin Duh.
  - Venue / outlet: **ECIR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Luo2025AttnComp; question: Q-14; review: positional_only -->
- **[AttnComp: Attention-Guided Adaptive Context Compression for Retrieval-Augmented Generation](<https://arxiv.org/abs/2509.17486>)**
  - Authors: Lvzhou Luo; Yixuan Cao; Ping Luo.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: cui2026corerag; question: Q-14; review: positional_only -->
- **[Less Is More: Elevating RAG via Performance-Driven Context Compression](<https://arxiv.org/abs/2508.19282>)**
  - Authors: Ziqiang Cui; Yunpeng Weng; Xing Tang; Peiyang Liu; Shiwei Li; Bowei He; Jiamin Chen; Yansen Zhang; Xiuqiang He; Chen Ma.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: chirkova2025provence; question: Q-14; review: positional_only -->
- **[Provence: efficient and robust context pruning for retrieval-augmented generation](<https://arxiv.org/abs/2501.16214>)**
  - Authors: Nadezhda Chirkova; Thibault Formal; Vassilina Nikoulina; Stéphane Clinchant.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-15"></a>

#### Q-15. In what form should retained evidence reach the generator?

*Focal question.*

<!-- record: louis2026oscar; question: Q-15; review: positional_only -->
- **[OSCAR: Online Soft Compression for RAG](<https://openreview.net/forum?id=ideKAUWvFE>)**
  - Authors: Maxime Louis; Thibault Formal; Hervé Déjean; Stéphane Clinchant.
  - Venue / outlet: **ICLR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Liu2026Rethinking; question: Q-15; review: positional_only -->
- **[Rethinking Soft Compression in Retrieval-Augmented Generation: A Query-Conditioned Selector Perspective](<https://doi.org/10.1145/3774904.3792700>)**
  - Authors: Yunhao Liu; Zian Jia; Xinyu Gao; Kanjun Xu; Yun Xiong.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: rau2025cocom; question: Q-15; review: positional_only -->
- **[Context Embeddings for Efficient Answer Generation in Retrieval-Augmented Generation](<https://doi.org/10.1145/3701551.3703527>)**
  - Authors: David Rau; Shuai Wang; Hervé Déjean; Stéphane Clinchant; Jaap Kamps.
  - Venue / outlet: **WSDM** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: chen2025ecorag; question: Q-15; review: positional_only -->
- **[ECoRAG: Evidentiality-guided Compression for Long Context RAG](<https://arxiv.org/abs/2506.05167>)**
  - Authors: Yeonseok Jeong; Jinsu Kim; Dohyeon Lee; Seung-won Hwang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Guo2025Enhancing; question: Q-15; review: positional_only -->
- **[Enhancing RAG Efficiency with Adaptive Context Compression](<https://arxiv.org/abs/2507.22931>)**
  - Authors: Shuyu Guo; Shuo Zhang; Zhaochun Ren.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Chawla2025FB; question: Q-15; review: positional_only -->
- **[FB-RAG: Improving RAG with Forward and Backward Lookup](<https://arxiv.org/abs/2505.17206>)**
  - Authors: Kushal Chawla; Alfy Samuel; Anoop Kumar; Daben Liu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: wu2025hclek; question: Q-15; review: positional_only -->
- **[HCLeK: Hierarchical Compression of Legal Knowledge for Retrieval-Augmented Generation](<https://doi.org/10.1145/3746252.3760925>)**
  - Authors: Jianhui Yang; Huanghai Liu; Mingruo Yuan; YiRan Hu; Yun Liu; Weixing Shen; Ben Kao.
  - Venue / outlet: **CIKM** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Jin2025Hierarchical; question: Q-15; review: positional_only -->
- **[Hierarchical Document Refinement for Long-context Retrieval-augmented Generation](<https://arxiv.org/abs/2505.10413>)**
  - Authors: Jiajie Jin; Xiaoxi Li; Guanting Dong; Yuyao Zhang; Yutao Zhu; Yongkang Wu; Zhonghua Li; Qi Ye; Zhicheng Dou.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Chen2025LIR3AG; question: Q-15; review: positional_only -->
- **[LIR$^3$AG: A Lightweight Rerank Reasoning Strategy Framework for Retrieval-Augmented Generation](<https://arxiv.org/abs/2512.18329>)**
  - Authors: Guo Chen; Junjie Huang; Huaijin Xie; Fei Sun; Tao Jia.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: li2025oreo; question: Q-15; review: positional_only -->
- **[Oreo: A Plug-in Context Reconstructor to Enhance Retrieval-Augmented Generation](<https://doi.org/10.1145/3731120.3744590>)**
  - Authors: Sha Li; Naren Ramakrishnan.
  - Venue / outlet: **ICTIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Yao2025ParetoRAG; question: Q-15; review: positional_only -->
- **[ParetoRAG: Leveraging Sentence-Context Attention for Robust and Efficient Retrieval-Augmented Generation](<https://arxiv.org/abs/2502.08178>)**
  - Authors: Ruobing Yao; Yifei Zhang; Shuang Song; Yuhua Liu; Neng Gao; Chenyang Tu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: lin2026pisco; question: Q-15; review: positional_only -->
- **[PISCO: Pretty Simple Compression for Retrieval-Augmented Generation](<https://arxiv.org/abs/2501.16075>)**
  - Authors: Maxime Louis; Hervé Déjean; Stéphane Clinchant.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: wu2025rankcot; question: Q-15; review: positional_only -->
- **[RankCoT: Refining Knowledge for Retrieval-Augmented Generation through Ranking Chain-of-Thoughts](<https://arxiv.org/abs/2502.17888>)**
  - Authors: Mingyan Wu; Zhenghao Liu; Yukun Yan; Xinze Li; Shi Yu; Zheni Zeng; Yu Gu; Ge Yu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: lin2025refrag; question: Q-15; review: positional_only -->
- **[REFRAG: Rethinking RAG based Decoding](<https://arxiv.org/abs/2509.01092>)**
  - Authors: Xiaoqiang Lin; Aritra Ghosh; Bryan Kian Hsiang Low; Anshumali Shrivastava; Vijai Mohan.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-16"></a>

#### Q-16. How should evidence be ordered, grouped, and connected?

*Focal question.*

<!-- record: Jin2026Attention; question: Q-16; review: positional_only -->
- **[Attention Weights as an Indicator: Analyzing and Improving Document Utilization in Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2026.acl-long.1245>)**
  - Authors: Jing Jin; Yuhan Song; Wen Luo; Houfeng Wang.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: yuan2026higoe; question: Q-16; review: positional_only -->
- **[HiGoE: Hierarchical Graph of Evidence to Enhance Retrieval-Augmented Generation for Long-context Summarization](<https://doi.org/10.18653/v1/2026.acl-long.902>)**
  - Authors: Long Yuan; Kaiwen Tian; Zi Chen; Bolong Zheng; Chuan Ma.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Zhang2026Stable; question: Q-16; review: positional_only -->
- **[Stable-RAG: Mitigating Retrieval-Permutation-Induced Hallucinations in Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2026.acl-long.1188>)**
  - Authors: Qianchi Zhang; Hainan Zhang; Liang Pang; Hong-Wei Zheng; Zhiming Zheng.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Wang2025BEE; question: Q-16; review: positional_only -->
- **[BEE-RAG: Balanced Entropy Engineering for Retrieval-Augmented Generation](<https://arxiv.org/abs/2508.05100>)**
  - Authors: Yuhao Wang; Ruiyang Ren; Yucheng Wang; Jing Liu; Wayne Xin Zhao; Hua Wu; Haifeng Wang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Hong2025Context; question: Q-16; review: positional_only -->
- **[Context-Aware Fine-Grained Graph RAG for Query-Focused Summarization](<https://doi.org/10.1145/3746252.3760935>)**
  - Authors: Yubin Hong; ChaoFan Li; Jingyi Zhang; Yingxia Shao.
  - Venue / outlet: **CIKM** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Ju2025Controlled; question: Q-16; review: positional_only -->
- **[Controlled Retrieval-augmented Context Evaluation for Long-form RAG](<https://arxiv.org/abs/2506.20051>)**
  - Authors: Jia-Huei Ju; Suzan Verberne; Maarten de Rijke; Andrew Yates.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Lee2025CORD; question: Q-16; review: positional_only -->
- **[CORD: Balancing COnsistency and Rank Distillation for Robust Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2025.naacl-short.66>)**
  - Authors: Youngwon Lee; Seung-won Hwang; Daniel F Campos; Filip Graliński; Zhewei Yao; Yuxiong He.
  - Venue / outlet: **NAACL (Short Papers)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Cuconasu2025Do; question: Q-16; review: positional_only -->
- **[Do RAG Systems Really Suffer From Positional Bias?](<https://doi.org/10.18653/v1/2025.emnlp-main.1422>)**
  - Authors: Florin Cuconasu; Simone Filice; Guy Horowitz; Yoelle Maarek; Fabrizio Silvestri.
  - Venue / outlet: **EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Hutter2025Lost; question: Q-16; review: positional_only -->
- **[Lost but Not Only in the Middle: Positional Bias in Retrieval Augmented Generation](<https://link.springer.com/chapter/10.1007/978-3-031-88708-6_16>)**
  - Authors: Jan Hutter; David Rau; Maarten Marx; Jaap Kamps.
  - Venue / outlet: **ECIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-17"></a>

#### Q-17. How should conflicts, reliability, and provenance be exposed?

*Focal question.*

<!-- record: ye2026tcr; question: Q-17; review: positional_only -->
- **[Seeing through the Conflict: Transparent Knowledge Conflict Handling in Retrieval-Augmented Generation](<https://arxiv.org/abs/2601.06842>)**
  - Authors: Hua Ye; Siyuan Chen; Ziqi Zhong; Canran Xiao; Haoliang Zhang; Yuhan Wu; Fei Shen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: li2025bordarag; question: Q-17; review: positional_only -->
- **[BordaRAG: Resolving Knowledge Conflict in Retrieval-Augmented Generation via Borda Voting Process](<https://doi.org/10.1145/3746252.3761038>)**
  - Authors: Yuxin Li; Chen Xu; Jun Xu; Ji-Rong Wen.
  - Venue / outlet: **CIKM** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: wang2025astute; question: Q-17; review: positional_only -->
- **[Astute RAG: Overcoming Imperfect Retrieval Augmentation and Knowledge Conflicts for Large Language Models](<https://arxiv.org/abs/2410.07176>)**
  - Authors: Fei Wang; Xingchen Wan; Ruoxi Sun; Jiefeng Chen; Sercan Ö. Arık.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-a5"></a>

### A5. Evidence-conditioned generation

Focus: Knowledge conflict; evidence use; controllability.

Questions: [Q-18](#q-18) · [Q-19](#q-19) · [Q-20](#q-20) · [Q-21](#q-21).

<a id="q-18"></a>

#### Q-18. Where and how should external evidence condition generation?

*Focal question.*

<!-- record: Liang2026FedMosaic; question: Q-18; review: positional_only -->
- **[FedMosaic: Federated Retrieval-Augmented Generation via Parametric Adapters](<https://sigir2026.org/en-AU/pages/program/accepted-papers>)**
  - Authors: Zhilin Liang; Yuxiang Wang; Zimu Zhou; Hainan Zhang; Boyi Liu; Yongxin Tong.
  - Venue / outlet: **SIGIR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: liu2026mergeprag; question: Q-18; review: positional_only -->
- **[MergePRAG: Orthogonal Merging of Passage-experts for Multi-hop Parametric RAG](<https://openreview.net/forum?id=FSL1J2gmJV>)**
  - Authors: Xuebing Liu; Shanbao Qiao; Roseline Nyange; Dongwook Min; Hyun Kim; Seung-Hoon Na.
  - Venue / outlet: **ICLR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: su2025parametric; question: Q-18; review: positional_only -->
- **[Parametric Retrieval Augmented Generation](<https://doi.org/10.1145/3726302.3729957>)**
  - Authors: Weihang Su; Yichen Tang; Qingyao Ai; Junxi Yan; Changyue Wang; Hongning Wang; Ziyi Ye; Yujia Zhou; Yiqun Liu.
  - Venue / outlet: **SIGIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: yen2024cepe; question: Q-18; review: positional_only -->
- **[Long-Context Language Modeling with Parallel Context Encoding](<https://aclanthology.org/2024.acl-long.142/>)**
  - Authors: Howard Yen; Tianyu Gao; Danqi Chen.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: Cheng2024xRAG; question: Q-18; review: positional_only -->
- **[xRAG: Extreme Context Compression for Retrieval-augmented Generation with One Token](<https://arxiv.org/abs/2405.13792>)**
  - Authors: Xin Cheng; Xun Wang; Xingxing Zhang; Tao Ge; Si-Qing Chen; Furu Wei; Huishuai Zhang; Dongyan Zhao.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: izacard2021leveraging; question: Q-18; review: positional_only -->
- **[Leveraging Passage Retrieval with Generative Models for Open Domain Question Answering](<https://doi.org/10.18653/v1/2021.eacl-main.74>)**
  - Authors: Gautier Izacard; Edouard Grave.
  - Venue / outlet: **EACL** · Year: **2021**.
  - Association review: [P](#how-to-use).

<a id="q-19"></a>

#### Q-19. How should generation reconcile external evidence and parametric knowledge?

*Focal question.*

<!-- record: sui2026ecd; question: Q-19; review: positional_only -->
- **[ECD: Evidence-guided Contrastive Decoding in Retrieval-Augmented Generation with Accurate Knowledge Reference Adjustment](<https://doi.org/10.1609/aaai.v40i39.40591>)**
  - Authors: Yize Sui; Yan Xu; Kun Hu; Jing Ren; Wenjing Yang.
  - Venue / outlet: **AAAI** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Lee2026GRAD; question: Q-19; review: positional_only -->
- **[GRAD: Generalizing RAG Adaptation with Decoding](<https://doi.org/10.18653/v1/2026.acl-long.2099>)**
  - Authors: Youngwon Lee; Seung-won Hwang; Zhewei Yao; Yuxiong He.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: zhao2026guarant; question: Q-19; review: positional_only -->
- **[Guaranteeing Knowledge Integration with Joint Decoding for Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2026.acl-long.192>)**
  - Authors: Zhengyi Zhao; Shubo Zhang; Zezhong Wang; Yuxi Zhang; Huimin Wang; Yutian Zhao; Yefeng Zheng; Binyang Li; Kam-Fai Wong; Xian Wu.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Mo2026OpenDecoder; question: Q-19; review: positional_only -->
- **[OpenDecoder: Open Large Language Model Decoding to Incorporate Document Quality in RAG](<https://doi.org/10.1145/3774904.3792524>)**
  - Authors: Fengran Mo; Zhan Su; Yuchen Hui; Jinghan Zhang; Jia Ao Sun; Zheyuan Liu; Chao Zhang; Tetsuya Sakai; Jian-Yun Nie.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Han2025Fine; question: Q-19; review: positional_only -->
- **[Fine-grained Knowledge Enhancement for Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2025.findings-acl.522>)**
  - Authors: Jingxuan Han; Zhendong Mao; Yi Liu; Yexuan Che; Zheren Fu; Quan Wang.
  - Venue / outlet: **Findings of ACL** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-20"></a>

#### Q-20. How should the generator learn useful and faithful evidence-conditioned behavior?

*Focal question.*

<!-- record: Song2025Aligning; question: Q-20; review: positional_only -->
- **[Aligning Extraction and Generation for Robust Retrieval-Augmented Generation](<https://doi.org/10.1145/3773966.3777939>)**
  - Authors: Hwanjun Song; Jeonghwan Choi; Minseok Kim.
  - Venue / outlet: **WSDM** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Wu2026Conflict; question: Q-20; review: positional_only -->
- **[Conflict-Aware RAG: Multi-Stage Learning with Conflict Signals for Robust Retrieval-Augmented Generation](<https://doi.org/10.1145/3774904.3792289>)**
  - Authors: Haiyan Wu; Chenchen Wang; Chaoqun Sun; Chengxiong Lu; Zhiqiang Zhang; Yanhong Chen.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Yuan2026Efficient; question: Q-20; review: positional_only -->
- **[Efficient Prior-Guided Reasoning for Robust Retrieval-Augmented Generation under Conflicts](<https://doi.org/10.18653/v1/2026.acl-long.1013>)**
  - Authors: Xiaowei Yuan; Ziyang Huang; Zhao Yang; Yequan Wang; Jun Zhao; Kang Liu.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: lin2026knowledgeabler1; question: Q-20; review: positional_only -->
- **[Resisting Contextual Interference in RAG via Parametric-Knowledge Reinforcement](<https://openreview.net/forum?id=6Qc6sO1jh9>)**
  - Authors: Chenyu Lin; Yilin Wen; Du Su; Hexiang Tan; Fei Sun; Muhan Chen; Chenfu Bao; Zhonghou Lv.
  - Venue / outlet: **ICLR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Choi2025Conflict; question: Q-20; review: positional_only -->
- **[Conflict-Aware Soft Prompting for Retrieval-Augmented Generation](<https://arxiv.org/abs/2508.15253>)**
  - Authors: Eunseong Choi; June Park; Hyeri Lee; Jongwuk Lee.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Chen2025DRAG; question: Q-20; review: positional_only -->
- **[DRAG: Distilling RAG for SLMs from LLMs to Transfer Knowledge and Mitigate Hallucination via Evidence and Graph-based Distillation](<https://arxiv.org/abs/2506.01954>)**
  - Authors: Jennifer Chen; Aidar Myrzakhan; Yaxin Luo; Hassaan Muhammad Khan; Sondos Mahmoud Bsharat; Zhiqiang Shen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: zhang2025faithfulrag; question: Q-20; review: positional_only -->
- **[FaithfulRAG: Fact-Level Conflict Modeling for Context-Faithful Retrieval-Augmented Generation](<https://arxiv.org/abs/2506.08938>)**
  - Authors: Qinggang Zhang; Zhishang Xiang; Yilin Xiao; Le Wang; Junhui Li; Xinrun Wang; Jinsong Su.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Jiao2025HIRAG; question: Q-20; review: positional_only -->
- **[HIRAG: Hierarchical-Thought Instruction-Tuning Retrieval-Augmented Generation](<https://arxiv.org/abs/2507.05714>)**
  - Authors: YiHan Jiao; ZheHao Tan; Dan Yang; DuoLin Sun; Jie Feng; Yue Shen; Jian Wang; Peng Wei.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: tu2025rbft; question: Q-20; review: positional_only -->
- **[Robust Fine-tuning for Retrieval Augmented Generation against Retrieval Defects](<https://doi.org/10.1145/3726302.3730078>)**
  - Authors: Yiteng Tu; Weihang Su; Yujia Zhou; Yiqun Liu; Qingyao Ai.
  - Venue / outlet: **SIGIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Liu2025RoseRAG; question: Q-20; review: positional_only -->
- **[RoseRAG: Robust Retrieval-augmented Generation with Small-scale LLMs via Margin-aware Preference Optimization](<https://arxiv.org/abs/2502.10993>)**
  - Authors: Tianci Liu; Haoxiang Jiang; Tianze Wang; Ran Xu; Yue Yu; Linjun Zhang; Tuo Zhao; Haoyu Wang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: huang2025selfaug; question: Q-20; review: positional_only -->
- **[SelfAug: Mitigating Catastrophic Forgetting in Retrieval-Augmented Generation via Distribution Self-Alignment](<https://arxiv.org/abs/2509.03934>)**
  - Authors: Yuqing Huang; Rongyang Zhang; Qimeng Wang; Chengqiang Lu; Yan Gao; Yi Wu; Yao Hu; Xuyang Zhi; Guiquan Liu; Xin Li; Hao Wang; Enhong Chen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Bhushan2025Systematic; question: Q-20; review: positional_only -->
- **[Systematic Knowledge Injection into Large Language Models via Diverse Augmentation for Domain-Specific RAG](<https://arxiv.org/abs/2502.08356>)**
  - Authors: Kushagra Bhushan; Yatin Nandwani; Dinesh Khandelwal; Sonam Gupta; Gaurav Pandey; Dinesh Raghu; Sachindra Joshi.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Dong2024Understand; question: Q-20; review: positional_only -->
- **[Understand What LLM Needs: Dual Preference Alignment for Retrieval-Augmented Generation](<https://doi.org/10.1145/3696410.3714717>)**
  - Authors: Guanting Dong; Yutao Zhu; Chenghao Zhang; Zechen Wang; Ji-Rong Wen; Zhicheng Dou.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: parag2024; question: Q-20; review: positional_only -->
- **[PA-RAG: RAG Alignment via Multi-Perspective Preference Optimization](<https://arxiv.org/abs/2412.14510>)**
  - Authors: Jiayi Wu; Hengyi Cai; Lingyong Yan; Hao Sun; Xiang Li; Shuaiqiang Wang; Dawei Yin; Ming Gao.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: asai2024selfrag; question: Q-20; review: positional_only -->
- **[Self-RAG: Learning to Retrieve, Generate, and Critique through Self-Reflection](<https://proceedings.iclr.cc/paper_files/paper/2024/hash/25f7be9694d7b32d5cc670927b8091e1-Abstract-Conference.html>)**
  - Authors: Akari Asai; Zeqiu Wu; Yizhong Wang; Avirup Sil; Hannaneh Hajishirzi.
  - Venue / outlet: **ICLR** · Year: **2024**.
  - Association review: [P](#how-to-use).

<a id="q-21"></a>

#### Q-21. How can evidence use be controlled and diagnosed?

*Focal question.*

<!-- record: Xiong2026Toward; question: Q-21; review: positional_only -->
- **[Toward Faithful Retrieval-Augmented Generation with Sparse Autoencoders](<https://openreview.net/forum?id=hgBZP67BkP>)**
  - Authors: Guangzhi Xiong; Zhenghao He; Bohan Liu; Sanchit Sinha; Aidong Zhang.
  - Venue / outlet: **ICLR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: liu2025selfelicit; question: Q-21; review: positional_only -->
- **[SelfElicit: Your Language Model Secretly Knows Where is the Relevant Evidence](<https://arxiv.org/abs/2502.08767>)**
  - Authors: Zhining Liu; Rana Ali Amjad; Ravinarayana Adkathimar; Tianxin Wei; Hanghang Tong.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Wang2025Unveiling; question: Q-21; review: positional_only -->
- **[Unveiling Knowledge Utilization Mechanisms in LLM-based Retrieval-Augmented Generation](<https://doi.org/10.1145/3726302.3730112>)**
  - Authors: Yuhao Wang; Ruiyang Ren; Yucheng Wang; Wayne Xin Zhao; Jing Liu; Hua Wu; Haifeng Wang.
  - Venue / outlet: **SIGIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-a6"></a>

### A6. Response quality and accountability

Focus: Coverage; claim support; uncertainty; repair.

Questions: [Q-22](#q-22) · [Q-23](#q-23) · [Q-24](#q-24) · [Q-25](#q-25).

<a id="q-22"></a>

#### Q-22. What should the answer cover, and in what form?

*Focal question.*

<!-- record: Wang2026Reinforced; question: Q-22; review: positional_only -->
- **[Reinforced Informativeness Optimization for Long-Form Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2026.acl-long.612>)**
  - Authors: Yuhao Wang; Ruiyang Ren; Yucheng Wang; Xin Zhao; Jing Liu; Hua Wu; Haifeng Wang.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: chen2025ri2ver; question: Q-22; review: positional_only -->
- **[Inter-Passage Verification for Multi-evidence Multi-answer QA](<https://arxiv.org/abs/2506.00425>)**
  - Authors: Bingsen Chen; Shengjie Wang; Xi Ye; Chen Zhao.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-23"></a>

#### Q-23. Which sources support each substantive claim?

*Focal question.*

<!-- record: certa2026; question: Q-23; review: positional_only -->
- **["I Don't Know" – Towards Appropriate Trust with Certainty-Aware Retrieval Augmented Generation](<https://arxiv.org/abs/2605.00957>)**
  - Authors: Daan Di Scala; Maaike de Boer; Pınar Yolum.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: jiang2026citeguard; question: Q-23; review: positional_only -->
- **[CiteGuard: Conformal False-Discovery Control for Faithful Retrieval-Augmented Generation](<https://github.com/XiangyuJiang01/citeguard>)**
  - Authors: Xiangyu Jiang.
  - Venue / outlet: **ICML** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: dassen2026factum; question: Q-23; review: positional_only -->
- **[FACTUM: Mechanistic Detection of Citation Hallucination in Long-Form RAG](<https://arxiv.org/abs/2601.05866>)**
  - Authors: Maxime Dassen; Rebecca Kotula; Kenton Murray; Andrew Yates; Dawn Lawrie; Efsun Kayi; James Mayfield; Kevin Duh.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Maheshwari2025CiteFix; question: Q-23; review: positional_only -->
- **[CiteFix: Enhancing RAG Accuracy Through Post-Processing Citation Correction](<https://arxiv.org/abs/2504.15629>)**
  - Authors: Harsh Maheshwari; Srikanth Tenneti; Alwarappan Nakkiran.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: franq2025; question: Q-23; review: positional_only -->
- **[Faithfulness-Aware Uncertainty Quantification for Fact-Checking the Output of Retrieval Augmented Generation](<https://arxiv.org/abs/2505.21072>)**
  - Authors: Ekaterina Fadeeva; Aleksandr Rubashevskii; Dzianis Piatrashyn; Roman Vashurin; Shehzaad Dhuliawala; Artem Shelmanov; Timothy Baldwin; Preslav Nakov; Mrinmaya Sachan; Maxim Panov.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: gao2023alce; question: Q-23; review: positional_only -->
- **[Enabling Large Language Models to Generate Text with Citations](<https://arxiv.org/abs/2305.14627>)**
  - Authors: Tianyu Gao; Howard Yen; Jiatong Yu; Danqi Chen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2023**.
  - Association review: [P](#how-to-use).

<a id="q-24"></a>

#### Q-24. When should the system answer, qualify, clarify, or abstain?

*Focal question.*

<!-- record: triantafyllopoulos2026kbood; question: Q-24; review: positional_only -->
- **[Knowing When Not to Answer: Lightweight KB-Aligned OOD Detection for Safe RAG](<https://doi.org/10.18653/v1/2026.acl-long.740>)**
  - Authors: Ilias Triantafyllopoulos; Renyi Qu; Salvatore Giorgi; Brenda Curtis; Lyle Ungar; João Sedoc.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: yeh2026lumina; question: Q-24; review: positional_only -->
- **[LUMINA: Detecting Hallucinations in RAG System with Context–Knowledge Signals](<https://openreview.net/forum?id=oJgNNBNEJM>)**
  - Authors: Samuel Yeh; Sharon Li; Tanwi Mallick.
  - Venue / outlet: **ICLR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: lu2026tpa; question: Q-24; review: positional_only -->
- **[TPA: Next Token Probability Attribution for Detecting Hallucinations in RAG](<https://doi.org/10.18653/v1/2026.acl-long.1159>)**
  - Authors: Pengqian Lu; Jie Lu; Anjin Liu; Guangquan Zhang.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Ren2026When; question: Q-24; review: positional_only -->
- **[When to Trust: A Causality-Aware Calibration Framework for Accurate Knowledge Graph Retrieval-Augmented Generation](<https://doi.org/10.1145/3774904.3792358>)**
  - Authors: Jing Ren; Bowen Li; Ziqi Xu; Xikun Zhang; Haytham Fayek; Xiaodong Li.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Sun2025Divide; question: Q-24; review: positional_only -->
- **[Divide-Then-Align: Honest Alignment based on the Knowledge Boundary of RAG](<https://arxiv.org/abs/2505.20871>)**
  - Authors: Xin Sun; Jianan Xie; Zhongqi Chen; Qiang Liu; Shu Wu; Yuehe Chen; Bowen Song; Weiqiang Wang; Zilei Wang; Liang Wang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: soudani2025axiomue; question: Q-24; review: positional_only -->
- **[Why Uncertainty Estimation Methods Fall Short in RAG: An Axiomatic Analysis](<https://arxiv.org/abs/2505.07459>)**
  - Authors: Heydar Soudani; Evangelos Kanoulas; Faegheh Hasibi.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-25"></a>

#### Q-25. How should a response be checked and repaired without introducing new errors?

*Focal question.*

<!-- record: jiang2026citeguard; question: Q-25; review: positional_only -->
- **[CiteGuard: Conformal False-Discovery Control for Faithful Retrieval-Augmented Generation](<https://github.com/XiangyuJiang01/citeguard>)**
  - Authors: Xiangyu Jiang.
  - Venue / outlet: **ICML** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: dassen2026factum; question: Q-25; review: positional_only -->
- **[FACTUM: Mechanistic Detection of Citation Hallucination in Long-Form RAG](<https://arxiv.org/abs/2601.05866>)**
  - Authors: Maxime Dassen; Rebecca Kotula; Kenton Murray; Andrew Yates; Dawn Lawrie; Efsun Kayi; James Mayfield; Kevin Duh.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Maheshwari2025CiteFix; question: Q-25; review: positional_only -->
- **[CiteFix: Enhancing RAG Accuracy Through Post-Processing Citation Correction](<https://arxiv.org/abs/2504.15629>)**
  - Authors: Harsh Maheshwari; Srikanth Tenneti; Alwarappan Nakkiran.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="domain-b"></a>

## B. System-level composition and optimization

How do local decisions interact under task and resource constraints?

<a id="group-b1"></a>

### B1. Composition, interfaces, and scheduling

Focus: Workflow coupling; shared-resource scheduling.

Questions: [Q-26](#q-26) · [Q-27](#q-27) · [Q-28](#q-28).

<a id="q-26"></a>

#### Q-26. How should RAG operations be composed into a complete workflow?

*Focal question.*

<!-- record: Xu2026PowerRAG; question: Q-26; review: positional_only -->
- **[PowerRAG: Building Smarter and More Accurate RAG Systems with OceanBase's Multi-modal Retrieval](<https://doi.org/10.1145/3788853.3801589>)**
  - Authors: Quanqing Xu; Chuanhui Yang; Feizhi Cai; Li Feng; Jiannan Ji; Zhifeng Yang; Guoping Wang; Yi Zhang.
  - Venue / outlet: **SIGMOD Companion** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Ko2025Cooperative; question: Q-26; review: positional_only -->
- **[Cooperative Retrieval-Augmented Generation for Question Answering: Mutual Information Exchange and Ranking by Contrasting Layers](<https://arxiv.org/abs/2512.10422>)**
  - Authors: Youmin Ko; Sungjong Seo; Hyunjoon Kim.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Cao2024LEGO; question: Q-26; review: positional_only -->
- **[LEGO-GraphRAG: Modularizing Graph-Based Retrieval-Augmented Generation for Design Space Exploration](<https://doi.org/10.14778/3748191.3748194>)**
  - Authors: Yukun Cao; Zengyi Gao; Zhiyang Li; Xike Xie; S. Kevin Zhou; Jianliang Xu.
  - Venue / outlet: **PVLDB** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: yan2024crag; question: Q-26; review: positional_only -->
- **[Corrective Retrieval Augmented Generation](<https://arxiv.org/abs/2401.15884>)**
  - Authors: Shi-Qi Yan; Jia-Chen Gu; Yun Zhu; Zhen-Hua Ling.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: Lee2024HybGRAG; question: Q-26; review: positional_only -->
- **[HybGRAG: Hybrid Retrieval-Augmented Generation on Textual and Relational Knowledge Bases](<https://arxiv.org/abs/2412.16311>)**
  - Authors: Meng-Chieh Lee; Qi Zhu; Costas Mavromatis; Zhen Han; Soji Adeshina; Vassilis N. Ioannidis; Huzefa Rangwala; Christos Faloutsos.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: trivedi2023interleaving; question: Q-26; review: positional_only -->
- **[Interleaving Retrieval with Chain-of-Thought Reasoning for Knowledge-Intensive Multi-Step Questions](<https://doi.org/10.18653/v1/2023.acl-long.557>)**
  - Authors: Harsh Trivedi; Niranjan Balasubramanian; Tushar Khot; Ashish Sabharwal.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2023**.
  - Association review: [P](#how-to-use).

<a id="q-27"></a>

#### Q-27. At which stages and through which interfaces should external knowledge enter the system?

*Focal question.*

<!-- record: Mridul2025AI4Contracts; question: Q-27; review: positional_only -->
- **[AI4Contracts: LLM &amp; RAG-Powered Encoding of Financial Derivative Contracts](<https://arxiv.org/abs/2506.01063>)**
  - Authors: Maruf Ahmed Mridul; Ian Sloyan; Aparna Gupta; Oshani Seneviratne.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Dong2025Decoupling; question: Q-27; review: positional_only -->
- **[Decoupling Knowledge and Context: An Efficient and Effective Retrieval Augmented Generation Framework via Cross Attention](<https://doi.org/10.1145/3696410.3714608>)**
  - Authors: Qian Dong; Qingyao Ai; Hongning Wang; Yiding Liu; Haitao Li; Weihang Su; Yiqun Liu; Tat-Seng Chua; Shaoping Ma.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: su2025parametric; question: Q-27; review: positional_only -->
- **[Parametric Retrieval Augmented Generation](<https://doi.org/10.1145/3726302.3729957>)**
  - Authors: Weihang Su; Yichen Tang; Qingyao Ai; Junxi Yan; Changyue Wang; Hongning Wang; Ziyi Ye; Yujia Zhou; Yiqun Liu.
  - Venue / outlet: **SIGIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Wang2025RAG; question: Q-27; review: positional_only -->
- **[RAG+: Enhancing Retrieval-Augmented Generation with Application-Aware Reasoning](<https://arxiv.org/abs/2506.11555>)**
  - Authors: Yu Wang; Shiwan Zhao; Zhihu Wang; Ming Fan; Xicheng Zhang; Yubo Zhang; Zhengfan Wang; Heyuan Huang; Ting Liu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: yen2024cepe; question: Q-27; review: positional_only -->
- **[Long-Context Language Modeling with Parallel Context Encoding](<https://aclanthology.org/2024.acl-long.142/>)**
  - Authors: Howard Yen; Tianyu Gao; Danqi Chen.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: Cheng2024xRAG; question: Q-27; review: positional_only -->
- **[xRAG: Extreme Context Compression for Retrieval-augmented Generation with One Token](<https://arxiv.org/abs/2405.13792>)**
  - Authors: Xin Cheng; Xun Wang; Xingxing Zhang; Tao Ge; Si-Qing Chen; Furu Wei; Huishuai Zhang; Dongyan Zhao.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: izacard2021leveraging; question: Q-27; review: positional_only -->
- **[Leveraging Passage Retrieval with Generative Models for Open Domain Question Answering](<https://doi.org/10.18653/v1/2021.eacl-main.74>)**
  - Authors: Gautier Izacard; Edouard Grave.
  - Venue / outlet: **EACL** · Year: **2021**.
  - Association review: [P](#how-to-use).

<!-- record: guu2020realm; question: Q-27; review: positional_only -->
- **[REALM: Retrieval-Augmented Language Model Pre-Training](<https://proceedings.mlr.press/v119/guu20a.html>)**
  - Authors: Kelvin Guu; Kenton Lee; Zora Tung; Panupong Pasupat; Ming-Wei Chang.
  - Venue / outlet: **ICML** · Year: **2020**.
  - Association review: [P](#how-to-use).

<a id="q-28"></a>

#### Q-28. How should retrieval and generation be scheduled within and across requests under a shared resource budget?

*Focal question.*

<!-- record: jin2026sara; question: Q-28; review: positional_only -->
- **[SARA: Selective and Adaptive Retrieval-augmented Generation with Context Compression](<https://doi.org/10.18653/v1/2026.acl-long.661>)**
  - Authors: Yiqiao Jin; Kartik Sharma; Vineeth Rakesh; Yingtong Dou; Menghai Pan; Mahashweta Das; Srijan Kumar.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Wen2026SpecCache; question: Q-28; review: positional_only -->
- **[SpecCache: Speculative KV Cache Reuse for Efficient RAG Serving](<https://doi.org/10.18653/v1/2026.acl-long.859>)**
  - Authors: Zijian Wen; Tao Zhang; Shuangwu Chen; Shenghao Ye; Yu Guo; Qirui Chen; Jingxian Shuai; Yunpeng Hou; Huasen He; Jian Yang.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Agarwal2025Cache; question: Q-28; review: positional_only -->
- **[Cache-Craft: Managing Chunk-Caches for Efficient Retrieval-Augmented Generation](<https://doi.org/10.1145/3725273>)**
  - Authors: Shubham Agarwal; Sai Sundaresan; Subrata Mitra; Debabrata Mahapatra; Archit Gupta; Rounak Sharma; Nirmal Joshua Kapu; Tong Yu; Shiv Saini.
  - Venue / outlet: **PACMMOD** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Yuan2025DepCache; question: Q-28; review: positional_only -->
- **[DepCache: A KV Cache Management Framework for GraphRAG with Dependency Attention](<https://doi.org/10.1145/3769778>)**
  - Authors: Hao Yuan; Xin Ai; Qiange Wang; Peizheng Li; Jiayang Yu; Chaoyi Chen; Xinbo Yang; Yanfeng Zhang; Zhenbo Fu; Yingyou Wen; Ge Yu.
  - Venue / outlet: **PACMMOD** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Jiang2025PipeRAG; question: Q-28; review: positional_only -->
- **[PipeRAG: Fast Retrieval-Augmented Generation via Adaptive Pipeline Parallelism](<https://doi.org/10.1145/3690624.3709194>)**
  - Authors: Wenqi Jiang; Shuai Zhang; Boran Han; Jie Wang; Bernie Wang; Tim Kraska.
  - Venue / outlet: **KDD (Vol. 1)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Zhu2025SubGCache; question: Q-28; review: positional_only -->
- **[SubGCache: Accelerating Graph-based RAG with Subgraph-level KV Cache](<https://arxiv.org/abs/2505.10951>)**
  - Authors: Qiuyu Zhu; Liang Zhang; Qianxiong Xu; Cheng Long; Jie Zhang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: chen2025and; question: Q-28; review: positional_only -->
- **[When and How to Augment Your Input: Question Routing Helps Balance the Accuracy and Efficiency of Large Language Models](<https://doi.org/10.18653/v1/2025.findings-naacl.200>)**
  - Authors: Shufan Chen; He Zheng; Lei Cui.
  - Venue / outlet: **Findings of NAACL** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: jeong2024adaptive; question: Q-28; review: positional_only -->
- **[Adaptive-RAG: Learning to Adapt Retrieval-Augmented Large Language Models through Question Complexity](<https://doi.org/10.18653/v1/2024.naacl-long.389>)**
  - Authors: Soyeong Jeong; Jinheon Baek; Sukmin Cho; Sung Ju Hwang; Jong Park.
  - Venue / outlet: **NAACL (Long Papers)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: yao2024cacheblend; question: Q-28; review: positional_only -->
- **[CacheBlend: Fast Large Language Model Serving for RAG with Cached Knowledge Fusion](<https://arxiv.org/abs/2405.16444v3>)**
  - Authors: Jiayi Yao; Hanchen Li; Yuhan Liu; Siddhant Ray; Yihua Cheng; Qizheng Zhang; Kuntai Du; Shan Lu; Junchen Jiang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: jin2024ragcache; question: Q-28; review: positional_only -->
- **[RAGCache: Efficient Knowledge Caching for Retrieval-Augmented Generation](<https://arxiv.org/abs/2404.12457v2>)**
  - Authors: Chao Jin; Zili Zhang; Xuanlin Jiang; Fangyue Liu; Xin Liu; Xuanzhe Liu; Xin Jin.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: agrawal2024sarathi; question: Q-28; review: positional_only -->
- **[Taming Throughput-Latency Tradeoff in LLM Inference with Sarathi-Serve](<https://www.usenix.org/conference/osdi24/presentation/agrawal>)**
  - Authors: Amey Agrawal; Nitin Kedia; Ashish Panwar; Jayashree Mohan; Nipun Kwatra; Bhargav Gulavani; Alexey Tumanov; Ramachandran Ramjee.
  - Venue / outlet: **OSDI** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: Lu2024TurboRAG; question: Q-28; review: positional_only -->
- **[TurboRAG: Accelerating Retrieval-Augmented Generation with Precomputed KV Caches for Chunked Text](<https://arxiv.org/abs/2410.07590>)**
  - Authors: Songshuo Lu; Hua Wang; Yutian Rong; Zhi Chen; Yaohua Tang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-b2"></a>

### B2. Cross-component optimization

Focus: Local versus global utility; coordination of updates.

Questions: [Q-29](#q-29) · [Q-30](#q-30) · [Q-31](#q-31).

<a id="q-29"></a>

#### Q-29. Which system configuration best satisfies the task objectives and resource constraints?

*Focal question.*

<!-- record: Afzal2026Beyond; question: Q-29; review: positional_only -->
- **[Beyond Grid Search: Leveraging Bayesian Optimization for Accelerating RAG Pipeline Optimization](<https://doi.org/10.18653/v1/2026.eacl-industry.19>)**
  - Authors: Anum Afzal; Xueru Zheng; Florian Matthes.
  - Venue / outlet: **EACL (Industry Track)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Zhou2026Inference; question: Q-29; review: positional_only -->
- **[Inference Scaling Law for Retrieval Augmented Generation](<https://doi.org/10.1609/aaai.v40i19.38692>)**
  - Authors: Shu Zhou; Yuxuan Ao; Yunyang Xuan; Xin Wang; Tao Fan; Hao Wang.
  - Venue / outlet: **AAAI** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Tian2026Predicting; question: Q-29; review: positional_only -->
- **[Predicting Retrieval Utility and Answer Quality in Retrieval-Augmented Generation](<https://arxiv.org/abs/2601.14546>)**
  - Authors: Fangzheng Tian; Debasis Ganguly; Craig Macdonald.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Ning2025Less; question: Q-29; review: positional_only -->
- **[Less LLM, More Documents: Searching for Improved RAG](<https://arxiv.org/abs/2510.02657>)**
  - Authors: Jingjie Ning; Yibo Kong; Yunfan Long; Jamie Callan.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Fu2024AutoRAG; question: Q-29; review: positional_only -->
- **[AutoRAG-HP: Automatic Online Hyper-Parameter Tuning for Retrieval-Augmented Generation](<https://arxiv.org/abs/2406.19251>)**
  - Authors: Jia Fu; Xiaoting Qin; Fangkai Yang; Lu Wang; Jue Zhang; Qingwei Lin; Yubo Chen; Dongmei Zhang; Saravan Rajmohan; Qi Zhang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: Kim2024AutoRAG; question: Q-29; review: positional_only -->
- **[AutoRAG: Automated Framework for optimization of Retrieval Augmented Generation Pipeline](<https://arxiv.org/abs/2410.20878>)**
  - Authors: Dongkyu Kim; Byoungwook Kim; Donggeon Han; Matouš Eibich.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<a id="q-30"></a>

#### Q-30. Which components should change, and how should their updates be coordinated?

*Focal question.*

<!-- record: liu2026carl; question: Q-30; review: positional_only -->
- **[Compete to Complete: Co-opetition Adversarial Learning for Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2026.acl-long.258>)**
  - Authors: Xin Liu; Yu-An Liu; Ruqing Zhang; Yixing Fan; Lixin Su; Jiafeng Guo; Xueqi Cheng.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Tang2025Boosting; question: Q-30; review: positional_only -->
- **[Boosting Retrieval-Augmented Generation with Generation-Augmented Retrieval: A Co-Training Approach](<https://doi.org/10.1145/3726302.3729907>)**
  - Authors: Yubao Tang; Ruqing Zhang; Jiafeng Guo; Maarten de Rijke; Yixing Fan; Xueqi Cheng.
  - Venue / outlet: **SIGIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Gao2025D; question: Q-30; review: positional_only -->
- **[D-RAG: Differentiable Retrieval-Augmented Generation for Knowledge Graph Question Answering](<https://doi.org/10.18653/v1/2025.emnlp-main.1793>)**
  - Authors: Guangze Gao; Zixuan Li; Chunfeng Yuan; Jiawei Li; Wu Jianzhuo; Yuehao Zhang; Xiaolong Jin; Bing Li; Weiming Hu.
  - Venue / outlet: **EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: gumbel2025; question: Q-30; review: positional_only -->
- **[Gumbel Reranking: Differentiable End-to-End Reranker Optimization](<https://arxiv.org/abs/2502.11116>)**
  - Authors: Siyuan Huang; Zhiyuan Ma; Jintao Du; Changhua Meng; Weiqiang Wang; Jingwen Leng; Minyi Guo; Zhouhan Lin.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Yan2025RPO; question: Q-30; review: positional_only -->
- **[RPO: Retrieval Preference Optimization for Robust Retrieval-Augmented Generation](<https://arxiv.org/abs/2501.13726>)**
  - Authors: Shi-Qi Yan; Quan Liu; Zhen-Hua Ling.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Dong2024Understand; question: Q-30; review: positional_only -->
- **[Understand What LLM Needs: Dual Preference Alignment for Retrieval-Augmented Generation](<https://doi.org/10.1145/3696410.3714717>)**
  - Authors: Guanting Dong; Yutao Zhu; Chenghao Zhang; Zechen Wang; Ji-Rong Wen; Zhicheng Dou.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: zamani2024stochastic; question: Q-30; review: positional_only -->
- **[Stochastic RAG: End-to-End Retrieval-Augmented Generation through Expected Utility Maximization](<https://arxiv.org/abs/2405.02816>)**
  - Authors: Hamed Zamani; Michael Bendersky.
  - Venue / outlet: **SIGIR** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: lin2024radit; question: Q-30; review: positional_only -->
- **[RA-DIT: Retrieval-Augmented Dual Instruction Tuning](<https://arxiv.org/abs/2310.01352>)**
  - Authors: Xi Victoria Lin; Xilun Chen; Mingda Chen; Weijia Shi; Maria Lomeli; Rich James; Pedro Rodriguez; Jacob Kahn; Gergely Szilvasy; Mike Lewis; Luke Zettlemoyer; Scott Yih.
  - Venue / outlet: **arXiv (preprint)** · Year: **2023**.
  - Association review: [P](#how-to-use).

<!-- record: izacard2021leveraging; question: Q-30; review: positional_only -->
- **[Leveraging Passage Retrieval with Generative Models for Open Domain Question Answering](<https://doi.org/10.18653/v1/2021.eacl-main.74>)**
  - Authors: Gautier Izacard; Edouard Grave.
  - Venue / outlet: **EACL** · Year: **2021**.
  - Association review: [P](#how-to-use).

<a id="q-31"></a>

#### Q-31. How can downstream outcomes provide useful feedback to upstream decisions?

*Focal question.*

<!-- record: chen2026grorag; question: Q-31; review: positional_only -->
- **[GRO-RAG: Gradient-aware Re-rank Optimization for Multi-source Retrieval-Augmented Generation](<https://openreview.net/forum?id=5zdubHFutd>)**
  - Authors: Siyuan Chen; Hang Ding; Kangxiaoyu; Jiechao Gao.
  - Venue / outlet: **ICLR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Fan2025End; question: Q-31; review: positional_only -->
- **[End-to-End Optimization for Multimodal Retrieval-Augmented Generation via Reward Backpropagation](<https://doi.org/10.18653/v1/2025.findings-emnlp.24>)**
  - Authors: Zhiyuan Fan; Longfei Yun; Ming Yan; Yumeng Wang; Dadi Guo; Brian Mak; James Kwok; Yi R. Fung.
  - Venue / outlet: **Findings of EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: YLW_NeurIPS_2025; question: Q-31; review: positional_only -->
- **[Improving Retrieval-Augmented Generation through Multi-Agent Reinforcement Learning](<https://papers.nips.cc/paper_files/paper/2025/hash/af88968c84990a352cedf922b635b140-Abstract-Conference.html>)**
  - Authors: Yiqun Chen; Lingyong Yan; Weiwei Sun; Xinyu Ma; Yi Zhang; Shuaiqiang Wang; Dawei Yin; Yiming Yang; Jiaxin Mao.
  - Venue / outlet: **NeurIPS** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: LML_ICLR_2025; question: Q-31; review: positional_only -->
- **[RAG-DDR: Optimizing Retrieval-Augmented Generation Using Differentiable Data Rewards](<https://arxiv.org/abs/2410.13509>)**
  - Authors: Xinze Li; Sen Mei; Zhenghao Liu; Yukun Yan; Shuo Wang; Shi Yu; Zheni Zeng; Hao Chen; Ge Yu; Zhiyuan Liu; Maosong Sun; Chenyan Xiong.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: shi2024replug; question: Q-31; review: positional_only -->
- **[REPLUG: Retrieval-Augmented Black-Box Language Models](<https://aclanthology.org/2024.naacl-long.463/>)**
  - Authors: Weijia Shi; Sewon Min; Michihiro Yasunaga; Minjoon Seo; Rich James; Mike Lewis; Luke Zettlemoyer; Wen-tau Yih.
  - Venue / outlet: **NAACL (Long Papers)** · Year: **2024**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-b3"></a>

### B3. Learning, rewards, and credit

Focus: Reward validity; delayed and interacting effects.

Questions: [Q-32](#q-32) · [Q-33](#q-33) · [Q-34](#q-34) · [Q-35](#q-35).

<a id="q-32"></a>

#### Q-32. Which RAG decisions are suitable for reward-driven training?

*Focal question.*

<!-- record: graphragrouter2026; question: Q-32; review: positional_only -->
- **[GraphRAG-Router: Learning Cost-Efficient Routing over GraphRAGs and LLMs with Reinforcement Learning](<https://arxiv.org/abs/2604.16401>)**
  - Authors: Dongzhe Fan; Chuanhao Ji; Zimu Wang; Tong Chen; Qiaoyu Tan.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Wu2026Optimizing; question: Q-32; review: positional_only -->
- **[Optimizing RAG Rerankers with LLM Feedback via Reinforcement Learning](<https://doi.org/10.18653/v1/2026.acl-long.1406>)**
  - Authors: Yuhang Wu; Xiangqing Shen; Fanfan Wang; Cangqi Zhou; Zhen Wu; Xinyu Dai; Rui Xia.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: ding2026ragdiet; question: Q-32; review: positional_only -->
- **[RAG-on-a-Diet: A Reinforcement Learning-Based Dynamic Resource Optimization Framework for RAG](<https://doi.org/10.18653/v1/2026.acl-long.1562>)**
  - Authors: Hongwen Ding; Yizheng Zhao.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: zhang2026smartchunk; question: Q-32; review: positional_only -->
- **[SmartChunk Retrieval: Query-Aware Chunk Compression with Planning for Efficient Document RAG](<https://proceedings.iclr.cc/paper_files/paper/2026/hash/5c1ff00b27ba052039bb41531236baac-Abstract-Conference.html>)**
  - Authors: Xuechen Zhang; Koustava Goswami; Samet Oymak; Jiasi Chen; Nedim Lipka.
  - Venue / outlet: **ICLR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: rlqr2025; question: Q-32; review: positional_only -->
- **[Annotation-Free Reinforcement Learning Query Rewriting via Verifiable Search Reward](<https://arxiv.org/abs/2507.23242>)**
  - Authors: Sungguk Cha; DongWook Kim; Taeseung Hahn; Mintae Kim; Youngsub Han; Byoung-Ki Jeon.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: zhu2025convsearchr1; question: Q-32; review: positional_only -->
- **[ConvSearch-R1: Enhancing Query Reformulation for Conversational Search with Reasoning via Reinforcement Learning](<https://arxiv.org/abs/2505.15776>)**
  - Authors: Changtai Zhu; Siyin Wang; Ruijun Feng; Kai Song; Xipeng Qiu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: YLW_NeurIPS_2025; question: Q-32; review: positional_only -->
- **[Improving Retrieval-Augmented Generation through Multi-Agent Reinforcement Learning](<https://papers.nips.cc/paper_files/paper/2025/hash/af88968c84990a352cedf922b635b140-Abstract-Conference.html>)**
  - Authors: Yiqun Chen; Lingyong Yan; Weiwei Sun; Xinyu Ma; Yi Zhang; Shuaiqiang Wang; Dawei Yin; Yiming Yang; Jiaxin Mao.
  - Venue / outlet: **NeurIPS** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Zhao2025MMRAG; question: Q-32; review: positional_only -->
- **[MMRAG-RFT: Two-stage Reinforcement Fine-tuning for Explainable Multi-modal Retrieval-augmented Generation](<https://arxiv.org/abs/2512.17194>)**
  - Authors: Shengwei Zhao; Jingwen Yao; Sitong Wei; Linhai Xu; Yuying Liu; Dong Zhang; Zhiqiang Tian; Shaoyi Du.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: r3_retrieval_rl2025; question: Q-32; review: positional_only -->
- **[Optimizing Retrieval for RAG via Reinforcement Learning](<https://arxiv.org/abs/2510.24652>)**
  - Authors: Jiawei Zhou; Lei Chen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: ZMK_arXiv_2025; question: Q-32; review: positional_only -->
- **[Rank-R1: Enhancing Reasoning in LLM-based Document Rerankers via Reinforcement Learning](<https://arxiv.org/abs/2503.06034>)**
  - Authors: Shengyao Zhuang; Xueguang Ma; Bevan Koopman; Jimmy Lin; Guido Zuccon.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: lin2025refrag; question: Q-32; review: positional_only -->
- **[REFRAG: Rethinking RAG based Decoding](<https://arxiv.org/abs/2509.01092>)**
  - Authors: Xiaoqiang Lin; Aritra Ghosh; Bryan Kian Hsiang Low; Anshumali Shrivastava; Vijai Mohan.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: ma2023rewrite; question: Q-32; review: positional_only -->
- **[Query Rewriting for Retrieval-Augmented Large Language Models](<https://aclanthology.org/2023.emnlp-main.322/>)**
  - Authors: Xinbei Ma; Yeyun Gong; Pengcheng He; Hai Zhao; Nan Duan.
  - Venue / outlet: **EMNLP** · Year: **2023**.
  - Association review: [P](#how-to-use).

<a id="q-33"></a>

#### Q-33. How should reward feedback update individual or coupled RAG policies?

*Focal question.*

<!-- record: Chen2025C; question: Q-33; review: positional_only -->
- **[C-3PO: Compact Plug-and-Play Proxy Optimization to Achieve Human-like Retrieval-Augmented Generation](<https://arxiv.org/abs/2502.06205>)**
  - Authors: Guoxin Chen; Minpeng Liao; Peiying Yu; Dingmin Wang; Zile Qiao; Chao Yang; Xin Zhao; Kai Fan.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: sun2025dynamicrag; question: Q-33; review: positional_only -->
- **[DynamicRAG: Leveraging Outputs of Large Language Model as Feedback for Dynamic Reranking in Retrieval-Augmented Generation](<https://arxiv.org/abs/2505.07233>)**
  - Authors: Jiashuo Sun; Xianrui Zhong; Sizhe Zhou; Jiawei Han.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: YLW_NeurIPS_2025; question: Q-33; review: positional_only -->
- **[Improving Retrieval-Augmented Generation through Multi-Agent Reinforcement Learning](<https://papers.nips.cc/paper_files/paper/2025/hash/af88968c84990a352cedf922b635b140-Abstract-Conference.html>)**
  - Authors: Yiqun Chen; Lingyong Yan; Weiwei Sun; Xinyu Ma; Yi Zhang; Shuaiqiang Wang; Dawei Yin; Yiming Yang; Jiaxin Mao.
  - Venue / outlet: **NeurIPS** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: ZMK_arXiv_2025; question: Q-33; review: positional_only -->
- **[Rank-R1: Enhancing Reasoning in LLM-based Document Rerankers via Reinforcement Learning](<https://arxiv.org/abs/2503.06034>)**
  - Authors: Shengyao Zhuang; Xueguang Ma; Bevan Koopman; Jimmy Lin; Guido Zuccon.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: lin2025refrag; question: Q-33; review: positional_only -->
- **[REFRAG: Rethinking RAG based Decoding](<https://arxiv.org/abs/2509.01092>)**
  - Authors: Xiaoqiang Lin; Aritra Ghosh; Bryan Kian Hsiang Low; Anshumali Shrivastava; Vijai Mohan.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: LML_ICLR_2025; question: Q-33; review: positional_only -->
- **[RAG-DDR: Optimizing Retrieval-Augmented Generation Using Differentiable Data Rewards](<https://arxiv.org/abs/2410.13509>)**
  - Authors: Xinze Li; Sen Mei; Zhenghao Liu; Yukun Yan; Shuo Wang; Shi Yu; Zheni Zeng; Hao Chen; Ge Yu; Zhiyuan Liu; Maosong Sun; Chenyan Xiong.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: ma2023rewrite; question: Q-33; review: positional_only -->
- **[Query Rewriting for Retrieval-Augmented Large Language Models](<https://aclanthology.org/2023.emnlp-main.322/>)**
  - Authors: Xinbei Ma; Yeyun Gong; Pengcheng He; Hai Zhao; Nan Duan.
  - Venue / outlet: **EMNLP** · Year: **2023**.
  - Association review: [P](#how-to-use).

<!-- record: SJW_arXiv_2017; question: Q-33; review: positional_only -->
- **[Proximal policy optimization algorithms](<https://arxiv.org/abs/1707.06347>)**
  - Authors: John Schulman; Filip Wolski; Prafulla Dhariwal; Alec Radford; Oleg Klimov.
  - Venue / outlet: **arXiv (preprint)** · Year: **2017**.
  - Association review: [P](#how-to-use).

<a id="q-34"></a>

#### Q-34. Which rewards reflect task quality, evidential support, and resource requirements?

*Focal question.*

<!-- record: qin2026cfrag; question: Q-34; review: positional_only -->
- **[Counterfactual Reasoning for Retrieval-Augmented Generation](<https://openreview.net/forum?id=9U51rOnGko>)**
  - Authors: Huaiyu Qin; Chunyu Wei; Yueguo Chen; Yunhai Wang.
  - Venue / outlet: **ICLR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: lin2025refrag; question: Q-34; review: positional_only -->
- **[REFRAG: Rethinking RAG based Decoding](<https://arxiv.org/abs/2509.01092>)**
  - Authors: Xiaoqiang Lin; Aritra Ghosh; Bryan Kian Hsiang Low; Anshumali Shrivastava; Vijai Mohan.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-35"></a>

#### Q-35. How should delayed system feedback be attributed to interacting decisions and modules?

*Focal question.*

<!-- record: Chen2025C; question: Q-35; review: positional_only -->
- **[C-3PO: Compact Plug-and-Play Proxy Optimization to Achieve Human-like Retrieval-Augmented Generation](<https://arxiv.org/abs/2502.06205>)**
  - Authors: Guoxin Chen; Minpeng Liao; Peiying Yu; Dingmin Wang; Zile Qiao; Chao Yang; Xin Zhao; Kai Fan.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-b4"></a>

### B4. Knowledge and deployment conditions

Focus: Changing admissible evidence and operational costs.

Questions: [Q-36](#q-36).

<a id="q-36"></a>

#### Q-36. Which design and optimization choices must change under different knowledge and deployment conditions?

*Focal question.*

No inherited question-level paper assignment in the v16 taxonomy. This is an explicit curation gap, not a claim that the question has no relevant literature.

[Back to contents](#contents)

<a id="domain-c"></a>

## C. Adaptive control, memory, and collaboration

Which decisions require observation-conditioned control or coordinated state?

<a id="group-c1"></a>

### C1. Agency and decision responsibility

Focus: Distinguishing available actions from revisable control.

Questions: [Q-37](#q-37).

<a id="q-37"></a>

#### Q-37. Which retrieval-related decisions are delegated, and what state makes them revisable?

*Focal question.*

<!-- record: yao2023react; question: Q-37; review: positional_only -->
- **[ReAct: Synergizing Reasoning and Acting in Language Models](<https://arxiv.org/abs/2210.03629>)**
  - Authors: Shunyu Yao; Jeffrey Zhao; Dian Yu; Nan Du; Izhak Shafran; Karthik Narasimhan; Yuan Cao.
  - Venue / outlet: **ICLR** · Year: **2023**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-c2"></a>

### C2. Planning, revision, and search control

Focus: Uncertain subgoals; changing evidence; stopping risk.

Questions: [Q-38](#q-38) · [Q-39](#q-39) · [Q-40](#q-40).

<a id="q-38"></a>

#### Q-38. How should a controller plan evidence acquisition when subgoals and source capabilities are uncertain?

*Focal question.*

<!-- record: Hui2026Interact; question: Q-38; review: manuscript_context_reviewed -->
- **[Interact-RAG: Reason and Interact with the Corpus, Beyond Black-Box Retrieval](<https://proceedings.iclr.cc/paper_files/paper/2026/hash/b61f288da3c106f65d57b0d45b470b6b-Abstract-Conference.html>)**
  - Authors: Yulong Hui; Chao Chen; Zhihang Fu; Yihao Liu; Jieping Ye; Huanchen Zhang.
  - Venue / outlet: **ICLR** · Year: **2026**.
  - Association review: [C](#how-to-use).

<!-- record: li2026proh; question: Q-38; review: manuscript_context_reviewed -->
- **[PRoH: Dynamic Planning and Reasoning over Knowledge Hypergraphs for Retrieval-Augmented Generation](<https://doi.org/10.1145/3774904.3792611>)**
  - Authors: Xiangjun Zai; Xingyu Tan; Xiaoyang Wang; Qing Liu; Xiwei Xu; Wenjie Zhang.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [C](#how-to-use).

<!-- record: Xu2025Towards; question: Q-38; review: manuscript_context_reviewed -->
- **[Towards Open-World Retrieval-Augmented Generation on Knowledge Graph: A Multi-Agent Collaboration Framework](<https://doi.org/10.1145/3774904.3792389>)**
  - Authors: Jiasheng Xu; Mingda Li; Yongqiang Tang; Peijie Wang; Wensheng Zhang.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [C](#how-to-use).

<!-- record: feng2025airrag; question: Q-38; review: manuscript_context_reviewed -->
- **[AirRAG: Autonomous Strategic Planning and Reasoning Steer Retrieval Augmented Generation](<https://doi.org/10.18653/v1/2025.findings-emnlp.1030>)**
  - Authors: Wenfeng Feng; Chuzhan Hao; Yuewei Zhang; Guochao Jiang; Jingyi Song.
  - Venue / outlet: **Findings of EMNLP** · Year: **2025**.
  - Association review: [C](#how-to-use).

<!-- record: parallelsearch2025; question: Q-38; review: primary_abstract_checked -->
- **[ParallelSearch: Train your LLMs to Decompose Query and Search Sub-queries in Parallel with Reinforcement Learning](<https://arxiv.org/abs/2508.09303>)**
  - Authors: Shu Zhao; Tan Yu; Anbang Xu; Japinder Singh; Aaditya Shukla; Rama Akkiraju.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [A](#how-to-use).

<!-- record: li2025searcho1; question: Q-38; review: primary_abstract_checked -->
- **[Search-o1: Agentic Search-Enhanced Large Reasoning Models](<https://arxiv.org/abs/2501.05366>)**
  - Authors: Xiaoxi Li; Guanting Dong; Jiajie Jin; Yuyao Zhang; Yujia Zhou; Yutao Zhu; Peitian Zhang; Zhicheng Dou.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [A](#how-to-use).

<!-- record: Chen2025Towards; question: Q-38; review: manuscript_context_reviewed -->
- **[Towards Omni-RAG: Comprehensive Retrieval-Augmented Generation for Large Language Models in Medical Applications](<https://arxiv.org/abs/2501.02460>)**
  - Authors: Zhe Chen; Yusheng Liao; Shuyang Jiang; Pingjie Wang; Yiqiu Guo; Yanfeng Wang; Yu Wang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [C](#how-to-use).

<a id="q-39"></a>

#### Q-39. How should new observations revise the evidence state and subsequent retrieval actions?

*Focal question.*

<!-- record: sourati2026ladrag; question: Q-39; review: manuscript_context_reviewed -->
- **[LAD-RAG: Layout-aware Dynamic RAG for Visually-Rich Document Understanding](<https://doi.org/10.18653/v1/2026.acl-long.724>)**
  - Authors: Zhivar Sourati; Zheng Wang; Marianne Menglin Liu; Yazhe Hu; Mengqing Guo; Sujeeth Bharadwaj; Kyu J. Han; Tao Sheng; Sujith Ravi; Morteza Dehghani; Dan Roth.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [C](#how-to-use).

<!-- record: Yuan2025Towards; question: Q-39; review: manuscript_context_reviewed -->
- **[Towards Self-cognitive Exploration: Metacognitive Knowledge Graph Retrieval Augmented Generation](<https://doi.org/10.1145/3770854.3780156>)**
  - Authors: Xujie Yuan; Shimin Di; Jielong Tang; Libin Zheng; Jian Yin.
  - Venue / outlet: **KDD (Vol. 1)** · Year: **2026**.
  - Association review: [C](#how-to-use).

<!-- record: deepresearcher2025; question: Q-39; review: manuscript_context_reviewed -->
- **[DeepResearcher: Scaling Deep Research via Reinforcement Learning in Real-world Environments](<https://arxiv.org/abs/2504.03160>)**
  - Authors: Yuxiang Zheng; Dayuan Fu; Xiangkun Hu; Xiaojie Cai; Lyumanshan Ye; Pengrui Lu; Pengfei Liu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [C](#how-to-use).

<!-- record: Li2025KnowTrace; question: Q-39; review: manuscript_context_reviewed -->
- **[KnowTrace: Bootstrapping Iterative Retrieval-Augmented Generation with Structured Knowledge Tracing](<https://doi.org/10.1145/3711896.3737015>)**
  - Authors: Rui Li; Quanyu Dai; Zeyu Zhang; Xu Chen; Zhenhua Dong; Ji-Rong Wen.
  - Venue / outlet: **KDD (Vol. 2)** · Year: **2025**.
  - Association review: [C](#how-to-use).

<!-- record: Cao2025NeuSym; question: Q-39; review: manuscript_context_reviewed -->
- **[NeuSym-RAG: Hybrid Neural Symbolic Retrieval with Multiview Structuring for PDF Question Answering](<https://doi.org/10.18653/v1/2025.acl-long.311>)**
  - Authors: Ruisheng Cao; Hanchong Zhang; Tiancheng Huang; Zhangyi Kang; Yuxin Zhang; Liangtai Sun; Hanqi Li; Yuxun Miao; Shuai Fan; Lu Chen; Kai Yu.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2025**.
  - Association review: [C](#how-to-use).

<!-- record: r1searcher2025; question: Q-39; review: manuscript_context_reviewed -->
- **[R1-Searcher: Incentivizing the Search Capability in LLMs via Reinforcement Learning](<https://arxiv.org/abs/2503.05592>)**
  - Authors: Huatong Song; Jinhao Jiang; Yingqian Min; Jie Chen; Zhipeng Chen; Wayne Xin Zhao; Lei Fang; Ji-Rong Wen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [C](#how-to-use).

<!-- record: research2025; question: Q-39; review: manuscript_context_reviewed -->
- **[ReSearch: Learning to Reason with Search for LLMs via Reinforcement Learning](<https://arxiv.org/abs/2503.19470>)**
  - Authors: Mingyang Chen; Linzhuang Sun; Tianpeng Li; Haoze Sun; Yijie Zhou; Chenzheng Zhu; Haofen Wang; Jeff Z. Pan; Wen Zhang; Huajun Chen; Fan Yang; Zenan Zhou; Weipeng Chen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [C](#how-to-use).

<!-- record: jin2025searchr1; question: Q-39; review: primary_abstract_checked -->
- **[Search-R1: Training LLMs to Reason and Leverage Search Engines with Reinforcement Learning](<https://arxiv.org/abs/2503.09516>)**
  - Authors: Bowen Jin; Hansi Zeng; Zhenrui Yue; Jinsung Yoon; Sercan Arik; Dong Wang; Hamed Zamani; Jiawei Han.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [A](#how-to-use).

<!-- record: Shen2024GeAR; question: Q-39; review: manuscript_context_reviewed -->
- **[GeAR: Graph-enhanced Agent for Retrieval-augmented Generation](<https://arxiv.org/abs/2412.18431>)**
  - Authors: Zhili Shen; Chenxin Diao; Pavlos Vougiouklis; Pascual Merita; Shriram Piramanayagam; Enting Chen; Damien Graux; Andre Melo; Ruofei Lai; Zeren Jiang; Zhongyang Li; YE QI; Yang Ren; Dandan Tu; Jeff Z. Pan.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [C](#how-to-use).

<a id="q-40"></a>

#### Q-40. When should search continue, change strategy, abstain, or terminate?

*Focal question.*

<!-- record: fang2026cogniverse; question: Q-40; review: manuscript_context_reviewed -->
- **[CogniVerse: Revolutionizing Multi-Modal Retrieval-Augmented Generation with Cognitive Reflection and Geometric Reasoning](<https://openaccess.thecvf.com/content/CVPR2026/html/Fang_CogniVerse_Revolutionizing_Multi-Modal_Retrieval-Augmented_Generation_with_Cognitive_Reflection_and_Geometric_CVPR_2026_paper.html>)**
  - Authors: Xiang Fang; Wanlong Fang; Changshuo Wang.
  - Venue / outlet: **CVPR** · Year: **2026**.
  - Association review: [C](#how-to-use).

<!-- record: prorag2026; question: Q-40; review: manuscript_context_reviewed -->
- **[ProRAG: Process-Supervised Reinforcement Learning for Retrieval-Augmented Generation](<https://arxiv.org/abs/2601.21912>)**
  - Authors: Zhao Wang; Ziliang Zhao; Zhicheng Dou.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [C](#how-to-use).

<!-- record: Fang2026SPARKLE; question: Q-40; review: manuscript_context_reviewed -->
- **[SPARKLE: A Structured and Plug-and-play Agentic Retrieval Policy for Adaptive RAG Models](<https://doi.org/10.18653/v1/2026.acl-long.1793>)**
  - Authors: Jinyuan Fang; Zaiqiao Meng; Craig Macdonald.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [C](#how-to-use).

<!-- record: leng2025decex; question: Q-40; review: manuscript_context_reviewed -->
- **[DecEx-RAG: Boosting Agentic Retrieval-Augmented Generation with Decision and Execution Optimization via Process Supervision](<https://arxiv.org/abs/2510.05691>)**
  - Authors: Yongqi Leng; Yikun Lei; Xikai Liu; Meizhi Zhong; Bojian Xiong; Yurong Zhang; Yan Gao; Yi Wu; Yao Hu; Deyi Xiong.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [C](#how-to-use).

<!-- record: Hu2025MCTS; question: Q-40; review: manuscript_context_reviewed -->
- **[MCTS-RAG: Enhancing Retrieval-Augmented Generation with Monte Carlo Tree Search](<https://arxiv.org/abs/2503.20757>)**
  - Authors: Yunhai Hu; Yilun Zhao; Chen Zhao; Arman Cohan.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [C](#how-to-use).

<!-- record: researcher2025; question: Q-40; review: manuscript_context_reviewed -->
- **[RE-Searcher: Robust Agentic Search with Goal-oriented Planning and Self-reflection](<https://arxiv.org/abs/2509.26048>)**
  - Authors: Daocheng Fu; Jianbiao Mei; Licheng Wen; Xuemeng Yang; Cheng Yang; Rong Wu; Tao Hu; Siqi Li; Yufan Shen; Xinyu Cai; Pinlong Cai; Botian Shi; Yong Liu; Yu Qiao.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [C](#how-to-use).

<!-- record: wu2025searchwisely; question: Q-40; review: primary_abstract_checked -->
- **[Search Wisely: Mitigating Sub-optimal Agentic Searches By Reducing Uncertainty](<https://arxiv.org/abs/2505.17281>)**
  - Authors: Peilin Wu; Mian Zhang; Xinlu Zhang; Xinya Du; Zhiyu Zoey Chen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [A](#how-to-use).

[Back to contents](#contents)

<a id="group-c3"></a>

### C3. Memory roles, lifecycle, and reuse

Focus: State lifetime; staleness; unsafe transfer.

Questions: [Q-41](#q-41) · [Q-42](#q-42) · [Q-43](#q-43).

<a id="q-41"></a>

#### Q-41. What information should persist, for which decisions, and over what lifetime?

*Focal question.*

<!-- record: Anon2026HGMem; question: Q-41; review: positional_only -->
- **[HGMem: Hypergraph-based Working Memory to Improve Multi-step RAG for Long-Context Complex Relational Modeling](<https://arxiv.org/abs/2512.23959v3>)**
  - Authors: Chulun Zhou; Chunkang Zhang; Guoxin Yu; Fandong Meng; Jie Zhou; Wai Lam; Mo Yu.
  - Venue / outlet: **ICML** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Rajesh2025Beyond; question: Q-41; review: positional_only -->
- **[Beyond Fact Retrieval: Episodic Memory for RAG with Generative Semantic Workspaces](<https://arxiv.org/abs/2511.07587>)**
  - Authors: Shreyas Rajesh; Pavan Holur; Chenda Duan; David Chong; Vwani Roychowdhury.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Wang2025ComoRAG; question: Q-41; review: positional_only -->
- **[ComoRAG: A Cognitive-Inspired Memory-Organized RAG for Stateful Long Narrative Reasoning](<https://arxiv.org/abs/2508.10419>)**
  - Authors: Juyuan Wang; Rongchen Zhao; Wei Wei; Yufeng Wang; Mo Yu; Jie Zhou; Jin Xu; Liyan Xu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Wang2025InstructRAG; question: Q-41; review: positional_only -->
- **[InstructRAG: Leveraging Retrieval-Augmented Generation on Instruction Graphs for LLM-Based Task Planning](<https://doi.org/10.1145/3726302.3730009>)**
  - Authors: Zheng Wang; Shu Xian Teo; Jun Jie Chew; Wei Shi.
  - Venue / outlet: **SIGIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: qian2024memorag; question: Q-41; review: positional_only -->
- **[MemoRAG: Boosting Long Context Processing with Global Memory-Enhanced Retrieval Augmentation](<https://doi.org/10.1145/3696410.3714805>)**
  - Authors: Hongjin Qian; Zheng Liu; Peitian Zhang; Kelong Mao; Defu Lian; Zhicheng Dou; Tiejun Huang.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: wang2025memos; question: Q-41; review: positional_only -->
- **[MemOS: A Memory OS for AI System](<https://arxiv.org/abs/2507.03724>)**
  - Authors: Zhiyu Li; Chenyang Xi; Chunyu Li; Ding Chen; Boyu Chen; Shichao Song; Simin Niu; Hanyu Wang; Jiawei Yang; Chen Tang; Qingchen Yu; Jihao Zhao; Yezhaohui Wang; Peng Liu; Zehao Lin; Pengyuan Wang; Jiahao Huo; Tianyi Chen; Kai Chen; Kehang Li; Zhen Tao; Huayi Lai; Hao Wu; Bo Tang; Zhengren Wang; Zhaoxin Fan; Ningyu Zhang; Linfeng Zhang; Junchi Yan; Mingchuan Yang; Tong Xu; Wei Xu; Huajun Chen; Haofen Wang; Hongkang Yang; Wentao Zhang; Zhi-Qin John Xu; Siheng Chen; Feiyu Xiong.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: du2025memr3; question: Q-41; review: positional_only -->
- **[MemR$^3$: Memory Retrieval via Reflective Reasoning for LLM Agents](<https://arxiv.org/abs/2512.20237>)**
  - Authors: Xingbo Du; Loka Li; Duzhen Zhang; Le Song.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Gu2025Toward; question: Q-41; review: positional_only -->
- **[Toward Structured Knowledge Reasoning: Contrastive Retrieval-Augmented Generation on Experience](<https://arxiv.org/abs/2506.00842>)**
  - Authors: Jiawei Gu; Ziting Xian; Yuanzhen Xie; Ye Liu; Enjie Liu; Ruichao Zhong; Mochi Gao; Yunzhi Tan; Bo Hu; Zang Li.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Su2025Towards; question: Q-41; review: positional_only -->
- **[Towards Explainable Transaction Risk Analysis With Dual Graph Retrieval Augmented Generation](<https://doi.org/10.1145/3746252.3761562>)**
  - Authors: Liang Su; Mingyang Zhang; Kangxiang Jia; Tengfei Liu; Weiqiang Wang; Yun Xiong; Xixi Wu; Xinyu Gao; Yongrui Fu; Jiawei Zhang.
  - Venue / outlet: **CIKM** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: hipporag2024; question: Q-41; review: positional_only -->
- **[HippoRAG: Neurobiologically Inspired Long-Term Memory for Large Language Models](<https://arxiv.org/abs/2405.14831>)**
  - Authors: Bernal Jiménez Gutiérrez; Yiheng Shu; Yu Gu; Michihiro Yasunaga; Yu Su.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: cheng2023selfmem; question: Q-41; review: positional_only -->
- **[Lift Yourself Up: Retrieval-augmented Text Generation with Self Memory](<https://arxiv.org/pdf/2305.02437>)**
  - Authors: Xin Cheng; Di Luo; Xiuying Chen; Lemao Liu; Dongyan Zhao; Rui Yan.
  - Venue / outlet: **NeurIPS** · Year: **2023**.
  - Association review: [P](#how-to-use).

<a id="q-42"></a>

#### Q-42. How should memory be written, retrieved, revised, and forgotten as evidence changes?

*Focal question.*

<!-- record: Xu2026Passive; question: Q-42; review: positional_only -->
- **[From Passive Retrieval to Active Memory Navigation: Learning to Use Memory as a Structured Action Space](<https://arxiv.org/abs/2607.05794>)**
  - Authors: Yue Xu; Yutao Sun; Yihao Liu; Mengyu Zhou; Jiayi Qiao; Lu Ma; Kai Tang; Wenjie Wang; Xiaoxi Jiang; Guanjun Jiang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: wang2026gamrag; question: Q-42; review: positional_only -->
- **[GAM-RAG: Gain-Adaptive Memory for Evolving Retrieval in Retrieval-Augmented Generation](<https://arxiv.org/abs/2603.01783>)**
  - Authors: Yifan Wang; Mingxuan Jiang; Zhihao Sun; Yixin Cao; Yicun Liu; Keyang Chen; Guangnan Ye; Hongfeng Chai.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: hu2026erm; question: Q-42; review: positional_only -->
- **[RAG without Forgetting: Continual Query-Infused Key Memory](<https://arxiv.org/abs/2602.05152>)**
  - Authors: Yuntong Hu; Sha Li; Naren Ramakrishnan; Liang Zhao.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: fan2026segmem; question: Q-42; review: positional_only -->
- **[SegMem-RAG: Adaptive Memory for Retrieval-Augmented Generation in Open-Ended Knowledge Environments](<https://doi.org/10.1609/aaai.v40i36.40320>)**
  - Authors: Xuanbo Fan; Tianqi Zhao; Yi Cheng; Chi Xiu; Jiaxin Guo; Boci Peng; Bingjing Xu; Jessica Zhang; Feng Sun; Yan Zhang.
  - Venue / outlet: **AAAI** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Cheng2025Evolving; question: Q-42; review: positional_only -->
- **[Evolving Graph-Based Context Modeling for Multi-Turn Conversational Retrieval-Augmented Generation](<https://doi.org/10.1145/3746252.3761355>)**
  - Authors: Yiruo Cheng; Hongjin Qian; Fengran Mo; Yongkang Wu; Zhonghua Li; Qi Ye; Ji-Rong Wen; Zhicheng Dou.
  - Venue / outlet: **CIKM** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Qin2025Towards; question: Q-42; review: positional_only -->
- **[Towards Adaptive Memory-Based Optimization for Enhanced Retrieval-Augmented Generation](<https://arxiv.org/abs/2504.05312>)**
  - Authors: Qitao Qin; Yucong Luo; Yihang Lu; Zhibo Chu; Xiaoman Liu; Xianwei Meng.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-43"></a>

#### Q-43. How can memory improve current decisions without importing stale, unsupported, or unauthorized assumptions?

*Focal question.*

<!-- record: wu2025longmemeval; question: Q-43; review: positional_only -->
- **[LongMemEval: Benchmarking Chat Assistants on Long-Term Interactive Memory](<https://arxiv.org/abs/2410.10813>)**
  - Authors: Di Wu; Hongwei Wang; Wenhao Yu; Yuwei Zhang; Kai-Wei Chang; Dong Yu.
  - Venue / outlet: **ICLR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Liu2025SEFRQO; question: Q-43; review: positional_only -->
- **[SEFRQO: A Self-Evolving Fine-Tuned RAG-Based Query Optimizer](<https://doi.org/10.1145/3769826>)**
  - Authors: Hanwen Liu; Qihan Zhang; Ryan Marcus; Ibrahim Sabek.
  - Venue / outlet: **PACMMOD** · Year: **2025**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-c4"></a>

### C4. Delegation, communication, and reconciliation

Focus: Coordination overhead; correlated errors; accountability.

Questions: [Q-44](#q-44) · [Q-45](#q-45) · [Q-46](#q-46).

<a id="q-44"></a>

#### Q-44. When should retrieval-related work be delegated, and how should roles be specialized?

*Focal question.*

<!-- record: Jia2026Agent; question: Q-44; review: positional_only -->
- **[Agent-Enhanced Heterogeneous Graph RAG for Academic Question Answering](<https://doi.org/10.1145/3774904.3792960>)**
  - Authors: Runsong Jia; Mengjia Wu; Ying Ding; Jie Lu; Yi Zhang.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Li2026Decoding; question: Q-44; review: positional_only -->
- **[Decoding the Market’s Pulse: Context-Enriched Agentic Retrieval Augmented Generation for Predicting Post-Earnings Price Shocks](<https://doi.org/10.18653/v1/2026.eacl-long.141>)**
  - Authors: Chenhui Li; Weihai Lu.
  - Venue / outlet: **EACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: chen2026legalgraphrag; question: Q-44; review: positional_only -->
- **[LegalGraphRAG: Multi-Agent Graph Retrieval-Augmented Generation for Reliable Legal Reasoning](<https://doi.org/10.18653/v1/2026.acl-long.1738>)**
  - Authors: Zerui Chen; Qinggang Zhang; Zhishang Xiang; Zhimin Wei; Linfeng Gao; Xiao Huang; Zhihong Zhang; Jinsong Su.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: liu2026hmrag; question: Q-44; review: positional_only -->
- **[HM-RAG: Hierarchical Multi-Agent Multimodal Retrieval Augmented Generation](<https://doi.org/10.1145/3746027.3754761>)**
  - Authors: Pei Liu; Xin Liu; Ruoyu Yao; Junming Liu; Siyuan Meng; Ding Wang; Jun Ma.
  - Venue / outlet: **ACM Multimedia** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: marag2025; question: Q-44; review: positional_only -->
- **[MA-RAG: Multi-Agent Retrieval-Augmented Generation via Collaborative Chain-of-Thought Reasoning](<https://arxiv.org/abs/2505.20096>)**
  - Authors: Thang Nguyen; Peter Chin; Yu-Wing Tai.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: chen2025squai; question: Q-44; review: positional_only -->
- **[SQuAI: Scientific Question-Answering with Multi-Agent Retrieval-Augmented Generation](<https://doi.org/10.1145/3746252.3761471>)**
  - Authors: Ines Besrour; Jingbo He; Tobias Schreieder; Michael Färber.
  - Venue / outlet: **CIKM** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Chang2024MAIN; question: Q-44; review: positional_only -->
- **[MAIN-RAG: Multi-Agent Filtering Retrieval-Augmented Generation](<https://arxiv.org/abs/2501.00332>)**
  - Authors: Chia-Yuan Chang; Zhimeng Jiang; Vineeth Rakesh; Menghai Pan; Chin-Chia Michael Yeh; Guanchu Wang; Mingzhi Hu; Zhichao Xu; Yan Zheng; Mahashweta Das; Na Zou.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<a id="q-45"></a>

#### Q-45. What should agents exchange, and how should evidence and task state remain consistent?

*Focal question.*

<!-- record: Muhamed2025CoRAG; question: Q-45; review: positional_only -->
- **[CoRAG: Collaborative Retrieval-Augmented Generation](<https://arxiv.org/abs/2504.01883>)**
  - Authors: Aashiq Muhamed; Mona Diab; Virginia Smith.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Zheng2025CoRAG; question: Q-45; review: positional_only -->
- **[CoRAG: Enhancing Hybrid Retrieval-Augmented Generation through a Cooperative Retriever Architecture](<https://doi.org/10.18653/v1/2025.findings-emnlp.872>)**
  - Authors: Zaiyi Zheng; Song Wang; Zihan Chen; Yaochen Zhu; Yinhan He; Liangjie Hong; Qi Guo; Jundong Li.
  - Venue / outlet: **Findings of EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Zhou2025Mobile; question: Q-45; review: positional_only -->
- **[Mobile-Agent-RAG: Driving Smart Multi-Agent Coordination with Contextual Knowledge Empowerment for Long-Horizon Mobile Automation](<https://arxiv.org/abs/2511.12254>)**
  - Authors: Yuxiang Zhou; Jichang Li; Yanhao Zhang; Haonan Lu; Guanbin Li.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Zhu2025Single; question: Q-45; review: positional_only -->
- **[Single LLM, Multiple Roles: A Unified Retrieval-Augmented Generation Framework Using Role-Specific Token Optimization](<https://arxiv.org/abs/2505.15444>)**
  - Authors: Yutao Zhu; Jiajie Jin; Hongjin Qian; Zheng Liu; Zhicheng Dou; Ji-Rong Wen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-46"></a>

#### Q-46. How should a team resolve disagreement and assign responsibility for its final claims?

*Focal question.*

<!-- record: tang2026eigenagent; question: Q-46; review: positional_only -->
- **[Eigen-Agent: Adaptive Multi-Agent Scientific Reasoning with Monitor-Based RAG](<https://openreview.net/forum?id=bGtmGTbmaz>)**
  - Authors: Xiangru Tang; Wanghan Xu; Yujie Wang; Zijie Guo; Yanjun Shao; Cixuan Zhang; Ziyi Wang; Lixin Zhang; Guancheng Wan; Zhenfei Yin; Wenlong Zhang; LEI BAI; Philip Torr; Hanrui Wang; Di Jin.
  - Venue / outlet: **ICLR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: chen2026legalgraphrag; question: Q-46; review: positional_only -->
- **[LegalGraphRAG: Multi-Agent Graph Retrieval-Augmented Generation for Reliable Legal Reasoning](<https://doi.org/10.18653/v1/2026.acl-long.1738>)**
  - Authors: Zerui Chen; Qinggang Zhang; Zhishang Xiang; Zhimin Wei; Linfeng Gao; Xiao Huang; Zhihong Zhang; Jinsong Su.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Xu2025Towards; question: Q-46; review: positional_only -->
- **[Towards Open-World Retrieval-Augmented Generation on Knowledge Graph: A Multi-Agent Collaboration Framework](<https://doi.org/10.1145/3774904.3792389>)**
  - Authors: Jiasheng Xu; Mingda Li; Yongqiang Tang; Peijie Wang; Wensheng Zhang.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: liu2026hmrag; question: Q-46; review: positional_only -->
- **[HM-RAG: Hierarchical Multi-Agent Multimodal Retrieval Augmented Generation](<https://doi.org/10.1145/3746027.3754761>)**
  - Authors: Pei Liu; Xin Liu; Ruoyu Yao; Junming Liu; Siyuan Meng; Ding Wang; Jun Ma.
  - Venue / outlet: **ACM Multimedia** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: N2025Separate; question: Q-46; review: positional_only -->
- **[Separate the Wheat from the Chaff: Winnowing Down Divergent Views in Retrieval Augmented Generation](<https://doi.org/10.18653/v1/2025.emnlp-main.587>)**
  - Authors: Song Wang; Zihan Chen; Peng Wang; Zhepei Wei; Zhen Tan; Yu Meng; Cong Shen; Jundong Li.
  - Venue / outlet: **EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Zhu2025Single; question: Q-46; review: positional_only -->
- **[Single LLM, Multiple Roles: A Unified Retrieval-Augmented Generation Framework Using Role-Specific Token Optimization](<https://arxiv.org/abs/2505.15444>)**
  - Authors: Yutao Zhu; Jiajie Jin; Hongjin Qian; Zheng Liu; Zhicheng Dou; Ji-Rong Wen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: wang2025vidorag; question: Q-46; review: positional_only -->
- **[ViDoRAG: Visual Document Retrieval-Augmented Generation via Dynamic Iterative Reasoning Agents](<https://arxiv.org/abs/2502.18017>)**
  - Authors: Qiuchen Wang; Ruixue Ding; Zehui Chen; Weiqi Wu; Shihang Wang; Pengjun Xie; Feng Zhao.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Suri2025VisDoM; question: Q-46; review: positional_only -->
- **[VisDoM: Multi-Document QA with Visually Rich Elements Using Multimodal Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2025.naacl-long.310>)**
  - Authors: Manan Suri; Puneet Mathur; Franck Dernoncourt; Kanika Goswami; Ryan A. Rossi; Dinesh Manocha.
  - Venue / outlet: **NAACL (Long Papers)** · Year: **2025**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-c5"></a>

### C5. Runtime interfaces and observability

Focus: Authority boundaries; bounded execution; traceability.

Questions: [Q-47](#q-47) · [Q-48](#q-48) · [Q-49](#q-49).

<a id="q-47"></a>

#### Q-47. Which actions and observations should the runtime expose, and within which authority boundaries?

*Focal question.*

<!-- record: Liu2026Auditing; question: Q-47; review: positional_only -->
- **[Auditing Agent Harness Safety](<https://arxiv.org/abs/2605.14271>)**
  - Authors: Chengzhi Liu; Yichen Guo; Yepeng Liu; Yuzhe Yang; Qianqi Yan; Xuandong Zhao; Wenyue Hua; Sheng Liu; Sharon Li; Yuheng Bu; Xin Eric Wang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Steiner2025MCP; question: Q-47; review: positional_only -->
- **[MCP vs RAG vs NLWeb vs HTML: A Comparison of the Effectiveness and Efficiency of Different Agent Interfaces to the Web](<https://www.semanticscholar.org/paper/76fdffbfb274dece6bc7dc8fc64856cead272c3a>)**
  - Authors: Aaron Steiner; R. Peeters; Christian Bizer.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-48"></a>

#### Q-48. How should the runtime make state transitions, retries, and recovery bounded and auditable?

*Focal question.*

<!-- record: Zhu2026RE; question: Q-48; review: positional_only -->
- **[RE-TRAC: REcursive TRAjectory Compression for Deep Search Agents](<https://arxiv.org/abs/2602.02486>)**
  - Authors: Jialiang Zhu; Gongrui Zhang; Xiaolong Ma; Lin Xu; Miaosen Zhang; Ruiqi Yang; Song Wang; Kai Qiu; Zhirong Wu; Qi Dai; Ruichun Ma; Bei Liu; Yifan Yang; Chong Luo; Zhengyuan Yang; Linjie Li; Lijuan Wang; Weizhu Chen; Xin Geng; Baining Guo.
  - Venue / outlet: **ICML** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Cornelio2025Hierarchical; question: Q-48; review: positional_only -->
- **[Hierarchical Planning for Complex Tasks with Knowledge Graph-RAG and Symbolic Verification](<https://arxiv.org/abs/2504.04578>)**
  - Authors: Cristina Cornelio; Flavio Petruzzellis; Pietro Lio.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Yu2025TableRAG; question: Q-48; review: positional_only -->
- **[TableRAG: A Retrieval Augmented Generation Framework for Heterogeneous Document Reasoning](<https://doi.org/10.18653/v1/2025.emnlp-main.710>)**
  - Authors: Xiaohan Yu; Pu Jian; Chong Chen.
  - Venue / outlet: **EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: jiang2025tcrag; question: Q-48; review: positional_only -->
- **[TC–RAG: Turing–Complete RAG’s Case study on Medical LLM Systems](<https://doi.org/10.18653/v1/2025.acl-long.558>)**
  - Authors: Xinke Jiang; Yue Fang; Rihong Qiu; Haoyu Zhang; Yongxin Xu; Hao Chen; Wentao Zhang; Ruizhe Zhang; Yuchen Fang; Xinyu Ma; Xu Chu; Junfeng Zhao; Yasha Wang.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-49"></a>

#### Q-49. What must be monitored to establish reliable, resource-bounded execution?

*Focal question.*

<!-- record: Helali2025Reliable; question: Q-49; review: positional_only -->
- **[Reliable and Cost-Effective Exploratory Data Analysis via Graph-Guided RAG](<https://doi.org/10.18653/v1/2025.emnlp-main.836>)**
  - Authors: Mossad Helali; Yutai Luo; Tae Jun Ham; Jim Plotts; Ashwin Chaugule; Jichuan Chang; Parthasarathy Ranganathan; Essam Mansour.
  - Venue / outlet: **EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Liu2025SEFRQO; question: Q-49; review: positional_only -->
- **[SEFRQO: A Self-Evolving Fine-Tuned RAG-Based Query Optimizer](<https://doi.org/10.1145/3769826>)**
  - Authors: Hanwen Liu; Qihan Zhang; Ryan Marcus; Ibrahim Sabek.
  - Venue / outlet: **PACMMOD** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Wang2025Towards; question: Q-49; review: positional_only -->
- **[Towards Reliable Agents: Benchmarking Customized LLM-Based Retrieval-Augmented Generation Frameworks with Deployment Validation](<https://doi.org/10.18653/v1/2025.naacl-industry.53>)**
  - Authors: Kevin Shukang Wang; Karel Joshua Harjono; Ramon Lawrence.
  - Venue / outlet: **NAACL (Industry Track)** · Year: **2025**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-c6"></a>

### C6. Learning stateful control

Focus: Long-horizon feedback; shortcuts; transfer.

Questions: [Q-50](#q-50) · [Q-51](#q-51) · [Q-52](#q-52).

<a id="q-50"></a>

#### Q-50. Which stateful decisions should training improve, and over what horizon?

*Focal question.*

<!-- record: Tan2025RAGa; question: Q-50; review: positional_only -->
- **[RAG-R1:Incentivizing the Search and Reasoning Capabilities of LLMs Through Multi-Query Parallelism](<https://doi.org/10.1609/aaai.v40i39.40603>)**
  - Authors: Zhiwen Tan; Jiaming Huang; Qintong Wu; Hongxuan Zhang; Chenyi Zhuang; Jinjie Gu.
  - Venue / outlet: **AAAI** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: ur22025; question: Q-50; review: positional_only -->
- **[UR2 : Unify RAG and Reasoning through Reinforcement Learning](<https://doi.org/10.18653/v1/2026.acl-long.580>)**
  - Authors: Weitao Li; Boran Xiang; Xiaolong Wang; Jingyi Ren; Ante Wang; Zhinan Gou; Weizhi Ma; Yang Liu.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: wang2026vimrag; question: Q-50; review: positional_only -->
- **[VimRAG: Navigating Massive Visual Context in Retrieval-Augmented Generation via Multimodal Memory Graph](<https://arxiv.org/abs/2602.12735v2>)**
  - Authors: Qiuchen Wang; Shihang Wang; Yu Zeng; Qiang Zhang; Fanrui Zhang; Zhuoning Guo; Bosi Zhang; Wenxuan Huang; Lin Chen; Zehui Chen; Pengjun Xie; Ruixue Ding.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: yuan2026memsearcher; question: Q-50; review: positional_only -->
- **[MemSearcher: Training LLMs to Reason, Search and Manage Memory via End-to-End Reinforcement Learning](<https://arxiv.org/abs/2511.02805>)**
  - Authors: Qianhao Yuan; Jie Lou; Zichao Li; Jiawei Chen; Yaojie Lu; Hongyu Lin; Le Sun; Debing Zhang; Xianpei Han.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Song2025Smart; question: Q-50; review: positional_only -->
- **[Smart-Searcher: Incentivizing the Dynamic Knowledge Acquisition of LLMs via Reinforcement Learning](<https://doi.org/10.18653/v1/2025.findings-emnlp.731>)**
  - Authors: Huatong Song; Jinhao Jiang; Wenqing Tian; Zhipeng Chen; Yuhuan Wu; Jiahao Zhao; Yingqian Min; Xin Zhao; Lei Fang; Ji-Rong Wen.
  - Venue / outlet: **Findings of EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Wang2025VRAG; question: Q-50; review: positional_only -->
- **[VRAG-RL: Empower Vision-Perception-Based RAG for Visually Rich Information Understanding via Iterative Reasoning with Reinforcement Learning](<https://arxiv.org/abs/2505.22019>)**
  - Authors: Qiuchen Wang; Ruixue Ding; Yu Zeng; Zehui Chen; Lin Chen; Shihang Wang; Pengjun Xie; Fei Huang; Feng Zhao.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-51"></a>

#### Q-51. How can trajectory feedback teach useful decisions without rewarding shortcuts or leaking privileged information?

*Focal question.*

<!-- record: dgpo2026; question: Q-51; review: positional_only -->
- **[Can Compact Language Models Search Like Agents? Distillation-Guided Policy Optimization for Preserving Agentic RAG Capabilities](<https://doi.org/10.18653/v1/2026.acl-long.1751>)**
  - Authors: Rikuto Kotoge; Mai Nishimura; Jiaxin Ma.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: yu2025graphragr1; question: Q-51; review: positional_only -->
- **[GraphRAG-R1: Graph Retrieval-Augmented Generation with Process-Constrained Reinforcement Learning](<https://doi.org/10.1145/3774904.3792589>)**
  - Authors: Chuanyue Yu; Kuo Zhao; Yuhan Li; Heng Chang; Mingjian Feng; Xiangzhe Jiang; Yufei Sun; Jia Li; Yuzhi Zhang; Qingyun Sun; Jianxin Li; Ziwei Zhang.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: acqo2026; question: Q-51; review: positional_only -->
- **[When should I search more: Adaptive Complex Query Optimization with Reinforcement Learning](<https://arxiv.org/abs/2601.21208>)**
  - Authors: Wei Wen; Sihang Deng; Tianjun Wei; Keyu Chen; Ruizhi Qiao; Xing Sun.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: aisearchplanner2025; question: Q-51; review: positional_only -->
- **[AI-SearchPlanner: Modular Agentic Search via Pareto-Optimal Multi-Objective Reinforcement Learning](<https://arxiv.org/abs/2508.20368>)**
  - Authors: Lang Mei; Zhihan Yang; Xiaohan Yu; Huanyao Zhang; Chong Chen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: evorag2026; question: Q-51; review: positional_only -->
- **[Curriculum Guided Reinforcement Learning for Efficient Multi Hop Retrieval Augmented Generation](<https://arxiv.org/abs/2505.17391>)**
  - Authors: Yuelyu Ji; Rui Meng; Zhuochun Li; Daqing He.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: leng2025decex; question: Q-51; review: positional_only -->
- **[DecEx-RAG: Boosting Agentic Retrieval-Augmented Generation with Decision and Execution Optimization via Process Supervision](<https://arxiv.org/abs/2510.05691>)**
  - Authors: Yongqi Leng; Yikun Lei; Xikai Liu; Meizhi Zhong; Bojian Xiong; Yurong Zhang; Yan Gao; Yi Wu; Yao Hu; Deyi Xiong.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: hiprag2025; question: Q-51; review: positional_only -->
- **[HiPRAG: Hierarchical Process Rewards for Efficient Agentic Retrieval Augmented Generation](<https://arxiv.org/abs/2510.07794>)**
  - Authors: Peilin Wu; Mian Zhang; Kun Wan; Wentian Zhao; Kaiyu He; Xinya Du; Zhiyu Chen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Wang2025InstructRAG; question: Q-51; review: positional_only -->
- **[InstructRAG: Leveraging Retrieval-Augmented Generation on Instruction Graphs for LLM-Based Task Planning](<https://doi.org/10.1145/3726302.3730009>)**
  - Authors: Zheng Wang; Shu Xian Teo; Jun Jie Chew; Wei Shi.
  - Venue / outlet: **SIGIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Li2025KnowTrace; question: Q-51; review: positional_only -->
- **[KnowTrace: Bootstrapping Iterative Retrieval-Augmented Generation with Structured Knowledge Tracing](<https://doi.org/10.1145/3711896.3737015>)**
  - Authors: Rui Li; Quanyu Dai; Zeyu Zhang; Xu Chen; Zhenhua Dong; Ji-Rong Wen.
  - Venue / outlet: **KDD (Vol. 2)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Wu2025MaskSearch; question: Q-51; review: positional_only -->
- **[MaskSearch: A Universal Pre-Training Framework to Enhance Agentic Search Capability](<https://arxiv.org/abs/2505.20285>)**
  - Authors: Weiqi Wu; Xin Guan; Shen Huang; Yong Jiang; Pengjun Xie; Fei Huang; Jiuxin Cao; Hai Zhao; Jingren Zhou.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: r1searcher2025; question: Q-51; review: positional_only -->
- **[R1-Searcher: Incentivizing the Search Capability in LLMs via Reinforcement Learning](<https://arxiv.org/abs/2503.05592>)**
  - Authors: Huatong Song; Jinhao Jiang; Yingqian Min; Jie Chen; Zhipeng Chen; Wayne Xin Zhao; Lei Fang; Ji-Rong Wen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: research2025; question: Q-51; review: positional_only -->
- **[ReSearch: Learning to Reason with Search for LLMs via Reinforcement Learning](<https://arxiv.org/abs/2503.19470>)**
  - Authors: Mingyang Chen; Linzhuang Sun; Tianpeng Li; Haoze Sun; Yijie Zhou; Chenzheng Zhu; Haofen Wang; Jeff Z. Pan; Wen Zhang; Huajun Chen; Fan Yang; Zenan Zhou; Weipeng Chen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: jin2025searchr1; question: Q-51; review: positional_only -->
- **[Search-R1: Training LLMs to Reason and Leverage Search Engines with Reinforcement Learning](<https://arxiv.org/abs/2503.09516>)**
  - Authors: Bowen Jin; Hansi Zeng; Zhenrui Yue; Jinsung Yoon; Sercan Arik; Dong Wang; Hamed Zamani; Jiawei Han.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: stepsearch2025; question: Q-51; review: positional_only -->
- **[StepSearch: Igniting LLMs Search Ability via Step-Wise Proximal Policy Optimization](<https://arxiv.org/abs/2505.15107>)**
  - Authors: Ziliang Wang; Xuhui Zheng; Kang An; Cijun Ouyang; Jialu Cai; Yuhang Wang; Yichao Wu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Lu2025Towards; question: Q-51; review: positional_only -->
- **[Towards Doctor-Like Reasoning: Medical RAG Fusing Knowledge with Patient Analogy through Textual Gradients](<https://www.semanticscholar.org/paper/6496b8db95a56a535ebcdba202a675f483633cae>)**
  - Authors: Yuxing Lu; Gecheng Fu; Wei Wu; Xukai Zhao; Goi Sin; Jinzhuo Wang.
  - Venue / outlet: **NeurIPS** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-52"></a>

#### Q-52. What learned behavior transfers when tools, evidence, and resource budgets change?

*Focal question.*

<!-- record: zhou2026ragscalerl; question: Q-52; review: positional_only -->
- **[The Retrieval Bottleneck: Scaling Laws for Reinforcement Learning in RAG](<https://doi.org/10.18653/v1/2026.acl-long.1478>)**
  - Authors: Shu Zhou; Jinman Leng; Yufei Song; Xin Wang; Tao Fan; Hao Wang.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Dai2025Careful; question: Q-52; review: positional_only -->
- **[Careful Queries, Credible Results: Teaching RAG Models Advanced Web Search Tools with Reinforcement Learning](<https://arxiv.org/abs/2508.07956>)**
  - Authors: Yuqin Dai; Shuo Yang; Guoqing Wang; Yong Deng; Zhanwei Zhang; Jun Yin; Pengyu Zeng; Zhenzhe Ying; Changhua Meng; Can Yi; Yuchen Zhou; Weiqiang Wang; Shuai Lu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: deepresearcher2025; question: Q-52; review: positional_only -->
- **[DeepResearcher: Scaling Deep Research via Reinforcement Learning in Real-world Environments](<https://arxiv.org/abs/2504.03160>)**
  - Authors: Yuxiang Zheng; Dayuan Fu; Xiangkun Hu; Xiaojie Cai; Lyumanshan Ye; Pengrui Lu; Pengfei Liu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-c7"></a>

### C7. Matched capability comparisons

Focus: Confounding control with resources or parallel capacity.

Questions: [Q-53](#q-53).

<a id="q-53"></a>

#### Q-53. Which matched comparisons substantiate a claimed agentic capability?

*Focal question.*

<!-- record: leng2025decex; question: Q-53; review: positional_only -->
- **[DecEx-RAG: Boosting Agentic Retrieval-Augmented Generation with Decision and Execution Optimization via Process Supervision](<https://arxiv.org/abs/2510.05691>)**
  - Authors: Yongqi Leng; Yikun Lei; Xikai Liu; Meizhi Zhong; Bojian Xiong; Yurong Zhang; Yan Gao; Yi Wu; Yao Hu; Deyi Xiong.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: deepresearcher2025; question: Q-53; review: positional_only -->
- **[DeepResearcher: Scaling Deep Research via Reinforcement Learning in Real-world Environments](<https://arxiv.org/abs/2504.03160>)**
  - Authors: Yuxiang Zheng; Dayuan Fu; Xiangkun Hu; Xiaojie Cai; Lyumanshan Ye; Pengrui Lu; Pengfei Liu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: hiprag2025; question: Q-53; review: positional_only -->
- **[HiPRAG: Hierarchical Process Rewards for Efficient Agentic Retrieval Augmented Generation](<https://arxiv.org/abs/2510.07794>)**
  - Authors: Peilin Wu; Mian Zhang; Kun Wan; Wentian Zhao; Kaiyu He; Xinya Du; Zhiyu Chen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: marag2025; question: Q-53; review: positional_only -->
- **[MA-RAG: Multi-Agent Retrieval-Augmented Generation via Collaborative Chain-of-Thought Reasoning](<https://arxiv.org/abs/2505.20096>)**
  - Authors: Thang Nguyen; Peter Chin; Yu-Wing Tai.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: r1searcher2025; question: Q-53; review: positional_only -->
- **[R1-Searcher: Incentivizing the Search Capability in LLMs via Reinforcement Learning](<https://arxiv.org/abs/2503.05592>)**
  - Authors: Huatong Song; Jinhao Jiang; Yingqian Min; Jie Chen; Zhipeng Chen; Wayne Xin Zhao; Lei Fang; Ji-Rong Wen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: jin2025searchr1; question: Q-53; review: positional_only -->
- **[Search-R1: Training LLMs to Reason and Leverage Search Engines with Reinforcement Learning](<https://arxiv.org/abs/2503.09516>)**
  - Authors: Bowen Jin; Hansi Zeng; Zhenrui Yue; Jinsung Yoon; Sercan Arik; Dong Wang; Hamed Zamani; Jiawei Han.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: sirag2025; question: Q-53; review: positional_only -->
- **[SIRAG: Towards Stable and Interpretable RAG with A Process-Supervised Multi-Agent Framework](<https://arxiv.org/abs/2509.18167>)**
  - Authors: Junlin Wang; Zehao Wu; Shaowei Lu; Yanlan Li; Xinghao Huang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: hipporag2024; question: Q-53; review: positional_only -->
- **[HippoRAG: Neurobiologically Inspired Long-Term Memory for Large Language Models](<https://arxiv.org/abs/2405.14831>)**
  - Authors: Bernal Jiménez Gutiérrez; Yiheng Shu; Yu Gu; Michihiro Yasunaga; Yu Su.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="domain-d"></a>

## D. Evaluation and evidence for claims

What observations make an application, capability, or scaling claim defensible?

<a id="group-d1"></a>

### D1. Claim definition

Focus: A metric may not identify the intended construct.

Questions: [Q-54](#q-54).

<a id="q-54"></a>

#### Q-54. What precisely is the evaluation claim, and which observations could support it?

*Focal question.*

No inherited question-level paper assignment in the v16 taxonomy. This is an explicit curation gap, not a claim that the question has no relevant literature.

[Back to contents](#contents)

<a id="group-d2"></a>

### D2. Evaluation objects

Focus: Hidden upstream failures and state transitions.

Questions: [Q-55](#q-55) · [Q-56](#q-56) · [Q-57](#q-57) · [Q-58](#q-58) · [Q-59](#q-59) · [Q-60](#q-60).

<a id="q-55"></a>

#### Q-55. Does the available knowledge support the task, and which source defects limit the attainable answer?

*Focal question.*

<!-- record: ouyang2025hoh; question: Q-55; review: positional_only -->
- **[HoH: A Dynamic Benchmark for Evaluating the Impact of Outdated Information on Retrieval-Augmented Generation](<https://arxiv.org/abs/2503.04800>)**
  - Authors: Jie Ouyang; Tingyue Pan; Mingyue Cheng; Ruiran Yan; Yucong Luo; Jiaying Lin; Qi Liu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: liang2025saferag; question: Q-55; review: positional_only -->
- **[SafeRAG: Benchmarking Security in Retrieval-Augmented Generation of Large Language Model](<https://arxiv.org/abs/2501.18636>)**
  - Authors: Xun Liang; Simin Niu; Zhiyu Li; Sensen Zhang; Hanyu Wang; Feiyu Xiong; Jason Zhaoxin Fan; Bo Tang; Shichao Song; Mengwei Wang; Jiawei Yang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: difallah2025wikirag; question: Q-55; review: positional_only -->
- **[WikiRAG: Revisiting Wikidata KGC Datasets with Community Updates and Retrieval-Augmented Generation](<https://doi.org/10.1145/3711896.3737444>)**
  - Authors: Djellel Difallah.
  - Venue / outlet: **KDD (Vol. 2)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-56"></a>

#### Q-56. How well does retrieval rank useful evidence and assemble a jointly sufficient set?

*Focal question.*

<!-- record: Tian2025Is; question: Q-56; review: positional_only -->
- **[Is Relevance Propagated from Retriever to Generator in RAG?](<https://arxiv.org/abs/2502.15025>)**
  - Authors: Fangzheng Tian; Debasis Ganguly; Craig Macdonald.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: abdallah2025rerankarena; question: Q-56; review: positional_only -->
- **[RerankArena: A Unified Platform for Evaluating Retrieval, Reranking and RAG with Human and LLM Feedback](<https://doi.org/10.1145/3746252.3761484>)**
  - Authors: Abdelrahman Abdallah; Mahmoud Abdalla; Bhawna Piryani; Jamshid Mozafari; Mohammed Ali; Adam Jatowt.
  - Venue / outlet: **CIKM** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: su2024bright; question: Q-56; review: positional_only -->
- **[BRIGHT: A Realistic and Challenging Benchmark for Reasoning-Intensive Retrieval](<https://arxiv.org/abs/2407.12883>)**
  - Authors: Hongjin Su; Howard Yen; Mengzhou Xia; Weijia Shi; Niklas Muennighoff; Han-yu Wang; Haisu Liu; Quan Shi; Zachary S. Siegel; Michael Tang; Ruoxi Sun; Jinsung Yoon; Sercan O. Arik; Danqi Chen; Tao Yu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: salemi2024erag; question: Q-56; review: positional_only -->
- **[Evaluating Retrieval Quality in Retrieval-Augmented Generation](<https://arxiv.org/pdf/2404.13781>)**
  - Authors: Alireza Salemi; Hamed Zamani.
  - Venue / outlet: **SIGIR** · Year: **2024**.
  - Association review: [P](#how-to-use).

<a id="q-57"></a>

#### Q-57. Was sufficient evidence preserved in the context, and did the generator use it appropriately?

*Focal question.*

<!-- record: gao2025uniah; question: Q-57; review: positional_only -->
- **[U-NIAH: Unified RAG and LLM Evaluation for Long Context Needle-in-a-Haystack](<https://doi.org/10.1145/3786609>)**
  - Authors: Yunfan Gao; Yun Xiong; Wenlong Wu; Bohan Li; Yijie Zhong; Haofen Wang.
  - Venue / outlet: **ACM TOIS** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: hagstrom2024reality; question: Q-57; review: positional_only -->
- **[A Reality Check on Context Utilisation for Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2025.acl-long.968>)**
  - Authors: Lovisa Hagström; Sara Vera Marjanovic; Haeun Yu; Arnav Arora; Christina Lioma; Maria Maistro; Pepa Atanasova; Isabelle Augenstein.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Vladika2025Influence; question: Q-57; review: positional_only -->
- **[On the Influence of Context Size and Model Choice in Retrieval-Augmented Generation Systems](<https://arxiv.org/abs/2502.14759>)**
  - Authors: Juraj Vladika; Florian Matthes.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Amiraz2025Distracting; question: Q-57; review: positional_only -->
- **[The Distracting Effect: Understanding Irrelevant Passages in RAG](<https://doi.org/10.18653/v1/2025.acl-long.892>)**
  - Authors: Chen Amiraz; Florin Cuconasu; Simone Filice; Zohar Karnin.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-58"></a>

#### Q-58. Which claims does the response make, and are they correct, supported, and appropriately attributed?

*Focal question.*

<!-- record: zheng2026citerag; question: Q-58; review: positional_only -->
- **[What Should I Cite? A RAG Benchmark for Academic Citation Prediction](<https://doi.org/10.1145/3774904.3792075>)**
  - Authors: Leqi Zheng; Jiajun Zhang; Canzhi Chen; Chaokun Wang; Hongwei Li; Yuying Li; Yaoxin Mao; Shannan Yan; Zixin Song; Zhiyuan Feng; Zhaolu Kang; Zirong Chen; Hang Zhang; Qiang Liu; Liang Wang; Ziyang Liu.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: xu2025citeeval; question: Q-58; review: positional_only -->
- **[CiteEval: Principle-Driven Citation Evaluation for Source Attribution](<https://arxiv.org/abs/2506.01829>)**
  - Authors: Yumo Xu; Peng Qi; Jifan Chen; Kunlun Liu; Rujun Han; Lan Liu; Bonan Min; Vittorio Castelli; Arshit Gupta; Zhiguo Wang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: wallat2025correctness; question: Q-58; review: positional_only -->
- **[Correctness is not Faithfulness in Retrieval Augmented Generation Attributions](<https://doi.org/10.1145/3731120.3744592>)**
  - Authors: Jonas Wallat; Maria Heuss; Maarten de Rijke; Avishek Anand.
  - Venue / outlet: **ICTIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: hirsch2025laquer; question: Q-58; review: positional_only -->
- **[LAQuer: Localized Attribution Queries in Content-grounded Generation](<https://arxiv.org/abs/2506.01187>)**
  - Authors: Eran Hirsch; Aviv Slobodkin; David Wan; Elias Stengel-Eskin; Mohit Bansal; Ido Dagan.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: gao2023alce; question: Q-58; review: positional_only -->
- **[Enabling Large Language Models to Generate Text with Citations](<https://arxiv.org/abs/2305.14627>)**
  - Authors: Tianyu Gao; Howard Yen; Jiatong Yu; Danqi Chen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2023**.
  - Association review: [P](#how-to-use).

<a id="q-59"></a>

#### Q-59. What does end-to-end task success reveal, and which failures remain hidden?

*Focal question.*

<!-- record: Leung2025Classifying; question: Q-59; review: positional_only -->
- **[Classifying and Addressing the Diversity of Errors in Retrieval-Augmented Generation Systems](<https://arxiv.org/abs/2510.13975>)**
  - Authors: Kin Kwan Leung; Mouloud Belbahri; Yi Sui; Alex Labach; Xueying Zhang; Stephen Anthony Rose; Jesse C. Cresswell.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Dong2025RAG; question: Q-59; review: positional_only -->
- **[RAG-Critic: Leveraging Automated Critic-Guided Agentic Workflow for Retrieval Augmented Generation](<https://doi.org/10.18653/v1/2025.acl-long.179>)**
  - Authors: Guanting Dong; Jiajie Jin; Xiaoxi Li; Yutao Zhu; Zhicheng Dou; Ji-Rong Wen.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: hsia2024ragged; question: Q-59; review: positional_only -->
- **[RAGGED: Towards Informed Design of Scalable and Stable RAG Systems](<https://proceedings.mlr.press/v267/hsia25a.html>)**
  - Authors: Jennifer Hsia; Afreen Shaikh; Zora Zhiruo Wang; Graham Neubig.
  - Venue / outlet: **ICML** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Kim2025Where; question: Q-59; review: positional_only -->
- **[Where Does Legal AI Fail? Evaluating RAG Pipelines](<https://doi.org/10.1145/3746252.3761151>)**
  - Authors: Yongjae Kim; Wonjae Lee.
  - Venue / outlet: **CIKM** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: ru2024ragchecker; question: Q-59; review: positional_only -->
- **[RAGChecker: A Fine-grained Framework for Diagnosing Retrieval-Augmented Generation](<https://arxiv.org/abs/2408.08067>)**
  - Authors: Dongyu Ru; Lin Qiu; Xiangkun Hu; Tianhang Zhang; Peng Shi; Shuaichen Chang; Cheng Jiayang; Cunxiang Wang; Shichao Sun; Huanyu Li; Zizhao Zhang; Binjie Wang; Jiarong Jiang; Tong He; Zhiguo Wang; Pengfei Liu; Yue Zhang; Zheng Zhang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<a id="q-60"></a>

#### Q-60. Which states, actions, and interactions must be observed to evaluate a stateful RAG system?

*Focal question.*

No inherited question-level paper assignment in the v16 taxonomy. This is an explicit curation gap, not a claim that the question has no relevant literature.

[Back to contents](#contents)

<a id="group-d3"></a>

### D3. Quality and operational dimensions

Focus: Conflated quality dimensions; loaded-service performance.

Questions: [Q-61](#q-61) · [Q-62](#q-62) · [Q-63](#q-63) · [Q-64](#q-64) · [Q-65](#q-65).

<a id="q-61"></a>

#### Q-61. How should correctness, request relevance, and information coverage be measured without conflating them?

*Focal question.*

<!-- record: Pradeep2025Great; question: Q-61; review: positional_only -->
- **[The Great Nugget Recall: Automating Fact Extraction and RAG Evaluation with Large Language Models](<https://doi.org/10.1145/3726302.3730090>)**
  - Authors: Ronak Pradeep; Nandan Thakur; Shivani Upadhyay; Daniel Campos; Nick Craswell; Ian Soboroff; Hoa Trang Dang; Jimmy Lin.
  - Venue / outlet: **SIGIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Dong2025Toward; question: Q-61; review: positional_only -->
- **[Toward Verifiable Instruction-Following Alignment for Retrieval Augmented Generation](<https://doi.org/10.1609/aaai.v39i22.34551>)**
  - Authors: Guanting Dong; Xiaoshuai Song; Yutao Zhu; Runqi Qiao; Zhicheng Dou; Ji-Rong Wen.
  - Venue / outlet: **AAAI** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Qi2024LONG; question: Q-61; review: positional_only -->
- **[LONG²RAG: Evaluating Long-Context &amp; Long-Form Retrieval-Augmented Generation with Key Point Recall](<https://www.semanticscholar.org/paper/edb2cc0f2d7ae50717b708292a543b319bae026e>)**
  - Authors: Zehan Qi; Rongwu Xu; Zhijiang Guo; Cunxiang Wang; Hao Zhang; Wei Xu.
  - Venue / outlet: **EMNLP** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: min2023factscore; question: Q-61; review: positional_only -->
- **[FActScore: Fine-grained Atomic Evaluation of Factual Precision in Long Form Text Generation](<https://arxiv.org/pdf/2305.14251>)**
  - Authors: Sewon Min; Kalpesh Krishna; Xinxi Lyu; M. Lewis; Wen-tau Yih; Pang Wei Koh; Mohit Iyyer; Luke Zettlemoyer; Hannaneh Hajishirzi.
  - Venue / outlet: **EMNLP** · Year: **2023**.
  - Association review: [P](#how-to-use).

<a id="q-62"></a>

#### Q-62. What exactly does a grounding or attribution score establish about evidence and the answer?

*Focal question.*

<!-- record: Liu2026Chain; question: Q-62; review: positional_only -->
- **[Chain of Evidence: Pixel-Level Visual Attribution for Iterative Retrieval-Augmented Generation](<https://sigir2026.org/en-AU/pages/program/accepted-papers>)**
  - Authors: Peiyang Liu; Ziqiang Cui; Xi Wang; Di Liang; Wei Ye.
  - Venue / outlet: **SIGIR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Yang2026Logic; question: Q-62; review: positional_only -->
- **[Logic Matters in Lightweight Hallucination Classification for RAG System](<https://aclanthology.org/2026.acl-long.73/>)**
  - Authors: Ningyuan Yang; Kaizhu Huang.
  - Venue / outlet: **ACL** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: wallat2025correctness; question: Q-62; review: positional_only -->
- **[Correctness is not Faithfulness in Retrieval Augmented Generation Attributions](<https://doi.org/10.1145/3731120.3744592>)**
  - Authors: Jonas Wallat; Maria Heuss; Maarten de Rijke; Avishek Anand.
  - Venue / outlet: **ICTIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Ma2025VISA; question: Q-62; review: positional_only -->
- **[VISA: Retrieval Augmented Generation with Visual Source Attribution](<https://doi.org/10.18653/v1/2025.acl-long.1456>)**
  - Authors: Xueguang Ma; Shengyao Zhuang; Bevan Koopman; Guido Zuccon; Wenhu Chen; Jimmy Lin.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-63"></a>

#### Q-63. Which changes should preserve an answer, and which should cause it to change?

*Focal question.*

<!-- record: Zhou2025EmoRAG; question: Q-63; review: positional_only -->
- **[EmoRAG: Evaluating RAG Robustness to Symbolic Perturbations](<https://doi.org/10.1145/3770854.3780238>)**
  - Authors: Xinyun Zhou; Xinfeng Li; Yinan Peng; Ming Xu; Xuanwang Zhang; Miao Yu; Yidong Wang; Xiaojun Jia; Kun Wang; Qingsong Wen; XiaoFeng Wang; Wei Dong.
  - Venue / outlet: **KDD (Vol. 1)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: trivia2026; question: Q-63; review: positional_only -->
- **[Rethinking Evaluation for LLM Hallucination Detection: A Desiderata, A New RAG-based Benchmark, New Insights](<https://doi.org/10.18653/v1/2026.acl-long.680>)**
  - Authors: Wenbo Chen; Veena Padmanabhan; Tootiya Giyahchi; Elaine Wong; Leman Akoglu.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Lee2025MAGIC; question: Q-63; review: positional_only -->
- **[MAGIC: A Multi-Hop and Graph-Based Benchmark for Inter-Context Conflicts in Retrieval-Augmented Generation](<https://arxiv.org/abs/2507.21544>)**
  - Authors: Jungyeon Lee; Kangmin Lee; Taeuk Kim.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Cao2025Out; question: Q-63; review: positional_only -->
- **[Out of Style: RAG's Fragility to Linguistic Variation](<https://arxiv.org/abs/2504.08231>)**
  - Authors: Tianyu Cao; Neel Bhandari; Akhila Yerukola; Akari Asai; Maarten Sap.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: peng2025uaeval4rag; question: Q-63; review: positional_only -->
- **[Unanswerability Evaluation for Retrieval Augmented Generation](<https://doi.org/10.18653/v1/2025.acl-long.415>)**
  - Authors: Xiangyu Peng; Prafulla Kumar Choubey; Caiming Xiong; Chien-Sheng Wu.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Yao2025Who; question: Q-63; review: positional_only -->
- **[Who is in the Spotlight: The Hidden Bias Undermining Multimodal Retrieval-Augmented Generation](<https://arxiv.org/abs/2506.11063>)**
  - Authors: Jiayu Yao; Shenghua Liu; Yiwei Wang; Lingrui Mei; Baolong Bi; Yuyao Ge; Zhecheng Li; Xueqi Cheng.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: zeng2025worse; question: Q-63; review: positional_only -->
- **[Worse than Zero-shot? A Fact-Checking Dataset for Evaluating the Robustness of RAG Against Misleading Retrievals](<https://arxiv.org/abs/2502.16101>)**
  - Authors: Linda Zeng; Rithwik Gupta; Divij Motwani; Yi Zhang; Diji Yang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-64"></a>

#### Q-64. Which harms or disparities are tested, at what boundary, and against which threat or population model?

*Focal question.*

<!-- record: Abolghasemi2025Evaluation; question: Q-64; review: positional_only -->
- **[Evaluation of Attribution Bias in Generator-Aware Retrieval-Augmented Large Language Models](<https://doi.org/10.18653/v1/2025.findings-acl.1087>)**
  - Authors: Amin Abolghasemi; Leif Azzopardi; Seyyed Hadi Hashemi; Maarten de Rijke; Suzan Verberne.
  - Venue / outlet: **Findings of ACL** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Li2025LLMs; question: Q-64; review: positional_only -->
- **[LLMs Trust Humans More, That’s a Problem! Unveiling and Mitigating the Authority Bias in Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2025.acl-long.1400>)**
  - Authors: Yuxuan Li; Xinwei Guo; Jiashi Gao; Guanhua Chen; Xiangyu Zhao; Jiaxin Zhang; Quanying Liu; Haiyan Wu; Xin Yao; Xuetao Wei.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: liang2025saferag; question: Q-64; review: positional_only -->
- **[SafeRAG: Benchmarking Security in Retrieval-Augmented Generation of Large Language Model](<https://arxiv.org/abs/2501.18636>)**
  - Authors: Xun Liang; Simin Niu; Zhiyu Li; Sensen Zhang; Hanyu Wang; Feiyu Xiong; Jason Zhaoxin Fan; Bo Tang; Shichao Song; Mengwei Wang; Jiawei Yang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Hu2024No; question: Q-64; review: positional_only -->
- **[No Free Lunch: Retrieval-Augmented Generation Undermines Fairness in LLMs, Even for Vigilant Users](<https://arxiv.org/abs/2410.07589>)**
  - Authors: Mengxuan Hu; Hongyi Wu; Zihan Guan; Ronghang Zhu; Dongliang Guo; Daiqing Qi; Sheng Li.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<a id="q-65"></a>

#### Q-65. What task quality and useful throughput are sustained under specified latency, cost, and load constraints?

*Focal question.*

<!-- record: Kwarteng2026SAGE; question: Q-65; review: positional_only -->
- **[SAGE-RAI: Design Patterns for Transparent RAG Systems](<https://doi.org/10.1145/3774904.3792929>)**
  - Authors: Joseph Kwarteng; Aisling Third; Alexander Mikroyannidis; David Tarrant; John Domingue.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Lajewska2026Trust; question: Q-65; review: positional_only -->
- **[Trust Me on This: A User Study of Trustworthiness for RAG Responses](<https://arxiv.org/abs/2601.14460>)**
  - Authors: Weronika Łajewska; Krisztian Balog.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: yao2024cacheblend; question: Q-65; review: positional_only -->
- **[CacheBlend: Fast Large Language Model Serving for RAG with Cached Knowledge Fusion](<https://arxiv.org/abs/2405.16444v3>)**
  - Authors: Jiayi Yao; Hanchen Li; Yuhan Liu; Siddhant Ray; Yihua Cheng; Qizheng Zhang; Kuntai Du; Shan Lu; Junchen Jiang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: jin2024ragcache; question: Q-65; review: positional_only -->
- **[RAGCache: Efficient Knowledge Caching for Retrieval-Augmented Generation](<https://arxiv.org/abs/2404.12457v2>)**
  - Authors: Chao Jin; Zili Zhang; Xuanlin Jiang; Fangyue Liu; Xin Liu; Xuanzhe Liu; Xin Jin.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: agrawal2024sarathi; question: Q-65; review: positional_only -->
- **[Taming Throughput-Latency Tradeoff in LLM Inference with Sarathi-Serve](<https://www.usenix.org/conference/osdi24/presentation/agrawal>)**
  - Authors: Amey Agrawal; Nitin Kedia; Ashish Panwar; Jayashree Mohan; Nipun Kwatra; Bhargav Gulavani; Alexey Tumanov; Ramachandran Ramjee.
  - Venue / outlet: **OSDI** · Year: **2024**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-d4"></a>

### D4. Evaluation settings

Focus: Unrepresentative populations, sources, or stressors.

Questions: [Q-66](#q-66) · [Q-67](#q-67) · [Q-68](#q-68) · [Q-69](#q-69) · [Q-70](#q-70).

<a id="q-66"></a>

#### Q-66. Which domain conditions and source assumptions make an evaluation representative of its intended use?

*Focal question.*

<!-- record: Zheng2025Benchmarking; question: Q-66; review: positional_only -->
- **[Benchmarking Foundation Models with Retrieval-Augmented Generation in Olympic-Level Physics Problem Solving](<https://arxiv.org/abs/2510.00919>)**
  - Authors: Shunfeng Zheng; Yudi Zhang; Meng Fang; Zihan Zhang; Zhitan Wu; Mykola Pechenizkiy; Ling Chen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Wang2025FinS; question: Q-66; review: positional_only -->
- **[FinS-Pilot: A Benchmark for Online Financial RAG System](<https://doi.org/10.1145/3746252.3761643>)**
  - Authors: Feng Wang; Yiding Sun; Jiaxin Mao; Xue Wei; Danqing Xu.
  - Venue / outlet: **CIKM** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Lin2025ScIRGen; question: Q-66; review: positional_only -->
- **[ScIRGen: Synthesize Realistic and Large-Scale RAG Dataset for Scientific Research](<https://doi.org/10.1145/3711896.3737432>)**
  - Authors: Junyong Lin; Lu Dai; Ruiqian Han; Yijie Sui; Ruilin Wang; Xingliang Sun; Qinglin Wu; Min Feng; Hao Liu; Hui Xiong.
  - Venue / outlet: **KDD (Vol. 2)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-67"></a>

#### Q-67. How should language and cultural coverage be separated from retrieval, generation, and judge performance?

*Focal question.*

<!-- record: anugraha2026m4rag; question: Q-67; review: positional_only -->
- **[M4-RAG: A Massive-Scale Multilingual Multi-Cultural Multimodal RAG](<https://openaccess.thecvf.com/content/CVPR2026/html/Anugraha_M4-RAG_A_Massive-Scale_Multilingual_Multi-Cultural_Multimodal_RAG_CVPR_2026_paper.html>)**
  - Authors: David Anugraha; Patrick Amadeus Irawan; Anshul Singh; En-Shiun Annie Lee; Genta Indra Winata.
  - Venue / outlet: **CVPR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Kim2025Ko; question: Q-67; review: positional_only -->
- **[Ko-LongRAG: A Korean Long-Context RAG Benchmark Built with a Retrieval-Free Approach](<https://doi.org/10.18653/v1/2025.findings-emnlp.938>)**
  - Authors: Yongil Kim; Heuiyeen Yeen; Hyeongu Yun; Jinsik Lee.
  - Venue / outlet: **Findings of EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Blandon2025MEMERAG; question: Q-67; review: positional_only -->
- **[MEMERAG: A Multilingual End-to-End Meta-Evaluation Benchmark for Retrieval Augmented Generation](<https://arxiv.org/abs/2502.17163>)**
  - Authors: María Andrea Cruz Blandón; Jayasimha Talur; Bruno Charron; Dong Liu; Saab Mansour; Marcello Federico.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Liu2025XRAG; question: Q-67; review: positional_only -->
- **[XRAG: Cross-lingual Retrieval-Augmented Generation](<https://arxiv.org/abs/2505.10089>)**
  - Authors: Wei Liu; Sony Trenous; Leonardo F. R. Ribeiro; Bill Byrne; Felix Hieber.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: thakur2024mirage; question: Q-67; review: positional_only -->
- **[MIRAGE-Bench: Automatic Multilingual Benchmark Arena for Retrieval-Augmented Generation Systems](<https://arxiv.org/abs/2410.13716>)**
  - Authors: Nandan Thakur; Suleman Kazi; Ge Luo; Jimmy Lin; Amin Ahmad.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<a id="q-68"></a>

#### Q-68. At what evidence granularity should multimodal retrieval, reasoning, and attribution be assessed?

*Focal question.*

<!-- record: yang2026chartmrag; question: Q-68; review: positional_only -->
- **[Chart-MRAG: Benchmarking Multimodal Retrieval Augmented Generation on Chart-based Documents](<https://doi.org/10.18653/v1/2026.acl-long.1164>)**
  - Authors: Yuming Yang; Jiang Zhong; Li Jin; Xiao Sun; Jingwang Huang; Jingpeng Gao; Qing Liu; Yang Bai; Jingyuan Zhang; Rui Jiang; Qin Lei; Kaiwen Wei.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Strich2026T2; question: Q-68; review: positional_only -->
- **[T2-RAGBench: Text-and-Table Aware Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2026.eacl-long.8>)**
  - Authors: Jan Strich; Enes Kutay Isgorur; Maximilian Trescher; Chris Biemann; Martin Semmann.
  - Venue / outlet: **EACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: loison2026vidorev3; question: Q-68; review: positional_only -->
- **[ViDoRe V3: A Comprehensive Evaluation of Retrieval Augmented Generation in Complex Real-World Scenarios](<https://doi.org/10.18653/v1/2026.acl-long.755>)**
  - Authors: António Loison; Quentin Macé; Antoine Edy; Victor Xing; Tom Balough; Gabriel de Souza P. Moreira; Bo Liu; Manuel Faysse; Celine Hudelot; Gautier Viaud.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: mrrag2025; question: Q-68; review: positional_only -->
- **[Ask in Any Modality: A Comprehensive Survey on Multimodal Retrieval-Augmented Generation](<https://arxiv.org/abs/2502.08826>)**
  - Authors: Mohammad Mahdi Abootorabi; Amirhosein Zobeiri; Mahdi Dehghani; Mohammadali Mohammadkhani; Bardia Mohammadi; Omid Ghahroodi; Mahdieh Soleymani Baghshah; Ehsaneddin Asgari.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Zhao2025FinRAGBench; question: Q-68; review: positional_only -->
- **[FinRAGBench-V: A Benchmark for Multimodal RAG with Visual Citation in the Financial Domain](<https://arxiv.org/abs/2505.17471>)**
  - Authors: Suifeng Zhao; Zhuoran Jin; Sujian Li; Jun Gao.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-69"></a>

#### Q-69. How should dialogue history, user interaction, and answer form enter the evaluation unit?

*Focal question.*

<!-- record: Katsis2025mtRAG; question: Q-69; review: positional_only -->
- **[&lt;scp&gt;mt&lt;/scp&gt;RAG: A Multi-Turn Conversational Benchmark for Evaluating Retrieval-Augmented Generation Systems](<https://doi.org/10.1162/tacl.a.19>)**
  - Authors: Yannis Katsis; Sara Rosenthal; Kshitij Fadnis; Chulaka Gunasekara; Young-Suk Lee; Lucian Popa; Vraj Shah; Huaiyu Zhu; Danish Contractor; Marina Danilevsky.
  - Venue / outlet: **TACL** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Cheng2025CORAL; question: Q-69; review: positional_only -->
- **[CORAL: Benchmarking Multi-turn Conversational Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2025.findings-naacl.72>)**
  - Authors: Yiruo Cheng; Kelong Mao; Ziliang Zhao; Guanting Dong; Hongjin Qian; Yongkang Wu; Tetsuya Sakai; Ji-Rong Wen; Zhicheng Dou.
  - Venue / outlet: **Findings of NAACL** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Li2025LexRAG; question: Q-69; review: positional_only -->
- **[LexRAG: Benchmarking Retrieval-Augmented Generation in Multi-Turn Legal Consultation Conversation](<https://doi.org/10.1145/3726302.3730340>)**
  - Authors: Haitao Li; Yifan Chen; Hu YiRan; Qingyao Ai; Junjie Chen; Xiaoyu Yang; Jianhui Yang; Yueyue Wu; Zeyang Liu; Yiqun Liu.
  - Venue / outlet: **SIGIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: liu2024chatqa; question: Q-69; review: positional_only -->
- **[ChatQA: Surpassing GPT-4 on Conversational QA and RAG](<https://doi.org/10.52202/079017-0493>)**
  - Authors: Zihan Liu; Wei Ping; Rajarshi Roy; Peng Xu; Chankyu Lee; Mohammad Shoeybi; Bryan Catanzaro.
  - Venue / outlet: **NeurIPS** · Year: **2024**.
  - Association review: [P](#how-to-use).

<a id="q-70"></a>

#### Q-70. How should changing knowledge and controlled stressors be introduced without changing the claim unnoticed?

*Focal question.*

<!-- record: zhou2026brink; question: Q-70; review: positional_only -->
- **[What Breaks Knowledge Graph based RAG? Benchmarking and Empirical Insights into Reasoning under Incomplete Knowledge](<https://doi.org/10.18653/v1/2026.eacl-long.114>)**
  - Authors: Dongzhuoran Zhou; Yuqicheng Zhu; Xiaxia Wang; Hongkuan Zhou; Yuan He; Jiaoyan Chen; Steffen Staab; Evgeny Kharlamov.
  - Venue / outlet: **EACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Lee2025GRADE; question: Q-70; review: positional_only -->
- **[GRADE: Generating multi-hop QA and fine-gRAined Difficulty matrix for RAG Evaluation](<https://arxiv.org/abs/2508.16994>)**
  - Authors: Jeongsoo Lee; Daeyong Kwon; Kyohoon Jin.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Zhang2025Respecting; question: Q-70; review: positional_only -->
- **[Respecting Temporal-Causal Consistency: Entity-Event Knowledge Graphs for Retrieval-Augmented Generation](<https://arxiv.org/abs/2506.05939>)**
  - Authors: Ze Yu Zhang; Zitao Li; Yaliang Li; Bolin Ding; Bryan Kian Hsiang Low.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-d5"></a>

### D5. Metrics, judges, and interventions

Focus: Invalid measures; judge drift; weak causal identification.

Questions: [Q-71](#q-71) · [Q-72](#q-72) · [Q-73](#q-73) · [Q-74](#q-74) · [Q-75](#q-75).

<a id="q-71"></a>

#### Q-71. Which reference-based or executable metric validly measures the intended property?

*Focal question.*

No inherited question-level paper assignment in the v16 taxonomy. This is an explicit curation gap, not a claim that the question has no relevant literature.

<a id="q-72"></a>

#### Q-72. How should a learned evaluator be validated for the decisions its scores will support?

*Focal question.*

<!-- record: Zhang2025Automatic; question: Q-72; review: positional_only -->
- **[An Automatic Method to Estimate Correctness of RAG](<https://www.semanticscholar.org/paper/72c31e5cfa4b5c15d17aa47370baeb009eb79ac8>)**
  - Authors: Chi Zhang; Vivek Datla; Aditya Shrivastava; Alfy Samuel; Zhiqi Huang; Anoop Kumar; Daben Liu.
  - Venue / outlet: **COLING** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: thakur2025assessing; question: Q-72; review: positional_only -->
- **[Assessing Support for the TREC 2024 RAG Track: A Large-Scale Comparative Study of LLM and Human Evaluations](<https://doi.org/10.1145/3726302.3730165>)**
  - Authors: Nandan Thakur; Ronak Pradeep; Shivani Upadhyay; Daniel Campos; Nick Craswell; Ian Soboroff; Hoa Trang Dang; Jimmy Lin.
  - Venue / outlet: **SIGIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: faithjudge2025; question: Q-72; review: positional_only -->
- **[Benchmarking LLM Faithfulness in RAG with Evolving Leaderboards](<https://arxiv.org/abs/2505.04847>)**
  - Authors: Manveer Singh Tamber; Forrest Sheng Bao; Chenyu Xu; Ge Luo; Suleman Kazi; Minseok Bae; Miaoran Li; Ofer Mendelevitch; Renyi Qu; Jimmy Lin.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Liu2025Judge; question: Q-72; review: positional_only -->
- **[Judge as A Judge: Improving the Evaluation of Retrieval-Augmented Generation through the Judge-Consistency of Large Language Models](<https://arxiv.org/abs/2502.18817>)**
  - Authors: Shuliang Liu; Xinze Li; Zhenghao Liu; Yukun Yan; Cheng Yang; Zheni Zeng; Zhiyuan Liu; Maosong Sun; Ge Yu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: ragrewardbench2024; question: Q-72; review: positional_only -->
- **[RAG-RewardBench: Benchmarking Reward Models in Retrieval Augmented Generation for Preference Alignment](<https://doi.org/10.18653/v1/2025.findings-acl.877>)**
  - Authors: Zhuoran Jin; Hongbang Yuan; Tianyi Men; Pengfei Cao; Yubo Chen; Jiexin Xu; Huaijun Li; Xiaojian Jiang; Kang Liu; Jun Zhao.
  - Venue / outlet: **Findings of ACL** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Li2025RAG; question: Q-72; review: positional_only -->
- **[RAG-Zeval: Enhancing RAG Responses Evaluator through End-to-End Reasoning and Ranking-Based Reinforcement Learning](<https://doi.org/10.18653/v1/2025.emnlp-main.1267>)**
  - Authors: Kun Li; Yunxiang Li; Tianhua Zhang; Hongyin Luo; Xixin Wu; James R. Glass; Helen M. Meng.
  - Venue / outlet: **EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Coman2025RAGferee; question: Q-72; review: positional_only -->
- **[RAGferee: Building Contextual Reward Models for Retrieval-Augmented Generation](<https://arxiv.org/abs/2509.26011>)**
  - Authors: Andrei C. Coman; Ionut-Teodor Sorodoc; Leonardo F. R. Ribeiro; Bill Byrne; James Henderson; Adrià de Gispert.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: saadfalcon2023ares; question: Q-72; review: positional_only -->
- **[ARES: An Automated Evaluation Framework for Retrieval-Augmented Generation Systems](<https://doi.org/10.18653/v1/2024.naacl-long.20>)**
  - Authors: Jon Saad-Falcon; Omar Khattab; Christopher Potts; Matei Zaharia.
  - Venue / outlet: **NAACL (Long Papers)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<a id="q-73"></a>

#### Q-73. Which human judgments are needed, and how should annotation and automated assessment be combined?

*Focal question.*

<!-- record: merker2025axioms; question: Q-73; review: positional_only -->
- **[Axioms for Retrieval-Augmented Generation](<https://doi.org/10.1145/3731120.3744601>)**
  - Authors: Jan Heinrich Merker; Maik Fröbe; Benno Stein; Martin Potthast; Matthias Hagen.
  - Venue / outlet: **ICTIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Yang2025Nugget; question: Q-73; review: positional_only -->
- **[Nugget-based Annotation Protocol and Tool For Evaluating Long-form Retrieval-Augmented Generation](<https://doi.org/10.1145/3726302.3730156>)**
  - Authors: Eugene Yang; Dawn Lawrie; Hoa Dang; Ian Soboroff; James Mayfield.
  - Venue / outlet: **SIGIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Gienapp2025Viability; question: Q-73; review: positional_only -->
- **[The Viability of Crowdsourcing for RAG Evaluation](<https://doi.org/10.1145/3726302.3730093>)**
  - Authors: Lukas Gienapp; Tim Hagen; Maik Fröbe; Matthias Hagen; Benno Stein; Martin Potthast; Harrisen Scells.
  - Venue / outlet: **SIGIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-74"></a>

#### Q-74. Which interventions can identify evidence use or component contribution, and under which assumptions?

*Focal question.*

<!-- record: Dietz2026Insider; question: Q-74; review: positional_only -->
- **[Insider Knowledge: How Much Can RAG Systems Gain from Evaluation Secrets?](<https://arxiv.org/abs/2601.13227>)**
  - Authors: Laura Dietz; Bryan Li; Eugene Yang; Dawn Lawrie; William Walden; James Mayfield.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Tan2026PRGB; question: Q-74; review: positional_only -->
- **[PRGB Benchmark: A Robust Placeholder-Assisted Algorithm for Benchmarking Retrieval-Augmented Generation](<https://doi.org/10.1609/aaai.v40i39.40602>)**
  - Authors: Zhehao Tan; Yihan Jiao; Dan Yang; Junwei Liu; Lei Liu; Jie Feng; Duolin Sun; Yue Shen; Jian Wang; Peng Wei; Jinjie Gu.
  - Venue / outlet: **AAAI** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: hagstrom2024reality; question: Q-74; review: positional_only -->
- **[A Reality Check on Context Utilisation for Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2025.acl-long.968>)**
  - Authors: Lovisa Hagström; Sara Vera Marjanovic; Haeun Yu; Arnav Arora; Christina Lioma; Maria Maistro; Pepa Atanasova; Isabelle Augenstein.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Ju2025Controlled; question: Q-74; review: positional_only -->
- **[Controlled Retrieval-augmented Context Evaluation for Long-form RAG](<https://arxiv.org/abs/2506.20051>)**
  - Authors: Jia-Huei Ju; Suzan Verberne; Maarten de Rijke; Andrew Yates.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-75"></a>

#### Q-75. How should continuing evaluation separate system improvement from changes in users, sources, and judges?

*Focal question.*

<!-- record: Garimella2026Situ; question: Q-75; review: positional_only -->
- **[In-Situ Eval: A Modular Framework for Custom and Real-Time RAG Benchmarking](<https://doi.org/10.1609/aaai.v40i48.42348>)**
  - Authors: Ritvik Garimella; Kaushik Roy; Chathurangi Shyalika; Amit Sheth.
  - Venue / outlet: **AAAI** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Filice2025Generating; question: Q-75; review: positional_only -->
- **[Generating Q&amp;A Benchmarks for RAG Evaluation in Enterprise Settings](<https://doi.org/10.18653/v1/2025.acl-industry.33>)**
  - Authors: Simone Filice; Guy Horowitz; David Carmel; Zohar Karnin; Liane Lewin-Eytan; Yoelle Maarek.
  - Venue / outlet: **ACL (Industry Track)** · Year: **2025**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-d6"></a>

### D6. Benchmark and infrastructure portfolio

Focus: Coverage gaps and incompatible protocols.

Questions: [Q-76](#q-76).

<a id="q-76"></a>

#### Q-76. Which combination of benchmarks and infrastructure can support the intended evaluation claims?

*Focal question.*

<!-- record: Wei2025CFVBench; question: Q-76; review: positional_only -->
- **[CFVBench: A Comprehensive Video Benchmark for Fine-grained Multimodal Retrieval-Augmented Generation](<https://doi.org/10.1145/3774904.3792726>)**
  - Authors: Kaiwen Wei; Xiao Liu; Jie Zhang; Zijian Wang; Ruida Liu; Yuming Yang; Xin Xiao; Xiao Sun; Haoyang Zeng; Changzai Pan; Yidan Zhang; Jiang Zhong; Peijin Wang; Yingchao Feng.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Tan2026PRGB; question: Q-76; review: positional_only -->
- **[PRGB Benchmark: A Robust Placeholder-Assisted Algorithm for Benchmarking Retrieval-Augmented Generation](<https://doi.org/10.1609/aaai.v40i39.40602>)**
  - Authors: Zhehao Tan; Yihan Jiao; Dan Yang; Junwei Liu; Lei Liu; Jie Feng; Duolin Sun; Yue Shen; Jian Wang; Peng Wei; Jinjie Gu.
  - Venue / outlet: **AAAI** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: trivia2026; question: Q-76; review: positional_only -->
- **[Rethinking Evaluation for LLM Hallucination Detection: A Desiderata, A New RAG-based Benchmark, New Insights](<https://doi.org/10.18653/v1/2026.acl-long.680>)**
  - Authors: Wenbo Chen; Veena Padmanabhan; Tootiya Giyahchi; Elaine Wong; Leman Akoglu.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Strich2026T2; question: Q-76; review: positional_only -->
- **[T2-RAGBench: Text-and-Table Aware Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2026.eacl-long.8>)**
  - Authors: Jan Strich; Enes Kutay Isgorur; Maximilian Trescher; Chris Biemann; Martin Semmann.
  - Venue / outlet: **EACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: loison2026vidorev3; question: Q-76; review: positional_only -->
- **[ViDoRe V3: A Comprehensive Evaluation of Retrieval Augmented Generation in Complex Real-World Scenarios](<https://doi.org/10.18653/v1/2026.acl-long.755>)**
  - Authors: António Loison; Quentin Macé; Antoine Edy; Victor Xing; Tom Balough; Gabriel de Souza P. Moreira; Bo Liu; Manuel Faysse; Celine Hudelot; Gautier Viaud.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: zhou2026brink; question: Q-76; review: positional_only -->
- **[What Breaks Knowledge Graph based RAG? Benchmarking and Empirical Insights into Reasoning under Incomplete Knowledge](<https://doi.org/10.18653/v1/2026.eacl-long.114>)**
  - Authors: Dongzhuoran Zhou; Yuqicheng Zhu; Xiaxia Wang; Hongkuan Zhou; Yuan He; Jiaoyan Chen; Steffen Staab; Evgeny Kharlamov.
  - Venue / outlet: **EACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: zheng2026citerag; question: Q-76; review: positional_only -->
- **[What Should I Cite? A RAG Benchmark for Academic Citation Prediction](<https://doi.org/10.1145/3774904.3792075>)**
  - Authors: Leqi Zheng; Jiajun Zhang; Canzhi Chen; Chaokun Wang; Hongwei Li; Yuying Li; Yaoxin Mao; Shannan Yan; Zixin Song; Zhiyuan Feng; Zhaolu Kang; Zirong Chen; Hang Zhang; Qiang Liu; Liang Wang; Ziyang Liu.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Katsis2025mtRAG; question: Q-76; review: positional_only -->
- **[&lt;scp&gt;mt&lt;/scp&gt;RAG: A Multi-Turn Conversational Benchmark for Evaluating Retrieval-Augmented Generation Systems](<https://doi.org/10.1162/tacl.a.19>)**
  - Authors: Yannis Katsis; Sara Rosenthal; Kshitij Fadnis; Chulaka Gunasekara; Young-Suk Lee; Lucian Popa; Vraj Shah; Huaiyu Zhu; Danish Contractor; Marina Danilevsky.
  - Venue / outlet: **TACL** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: zhang2025autoevolve; question: Q-76; review: positional_only -->
- **[AutoEvolve: Automatically Evolving Queries for Applicable and Scalable Retrieval-Augmented Generation Benchmarking](<https://doi.org/10.18653/v1/2025.findings-emnlp.403>)**
  - Authors: Ding-Chu Zhang; Xiaowen Zhang; Yue Fei; Renjun Hu; Xiao-Wen Yang; Zhi Zhou; Baixuan Li; Yu-Feng Li; Xing Shi; Wei Lin.
  - Venue / outlet: **Findings of EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Ju2025Controlled; question: Q-76; review: positional_only -->
- **[Controlled Retrieval-augmented Context Evaluation for Long-form RAG](<https://arxiv.org/abs/2506.20051>)**
  - Authors: Jia-Huei Ju; Suzan Verberne; Maarten de Rijke; Andrew Yates.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: lyu2025crudrag; question: Q-76; review: positional_only -->
- **[CRUD-RAG: A Comprehensive Chinese Benchmark for Retrieval-Augmented Generation of Large Language Models](<https://doi.org/10.1145/3701228>)**
  - Authors: Yuanjie Lyu; Zhiyu Li; Simin Niu; Feiyu Xiong; Bo Tang; Wenjin Wang; Hao Wu; Huanyong Liu; Tong Xu; Enhong Chen.
  - Venue / outlet: **ACM TOIS** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Wang2025FinS; question: Q-76; review: positional_only -->
- **[FinS-Pilot: A Benchmark for Online Financial RAG System](<https://doi.org/10.1145/3746252.3761643>)**
  - Authors: Feng Wang; Yiding Sun; Jiaxin Mao; Xue Wei; Danqing Xu.
  - Venue / outlet: **CIKM** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Sorodoc2025GaRAGe; question: Q-76; review: positional_only -->
- **[GaRAGe: A Benchmark with Grounding Annotations for RAG Evaluation](<https://arxiv.org/abs/2506.07671>)**
  - Authors: Ionut-Teodor Sorodoc; Leonardo F. R. Ribeiro; Rexhina Blloshmi; Christopher Davis; Adrià de Gispert.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Lee2025GRADE; question: Q-76; review: positional_only -->
- **[GRADE: Generating multi-hop QA and fine-gRAined Difficulty matrix for RAG Evaluation](<https://arxiv.org/abs/2508.16994>)**
  - Authors: Jeongsoo Lee; Daeyong Kwon; Kyohoon Jin.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: hirsch2025laquer; question: Q-76; review: positional_only -->
- **[LAQuer: Localized Attribution Queries in Content-grounded Generation](<https://arxiv.org/abs/2506.01187>)**
  - Authors: Eran Hirsch; Aviv Slobodkin; David Wan; Elias Stengel-Eskin; Mohit Bansal; Ido Dagan.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Li2025LaRA; question: Q-76; review: positional_only -->
- **[LaRA: Benchmarking Retrieval-Augmented Generation and Long-Context LLMs – No Silver Bullet for LC or RAG Routing](<https://arxiv.org/abs/2502.09977>)**
  - Authors: Kuan Li; Liwen Zhang; Yong Jiang; Pengjun Xie; Fei Huang; Shuai Wang; Minhao Cheng.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Li2025LexRAG; question: Q-76; review: positional_only -->
- **[LexRAG: Benchmarking Retrieval-Augmented Generation in Multi-Turn Legal Consultation Conversation](<https://doi.org/10.1145/3726302.3730340>)**
  - Authors: Haitao Li; Yifan Chen; Hu YiRan; Qingyao Ai; Junjie Chen; Xiaoyu Yang; Jianhui Yang; Yueyue Wu; Zeyang Liu; Yiqun Liu.
  - Venue / outlet: **SIGIR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Lee2025MAGIC; question: Q-76; review: positional_only -->
- **[MAGIC: A Multi-Hop and Graph-Based Benchmark for Inter-Context Conflicts in Retrieval-Augmented Generation](<https://arxiv.org/abs/2507.21544>)**
  - Authors: Jungyeon Lee; Kangmin Lee; Taeuk Kim.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Blandon2025MEMERAG; question: Q-76; review: positional_only -->
- **[MEMERAG: A Multilingual End-to-End Meta-Evaluation Benchmark for Retrieval Augmented Generation](<https://arxiv.org/abs/2502.17163>)**
  - Authors: María Andrea Cruz Blandón; Jayasimha Talur; Bruno Charron; Dong Liu; Saab Mansour; Marcello Federico.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Park2025MIRAGE; question: Q-76; review: positional_only -->
- **[MIRAGE: A Metric-Intensive Benchmark for Retrieval-Augmented Generation Evaluation](<https://arxiv.org/abs/2504.17137>)**
  - Authors: Chanhee Park; Hyeonseok Moon; Chanjun Park; Heuiseok Lim.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: ragrewardbench2024; question: Q-76; review: positional_only -->
- **[RAG-RewardBench: Benchmarking Reward Models in Retrieval Augmented Generation for Preference Alignment](<https://doi.org/10.18653/v1/2025.findings-acl.877>)**
  - Authors: Zhuoran Jin; Hongbang Yuan; Tianyi Men; Pengfei Cao; Yubo Chen; Jiexin Xu; Huaijun Li; Xiaojian Jiang; Kang Liu; Jun Zhao.
  - Venue / outlet: **Findings of ACL** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: abdallah2025rerankarena; question: Q-76; review: positional_only -->
- **[RerankArena: A Unified Platform for Evaluating Retrieval, Reranking and RAG with Human and LLM Feedback](<https://doi.org/10.1145/3746252.3761484>)**
  - Authors: Abdelrahman Abdallah; Mahmoud Abdalla; Bhawna Piryani; Jamshid Mozafari; Mohammed Ali; Adam Jatowt.
  - Venue / outlet: **CIKM** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: liang2025saferag; question: Q-76; review: positional_only -->
- **[SafeRAG: Benchmarking Security in Retrieval-Augmented Generation of Large Language Model](<https://arxiv.org/abs/2501.18636>)**
  - Authors: Xun Liang; Simin Niu; Zhiyu Li; Sensen Zhang; Hanyu Wang; Feiyu Xiong; Jason Zhaoxin Fan; Bo Tang; Shichao Song; Mengwei Wang; Jiawei Yang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Dong2025Toward; question: Q-76; review: positional_only -->
- **[Toward Verifiable Instruction-Following Alignment for Retrieval Augmented Generation](<https://doi.org/10.1609/aaai.v39i22.34551>)**
  - Authors: Guanting Dong; Xiaoshuai Song; Yutao Zhu; Runqi Qiao; Zhicheng Dou; Ji-Rong Wen.
  - Venue / outlet: **AAAI** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: zeng2025worse; question: Q-76; review: positional_only -->
- **[Worse than Zero-shot? A Fact-Checking Dataset for Evaluating the Robustness of RAG Against Misleading Retrievals](<https://arxiv.org/abs/2502.16101>)**
  - Authors: Linda Zeng; Rithwik Gupta; Divij Motwani; Yi Zhang; Diji Yang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: saadfalcon2023ares; question: Q-76; review: positional_only -->
- **[ARES: An Automated Evaluation Framework for Retrieval-Augmented Generation Systems](<https://doi.org/10.18653/v1/2024.naacl-long.20>)**
  - Authors: Jon Saad-Falcon; Omar Khattab; Christopher Potts; Matei Zaharia.
  - Venue / outlet: **NAACL (Long Papers)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: rau2024bergen; question: Q-76; review: positional_only -->
- **[BERGEN: A Benchmarking Library for Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2024.findings-emnlp.449>)**
  - Authors: David Rau; Hervé Déjean; Nadezhda Chirkova; Thibault Formal; Shuai Wang; Stéphane Clinchant; Vassilina Nikoulina.
  - Venue / outlet: **Findings of EMNLP** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: su2024bright; question: Q-76; review: positional_only -->
- **[BRIGHT: A Realistic and Challenging Benchmark for Reasoning-Intensive Retrieval](<https://arxiv.org/abs/2407.12883>)**
  - Authors: Hongjin Su; Howard Yen; Mengzhou Xia; Weijia Shi; Niklas Muennighoff; Han-yu Wang; Haisu Liu; Quan Shi; Zachary S. Siegel; Michael Tang; Ruoxi Sun; Jinsung Yoon; Sercan O. Arik; Danqi Chen; Tao Yu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: liu2024chatqa; question: Q-76; review: positional_only -->
- **[ChatQA: Surpassing GPT-4 on Conversational QA and RAG](<https://doi.org/10.52202/079017-0493>)**
  - Authors: Zihan Liu; Wei Ping; Rajarshi Roy; Peng Xu; Chankyu Lee; Mohammad Shoeybi; Bryan Catanzaro.
  - Venue / outlet: **NeurIPS** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: yang2024crag; question: Q-76; review: positional_only -->
- **[CRAG - Comprehensive RAG Benchmark](<https://www.semanticscholar.org/paper/ec1bec009e68a4df478aaf11e3615e5587768990>)**
  - Authors: Xiao Yang; Kai Sun; Hao Xin; Yushi Sun; N. Bhalla; Xiangsen Chen; Sajal Choudhary; R. Gui; Ziran Jiang; Ziyu Jiang; Lingkun Kong; Brian Moran; Jiaqi Wang; Y. Xu; An Yan; Chenyu Yang; Eting Yuan; Hanwen Zha; Nan Tang; Lei Chen.
  - Venue / outlet: **NeurIPS** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: krishna2024frames; question: Q-76; review: positional_only -->
- **[Fact, Fetch, and Reason: A Unified Evaluation of Retrieval-Augmented Generation](<https://www.semanticscholar.org/paper/46ff7e02fd4ff5fdfb9f85bc7071725b8089061f>)**
  - Authors: Satyapriya Krishna; Kalpesh Krishna; Anhad Mohananey; S. Schwarcz; Adam Stambler; Shyam Upadhyay; Manaal Faruqui.
  - Venue / outlet: **NAACL** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: thakur2024mirage; question: Q-76; review: positional_only -->
- **[MIRAGE-Bench: Automatic Multilingual Benchmark Arena for Retrieval-Augmented Generation Systems](<https://arxiv.org/abs/2410.13716>)**
  - Authors: Nandan Thakur; Suleman Kazi; Ge Luo; Jimmy Lin; Amin Ahmad.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: han2024lfrqa; question: Q-76; review: positional_only -->
- **[RAG-QA Arena: Evaluating Domain Robustness for Long-form Retrieval Augmented Question Answering](<https://www.semanticscholar.org/paper/a9b04034e31a8c8ec5adff3c4665eda58b1f3013>)**
  - Authors: Rujun Han; Yuhao Zhang; Peng Qi; Yumo Xu; Jenyuan Wang; Lan Liu; William Yang Wang; Bonan Min; Vittorio Castelli.
  - Venue / outlet: **EMNLP** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: es2024ragas; question: Q-76; review: positional_only -->
- **[RAGAs: Automated Evaluation of Retrieval Augmented Generation](<https://doi.org/10.18653/v1/2024.eacl-demo.16>)**
  - Authors: Shahul Es; Jithin James; Luis Espinosa Anke; Steven Schockaert.
  - Venue / outlet: **EACL (System Demonstrations)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: ru2024ragchecker; question: Q-76; review: positional_only -->
- **[RAGChecker: A Fine-grained Framework for Diagnosing Retrieval-Augmented Generation](<https://arxiv.org/abs/2408.08067>)**
  - Authors: Dongyu Ru; Lin Qiu; Xiangkun Hu; Tianhang Zhang; Peng Shi; Shuaichen Chang; Cheng Jiayang; Cunxiang Wang; Shichao Sun; Huanyu Li; Zizhao Zhang; Binjie Wang; Jiarong Jiang; Tong He; Zhiguo Wang; Pengfei Liu; Yue Zhang; Zheng Zhang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: pradeep2024ragnarok; question: Q-76; review: positional_only -->
- **[Ragnarök: A Reusable RAG Framework and Baselines for TREC 2024 Retrieval-Augmented Generation Track](<https://arxiv.org/abs/2406.16828>)**
  - Authors: Ronak Pradeep; Nandan Thakur; Sahel Sharifymoghaddam; Eric Zhang; Ryan Nguyen; Daniel Campos; Nick Craswell; Jimmy Lin.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: hui2024uda; question: Q-76; review: positional_only -->
- **[UDA: A Benchmark Suite for Retrieval Augmented Generation in Real-world Document Analysis](<https://www.semanticscholar.org/paper/61f8baae9aecadc8bed1ce263c32bd108b476ebd>)**
  - Authors: Yulong Hui; Yao Lu; Huanchen Zhang.
  - Venue / outlet: **NeurIPS** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: chen2024rgb; question: Q-76; review: positional_only -->
- **[Benchmarking Large Language Models in Retrieval-Augmented Generation](<https://arxiv.org/abs/2309.01431>)**
  - Authors: Jiawei Chen; Hongyu Lin; Xianpei Han; Le Sun.
  - Venue / outlet: **arXiv (preprint)** · Year: **2023**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-d7"></a>

### D7. Agentic capability evaluation

Focus: Extra search or state mistaken for useful control.

Questions: [Q-77](#q-77) · [Q-78](#q-78).

<a id="q-77"></a>

#### Q-77. How can evaluation distinguish useful planning, revision, and stopping from merely longer search?

*Focal question.*

<!-- record: neighborhoods2026; question: Q-77; review: positional_only -->
- **[Why Neighborhoods Matter: Traversal Context and Provenance in Agentic GraphRAG](<https://arxiv.org/abs/2605.15109>)**
  - Authors: Riccardo Terrenzi; Maximilian von Zastrow; Serkan Ayvaz.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: wu2025searchwisely; question: Q-77; review: positional_only -->
- **[Search Wisely: Mitigating Sub-optimal Agentic Searches By Reducing Uncertainty](<https://arxiv.org/abs/2505.17281>)**
  - Authors: Peilin Wu; Mian Zhang; Xinlu Zhang; Xinya Du; Zhiyu Zoey Chen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-78"></a>

#### Q-78. What controlled evidence establishes the contribution of memory and multi-agent collaboration?

*Focal question.*

<!-- record: wu2025longmemeval; question: Q-78; review: positional_only -->
- **[LongMemEval: Benchmarking Chat Assistants on Long-Term Interactive Memory](<https://arxiv.org/abs/2410.10813>)**
  - Authors: Di Wu; Hongwei Wang; Wenhao Yu; Yuwei Zhang; Kai-Wei Chang; Dong Yu.
  - Venue / outlet: **ICLR** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Steiner2025MCP; question: Q-78; review: positional_only -->
- **[MCP vs RAG vs NLWeb vs HTML: A Comparison of the Effectiveness and Efficiency of Different Agent Interfaces to the Web](<https://www.semanticscholar.org/paper/76fdffbfb274dece6bc7dc8fc64856cead272c3a>)**
  - Authors: Aaron Steiner; R. Peeters; Christian Bizer.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Wang2025Towards; question: Q-78; review: positional_only -->
- **[Towards Reliable Agents: Benchmarking Customized LLM-Based Retrieval-Augmented Generation Frameworks with Deployment Validation](<https://doi.org/10.18653/v1/2025.naacl-industry.53>)**
  - Authors: Kevin Shukang Wang; Karel Joshua Harjono; Ramon Lawrence.
  - Venue / outlet: **NAACL (Industry Track)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Ni2025TP; question: Q-78; review: positional_only -->
- **[TP-RAG: Benchmarking Retrieval-Augmented Large Language Model Agents for Spatiotemporal-Aware Travel Planning](<https://doi.org/10.18653/v1/2025.emnlp-main.626>)**
  - Authors: Hang Ni; Fan Liu; Xinyu Ma; Lixin Su; Shuaiqiang Wang; Dawei Yin; Hui Xiong; Hao Liu.
  - Venue / outlet: **EMNLP** · Year: **2025**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-d8"></a>

### D8. Inherited common-protocol case study

Focus: Aggregate results cannot recover missing experiment details.

Questions: [Q-79](#q-79).

<a id="q-79"></a>

#### Q-79. Which conclusions can the reported common-protocol results support, and which remain unidentifiable?

*Focal question.*

<!-- record: hiprag2025; question: Q-79; review: positional_only -->
- **[HiPRAG: Hierarchical Process Rewards for Efficient Agentic Retrieval Augmented Generation](<https://arxiv.org/abs/2510.07794>)**
  - Authors: Peilin Wu; Mian Zhang; Kun Wan; Wentian Zhao; Kaiyu He; Xinya Du; Zhiyu Chen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: r1searcher2025; question: Q-79; review: positional_only -->
- **[R1-Searcher: Incentivizing the Search Capability in LLMs via Reinforcement Learning](<https://arxiv.org/abs/2503.05592>)**
  - Authors: Huatong Song; Jinhao Jiang; Yingqian Min; Jie Chen; Zhipeng Chen; Wayne Xin Zhao; Lei Fang; Ji-Rong Wen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: jin2025searchr1; question: Q-79; review: positional_only -->
- **[Search-R1: Training LLMs to Reason and Leverage Search Engines with Reinforcement Learning](<https://arxiv.org/abs/2503.09516>)**
  - Authors: Bowen Jin; Hansi Zeng; Zhenrui Yue; Jinsung Yoon; Sercan Arik; Dong Wang; Hamed Zamani; Jiawei Han.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: stepsearch2025; question: Q-79; review: positional_only -->
- **[StepSearch: Igniting LLMs Search Ability via Step-Wise Proximal Policy Optimization](<https://arxiv.org/abs/2505.15107>)**
  - Authors: Ziliang Wang; Xuhui Zheng; Kang An; Cijun Ouyang; Jialu Cai; Yuhang Wang; Yichao Wu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-d9"></a>

### D9. Uncertainty and reproducible reporting

Focus: Uncertainty, versioning, and reporting omissions.

Questions: [Q-80](#q-80).

<a id="q-80"></a>

#### Q-80. Which uncertainty, versioning, and reporting practices make a comparative claim reproducible and appropriately limited?

*Focal question.*

<!-- record: dror2018hitchhiker; question: Q-80; review: positional_only -->
- **[The Hitchhiker's Guide to Testing Statistical Significance in Natural Language Processing](<https://aclanthology.org/P18-1128/>)**
  - Authors: Rotem Dror; Gili Baumer; Segev Shlomov; Roi Reichart.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2018**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="domain-e"></a>

## E. Open research and conditional scaling

Which unresolved mechanisms and conditions should future research test?

<a id="group-e1"></a>

### E1. Adaptive control and interface validity

Focus: Unidentified control benefit and invalid recombination.

Questions: [Q-81](#q-81) · [Q-82](#q-82).

<a id="q-81"></a>

#### Q-81. Under what workload conditions does observation-conditioned control improve the quality–latency–cost trade-off over prescribed or once-routed workflows?

*Open research question.*

<!-- record: datacentric2025agentic; question: Q-81; review: positional_only -->
- **[Data-Centric Perspectives on Agentic Retrieval-Augmented Generation: A Survey](<https://aclanthology.org/2026.findings-acl.78/>)**
  - Authors: Jingwen Deng; Jihao Huang; Zhen Hao Wong; Hao Liang; Quanqing Xu; Bin Cui; Wentao Zhang.
  - Venue / outlet: **Findings of ACL** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: singh2025agentic; question: Q-81; review: positional_only -->
- **[Agentic Retrieval-Augmented Generation: A Survey on Agentic RAG](<https://arxiv.org/abs/2501.09136>)**
  - Authors: Aditi Singh; Abul Ehtesham; Saket Kumar; Tala Talaei Khoei; Athanasios V. Vasilakos.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-82"></a>

#### Q-82. Which interface conditions let locally improved components preserve end-to-end evidence validity when they are recombined?

*Open research question.*

No inherited question-level paper assignment in the v16 taxonomy. This is an explicit curation gap, not a claim that the question has no relevant literature.

[Back to contents](#contents)

<a id="group-e2"></a>

### E2. Credit and portable policies

Focus: Biased feedback and backend-dependent behavior.

Questions: [Q-83](#q-83) · [Q-84](#q-84).

<a id="q-83"></a>

#### Q-83. When can long-horizon feedback identify useful retrieval decisions rather than merely reinforce successful-looking trajectories?

*Open research question.*

<!-- record: leng2025decex; question: Q-83; review: positional_only -->
- **[DecEx-RAG: Boosting Agentic Retrieval-Augmented Generation with Decision and Execution Optimization via Process Supervision](<https://arxiv.org/abs/2510.05691>)**
  - Authors: Yongqi Leng; Yikun Lei; Xikai Liu; Meizhi Zhong; Bojian Xiong; Yurong Zhang; Yan Gao; Yi Wu; Yao Hu; Deyi Xiong.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: hiprag2025; question: Q-83; review: positional_only -->
- **[HiPRAG: Hierarchical Process Rewards for Efficient Agentic Retrieval Augmented Generation](<https://arxiv.org/abs/2510.07794>)**
  - Authors: Peilin Wu; Mian Zhang; Kun Wan; Wentian Zhao; Kaiyu He; Xinya Du; Zhiyu Chen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: stepsearch2025; question: Q-83; review: positional_only -->
- **[StepSearch: Igniting LLMs Search Ability via Step-Wise Proximal Policy Optimization](<https://arxiv.org/abs/2505.15107>)**
  - Authors: Ziliang Wang; Xuhui Zheng; Kang An; Cijun Ouyang; Jialu Cai; Yuhang Wang; Yichao Wu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-84"></a>

#### Q-84. Can policies learn portable information goals without binding them to a particular retrieval backend or reward judge?

*Open research question.*

<!-- record: deepresearcher2025; question: Q-84; review: positional_only -->
- **[DeepResearcher: Scaling Deep Research via Reinforcement Learning in Real-world Environments](<https://arxiv.org/abs/2504.03160>)**
  - Authors: Yuxiang Zheng; Dayuan Fu; Xiangkun Hu; Xiaojie Cai; Lyumanshan Ye; Pengrui Lu; Pengfei Liu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: jin2025searchr1; question: Q-84; review: positional_only -->
- **[Search-R1: Training LLMs to Reason and Leverage Search Engines with Reinforcement Learning](<https://arxiv.org/abs/2503.09516>)**
  - Authors: Bowen Jin; Hansi Zeng; Zhenrui Yue; Jinsung Yoon; Sercan Arik; Dong Wang; Hamed Zamani; Jiawei Han.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-e3"></a>

### E3. Quality-preserving selective acquisition

Focus: Changing load, answerability, and search cost.

Questions: [Q-85](#q-85).

<a id="q-85"></a>

#### Q-85. How can retrieval and stopping policies preserve required answer quality as evidence availability, service load, and search costs change?

*Open research question.*

<!-- record: acqo2026; question: Q-85; review: positional_only -->
- **[When should I search more: Adaptive Complex Query Optimization with Reinforcement Learning](<https://arxiv.org/abs/2601.21208>)**
  - Authors: Wei Wen; Sihang Deng; Tianjun Wei; Keyu Chen; Ruizhi Qiao; Xing Sun.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: wu2025searchwisely; question: Q-85; review: positional_only -->
- **[Search Wisely: Mitigating Sub-optimal Agentic Searches By Reducing Uncertainty](<https://arxiv.org/abs/2505.17281>)**
  - Authors: Peilin Wu; Mian Zhang; Xinlu Zhang; Xinya Du; Zhiyu Zoey Chen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-e4"></a>

### E4. Source change and selective persistence

Focus: Invalid derived state and changing permissions.

Questions: [Q-86](#q-86) · [Q-87](#q-87).

<a id="q-86"></a>

#### Q-86. How can a source correction or withdrawal propagate through indices, contexts, and derived memories without erasing needed provenance?

*Open research question.*

<!-- record: wang2026gamrag; question: Q-86; review: positional_only -->
- **[GAM-RAG: Gain-Adaptive Memory for Evolving Retrieval in Retrieval-Augmented Generation](<https://arxiv.org/abs/2603.01783>)**
  - Authors: Yifan Wang; Mingxuan Jiang; Zhihao Sun; Yixin Cao; Yicun Liu; Keyang Chen; Guangnan Ye; Hongfeng Chai.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: hu2026erm; question: Q-86; review: positional_only -->
- **[RAG without Forgetting: Continual Query-Infused Key Memory](<https://arxiv.org/abs/2602.05152>)**
  - Authors: Yuntong Hu; Sha Li; Naren Ramakrishnan; Liang Zhao.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: gutierrez2025hipporag2; question: Q-86; review: positional_only -->
- **[From RAG to Memory: Non-Parametric Continual Learning for Large Language Models](<https://arxiv.org/abs/2502.14802>)**
  - Authors: Bernal Jiménez Gutiérrez; Yiheng Shu; Weijian Qi; Sizhe Zhou; Yu Su.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: hipporag2024; question: Q-86; review: positional_only -->
- **[HippoRAG: Neurobiologically Inspired Long-Term Memory for Large Language Models](<https://arxiv.org/abs/2405.14831>)**
  - Authors: Bernal Jiménez Gutiérrez; Yiheng Shu; Yu Gu; Michihiro Yasunaga; Yu Su.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<a id="q-87"></a>

#### Q-87. Can selective persistence remain beneficial over task streams in which both evidence and access permissions change?

*Open research question.*

<!-- record: wu2025longmemeval; question: Q-87; review: positional_only -->
- **[LongMemEval: Benchmarking Chat Assistants on Long-Term Interactive Memory](<https://arxiv.org/abs/2410.10813>)**
  - Authors: Di Wu; Hongwei Wang; Wenhao Yu; Yuwei Zhang; Kai-Wei Chang; Dong Yu.
  - Venue / outlet: **ICLR** · Year: **2025**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-e5"></a>

### E5. Conditional multi-agent and swarm scaling

Focus: Dynamic allocation benefit versus coordination and load.

Questions: [Q-88](#q-88).

<a id="q-88"></a>

#### Q-88. Which task, source, and load conditions justify dynamic team allocation beyond a single controller or fixed team?

*Open research question.*

<!-- record: marag2025; question: Q-88; review: positional_only -->
- **[MA-RAG: Multi-Agent Retrieval-Augmented Generation via Collaborative Chain-of-Thought Reasoning](<https://arxiv.org/abs/2505.20096>)**
  - Authors: Thang Nguyen; Peter Chin; Yu-Wing Tai.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: sirag2025; question: Q-88; review: positional_only -->
- **[SIRAG: Towards Stable and Interpretable RAG with A Process-Supervised Multi-Agent Framework](<https://arxiv.org/abs/2509.18167>)**
  - Authors: Junlin Wang; Zehao Wu; Shaowei Lu; Yanlan Li; Xinghao Huang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: kim2025agentscaling; question: Q-88; review: positional_only -->
- **[Towards a Science of Scaling Agent Systems](<https://arxiv.org/abs/2512.08296v3>)**
  - Authors: Yubin Kim; Ken Gu; Chanwoo Park; Chunjong Park; Samuel Schmidgall; A. Ali Heydari; Yao Yan; Zhihan Zhang; Yuchen Zhuang; Yun Liu; Mark Malhotra; Paul Pu Liang; Hae Won Park; Yuzhe Yang; Xuhai Xu; Yilun Du; Shwetak Patel; Tim Althoff; Daniel McDuff; Xin Liu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-e6"></a>

### E6. Modality and domain transfer

Focus: Lost qualifications and authority-dependent answerability.

Questions: [Q-89](#q-89) · [Q-90](#q-90).

<a id="q-89"></a>

#### Q-89. How can cross-modal transformations preserve the evidence units and qualifications needed to verify a generated claim?

*Open research question.*

<!-- record: mma2025rag; question: Q-89; review: positional_only -->
- **[MMA-RAG: A Survey on Multimodal Agentic Retrieval-Augmented Generation](<https://hal.science/hal-05322313v2>)**
  - Authors: Vladana Perlić; Stéphane Lebailly; Vadim Malvone; Van-Tam Nguyen; Pascal Urard.
  - Venue / outlet: **HAL working paper** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: mrrag2025; question: Q-89; review: positional_only -->
- **[Ask in Any Modality: A Comprehensive Survey on Multimodal Retrieval-Augmented Generation](<https://arxiv.org/abs/2502.08826>)**
  - Authors: Mohammad Mahdi Abootorabi; Amirhosein Zobeiri; Mahdi Dehghani; Mohammadali Mohammadkhani; Bardia Mohammadi; Omid Ghahroodi; Mahdieh Soleymani Baghshah; Ehsaneddin Asgari.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-90"></a>

#### Q-90. Which evidence-selection and abstention policies transfer to domains where source authority, time, and access determine answerability?

*Open research question.*

<!-- record: deepresearcher2025; question: Q-90; review: positional_only -->
- **[DeepResearcher: Scaling Deep Research via Reinforcement Learning in Real-world Environments](<https://arxiv.org/abs/2504.03160>)**
  - Authors: Yuxiang Zheng; Dayuan Fu; Xiangkun Hu; Xiaojie Cai; Lyumanshan Ye; Pengrui Lu; Pengfei Liu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Zhao2025FinRAGBench; question: Q-90; review: positional_only -->
- **[FinRAGBench-V: A Benchmark for Multimodal RAG with Visual Citation in the Financial Domain](<https://arxiv.org/abs/2505.17471>)**
  - Authors: Suifeng Zhao; Zhuoran Jin; Sujian Li; Jun Gao.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-e7"></a>

### E7. Integrity, privacy, and fairness

Focus: Attacks, composition leakage, and hidden disparities.

Questions: [Q-91](#q-91) · [Q-92](#q-92) · [Q-93](#q-93).

<a id="q-91"></a>

#### Q-91. Can evidence integrity and action boundaries be preserved when retrieved content, source structure, or shared state is adversarial?

*Open research question.*

<!-- record: Liu2026Auditing; question: Q-91; review: positional_only -->
- **[Auditing Agent Harness Safety](<https://arxiv.org/abs/2605.14271>)**
  - Authors: Chengzhi Liu; Yichen Guo; Yepeng Liu; Yuzhe Yang; Qianqi Yan; Xuandong Zhao; Wenyue Hua; Sheng Liu; Sharon Li; Yuheng Bu; Xin Eric Wang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: zhang2026deja; question: Q-91; review: positional_only -->
- **[Beyond Explicit Refusals: Soft-Failure Attacks on Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2026.acl-long.1397>)**
  - Authors: Wentao Zhang; Yan Zhuang; ZhuHang Zheng; Mingfei Zhang; Jiawen Deng; Fuji Ren.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Wang2026Combating; question: Q-91; review: positional_only -->
- **[Combating Knowledge Corruption in Agent Systems: A Byzantine-Tolerant Secure Collaborative RAG Framework](<https://doi.org/10.1145/3774904.3792200>)**
  - Authors: Zhaoqi Wang; Daqing He; Zijian Zhang; Ye Liu; Jiamou Liu; Zhirui Zeng; Zhan Qin; Zhen Li; Xin Li; Hongwei Yao; Jincheng An; Yong Liu; Yi Li; Qi Sun; Xiulei Liu; Liehuang Zhu.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Luo2026IRAG; question: Q-91; review: positional_only -->
- **[IRAG: Robust Multimodal Retrieval-Augmented Generation via Hazard Separation](<https://doi.org/10.1145/3774904.3792319>)**
  - Authors: Ruikun Luo; Zixiao Feng; Lin Gu; Xiaoyu Xia.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: wang2025kepo; question: Q-91; review: positional_only -->
- **[KEPo: Knowledge Evolution Poison on Graph-based Retrieval-Augmented Generation](<https://doi.org/10.1145/3774904.3792547>)**
  - Authors: Qizhi Chen; Chao Qi; Yihong Huang; Muquan Li; Rongzheng Wang; Dongyang Zhang; Ke Qin; Shuang Liang.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: xiao2026logicpoison; question: Q-91; review: positional_only -->
- **[LogicPoison: Logical Attacks on Graph Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2026.acl-long.252>)**
  - Authors: Yilin Xiao; Jin Chen; Qinggang Zhang; Yujing Zhang; Chuang Zhou; Longhao Yang; Lingfei Ren; Xin Yang; Xiao Huang.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Yang2026ShieldRAG; question: Q-91; review: positional_only -->
- **[ShieldRAG: Safeguarding Retrieval-Augmented Generation from Untrusted Knowledge Bases](<https://doi.org/10.1609/aaai.v40i40.40725>)**
  - Authors: Peiru Yang; Haoran Zheng; Yi Luo; Xinyi Liu; Jinrui Wang; Huili Wang; Xintian Li; Yongfeng Huang; Tao Qi.
  - Venue / outlet: **AAAI** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Chaturvedi2025AIP; question: Q-91; review: positional_only -->
- **[AIP: Subverting Retrieval-Augmented Generation via Adversarial Instructional Prompt](<https://arxiv.org/abs/2509.15159>)**
  - Authors: Saket S. Chaturvedi; Gaurav Bagwe; Lan Zhang; Xiaoyong Yuan.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Wang2025Joint; question: Q-91; review: positional_only -->
- **[Joint-GCG: Unified Gradient-Based Poisoning Attacks on Retrieval-Augmented Generation Systems](<https://arxiv.org/abs/2506.06151>)**
  - Authors: Haowei Wang; Rupeng Zhang; Junjie Wang; Mingyang Li; Yuekai Huang; Dandan Wang; Qing Wang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Kim2025Safeguarding; question: Q-91; review: positional_only -->
- **[Safeguarding RAG Pipelines with GMTP: A Gradient-based Masked Token Probability Method for Poisoned Document Detection](<https://doi.org/10.18653/v1/2025.findings-acl.1263>)**
  - Authors: San Kim; Jonghwi Kim; Yejin Jeon; Gary Lee.
  - Venue / outlet: **Findings of ACL** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: liang2025saferag; question: Q-91; review: positional_only -->
- **[SafeRAG: Benchmarking Security in Retrieval-Augmented Generation of Large Language Model](<https://arxiv.org/abs/2501.18636>)**
  - Authors: Xun Liang; Simin Niu; Zhiyu Li; Sensen Zhang; Hanyu Wang; Feiyu Xiong; Jason Zhaoxin Fan; Bo Tang; Shichao Song; Mengwei Wang; Jiawei Yang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Song2025Silent; question: Q-91; review: positional_only -->
- **[The Silent Saboteur: Imperceptible Adversarial Attacks against Black-Box Retrieval-Augmented Generation Systems](<https://arxiv.org/abs/2505.18583>)**
  - Authors: Hongru Song; Yu-an Liu; Ruqing Zhang; Jiafeng Guo; Jianming Lv; Maarten de Rijke; Xueqi Cheng.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: zhang2025ragforensics; question: Q-91; review: positional_only -->
- **[Traceback of Poisoning Attacks to Retrieval-Augmented Generation](<https://doi.org/10.1145/3696410.3714756>)**
  - Authors: Baolei Zhang; Haoran Xin; Minghong Fang; Zhuqing Liu; Biao Yi; Tong Li; Zheli Liu.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-92"></a>

#### Q-92. How can privacy claims cover repeated retrieval, generation, and memory reuse rather than only one protected interface?

*Open research question.*

<!-- record: xie2026canary; question: Q-92; review: positional_only -->
- **[Detecting RAG Extraction Attack via Dual-Path Runtime Integrity Game](<https://doi.org/10.18653/v1/2026.acl-long.385>)**
  - Authors: Yuanbo Xie; Yingjie Zhang; Yulin Li; Shouyou Song; Xiaokun Chen; Zhihan Liu; Liya Su; Tingwen Liu.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Chen2026Fine; question: Q-92; review: positional_only -->
- **[Fine-Grained Privacy Extraction from Retrieval-Augmented Generation Systems by Exploiting Knowledge Asymmetry](<https://openreview.net/forum?id=B6ILMPPKnK>)**
  - Authors: Yufei Chen; Yao Wang; Haibin Zhang; Tao Gu.
  - Venue / outlet: **ICLR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: liang2026pisces; question: Q-92; review: positional_only -->
- **[Pisces: Cryptography-based Private Retrieval-Augmented Generation with Dual-Path Retrieval](<https://openreview.net/forum?id=Re3A6vzCTC>)**
  - Authors: Xiaojian Liang; Lushan Song; Shishuai Du; Weicheng Zhu; Tan Li Hui Faith; Jun Jie Sim; Haibing Jin; Zhenghao Wu; Yingting Liu; Xin Zhang; Jiang-Ming Yang; Pu Duan.
  - Venue / outlet: **ICLR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: yang2026agea; question: Q-92; review: positional_only -->
- **[Query-Efficient Agentic Graph Extraction Attacks on GraphRAG Systems](<https://doi.org/10.18653/v1/2026.acl-long.727>)**
  - Authors: Shuhua Yang; Jiahao Zhang; Yilong Wang; Dongwon Lee; Suhang Wang.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Wang2026Silent; question: Q-92; review: positional_only -->
- **[Silent Leaks: Implicit Knowledge Extraction Attack on RAG Systems](<https://openreview.net/forum?id=zfVICPB5Sv>)**
  - Authors: Yuhao Wang; Wenjie Qu; Shengfang Zhai; Yanze Jiang; Liu Zichen; Yue Liu; Yinpeng Dong; Jiaheng Zhang.
  - Venue / outlet: **ICLR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Zhang2025Beyond; question: Q-92; review: positional_only -->
- **[Beyond Text: Unveiling Privacy Vulnerabilities in Multi-modal Retrieval-Augmented Generation](<https://arxiv.org/abs/2505.13957>)**
  - Authors: Jiankun Zhang; Shenglai Zeng; Jie Ren; Tianqi Zheng; Hui Liu; Xianfeng Tang; Hui Liu; Yi Chang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Yang2025MrM; question: Q-92; review: positional_only -->
- **[MrM: Black-Box Membership Inference Attacks against Multimodal RAG Systems](<https://arxiv.org/abs/2506.07399>)**
  - Authors: Peiru Yang; Jinhua Yin; Haoran Zheng; Xueying Bai; Huili Wang; Yufei Sun; Xintian Li; Shangguang Wang; Yongfeng Huang; Tao Qi.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Ning2025Privacy; question: Q-92; review: positional_only -->
- **[Privacy-protected Retrieval-Augmented Generation for Knowledge Graph Question Answering](<https://arxiv.org/abs/2508.08785>)**
  - Authors: Yunfeng Ning; Mayi Xu; Jintao Wen; Qiankun Pi; Yuanyuan Zhu; Ming Zhong; Jiawei Jiang; Tieyun Qian.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Zeng2025S; question: Q-92; review: positional_only -->
- **[S-RAG: A Novel Audit Framework for Detecting Unauthorized Use of Personal Data in RAG Systems](<https://doi.org/10.18653/v1/2025.acl-long.512>)**
  - Authors: Zhirui Zeng; Jiamou Liu; Meng-Fen Chiang; Jialing He; Zijian Zhang.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<a id="q-93"></a>

#### Q-93. How can disparity be located and reduced across evidence availability, retrieval exposure, and attributed answers without concealing utility losses?

*Open research question.*

<!-- record: Dehghan2026Who; question: Q-93; review: positional_only -->
- **[Who Benefits from RAG? The Role of Exposure, Utility and Attribution Bias](<https://www.semanticscholar.org/paper/e92670f19a6c4b9ace7b9e8436faffa692870e67>)**
  - Authors: M. Dehghan; Graham McDonald.
  - Venue / outlet: **ECIR** · Year: **2026**.
  - Association review: [P](#how-to-use).

<!-- record: Kim2025Mitigating; question: Q-93; review: positional_only -->
- **[Mitigating Bias in RAG: Controlling the Embedder](<https://arxiv.org/abs/2502.17390>)**
  - Authors: Taeyoun Kim; Jacob Springer; Aditi Raghunathan; Maarten Sap.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: Bagwe2025Your; question: Q-93; review: positional_only -->
- **[Your RAG is Unfair: Exposing Fairness Vulnerabilities in Retrieval-Augmented Generation via Backdoor Attacks](<https://arxiv.org/abs/2509.22486>)**
  - Authors: Gaurav Bagwe; Saket S. Chaturvedi; Xiaolong Ma; Xiaoyong Yuan; Kuang-Ching Wang; Lan Zhang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-e8"></a>

### E8. Comparable evaluation infrastructure

Focus: Incompatible workloads and incomplete run evidence.

Questions: [Q-94](#q-94).

<a id="q-94"></a>

#### Q-94. What workload and reporting infrastructure makes RAG quality, efficiency, and scaling evidence comparable without imposing a universal score?

*Open research question.*

<!-- record: YGZ_CCF_2024; question: Q-94; review: positional_only -->
- **[Evaluation of Retrieval-Augmented Generation: A Survey](<https://link.springer.com/chapter/10.1007/978-981-96-1024-2_8>)**
  - Authors: Hao Yu; Aoran Gan; Kai Zhang; Shiwei Tong; Qi Liu; Zhaofeng Liu.
  - Venue / outlet: **CCF Conference on Big Data 2024 (CCIS; published 2025)** · Year: **2025**.
  - Association review: [P](#how-to-use).

<!-- record: ru2024ragchecker; question: Q-94; review: positional_only -->
- **[RAGChecker: A Fine-grained Framework for Diagnosing Retrieval-Augmented Generation](<https://arxiv.org/abs/2408.08067>)**
  - Authors: Dongyu Ru; Lin Qiu; Xiangkun Hu; Tianhang Zhang; Peng Shi; Shuaichen Chang; Cheng Jiayang; Cunxiang Wang; Shichao Sun; Huanyu Li; Zizhao Zhang; Binjie Wang; Jiarong Jiang; Tong He; Zhiguo Wang; Pengfei Liu; Yue Zhang; Zheng Zhang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.
  - Association review: [P](#how-to-use).

<!-- record: dror2018hitchhiker; question: Q-94; review: positional_only -->
- **[The Hitchhiker's Guide to Testing Statistical Significance in Natural Language Processing](<https://aclanthology.org/P18-1128/>)**
  - Authors: Rotem Dror; Gili Baumer; Segev Shlomov; Roi Reichart.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2018**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="group-e9"></a>

### E9. Native acquisition and reasoning interfaces

Focus: Integration versus replaceability and auditability.

Questions: [Q-95](#q-95).

<a id="q-95"></a>

#### Q-95. Which acquisition and reasoning interfaces should be learned jointly, and which should remain explicit to preserve replaceability and audit?

*Open research question.*

<!-- record: dsi2022; question: Q-95; review: positional_only -->
- **[Transformer Memory as a Differentiable Search Index](<https://arxiv.org/abs/2202.06991>)**
  - Authors: Yi Tay; Vinh Q. Tran; Mostafa Dehghani; Jianmo Ni; Dara Bahri; Harsh Mehta; Zhen Qin; Kai Hui; Zhe Zhao; Jai Gupta; Tal Schuster; William W. Cohen; Donald Metzler.
  - Venue / outlet: **arXiv (preprint)** · Year: **2022**.
  - Association review: [P](#how-to-use).

<!-- record: guu2020realm; question: Q-95; review: positional_only -->
- **[REALM: Retrieval-Augmented Language Model Pre-Training](<https://proceedings.mlr.press/v119/guu20a.html>)**
  - Authors: Kelvin Guu; Kenton Lee; Zora Tung; Panupong Pasupat; Ming-Wei Chang.
  - Venue / outlet: **ICML** · Year: **2020**.
  - Association review: [P](#how-to-use).

<!-- record: lewis2020rag; question: Q-95; review: positional_only -->
- **[Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks](<https://papers.nips.cc/paper/2020/hash/6b493230205f780e1bc26945df7481e5-Abstract.html>)**
  - Authors: Patrick Lewis; Ethan Perez; Aleksandra Piktus; Fabio Petroni; Vladimir Karpukhin; Naman Goyal; Heinrich Küttler; Mike Lewis; Wen-tau Yih; Tim Rocktäschel; Sebastian Riedel; Douwe Kiela.
  - Venue / outlet: **NeurIPS** · Year: **2020**.
  - Association review: [P](#how-to-use).

[Back to contents](#contents)

<a id="supporting-literature"></a>

## Supporting literature without a question-level assignment

These 86 records support background, cross-question discussion, or the inherited evaluation protocol. They are grouped by their first chapter-level citation in v16, which is a navigation convention and does not introduce new question–paper associations. Provider reports describe their publishers' observations or systems and are not treated as peer-reviewed evaluations.

- [S1. Introduction](#support-1) (15 records)
- [S2. Anatomy of RAG: Components, Properties, and Challenges](#support-2) (10 records)
- [S3. Treating RAG as a Whole: System Design and Optimization](#support-3) (49 records)
- [S4. Agentic RAG: Capabilities, Architectures, and Engineering](#support-4) (1 records)
- [S5. Evaluation of RAG: Objects, Quality Dimensions, Settings, and Methods](#support-5) (7 records)
- [S6. Reported Evaluation Protocol and Reproducibility Status](#support-6) (4 records)

<a id="support-1"></a>

### S1. Introduction

<!-- record: google2025aimode; question: unassigned; review: not-question-mapped -->
- **[AI in Search: Going Beyond Information to Intelligence](<https://blog.google/products-and-platforms/products/search/google-search-ai-mode-update/>)**
  - Authors: Elizabeth Reid.
  - Venue / outlet: **Google Blog (provider report)** · Year: **2025**.

<!-- record: peng2024graphragsurvey; question: unassigned; review: not-question-mapped -->
- **[Graph Retrieval-Augmented Generation: A Survey](<https://doi.org/10.1145/3777378>)**
  - Authors: Boci Peng; Yun Zhu; Yongchao Liu; Xiaohe Bo; Haizhou Shi; Chuntao Hong; Yan Zhang; Siliang Tang.
  - Venue / outlet: **ACM TOIS** · Year: **2025**.

<!-- record: anthropic2025multiagent; question: unassigned; review: not-question-mapped -->
- **[How We Built Our Multi-Agent Research System](<https://www.anthropic.com/engineering/multi-agent-research-system>)**
  - Authors: Anthropic.
  - Venue / outlet: **Anthropic Engineering (industry report)** · Year: **2025**.

<!-- record: google2025searchscale; question: unassigned; review: not-question-mapped -->
- **[More Opportunities for Your Business on Google Search](<https://blog.google/products/ads-commerce/google-search-ai-brand-discovery/>)**
  - Authors: Google.
  - Venue / outlet: **Google Blog (provider report)** · Year: **2025**.

<!-- record: openai2025usage; question: unassigned; review: not-question-mapped -->
- **[OpenAI's New Economic Analysis](<https://openai.com/global-affairs/new-economic-analysis/>)**
  - Authors: OpenAI.
  - Venue / outlet: **OpenAI (provider report)** · Year: **2025**.

<!-- record: GRS_arXiv_2024; question: unassigned; review: not-question-mapped -->
- **[A Comprehensive Survey of Retrieval-Augmented Generation (RAG): Evolution, Current Landscape and Future Directions](<https://arxiv.org/abs/2410.12837>)**
  - Authors: Shailja Gupta; Rajesh Ranjan; Surya Narayan Singh.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.

<!-- record: FDN_KDD_2024; question: unassigned; review: not-question-mapped -->
- **[A Survey on RAG Meeting LLMs: Towards Retrieval-Augmented Large Language Models](<https://doi.org/10.1145/3637528.3671470>)**
  - Authors: Wenqi Fan; Yujuan Ding; Liangbo Ning; Shijie Wang; Hengyun Li; Dawei Yin; Tat-Seng Chua; Qing Li.
  - Venue / outlet: **KDD** · Year: **2024**.

<!-- record: wu2024rag; question: unassigned; review: not-question-mapped -->
- **[Retrieval-Augmented Generation for Natural Language Processing: A Survey](<https://arxiv.org/abs/2407.13193>)**
  - Authors: Shangyu Wu; Ying Xiong; Yufei Cui; Haolun Wu; Can Chen; Ye Yuan; Lianming Huang; Xue Liu; Tei-Wei Kuo; Nan Guan; Chun Jason Xue.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.

<!-- record: ZLL_arXiv_2024; question: unassigned; review: not-question-mapped -->
- **[Trustworthiness in Retrieval-Augmented Generation Systems: A Survey](<https://arxiv.org/abs/2409.10102>)**
  - Authors: Yujia Zhou; Wenbo Zhang; Jingying Shao; Yan Liu; Xiaoxi Li; Jiajie Jin; Hongjin Qian; Zheng Liu; Chaozhuo Li; Jason Chen Zhang; Zhicheng Dou; Philip S. Yu; Jiaxin Mao.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.

<!-- record: shao2023enhancing; question: unassigned; review: not-question-mapped -->
- **[Enhancing Retrieval-Augmented Large Language Models with Iterative Retrieval-Generation Synergy](<https://doi.org/10.18653/v1/2023.findings-emnlp.620>)**
  - Authors: Zhihong Shao; Yeyun Gong; Yelong Shen; Minlie Huang; Nan Duan; Weizhu Chen.
  - Venue / outlet: **Findings of EMNLP** · Year: **2023**.

<!-- record: gao2023survey; question: unassigned; review: not-question-mapped -->
- **[Retrieval-Augmented Generation for Large Language Models: A Survey](<https://arxiv.org/abs/2312.10997>)**
  - Authors: Yunfan Gao; Yun Xiong; Xinyu Gao; Kangxiang Jia; Jinliu Pan; Yuxi Bi; Yi Dai; Jiawei Sun; Meng Wang; Haofen Wang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2023**.

<!-- record: carlini2021extracting; question: unassigned; review: not-question-mapped -->
- **[Extracting Training Data from Large Language Models](<https://www.usenix.org/conference/usenixsecurity21/presentation/carlini-extracting>)**
  - Authors: Nicholas Carlini; Florian Tramer; Eric Wallace; Matthew Jagielski; Ariel Herbert-Voss; Katherine Lee; Adam Roberts; Tom Brown; Dawn Song; Ulfar Erlingsson; Alina Oprea; Colin Raffel.
  - Venue / outlet: **USENIX Security** · Year: **2021**.

<!-- record: petroni2021kilt; question: unassigned; review: not-question-mapped -->
- **[KILT: A Benchmark for Knowledge Intensive Language Tasks](<https://arxiv.org/abs/2009.02252>)**
  - Authors: Fabio Petroni; Aleksandra Piktus; Angela Fan; Patrick Lewis; Majid Yazdani; Nicola De Cao; James Thorne; Yacine Jernite; Vladimir Karpukhin; Jean Maillard; Vassilis Plachouras; Tim Rocktaschel; Sebastian Riedel.
  - Venue / outlet: **NAACL** · Year: **2021**.

<!-- record: brown2020language; question: unassigned; review: not-question-mapped -->
- **[Language Models are Few-Shot Learners](<https://proceedings.neurips.cc/paper_files/paper/2020/hash/1457c0d6bfcb4967418bfb8ac142f64a-Abstract.html>)**
  - Authors: Tom B. Brown; Benjamin Mann; Nick Ryder; Melanie Subbiah; Jared Kaplan; Prafulla Dhariwal; Arvind Neelakantan; Pranav Shyam; Girish Sastry; Amanda Askell; Sandhini Agarwal; Ariel Herbert-Voss; Gretchen Krueger; Tom Henighan; Rewon Child; Aditya Ramesh; Daniel M. Ziegler; Jeffrey Wu; Clemens Winter; Christopher Hesse; Mark Chen; Eric Sigler; Mateusz Litwin; Scott Gray; Benjamin Chess; Jack Clark; Christopher Berner; Sam McCandlish; Alec Radford; Ilya Sutskever; Dario Amodei.
  - Venue / outlet: **NeurIPS** · Year: **2020**.

<!-- record: kaplan2020scaling; question: unassigned; review: not-question-mapped -->
- **[Scaling Laws for Neural Language Models](<https://arxiv.org/abs/2001.08361>)**
  - Authors: Jared Kaplan; Sam McCandlish; Tom Henighan; Tom B. Brown; Benjamin Chess; Rewon Child; Scott Gray; Alec Radford; Jeffrey Wu; Dario Amodei.
  - Venue / outlet: **arXiv (preprint)** · Year: **2020**.

<a id="support-2"></a>

### S2. Anatomy of RAG: Components, Properties, and Challenges

<!-- record: Salemi2024Learning; question: unassigned; review: not-question-mapped -->
- **[Learning to Rank for Multiple Retrieval-Augmented Models through Iterative Utility Maximization](<https://www.semanticscholar.org/paper/23760b6f0b2daaf71108ebb7dca3b83763f83149>)**
  - Authors: Alireza Salemi; Hamed Zamani.
  - Venue / outlet: **ICTIR** · Year: **2024**.

<!-- record: liu2023lostmiddle; question: unassigned; review: not-question-mapped -->
- **[Lost in the Middle: How Language Models Use Long Contexts](<https://arxiv.org/abs/2307.03172>)**
  - Authors: Nelson F. Liu; Kevin Lin; John Hewitt; Ashwin Paranjape; Michele Bevilacqua; Fabio Petroni; Percy Liang.
  - Venue / outlet: **TACL** · Year: **2023**.

<!-- record: wang2023query2doc; question: unassigned; review: not-question-mapped -->
- **[Query2doc: Query Expansion with Large Language Models](<https://arxiv.org/abs/2303.07678>)**
  - Authors: Liang Wang; Nan Yang; Furu Wei.
  - Venue / outlet: **EMNLP** · Year: **2023**.

<!-- record: schick2023toolformer; question: unassigned; review: not-question-mapped -->
- **[Toolformer: Language Models Can Teach Themselves to Use Tools](<https://arxiv.org/abs/2302.04761>)**
  - Authors: Timo Schick; Jane Dwivedi-Yu; Roberto Dessì; Roberta Raileanu; Maria Lomeli; Luke Zettlemoyer; Nicola Cancedda; Thomas Scialom.
  - Venue / outlet: **NeurIPS** · Year: **2023**.

<!-- record: dejong2023fido; question: unassigned; review: not-question-mapped -->
- **[FiDO: Fusion-in-Decoder optimized for stronger performance and faster inference](<https://arxiv.org/abs/2212.08153>)**
  - Authors: Michiel de Jong; Yury Zemlyanskiy; Joshua Ainslie; Nicholas FitzGerald; Sumit Sanghai; Fei Sha; William Cohen.
  - Venue / outlet: **arXiv (preprint)** · Year: **2022**.

<!-- record: XXL_ICLR_2021; question: unassigned; review: not-question-mapped -->
- **[Approximate Nearest Neighbor Negative Contrastive Learning for Dense Text Retrieval](<https://openreview.net/forum?id=zeFrfgyZln>)**
  - Authors: Lee Xiong; Chenyan Xiong; Ye Li; Kwok-Fung Tang; Jialin Liu; Paul N Bennett; Junaid Ahmed; Arnold Overwijk.
  - Venue / outlet: **ICLR** · Year: **2021**.

<!-- record: thakur2021beir; question: unassigned; review: not-question-mapped -->
- **[BEIR: A Heterogeneous Benchmark for Zero-shot Evaluation of Information Retrieval Models](<https://arxiv.org/abs/2104.08663>)**
  - Authors: Nandan Thakur; Nils Reimers; Andreas Rücklé; Abhishek Srivastava; Iryna Gurevych.
  - Venue / outlet: **NeurIPS (Datasets and Benchmarks)** · Year: **2021**.

<!-- record: contriever2022; question: unassigned; review: not-question-mapped -->
- **[Unsupervised Dense Information Retrieval with Contrastive Learning](<https://arxiv.org/abs/2112.09118>)**
  - Authors: Gautier Izacard; Mathilde Caron; Lucas Hosseini; Sebastian Riedel; Piotr Bojanowski; Armand Joulin; Edouard Grave.
  - Venue / outlet: **arXiv (preprint)** · Year: **2021**.

<!-- record: nakano2021webgpt; question: unassigned; review: not-question-mapped -->
- **[WebGPT: Browser-Assisted Question-Answering with Human Feedback](<https://arxiv.org/abs/2112.09332>)**
  - Authors: Reiichiro Nakano; Jacob Hilton; Suchir Balaji; Jeff Wu; Long Ouyang; Christina Kim; Christopher Hesse; Shantanu Jain; Vineet Kosaraju; William Saunders; Xu Jiang; Karl Cobbe; Tyna Eloundou; Gretchen Krueger; Kevin Button; Matthew Knight; Benjamin Chess; John Schulman.
  - Venue / outlet: **arXiv (preprint)** · Year: **2021**.

<!-- record: malkov2020hnsw; question: unassigned; review: not-question-mapped -->
- **[Efficient and Robust Approximate Nearest Neighbor Search Using Hierarchical Navigable Small World Graphs](<https://doi.org/10.1109/TPAMI.2018.2889473>)**
  - Authors: Yu A. Malkov; Dmitry A. Yashunin.
  - Venue / outlet: **IEEE TPAMI** · Year: **2020**.

<a id="support-3"></a>

### S3. Treating RAG as a Whole: System Design and Optimization

<!-- record: Wang2026All; question: unassigned; review: not-question-mapped -->
- **[All Languages Matter: Understanding and Mitigating Language Bias in Multilingual RAG](<https://doi.org/10.18653/v1/2026.acl-long.338>)**
  - Authors: Dan Wang; Guozhao Mo; Yafei Shi; Cheng Zhang; Bo Zheng; Boxi Cao; Xuanang Chen; Yaojie Lu; Hongyu Lin; Ben He; Xianpei Han; Le Sun.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.

<!-- record: Nkhata2026ClusterRAG; question: unassigned; review: not-question-mapped -->
- **[ClusterRAG: Cluster-Based Collaborative Filtering for Personalized Retrieval-Augmented Generation](<https://aclanthology.org/2026.acl-long.940/>)**
  - Authors: Gibson Nkhata; Uttamasha Anjally Oyshi; Quan Mai; Susan Gauch.
  - Venue / outlet: **ACL** · Year: **2026**.

<!-- record: Shen2025DRAGON; question: unassigned; review: not-question-mapped -->
- **[DRAGON: Domain-specific Robust Automatic Data Generation for RAG Optimization](<https://doi.org/10.18653/v1/2026.findings-eacl.56>)**
  - Authors: Haiyang Shen; Hang Yan; Zhongshi Xing; Mugeng Liu; Yue Li; Zhiyang Chen; Yuxiang Wang; Jiuzheng Wang; Yun Ma.
  - Venue / outlet: **Findings of EACL** · Year: **2026**.

<!-- record: Hu2026Iterative; question: unassigned; review: not-question-mapped -->
- **[Iterative Multi-Granular RAG with Contextual Hierarchical Graph](<https://doi.org/10.1609/aaai.v40i37.40370>)**
  - Authors: Yanli Hu; Teng Liu; Zhuangyi Zhou; Weixin Zeng; Zhen Tan; Xiang Zhao.
  - Venue / outlet: **AAAI** · Year: **2026**.

<!-- record: Li2026Language; question: unassigned; review: not-question-mapped -->
- **[Language Drift in Multilingual Retrieval-Augmented Generation: Characterization and Decoding-Time Mitigation](<https://doi.org/10.1609/aaai.v40i37.40417>)**
  - Authors: Bo Li; Zhenghua Xu; Rui Xie.
  - Venue / outlet: **AAAI** · Year: **2026**.

<!-- record: park2026m3kg; question: unassigned; review: not-question-mapped -->
- **[M$^3$KG-RAG: Multi-hop Multimodal Knowledge Graph-enhanced Retrieval-Augmented Generation](<https://openaccess.thecvf.com/content/CVPR2026/html/Park_M3KG-RAG_Multi-hop_Multimodal_Knowledge_Graph-enhanced_Retrieval-Augmented_Generation_CVPR_2026_paper.html>)**
  - Authors: Hyeongcheol Park; Jiyoung Seo; Jaewon Mun; Hogun Park; Wonmin Byeon; Sung June Kim; Hyeonsoo Im; JeungSub Lee; Sangpil Kim.
  - Venue / outlet: **CVPR** · Year: **2026**.

<!-- record: Ma2026MGK; question: unassigned; review: not-question-mapped -->
- **[MGK-RAG: Multi-Granularity Knowledge Guided Retrieval-Augmented Generation for Radiology Report](<https://doi.org/10.1145/3774904.3792924>)**
  - Authors: Jiaqing Ma; Xiaodong Yue; Yufei Chen; Jie Shi; Zhipeng Wei; Zeyu Jia.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.

<!-- record: Zhang2025Mixture; question: unassigned; review: not-question-mapped -->
- **[Mixture-of-RAG: Integrating Text and Tables with Large Language Models](<https://doi.org/10.1145/3770854.3780171>)**
  - Authors: Chi Zhang; Qiyang Chen; Mengqi Zhang.
  - Venue / outlet: **KDD (Vol. 1)** · Year: **2026**.

<!-- record: yuan2026mkgrag; question: unassigned; review: not-question-mapped -->
- **[mKG-RAG: Leveraging Multimodal Knowledge Graphs in Retrieval-Augmented Generation for Knowledge-intensive VQA](<https://sigir2026.org/en-AU/pages/program/accepted-papers>)**
  - Authors: Xu Yuan; Liang-Bo Ning; Qingqing Ye; Wenqi Fan; Li Qing.
  - Venue / outlet: **SIGIR** · Year: **2026**.

<!-- record: Ranaldi2025Multilingual; question: unassigned; review: not-question-mapped -->
- **[Multilingual Retrieval-Augmented Generation for Knowledge-Intensive Question Answering Task](<https://doi.org/10.18653/v1/2026.findings-eacl.35>)**
  - Authors: Leonardo Ranaldi.
  - Venue / outlet: **Findings of EACL** · Year: **2026**.

<!-- record: Pu2026Organ; question: unassigned; review: not-question-mapped -->
- **[Organ-Aware Routing Mixture-of-Retrieval Augmented Generation for Fetal Ultrasound Reporting](<https://doi.org/10.1609/aaai.v40i10.37795>)**
  - Authors: Bin Pu; Siyu Wang; Rongbin Li; Xinpeng Ding; Lei Zhao; Chaoqi Chen; Shengli Li; Kenli Li.
  - Venue / outlet: **AAAI** · Year: **2026**.

<!-- record: Wang2026Purifying; question: unassigned; review: not-question-mapped -->
- **[Purifying Multimodal Retrieval: Fragment-Level Evidence Selection for RAG](<https://sigir2026.org/en-AU/pages/program/accepted-papers>)**
  - Authors: Xihang Wang; Zihan Wang; Chengkai Huang; Cao Liu; Ke Zeng; Quan Z. Sheng; Lina Yao.
  - Venue / outlet: **SIGIR** · Year: **2026**.

<!-- record: li2026regionrag; question: unassigned; review: not-question-mapped -->
- **[RegionRAG: Region-level Retrieval-Augmented Generation for Visual Document Understanding](<https://doi.org/10.1609/aaai.v40i8.37597>)**
  - Authors: Yinglu Li; Zhiying Lu; Zhihang Liu; Yiwei Sun; Chuanbin Liu; Hongtao Xie.
  - Venue / outlet: **AAAI** · Year: **2026**.

<!-- record: Um2026RPO; question: unassigned; review: not-question-mapped -->
- **[RPO-RAG: Aligning Small LLMs with Relation-aware Preference Optimization for Knowledge Graph Question Answering](<https://doi.org/10.1145/3774904.3792730>)**
  - Authors: Kaehyun Um; KyuHwan Yeom; Haerim Yang; Minyoung Choi; Hyeongjun Yang; Kyong-Ho Lee.
  - Venue / outlet: **The Web Conference (WWW)** · Year: **2026**.

<!-- record: gao2026multimodalsurvey; question: unassigned; review: not-question-mapped -->
- **[Scaling Beyond Context: A Survey of Multimodal Retrieval-Augmented Generation for Document Understanding](<https://doi.org/10.18653/v1/2026.acl-long.204>)**
  - Authors: Sensen Gao; Shanshan Zhao; Xu Jiang; Lunhao Duan; Yong Xien Chng; Qing-Guo Chen; Weihua Luo; Kaifu Zhang; Jia-Wang Bian; Mingming Gong.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.

<!-- record: asai2026openscholar; question: unassigned; review: not-question-mapped -->
- **[Synthesizing scientific literature with retrieval-augmented language models](<https://doi.org/10.1038/s41586-025-10072-4>)**
  - Authors: Akari Asai; Jacqueline He; Rulin Shao; Weijia Shi; Amanpreet Singh; Joseph Chee Chang; Kyle Lo; Luca Soldaini; Sergey Feldman; Mike D’Arcy; David Wadden; Matt Latzke; Jenna Sparks; Jena D. Hwang; Varsha Kishore; Minyang Tian; Pan Ji; Shengyan Liu; Hao Tong; Bohao Wu; Yanyu Xiong; Luke Zettlemoyer; Graham Neubig; Daniel S. Weld; Doug Downey; Wen-tau Yih; Pang Wei Koh; Hannaneh Hajishirzi.
  - Venue / outlet: **Nature** · Year: **2026**.

<!-- record: yeo2026universalrag; question: unassigned; review: not-question-mapped -->
- **[UniversalRAG: Retrieval-Augmented Generation over Corpora of Diverse Modalities and Granularities](<https://doi.org/10.18653/v1/2026.acl-long.177>)**
  - Authors: Woongyeong Yeo; Kangsan Kim; Soyeong Jeong; Jinheon Baek; Sung Ju Hwang.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.

<!-- record: Ren2025VideoRAG; question: unassigned; review: not-question-mapped -->
- **[VideoRAG: Retrieval-Augmented Generation with Extreme Long-Context Videos](<https://doi.org/10.1145/3770854.3783944>)**
  - Authors: Xubin Ren; Lingrui Xu; Long Xia; Shuaiqiang Wang; Dawei Yin; Chao Huang.
  - Venue / outlet: **KDD (Vol. 1)** · Year: **2026**.

<!-- record: fu2026videostir; question: unassigned; review: not-question-mapped -->
- **[VideoStir: Understanding Long Videos via Spatio-Temporally Structured and Intent-Aware RAG](<https://doi.org/10.18653/v1/2026.acl-long.1656>)**
  - Authors: Honghao Fu; Miao Xu; Yiwei Wang; Dailing Zhang; Jun Liu; Yujun Cai.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2026**.

<!-- record: shojaee2025mkp; question: unassigned; review: not-question-mapped -->
- **[Federated Retrieval Augmented Generation for Multi-Product Question Answering](<https://arxiv.org/abs/2501.14998>)**
  - Authors: Parshin Shojaee; Sai Sree Harsha; Dan Luo; Akash Maharaj; Tong Yu; Yunyao Li.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.

<!-- record: chakraborty2025fedsurvey; question: unassigned; review: not-question-mapped -->
- **[Federated Retrieval-Augmented Generation: A Systematic Mapping Study](<https://arxiv.org/abs/2505.18906>)**
  - Authors: Abhijit Chakraborty; Chahana Dahal; Vivek Gupta.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.

<!-- record: Yuan2025FineRAG; question: unassigned; review: not-question-mapped -->
- **[FineRAG: Fine-grained Retrieval-Augmented Text-to-Image Generation](<https://www.semanticscholar.org/paper/488a57a382ea5cce0cf5fe52af8dc720156fd723>)**
  - Authors: Huaying Yuan; Ziliang Zhao; Shuting Wang; Shitao Xiao; Minheng Ni; Zheng Liu; Zhicheng Dou.
  - Venue / outlet: **COLING** · Year: **2025**.

<!-- record: Yazan2025Improving; question: unassigned; review: not-question-mapped -->
- **[Improving RAG for Personalization with Author Features and Contrastive Examples](<https://link.springer.com/chapter/10.1007/978-3-031-88714-7_40>)**
  - Authors: Mert Yazan; Suzan Verberne; Frederik Situmeang.
  - Venue / outlet: **ECIR** · Year: **2025**.

<!-- record: Zhou2025depth; question: unassigned; review: not-question-mapped -->
- **[In-depth Analysis of Graph-based RAG in a Unified Framework](<https://arxiv.org/abs/2503.04338>)**
  - Authors: Yingli Zhou; Yaodong Su; Youran Sun; Shu Wang; Taotao Wang; Runyuan He; Yongwei Zhang; Sicong Liang; Xilin Liu; Yuchi Ma; Yixiang Fang.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.

<!-- record: Park2025Investigating; question: unassigned; review: not-question-mapped -->
- **[Investigating Language Preference of Multilingual RAG Systems](<https://arxiv.org/abs/2502.11175>)**
  - Authors: Jeonghyun Park; Hwanhee Lee.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.

<!-- record: Mekonnen2025Lightweight; question: unassigned; review: not-question-mapped -->
- **[Lightweight and Direct Document Relevance Optimization for Generative Information Retrieval](<https://doi.org/10.1145/3726302.3730023>)**
  - Authors: Kidist Amde Mekonnen; Yubao Tang; Maarten de Rijke.
  - Venue / outlet: **SIGIR** · Year: **2025**.

<!-- record: Hieu2025MaGiX; question: unassigned; review: not-question-mapped -->
- **[MaGiX: A Multi-Granular Adaptive Graph Intelligence Framework for Enhancing Cross-Lingual RAG](<https://doi.org/10.18653/v1/2025.findings-emnlp.279>)**
  - Authors: Nguyen Manh Hieu; Vu Lam Anh; Hung Pham Van; Nam Le Hai; Linh Ngo Van; Nguyen Thi Ngoc Diep; Thien Huu Nguyen.
  - Venue / outlet: **Findings of EMNLP** · Year: **2025**.

<!-- record: Wu2025Medical; question: unassigned; review: not-question-mapped -->
- **[Medical Graph RAG: Evidence-based Medical Large Language Model via Graph Retrieval-Augmented Generation](<https://doi.org/10.18653/v1/2025.acl-long.1381>)**
  - Authors: Junde Wu; Jiayuan Zhu; Yunli Qi; Jingkun Chen; Min Xu; Filippo Menolascina; Yueming Jin; Vicente Grau.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2025**.

<!-- record: Hsu2025MedPlan; question: unassigned; review: not-question-mapped -->
- **[MedPlan: A Two-Stage RAG-Based System for Personalized Medical Plan Generation](<https://arxiv.org/abs/2503.17900>)**
  - Authors: Hsin-Ling Hsu; Cong-Tinh Dao; Luning Wang; Zitao Shuai; Thao Nguyen Minh Phan; Jun-En Ding; Chun-Chieh Liao; Pengfei Hu; Xiaoxue Han; Chih-Ho Hsu; Dongsheng Luo; Wen-Chih Peng; Feng Liu; Fang-Ming Hung; Chenwei Wu.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.

<!-- record: Yu2025MIND; question: unassigned; review: not-question-mapped -->
- **[MIND-RAG: Multimodal Context-Aware and Intent-Aware Retrieval-Augmented Generation for Educational Publications](<https://doi.org/10.1109/iccvw69036.2025.00438>)**
  - Authors: Jiayang Yu; Yuxi Xie; Guixuan Zhang; Jie Liu; Zhi Zeng; Ying Huang; Shuwu Zhang.
  - Venue / outlet: **ICCV Workshops** · Year: **2025**.

<!-- record: Shin2026MultiDocFusion; question: unassigned; review: not-question-mapped -->
- **[MultiDocFusion : Hierarchical and Multimodal Chunking Pipeline for Enhanced RAG on Long Industrial Documents](<https://doi.org/10.18653/v1/2025.emnlp-main.1062>)**
  - Authors: Joongmin Shin; Chanjun Park; Jeongbae Park; Jaehyung Seo; Heuiseok Lim.
  - Venue / outlet: **EMNLP** · Year: **2025**.

<!-- record: He2025pFedRAG; question: unassigned; review: not-question-mapped -->
- **[pFedRAG: A Personalized Federated Retrieval-Augmented Generation System with Depth-Adaptive Tiered Embedding Tuning](<https://doi.org/10.18653/v1/2025.findings-emnlp.769>)**
  - Authors: Hangyu He; Xin Yuan; Kai Wu; Ren Ping Liu; Wei Ni.
  - Venue / outlet: **Findings of EMNLP** · Year: **2025**.

<!-- record: Kachuee2025PrismRAG; question: unassigned; review: not-question-mapped -->
- **[PrismRAG: Boosting RAG Factuality with Distractor Resilience and Strategized Reasoning](<https://arxiv.org/abs/2507.18857>)**
  - Authors: Mohammad Kachuee; Teja Gollapudi; Minseok Kim; Yin Huang; Kai Sun; Xiao Yang; Jiaqi Wang; Nirav Shah; Yue Liu; Aaron Colak; Anuj Kumar; Wen-tau Yih; Xin Luna Dong.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.

<!-- record: Zhang2025PrLM; question: unassigned; review: not-question-mapped -->
- **[PrLM: Learning Explicit Reasoning for Personalized RAG via Contrastive Reward Optimization](<https://doi.org/10.1145/3746252.3760851>)**
  - Authors: Kepu Zhang; Teng Shi; Weijie Yu; Jun Xu.
  - Venue / outlet: **CIKM** · Year: **2025**.

<!-- record: Lee2025Reference; question: unassigned; review: not-question-mapped -->
- **[Reference-Based Super-Resolution via Image-Based Retrieval-Augmented Generation Diffusion](<https://doi.org/10.1109/iccv51701.2025.01002>)**
  - Authors: Byeonghun Lee; Hyunmin Cho; Hong Gyu Choi; Soo Min Kang; Iljun Ahn; Kyong Hwan Jin.
  - Venue / outlet: **ICCV** · Year: **2025**.

<!-- record: Shi2025Retrieval; question: unassigned; review: not-question-mapped -->
- **[Retrieval Augmented Generation with Collaborative Filtering for Personalized Text Generation](<https://doi.org/10.1145/3726302.3730075>)**
  - Authors: Teng Shi; Jun Xu; Xiao Zhang; Xiaoxue Zang; Kai Zheng; Yang Song; Han Li.
  - Venue / outlet: **SIGIR** · Year: **2025**.

<!-- record: Chen2025Seeing; question: unassigned; review: not-question-mapped -->
- **[Seeing Beyond: Enhancing Visual Question Answering with Multi-Modal Retrieval](<https://www.semanticscholar.org/paper/4bd36954d9ef96bc227d54f7484041077d9648be>)**
  - Authors: Boqi Chen; Anuj Khare; G. Kumar; Arjun Akula; P. Narayana; D. Clinton; Alexander Hamilton.
  - Venue / outlet: **COLING** · Year: **2025**.

<!-- record: GLJ_ICLR_2025; question: unassigned; review: not-question-mapped -->
- **[SmartRAG: Jointly Learn RAG-Related Tasks From the Environment Feedback](<https://proceedings.iclr.cc/paper_files/paper/2025/hash/83ccb398f3ce9c4d137011f36a03c7d4-Abstract-Conference.html>)**
  - Authors: Jingsheng Gao; Linxu Li; Ke Ji; Weiyuan Li; Yixin Lian; Yuzhuo Fu; Bin Dai.
  - Venue / outlet: **ICLR** · Year: **2025**.

<!-- record: arora2026streamrag; question: unassigned; review: not-question-mapped -->
- **[Stream RAG: Instant and Accurate Spoken Dialogue Systems with Streaming Tool Usage](<https://arxiv.org/abs/2510.02044>)**
  - Authors: Siddhant Arora; Haidar Khan; Kai Sun; Xin Luna Dong; Sajal Choudhary; Seungwhan Moon; Xinyuan Zhang; Adithya Sagar; Surya Teja Appini; Kaushik Patnaik; Sanat Sharma; Shinji Watanabe; Anuj Kumar; Ahmed Aly; Yue Liu; Florian Metze; Zhaojiang Lin.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.

<!-- record: Laitenberger2025Stronger; question: unassigned; review: not-question-mapped -->
- **[Stronger Baselines for Retrieval-Augmented Generation with Long-Context Language Models](<https://doi.org/10.18653/v1/2025.emnlp-main.1656>)**
  - Authors: Alex Laitenberger; Christopher D Manning; Nelson F. Liu.
  - Venue / outlet: **EMNLP** · Year: **2025**.

<!-- record: li2025tgrag; question: unassigned; review: not-question-mapped -->
- **[T-GRAG: A Dynamic GraphRAG Framework for Resolving Temporal Conflicts and Redundancy in Knowledge Retrieval](<https://doi.org/10.1145/3746027.3755628>)**
  - Authors: Dong Li; Yichen Niu; Ying Ai; Xiang Zou; Biqing Qi; Jianxing Liu.
  - Venue / outlet: **ACM Multimedia** · Year: **2025**.

<!-- record: gao2025tvnrag; question: unassigned; review: not-question-mapped -->
- **[TV-RAG: A Temporal-aware and Semantic Entropy-Weighted Framework for Long Video Retrieval and Understanding](<https://doi.org/10.1145/3746027.3755873>)**
  - Authors: Zongsheng Cao; Yangfan He; Anran Liu; Jun Xie; Feng Chen; Zhepeng Wang.
  - Venue / outlet: **ACM Multimedia** · Year: **2025**.

<!-- record: tanaka2025vdocrag; question: unassigned; review: not-question-mapped -->
- **[VDocRAG: Retrieval-Augmented Generation over Visually-Rich Documents](<https://arxiv.org/abs/2504.09795>)**
  - Authors: Ryota Tanaka; Taichi Iki; Taku Hasegawa; Kyosuke Nishida; Kuniko Saito; Jun Suzuki.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.

<!-- record: chen2025wavrag; question: unassigned; review: not-question-mapped -->
- **[WavRAG: Audio-Integrated Retrieval Augmented Generation for Spoken Dialogue Models](<https://arxiv.org/abs/2502.14727>)**
  - Authors: Yifu Chen; Shengpeng Ji; Haoxiao Wang; Ziqing Wang; Siyu Chen; Jinzheng He; Jin Xu; Zhou Zhao.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.

<!-- record: shao2024deepseekmath; question: unassigned; review: not-question-mapped -->
- **[DeepSeekMath: Pushing the Limits of Mathematical Reasoning in Open Language Models](<https://arxiv.org/abs/2402.03300>)**
  - Authors: Zhihong Shao; Peiyi Wang; Qihao Zhu; Runxin Xu; Junxiao Song; Xiao Bi; Haowei Zhang; Mingchuan Zhang; Y. K. Li; Y. Wu; Daya Guo.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.

<!-- record: Xu2024Unsupervised; question: unassigned; review: not-question-mapped -->
- **[Unsupervised Information Refinement Training of Large Language Models for Retrieval-Augmented Generation](<https://aclanthology.org/2024.acl-long.9/>)**
  - Authors: Shicheng Xu; Liang Pang; Mo Yu; Fandong Meng; Huawei Shen; Xueqi Cheng; Jie Zhou.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2024**.

<!-- record: izacard2023atlas; question: unassigned; review: not-question-mapped -->
- **[ATLAS: Few-shot Learning with Retrieval Augmented Language Models](<https://arxiv.org/abs/2208.03299>)**
  - Authors: Gautier Izacard; Patrick Lewis; Maria Lomeli; Lucas Hosseini; Fabio Petroni; Timo Schick; Jane Dwivedi-Yu; Armand Joulin; Sebastian Riedel; Edouard Grave.
  - Venue / outlet: **JMLR** · Year: **2023**.

<!-- record: rafailov2023dpo; question: unassigned; review: not-question-mapped -->
- **[Direct Preference Optimization: Your Language Model is Secretly a Reward Model](<https://arxiv.org/abs/2305.18290>)**
  - Authors: Rafael Rafailov; Archit Sharma; Eric Mitchell; Christopher D. Manning; Stefano Ermon; Chelsea Finn.
  - Venue / outlet: **NeurIPS** · Year: **2023**.

<!-- record: khandelwal2020generalization; question: unassigned; review: not-question-mapped -->
- **[Generalization through Memorization: Nearest Neighbor Language Models](<https://arxiv.org/abs/1911.00172>)**
  - Authors: Urvashi Khandelwal; Omer Levy; Dan Jurafsky; Luke Zettlemoyer; Mike Lewis.
  - Venue / outlet: **ICLR** · Year: **2020**.

<a id="support-4"></a>

### S4. Agentic RAG: Capabilities, Architectures, and Engineering

<!-- record: deepseekr12025; question: unassigned; review: not-question-mapped -->
- **[DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning](<https://arxiv.org/abs/2501.12948>)**
  - Authors: DeepSeek-AI.
  - Venue / outlet: **arXiv (preprint)** · Year: **2025**.

<a id="support-5"></a>

### S5. Evaluation of RAG: Objects, Quality Dimensions, Settings, and Methods

<!-- record: qwen2024qwen25; question: unassigned; review: not-question-mapped -->
- **[Qwen2.5 Technical Report](<https://arxiv.org/abs/2412.15115>)**
  - Authors: Qwen Team.
  - Venue / outlet: **arXiv (preprint)** · Year: **2024**.

<!-- record: trivedi2022musique; question: unassigned; review: not-question-mapped -->
- **[MuSiQue: Multihop Questions via Single-hop Question Composition](<https://aclanthology.org/2022.tacl-1.31/>)**
  - Authors: Harsh Trivedi; Niranjan Balasubramanian; Tushar Khot; Ashish Sabharwal.
  - Venue / outlet: **TACL** · Year: **2022**.

<!-- record: ho2020twowiki; question: unassigned; review: not-question-mapped -->
- **[Constructing a Multi-hop QA Dataset for Comprehensive Evaluation of Reasoning Steps](<https://aclanthology.org/2020.coling-main.580/>)**
  - Authors: Xanh Ho; Anh-Khoa Duong Nguyen; Saku Sugawara; Akiko Aizawa.
  - Venue / outlet: **COLING** · Year: **2020**.

<!-- record: kwiatkowski2019nq; question: unassigned; review: not-question-mapped -->
- **[Natural Questions: A Benchmark for Question Answering Research](<https://aclanthology.org/Q19-1026/>)**
  - Authors: Tom Kwiatkowski; Jennimaria Palomaki; Olivia Redfield; Michael Collins; Ankur Parikh; Chris Alberti; Danielle Epstein; Illia Polosukhin; Jacob Devlin; Kenton Lee; Kristina Toutanova; Llion Jones; Matthew Kelcey; Ming-Wei Chang; Andrew M. Dai; Jakob Uszkoreit; Quoc Le; Slav Petrov.
  - Venue / outlet: **TACL** · Year: **2019**.

<!-- record: yang2018hotpotqa; question: unassigned; review: not-question-mapped -->
- **[HotpotQA: A Dataset for Diverse, Explainable Multi-hop Question Answering](<https://aclanthology.org/D18-1259/>)**
  - Authors: Zhilin Yang; Peng Qi; Saizheng Zhang; Yoshua Bengio; William Cohen; Ruslan Salakhutdinov; Christopher D. Manning.
  - Venue / outlet: **EMNLP** · Year: **2018**.

<!-- record: joshi2017triviaqa; question: unassigned; review: not-question-mapped -->
- **[TriviaQA: A Large Scale Distantly Supervised Challenge Dataset for Reading Comprehension](<https://aclanthology.org/P17-1147/>)**
  - Authors: Mandar Joshi; Eunsol Choi; Daniel Weld; Luke Zettlemoyer.
  - Venue / outlet: **ACL (Long Papers)** · Year: **2017**.

<!-- record: robertson2009prf; question: unassigned; review: not-question-mapped -->
- **[The Probabilistic Relevance Framework: BM25 and Beyond](<https://doi.org/10.1561/1500000019>)**
  - Authors: Stephen Robertson; Hugo Zaragoza.
  - Venue / outlet: **Foundations and Trends in Information Retrieval** · Year: **2009**.

<a id="support-6"></a>

### S6. Reported Evaluation Protocol and Reproducibility Status

<!-- record: JZD_WWW_2025; question: unassigned; review: not-question-mapped -->
- **[FlashRAG: A Modular Toolkit for Efficient Retrieval-Augmented Generation Research](<https://dl.acm.org/doi/abs/10.1145/3701716.3715313>)**
  - Authors: Jiajie Jin; Yutao Zhu; Zhicheng Dou; Guanting Dong; Xinyu Yang; Chenghao Zhang; Tong Zhao; Zhao Yang; Ji-Rong Wen.
  - Venue / outlet: **The Web Conference (Companion)** · Year: **2025**.

<!-- record: kwon2023vllm; question: unassigned; review: not-question-mapped -->
- **[Efficient Memory Management for Large Language Model Serving with PagedAttention](<https://doi.org/10.1145/3600006.3613165>)**
  - Authors: Woosuk Kwon; Zhuohan Li; Siyuan Zhuang; Ying Sheng; Lianmin Zheng; Cody Hao Yu; Joseph E. Gonzalez; Hao Zhang; Ion Stoica.
  - Venue / outlet: **SOSP** · Year: **2023**.

<!-- record: mallen2023popqa; question: unassigned; review: not-question-mapped -->
- **[When Not to Trust Language Models: Investigating Effectiveness of Parametric and Non-Parametric Memories](<https://aclanthology.org/2023.acl-long.546.pdf>)**
  - Authors: Alex Troy Mallen; Akari Asai; Victor Zhong; Rajarshi Das; Hannaneh Hajishirzi; Daniel Khashabi.
  - Venue / outlet: **ACL** · Year: **2022**.

<!-- record: lin2021pyserini; question: unassigned; review: not-question-mapped -->
- **[Pyserini: A Python Toolkit for Reproducible Information Retrieval Research with Sparse and Dense Representations](<https://doi.org/10.1145/3404835.3463238>)**
  - Authors: Jimmy Lin; Xueguang Ma; Sheng-Chieh Lin; Jheng-Hong Yang; Ronak Pradeep; Rodrigo Nogueira.
  - Venue / outlet: **SIGIR** · Year: **2021**.

[Back to contents](#contents)

<a id="venue-abbreviations"></a>

## Venue abbreviations

| Abbreviation | Venue |
| --- | --- |
| ACL / EACL / NAACL | Annual meeting / European chapter / North American or Nations of the Americas chapter conferences of the Association for Computational Linguistics |
| EMNLP / COLING | Empirical Methods in Natural Language Processing / International Conference on Computational Linguistics |
| TACL / ACM TOIS | Transactions of the Association for Computational Linguistics / ACM Transactions on Information Systems |
| SIGIR / ECIR / ICTIR | ACM SIGIR / European Conference on Information Retrieval / International Conference on Innovative Concepts and Theories in Information Retrieval (formerly Theory of Information Retrieval) |
| CIKM / WSDM / WWW | Conference on Information and Knowledge Management / Web Search and Data Mining / The Web Conference |
| ICLR / ICML / NeurIPS | International Conference on Learning Representations / International Conference on Machine Learning / Neural Information Processing Systems |
| KDD / AAAI | ACM SIGKDD Conference on Knowledge Discovery and Data Mining / AAAI Conference on Artificial Intelligence |
| CVPR / ICCV | IEEE/CVF Conference on Computer Vision and Pattern Recognition / International Conference on Computer Vision |
| JMLR / IEEE TPAMI | Journal of Machine Learning Research / IEEE Transactions on Pattern Analysis and Machine Intelligence |
| PACMMOD / PVLDB / ICDE | Proceedings of the ACM on Management of Data / Proceedings of the VLDB Endowment / IEEE International Conference on Data Engineering |
| OSDI / SOSP | USENIX Symposium on Operating Systems Design and Implementation / ACM Symposium on Operating Systems Principles |

<a id="metadata-notes"></a>

## Metadata and maintenance notes

The question IDs, subcategories, and 535 association-review statuses are inherited unchanged from the v16 taxonomy. Bibliographic metadata is a versioned catalogue, not a fresh full-library publication audit. Preprint-to-proceedings updates should be supported by a matching primary record rather than inferred from a BibTeX key or paper year.

The following targeted metadata repairs were checked against primary publication or repository pages on 2026-09-11. They update this public catalogue without silently modifying the v16 manuscript or changing association-review labels:

| Record | Correction / clarification | Primary source |
| --- | --- | --- |
| `asai2024selfrag` | Conference year corrected from 2023 (preprint year) to ICLR 2024; primary proceedings link supplied. | [Record](<https://proceedings.iclr.cc/paper_files/paper/2024/hash/25f7be9694d7b32d5cc670927b8091e1-Abstract-Conference.html>) |
| `lewis2020rag` | Replaced preprint-only venue with the verified NeurIPS 2020 publication. | [Record](<https://papers.nips.cc/paper/2020/hash/6b493230205f780e1bc26945df7481e5-Abstract.html>) |
| `su2024dragin` | Formal ACL 2024 title, venue, and primary publication link. | [Record](<https://aclanthology.org/2024.acl-long.702/>) |
| `guu2020realm` | ICML 2020 confirmed; retained the REALM title and author spelling printed on the proceedings PDF. | [Record](<https://proceedings.mlr.press/v119/guu20a.html>) |
| `brown2020language` | NeurIPS 2020 confirmed; retained full author forms appearing on the proceedings PDF. | [Record](<https://proceedings.neurips.cc/paper_files/paper/2020/hash/1457c0d6bfcb4967418bfb8ac142f64a-Abstract.html>) |
| `Chakraborty2025Principled` | Resolved the generic LNCS series to ECIR 2026; publication year remains 2026. | [Record](<https://link.springer.com/chapter/10.1007/978-3-032-21300-6_45>) |
| `Gabin2025Leveraging` | Resolved the generic LNCS series to ECIR 2025. | [Record](<https://link.springer.com/chapter/10.1007/978-3-031-88711-6_20>) |
| `Hutter2025Lost` | Resolved the generic LNCS series to ECIR 2025; retained title and subtitle. | [Record](<https://link.springer.com/chapter/10.1007/978-3-031-88708-6_16>) |
| `Yazan2025Improving` | Resolved the generic LNCS series to ECIR 2025. | [Record](<https://link.springer.com/chapter/10.1007/978-3-031-88714-7_40>) |
| `YGZ_CCF_2024` | Resolved the generic CCIS series; distinguished the 2024 event from the 2025 publication year. | [Record](<https://link.springer.com/chapter/10.1007/978-981-96-1024-2_8>) |
| `Kim2024AutoRAG` | Filled the missing venue from the arXiv record, not a presumed conference acceptance. | [Record](<https://arxiv.org/abs/2410.20878>) |

Institutional reports retain their supplied corporate author when no individual byline was recorded. Their outlets are labeled as provider or industry reports, not conferences. Formatting normalization decodes author-name accents and shortens venue names while retaining identifiable tracks.

**Contributing corrections.** Please identify the Q ID and paper title, supply a DOI or primary publication link, and state whether the proposed change concerns author order, title, venue, year, or a question association. Metadata corrections do not by themselves verify a paper's scientific claims. A proposed new association should explain its role and point to the relevant source passage.

This catalogue contains bibliographic information and original organizational text; it does not reproduce paper abstracts or full texts. Rights in the linked publications remain with their respective holders.

[Back to contents](#contents)
