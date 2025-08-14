# RAG_Overview

This repository aims to provide a comprehensive overview of Retrieval-augmented Generation (RAG) by curating highly related resources, including representative papers, workshops, tutorials, evaluation tracts and open-source projects.
Given the rapid evolution of this field, we will continue to update the repository on a regular basis.

- <a href="#sp">Survey Papers</a>
- <a href="#wt">Workshops & Tutorials</a>
- <a href="#ec">Evaluation Campaigns</a>
- <a href="#op">Open-source Projects</a>
- <a href="#ps">Papers</a>
  - <a href="#ro">Retrieval Orchestration</a>
    - <a href="#when">When to retrieve</a>
    - <a href="#where">Where to retrieve</a>
    - <a href="#what">What to retrieve</a>
    - <a href="#how">How to retrieve</a>
  - <a href="#o">Optimization</a>
    -  <a href="#rfgo">Retriever (frozen), Generator (optimization)</a>
    -  <a href="#rogf">Retriever (optimization), Generator (frozen)</a>
    -  <a href="#jo">Joint Optimization</a>

## <a name="sp"></a>[Survey Papers]()

- ⭐ Retrieval-Enhanced Machine Learning: Synthesis and Opportunities ([link](https://arxiv.org/abs/2407.12982), 2024)
  - Highlight: This is the survey manuscript used in the tutorials ([Retrieval-Enhanced Machine Learning](https://retrieval-enhanced-ml.github.io)) at SIGIR 2025 and SIGIR-AP 2024. This tutorial introduces core REML concepts and synthesizing the literature from various domains in machine learning (ML), including but beyond NLP. **What is unique to our approach is that we used consistent notations, to provide researchers with a unified and expandable framework**.

- A Survey on RAG Meeting LLMs Towards Retrieval-Augmented Large Language Models ([paper](https://arxiv.org/abs/2405.06211), [RAG-Meets-LLMs Tutorial at KDD'24](https://advanced-recommender-systems.github.io/RAG-Meets-LLMs/))
  - Highlight: This tutorial comprehensively reviews existing research studies in retrieval-augmented large language models (RA-LLMs), covering three primary technical perspectives: architectures, training strategies, and applications. As the preliminary knowledge, the authors briefly introduce the foundations and recent advances of LLMs. Then, to illustrate the practical significance of RAG for LLMs, the authors categorize mainstream relevant work by application areas, detailing the challenges of each and the corresponding capabilities of RA-LLMs specifically. Finally, to deliver deeper insights, the authors discuss current limitations and several promising directions for future research. Meanwhile, the **accompanying [survey paper](https://arxiv.org/abs/2405.06211) and [slides](https://advanced-recommender-systems.github.io/RAG-Meets-LLMs/)** are publicly available.

- A Survey on Hallucination in Large Language Models: Principles, Taxonomy, Challenges, and Open Questions ([paper](https://arxiv.org/pdf/2311.05232), ACM Transactions on Information Systems-2025)
  - Highlight: The discussion includes representative methodologies for mitigating LLM hallucinations. Additionally, **the authors delve into the current limitations faced by retrieval-augmented LLMs in combating hallucinations**, offering insights for developing more robust IR systems. 

- A Comprehensive Survey of Retrieval-Augmented Generation (RAG): Evolution, Current Landscape and Future Directions ([paper](https://arxiv.org/pdf/2410.12837), 2024)
  - Highlight: The study explores the basic architecture of RAG, focusing on how retrieval and generation are integrated to handle knowledge-intensive tasks. A detailed review of the significant technological advancements in RAG is provided, including key innovations in retrieval-augmented language models and applications across various domains such as question-answering, summarization, and knowledge-based tasks. Recent research breakthroughs are discussed, highlighting novel methods for improving retrieval efficiency. Furthermore, the paper examines ongoing challenges such as scalability, bias, and ethical concerns in deployment.

- Retrieval-Augmented Generation for AI-Generated Content: A Survey ([paper](https://arxiv.org/pdf/2402.19473), 2024)
  - Highlight: The authors first classify RAG foundations according to how the retriever augments the generator. They distill the fundamental abstractions of the augmentation methodologies for various retrievers and generators. This unified perspective encompasses all RAG scenarios, illuminating advancements and pivotal technologies that help with potential future progress. The authors also summarize additional enhancements methods for RAG, facilitating effective engineering and implementation of RAG systems. Then from another view, the authors survey on practical applications of RAG across different modalities and tasks, offering valuable references for researchers and practitioners. Furthermore, the authors introduce the benchmarks for RAG, discuss the limitations of current RAG systems, and suggest potential directions for future research. 

- Information Retrieval for Artificial General Intelligence: A New Perspective on Information Retrieval Research ([Perspective paper@SIGIR-2025](https://dl.acm.org/doi/pdf/10.1145/3726302.3730349))
  - Highlight: The author presents a new perspective on IR research in which the users of an IR system are intelligent agents instead of human users. Extending the current work on retrieval-augmented generation (RAG), the author identifies five novel IR tasks that an intelligent agent must be able to perform in order to achieve Human-Level Artificial Intelligence, or Artificial General Intelligence (AGI), including 1) External Information Retrieval (EIR) to access new information unseen by the agent, 2) Provenance Information Retrieval (PIR) to trace the provenance of information, 3) Curriculum Information Retrieval (CIR) to actively acquire the most useful new data and information for lifelong learning, 4) Rule Information Retrieval (RIR) to perform reasoning and problem solving, and 5) Scenario Information Retrieval (SIR) to leverage past scenarios for problem solving and decision making. 

- Synergizing RAG and Reasoning: A Systematic Review ([paper](https://arxiv.org/pdf/2504.15909), 2025)
  - Highlight: This survey paper presents **a systematic review of the collaborative interplay between RAG and reasoning**, clearly defining "reasoning" within the RAG context. It construct a comprehensive taxonomy encompassing multi-dimensional collaborative objectives, representative paradigms, and technical implementations, and analyze the bidirectional synergy methods.

## <a name="ec"></a>[Evaluation Campaigns]()
 
- **TREC RAG Track** ([site](https://trec-rag.github.io), 2024, 2025)
  - Highlight: The TREC RAG Track is an **ongoing, multi-year effort**. It aims to bring the research community together around a unified benchmark to evaluate the end-to-end performance of systems that combine retrieval and generation. By structuring participation through distinct but complementary tasks, the track enabled deeper analysis of individual system components and their interactions. In fact, the following TREC tracks (BioGEN 2025 Track, DRAGUN 2025 Track, IKAT 2025 Track, RAGTIME 2025 Track) also support RAG-based approaches, please refer to the corresponding websites for more information.

- **SIGIR 2025 LiveRAG Challenge track** ([site](https://liverag.tii.ae)) 
  - Highlight: The goal of the SIGIR'2025 LiveRAG Challenge is to allow research teams across academia and industry to advance their RAG research and compare the performance of their solutions with other teams, on a fixed corpus (derived from the publicly available FineWeb) and a fixed open-source LLM, Falcon3-10B-Instruct.

- **Meta Comprehensive RAG Benchmark: KDD Cup 2024** ([site](https://www.aicrowd.com/challenges/meta-comprehensive-rag-benchmark-kdd-cup-2024)) 
  - Highlight: The Meta Comprehensive RAG Challenge (CRAG) aims to provide a good benchmark with clear metrics and evaluation protocols, to enable rigorous assessment of the RAG systems, drive innovations, and advance the solutions.
 
## <a name="op"></a>[Open-source Projects]()
- **FlashRAG**: A Modular Toolkit for Efficient Retrieval-Augmented Generation Research ([paper](https://arxiv.org/pdf/2405.13576), [site](https://github.com/RUC-NLPIR/FlashRAG))
  - Highlight: FlashRAG is a Python toolkit for the reproduction and development of Retrieval Augmented Generation (RAG) research. Our toolkit includes about 36 pre-processed benchmark RAG datasets and around 17 state-of-the-art RAG algorithms.

- **LightRAG**: Simple and Fast Retrieval-Augmented Generation ([paper](https://arxiv.org/pdf/2410.05779), [site](https://github.com/HKUDS/LightRAG))
  - Highlight: Focusing on the effective combination of LLM-generated knowledge graphs and graph machine learning, other closely related work includes [GraphRAG](https://github.com/microsoft/graphrag?tab=readme-ov-file) by Microsoft Research.

 - **BERGEN**: A Benchmarking Library for Retrieval-Augmented Generation ([paper](https://aclanthology.org/2024.findings-emnlp.449.pdf), [site](https://github.com/naver/bergen))
   - Highlight: A library designed to benchmark RAG systems with a focus on question-answering (QA). It addresses the challenge of inconsistent benchmarking in comparing approaches and understanding the impact of each component in a RAG pipeline.
     
## <a name="wt"></a>[Workshops & Tutorials]()
- **Retrieval-Enhanced Machine Learning** ([site](https://retrieval-enhanced-ml.github.io))
  - Highlight: This is an **ongoing, multi-year effort** that now includes tutorials at **SIGIR 2025** and **SIGIR-AP 2024**, as well as a workshop held in conjunction with **SIGIR 2023**. Meanwhile, the survey manuscript titled “Retrieval-Enhanced Machine Learning: Synthesis and Opportunities” (detailed in <a href="#sp">Survey Papers</a>) and the accompanying slides (e.g., [REML@SIGIR-2025 slides](https://retrieval-enhanced-ml.github.io/sigir-2025.html)) are publicly available.

- ⭐ **Tutorial: Retrieval-based Language Models and Applications**
  - Highlight: This tutorial at ACL-2023 ([site](https://acl2023-retrieval-lm.github.io) and [paper](https://aclanthology.org/2023.acl-tutorials.6.pdf)) offers a detailed survey, The slides and reference papers are also available on the website. The **subsequent position paper** by Akari Asai et al. ([Reliable, Adaptable, and Attributable Language Models with Retrieval](https://arxiv.org/abs/2403.03187)) is also highly insightful and thought-provoking.

- ⭐ **Tutorial: Retrieval and Ranking with LLMs**
  - Highlight: Generative LLMs like GPT, Gemini, and Llama are transforming Information Retrieval, enabling new and more effective approaches to document retrieval and ranking. The switch from the previous generation pre-trained language models backbones (e.g., BERT, T5) to the new generative LLMs backbones has required the field to adapt training processes; it also has provided unprecedented capabilities and opportunities, **stimulating research into zero-shot approaches**, reasoning approaches, reinforcement learning based training, and multilingual and multimodal applications. This tutorial at SIGIR-2025 ([site](https://ielab.io/tutorials/r2llms.html) and [slides](https://ielab.io/tutorials/r2llms.html)) provides a systematic overview of LLM-based retrievers and rankers, covering fundamental architectures, training paradigms, real-world deployment considerations, and open challenges and research directions. At the end of the tutorial, **a number of helpful tools for research on LLM-retrievers** are listed.

- **R3AG: Workshop on Refined and Reliable Retrieval Augmented Generation** 
  - Highlight: This is an ongoing, multi-year effort ([site](https://ii-research.github.io/R3AG/)) that now includes workshops **R3AG@SIGIR-AP 2024** ([site](https://r3ag-sigir-ap.github.io/) and [paper](https://arxiv.org/pdf/2410.20598)) and **R3AG@SIGIR-AP 2025** ([site](https://ii-research.github.io/R3AG/2025/), **which calls for papers now**).

- **BREV-RAG (Beyond Relevance-based EValuation of RAG systems)**
  - Highlight: The workshop of [BREV-RAG@SIGIR-AP 2025](http://sakailab.com/brev-rag/) (**calling for papers now**) focuses on the viewpoint of evaluation, which will be held in December, 2025. 
 
## <a name="ps"></a>[Papers]()

### <a name='ro'></a>[Retrieval Orchestration]()

#### <a name='when'></a>[When to retrieval]()
- [CLL24] [Unified Active Retrieval for Retrieval-Augmented Generation](https://arxiv.org/abs/2406.12534). EMNLP Findings.
- [JBC24] [Adaptive-RAG: Learning to Adapt Retrieval-Augmented Large Language Models through Question Complexity](https://aclanthology.org/2024.naacl-long.389/). NAACL.
- [JXG23] [Active Retrieval-Augmented Generation](https://aclanthology.org/2023.emnlp-main.495/). EMNLP.
- [STA24] [DRAGIN: Dynamic Retrieval-Augmented Generation Based on the Real-Time Information Needs of Large Language Models](https://aclanthology.org/2024.acl-long.702.pdf). ACL.
- [AWW24] [Self-RAG: Learning to Retrieve, Generate, and Critique through Self-Reflection](https://openreview.net/pdf?id=hSyW5go0v8). ICLR.
- [CQL25] [PAIRS: Parametric-Verified Adaptive Information Retrieval and Selection for Efficient RAG](https://arxiv.org/abs/2508.04057). arXiv.
- [CLL24] [Unified Active Retrieval for Retrieval-Augmented Generation](https://arxiv.org/abs/2406.12534). EMNLP Findings.

#### <a name='where'></a>[Where to retrieve]()
- [PYZ23] [Knowledge-in-Context: Towards Knowledgeable Semi-Parametric Language Models](https://arxiv.org/abs/2210.16433). ICLR.
- [SKZ24] [Optimization Methods for Personalizing Large Language Models through Retrieval Augmentation](https://arxiv.org/pdf/2404.05970). SIGIR.
- [KD24] [LTRR: Learning To Rank Retrievers for LLMs](https://arxiv.org/abs/2506.13743). SIGIR-2025-LiveRAG.
- [GKP25] [Efficient Federated Search for Retrieval-Augmented Generation](https://arxiv.org/abs/2502.19280). EuroMLSys.
- [WWL25] [MultiRAG: A Knowledge-guided Framework for Mitigating Hallucination in Multi-source Retrieval Augmented Generation](https://arxiv.org/abs/2508.03553). ICDE.


#### <a name='what'></a>[What to retrieval]()
- [NZC19] [Learning to Attend On Essential Terms: An Enhanced Retriever-Reader Model for Open-domain Question Answering](https://aclanthology.org/N19-1030/). NAACL.
- [BMH22] [Improving Language Models by Retrieving from Trillions of Tokens (RETRO)](https://proceedings.mlr.press/v162/borgeaud22a/borgeaud22a.pdf). ICML.
- [XLI21] [Answering Complex Open-Domain Questions with Multi-Hop Dense Retrieval](https://arxiv.org/abs/2009.12756). ICLR.
- [LLL22] [Query Expansion Using Contextual Clue Sampling with Language Models](https://arxiv.org/abs/2210.07093). arXiv.
- [MHL21] [Generation-Augmented Retrieval for Open-Domain Question Answering](https://aclanthology.org/2021.acl-long.316/). ACL.
- [GPT22] [Transform-Retrieve-Generate: Natural Language-Centric Outside-Knowledge Visual Question Answering](https://ieeexplore.ieee.org/document/9879942/). CVPR.
- [PLY20] [Unsupervised Question Decomposition for Question Answering](https://aclanthology.org/2020.emnlp-main.713/). EMNLP.
- [ZRY22] [Learning to Decompose: Hypothetical Question Decomposition Based on Comparable Texts](https://arxiv.org/abs/2210.16865). EMNLP.
- [CZC25] [When and How to Augment Your Input: Question Routing Helps Balance the Accuracy and Efficiency of Large Language Models](https://aclanthology.org/2025.findings-naacl.200/). NAACL Findings.
- [ZLH25] [Query Routing for Retrieval-Augmented Language Models](https://aclanthology.org/2025.findings-naacl.200/). arXiv.

#### <a name='how'></a>[How to retrieval]()
- [PC98] [A Language Modeling Approach to Information Retrieval](https://doi.org/10.1145/290941.291008). SIGIR.
- [FLP22] [From Distillation to Hard Negative Sampling: Making Sparse Neural IR Models More Effective](https://arxiv.org/abs/2205.04733). SIGIR.
- [MKT21] [Learning Passage Impacts for Inverted Indexes](https://arxiv.org/abs/2104.12016). SIGIR.
- [GDC21] [COIL: Revisit Exact Lexical Match in Information Retrieval with Contextualized Inverted List](https://arxiv.org/abs/2104.07186). NAACL.
- [WC06] [LDA-Based Document Models for Ad-Hoc Retrieval](https://doi.org/10.1145/1148170.1148204). SIGIR.
- [AE06] [Latent Semantic Indexing (LSI) Fails for TREC Collections](https://dl.acm.org/doi/abs/10.1145/1964897.1964900). SIGKDD Explorations Newsletter.
- [LM21] [A Few Brief Notes on DeepImpact, COIL, and a Conceptual Framework for Information Retrieval Techniques](https://arxiv.org/abs/2106.14807). arXiv.
- [KOM20] [Dense Passage Retrieval for Open-Domain Question Answering](https://aclanthology.org/2020.emnlp-main.550/). EMNLP.
- [RKH21] [Learning Transferable Visual Models From Natural Language Supervision](https://proceedings.mlr.press/v139/radford21a/radford21a.pdf). ICML.
- [LLX22] [BLIP: Bootstrapping Language-Image Pre-training for Unified Vision-Language Understanding and Generation](https://arxiv.org/abs/2201.12086). ICML.
- [LLS23] [BLIP-2: Bootstrapping Language-Image Pre-training with Frozen Image Encoders and Large Language Models](https://arxiv.org/abs/2301.12597). ICML.
- [XSA25] [BLIP-3: A Family of Open Large Multimodal Models](https://arxiv.org/pdf/2408.08872v3). arXiv.
- [KZ20] [ColBERT: Efficient and Effective Passage Search via Contextualized Late Interaction over BERT](https://dl.acm.org/doi/10.1145/3397271.3401075). SIGIR.
- [MT24] [A Reproducibility Study of PLAID](https://dl.acm.org/doi/10.1145/3626772.3657856). SIGIR.
- [DHJ24] [MUVERA: Multi-Vector Retrieval via Fixed Dimensional Encoding](https://proceedings.neurips.cc/paper_files/paper/2024/hash/b71cfefae46909178603b5bc6c11d3ae-Abstract-Conference.html). NeurIPS.
- [XXL21] [Approximate Nearest Neighbor Negative Contrastive Learning for Dense Text Retrieval](https://openreview.net/forum?id=zeFrfgyZln). ICLR.
- [KZ20] [ColBERT: Efficient and Effective Passage Search via Contextualized Late Interaction over BERT](https://dl.acm.org/doi/10.1145/3397271.3401075). SIGIR.
- [MTO21] [On Single and Multiple Representations in Dense Passage Retrieval](https://dl.acm.org/doi/10.1145/3397271.3401075). IIR.
- [NC20] [Passage Re-ranking with BERT](https://arxiv.org/abs/1901.04085). arXiv.
- [SZ25] [Learning to Rank for Multiple Retrieval-Augmented Models through Iterative Utility Maximization](https://dl.acm.org/doi/10.1145/3731120.3744584). ICTIR.
- [SZ24] [Towards a Search Engine for Machines: Unified Ranking for Multiple Retrieval-Augmented Large Language Models](https://dl.acm.org/doi/10.1145/3626772.3657733). SIGIR.
- [SYM23] [Is ChatGPT Good at Search? Investigating Large Language Models as Re-Ranking Agents](https://arxiv.org/pdf/2304.09542). EMNLP.
- [SYX25] [BRIGHT: A Realistic and Challenging Benchmark for Reasoning-Intensive Retrieval](https://arxiv.org/abs/2407.12883). ICLR.
- [YYR25] [Rank-K: Test-Time Reasoning for Listwise Reranking](https://arxiv.org/abs/2505.14432). arXiv
- [ZMK25] [Rank-R1: Enhancing Reasoning in LLM-based Document Rerankers via Reinforcement Learning](https://arxiv.org/abs/2503.06034). arXiv
- [SPS25] [RankLLM: A Python Package for Reranking with LLMs](https://arxiv.org/abs/2505.19284). SIGIR.
- [ZZK24] [A Setwise Approach for Effective and Highly Efficient Zero‑shot Ranking with Large Language Models](https://arxiv.org/abs/2310.09497). SIGIR.
- [ZLZ24] [Planning Ahead in Generative Retrieval: Guiding Autoregressive Generation through Simultaneous Decoding](https://arxiv.org/abs/2404.14600). SIGIR.
- [MTB21] [Rethinking Search: Making Domain Experts out of Dilettantes](https://arxiv.org/abs/2105.02274). SIGIR Forum.
- [LJZ25] [From Matching to Generation: A Survey on Generative Information Retrieval](https://arxiv.org/abs/2404.14851). TOIS.

### <a name='o'></a>[Optimization]()

#### <a name='rfgo'></a>[Retriever (frozen), Generator (optimization)]()
- [IG21] [Leveraging Passage Retrieval with Generative Models for Open Domain Question Answering](https://aclanthology.org/2021.eacl-main.74/). EACL.
- [HCR23] [FiD-Light: Efficient and Effective Retrieval-Augmented Text Generation](https://dl.acm.org/doi/10.1145/3539618.3591687). SIGIR.
- [ZB24] [Stochastic RAG: End-to-End Retrieval-Augmented Generation through Expected Utility Maximization](https://dl.acm.org/doi/10.1145/3626772.3657923). SIGIR.

#### <a name='rogf'></a>[Retriever (optimization), Generator (frozen)]()
- [SMY24] [REPLUG: Retrieval-Augmented Black-Box Language Models](https://aclanthology.org/2024.naacl-long.463.pdf). NAACL.

#### <a name='jo'></a>[Joint Optimization]()
- [LML25] [RAG-DDR: Optimizing Retrieval-Augmented Generation Using Differentiable Data Rewards](https://arxiv.org/abs/2410.13509). ICLR.
- [XLZ24] [C-Pack: Packed Resources For General Chinese Embeddings](https://arxiv.org/abs/2309.07597). SIGIR.
- [GLJ25] [SmartRAG: Jointly Learn RAG-Related Tasks From the Environment Feedback](https://arxiv.org/abs/2410.18141). ICLR.

