# Paper Screening & Selection Results
## LLM Memory & Hallucination — Revised & Validated

**Evaluation Date:** 2026-11-11 (revised)
**Total Entries Screened:** 128 (includes 3 confirmed duplicates)
**Unique Papers Evaluated:** 125
**Evaluator:** Claude Sonnet 4.6 — full re-read of all abstracts, criteria applied consistently

---

## Criteria Applied

**Include if ALL four hold:**
1. Published **2023–2026** (strict; 2022 papers excluded)
2. **Explicitly addresses** LLM memory systems, memory-augmented architectures, memory-based anti-hallucination methods, OR memory evaluation benchmarks — "memory" must appear as a primary research dimension, not incidentally
3. **Open-source weights / architecture OR sufficient technical specification** for reproducibility
4. **Reports quantitative evaluation** on recognised datasets or benchmarks

**Exclude if ANY of these apply:**
- E1: Exclusive reliance on closed-source APIs (black-box internals)
- E2: Standard RAG without a dedicated memory-management subsystem; or non-memory anti-hallucination (fine-tuning, attention analysis, prompt engineering)
- E3: Theoretical / position paper without quantitative baselines; survey without primary quantitative contribution

---

## ⚠️ Duplicates Noted (counted once under their first entry)

- **Paper 107** = duplicate of Paper 45 (PRISM) — not re-evaluated
- **Paper 121** = duplicate of Paper 73 (MemGraphRAG)
- **Paper 122** = duplicate of Paper 72 (CogitoRAG/Understand Then Memory)

---

# INCLUDED PAPERS

## RQ1 – Benchmarks & Evaluation

**5. HalluLens: LLM Hallucination Benchmark --> Included --> ACL 2025; abstract explicitly distinguishes hallucinations contradicting "parametric memory" (extrinsic) vs. context (intrinsic); open-source; quantitative benchmark evaluated with dynamic test generation.**

**10. What Matters in Memorizing and Recalling Facts? --> Included --> EMNLP 2024 (Findings); title and scope explicitly target memorising and recalling facts from parametric memory; BELIEF framework with MyriadLAMA dataset provide quantitative probing results.**

**11. LongMemEval: Benchmarking Chat Assistants on Long-Term Interactive Memory --> Included --> ICLR 2025; core research object is long-term memory with five dedicated memory-ability dimensions; open benchmark; 30% cross-session accuracy drop is a primary quantitative finding.**

**12. Evaluating Very Long-Term Conversational Memory of LLM Agents (LoCoMo) --> Included --> ACL 2024; explicitly designed to evaluate LLMs on very long-term conversational memory; open dataset; quantitative evaluation across 300-turn, up-to-35-session conversations.**

**13. MemBench: Towards More Comprehensive Evaluation on the Memory of LLM-based Agents --> Included --> ACL 2025 (Findings); benchmark explicitly evaluates agent memory across effectiveness, efficiency, and capacity; distinguishes factual from reflective memory with quantitative metrics.**

**14. Evaluating the Long-Term Memory of Large Language Models (LOCCO) --> Included --> ACL 2025 (Findings); LOCCO dataset is explicitly for LLM long-term memory evaluation; demonstrates memory decay over time quantitatively.**

**15. RealMem: Benchmarking LLMs in Real-World Memory-Driven Interaction --> Included --> ACL 2026 (Findings); first benchmark grounded in memory-driven interaction; 2,000+ cross-session dialogues with quantitative evaluation of memory-dependent task completion.**

**16. HaluMem: Evaluating Hallucinations in Memory Systems of Agents --> Included --> arXiv 2025; first operation-level hallucination benchmark explicitly for agent memory systems; 15k memory points, 1M+ tokens, quantitative across extraction/updating/QA operations.**

**17. RAGTruth: A Hallucination Corpus for Developing Trustworthy Retrieval-Augmented Language Models --> Included --> ACL 2024; 18,000-response corpus for hallucination in memory-augmented generation; word-level annotations; quantitative fine-tuning baselines; serves as an evaluation benchmark for RAG memory faithfulness.**

**23. ConflictBank: A Benchmark for Evaluating the Influence of Knowledge Conflicts in LLMs --> Included --> NeurIPS 2024; explicitly studies knowledge conflicts across three axes including context-memory and intra-memory conflicts; 7.4M claim-evidence pairs and 553k QA pairs provide quantitative baselines.**

**24. RECALL: A Benchmark for LLMs Robustness against External Counterfactual Knowledge --> Included --> arXiv 2023 (workshop); directly evaluates the conflict between parametric (internal) memory and counterfactual external context; quantitative robustness metrics.**

**25. Adaptive Chameleon or Stubborn Sloth: Revealing the Behavior of LLMs in Knowledge Conflicts --> Included --> ICLR 2024 (Spotlight); framework extracting parametric knowledge and constructing counter-evidence to study parametric memory behaviour; quantitative confirmation-bias measurements.**

**28. Med-HALT: Medical Domain Hallucination Test for Large Language Models --> Included --> CoNLL 2023; abstract explicitly includes "memory-based hallucination tests" alongside reasoning tests; domain-specific but memory evaluation is a primary stated dimension; quantitative benchmark.**

**34. SuperMemory-VQA: An Egocentric Visual Question-Answering Benchmark for Long-Horizon Memory --> Excluded --> Non-textual modality (egocentric video); review scope restricted to text-based LLM memory systems.**

**37. Memory in Large Language Models: Mechanisms, Evaluation and Evolution --> Included --> arXiv 2025; comprehensive survey with explicit memory taxonomy (parametric, contextual, external, procedural) plus an evaluation framework; qualifies as memory-system survey with systematic analysis.**

**38. MemoryBank: Enhancing Large Language Models with Long-Term Memory --> Included --> AAAI 2024; proposes a long-term memory mechanism inspired by Ebbinghaus Forgetting Curve; evaluation metrics for memory faithfulness and factual consistency are reported quantitatively.**

**43. MCPHallu: Benchmarking Reasoning, Execution, and Memory Hallucinations in MCP Agents --> Included --> arXiv 2026; explicitly includes a "memory" hallucination axis; 358 tasks across five domains; quantitative evaluation of 14 LLMs.**

**45. PRISM: Probing Reasoning, Instruction, and Source Memory in LLM Hallucinations --> Included --> arXiv 2026; "source memory" is an explicit fourth diagnostic dimension; 9,448 instances; quantitative disentanglement of hallucination sources including memory.**

**46. ES-MemEval: Benchmarking Conversational Agents on Personalized Long-Term Emotional Support --> Included --> WWW 2026; evaluates five memory capabilities explicitly in long-term conversational agents; EvoEmo dataset; quantitative memory performance metrics.**

**47. Towards Root Memory: Benchmarking and Enhancing Implicit Logical Memory Retrieval for Personalized LLMs --> Included --> arXiv 2026; IMLogic benchmark for implicit logical memory retrieval; root memory representation; quantitative divergence between semantic and logical relevance.**

**48. Locomo-Plus: Beyond-Factual Cognitive Memory Evaluation Framework for LLM Agents --> Included --> arXiv 2026; cognitive memory evaluation framework; extends factual accuracy to constraint-consistency; quantitative evaluation of memory management behaviour.**

**49. MemoryBench: A Benchmark for Memory and Continual Learning in LLM Systems --> Included --> arXiv 2025; comprehensive benchmark for long-term memory and continual learning; 8K–128K token contexts; quantitative effectiveness and efficiency metrics.**

**50. MemoryRewardBench: Benchmarking Reward Models for Long-Term Memory Management --> Included --> arXiv 2026; first benchmark studying reward models for long-term memory management quality; quantitative systematic gap analysis across 8K–128K tokens.**

**51. TWIST: A Proposed Benchmark for Intervention Quality in Conversational Memory --> Included --> arXiv 2026; explicitly evaluates memory-system intervention quality (contradiction detection, belief updating, draft vetting); quantitative evaluation dimensions described; note: no PDF available, evaluated from abstract.**

---

## RQ2 – Memory-Based Methods

**39. MemGPT: Towards LLMs as Operating Systems --> Included --> arXiv/NeurIPS 2023 Workshop; OS-inspired virtual context management system; dedicated memory hierarchy with explicit page-in/page-out operations; hallucination evaluation on long-term memory scenarios; open-source.**

**52. MemBook: A Hierarchical Reasoning-based Memory Framework for Hallucination-Resistant LLM Agents --> Included --> EMNLP 2026 (Findings); hierarchical time-aware memory (Sessions → Chapters → Memory Points) with explicit retrieval mechanism suppressing cross-stage hallucination; quantitative results.**

**53. Synthius-Mem: Brain-Inspired Hallucination-Resistant Persona Memory --> Included --> arXiv 2026; brain-inspired hierarchical memory across six cognitive domains; achieves 94.4% on LoCoMo; adversarial robustness tests provide quantitative baselines.**

**54. Memory is Reconstructed, Not Retrieved: Graph Memory for LLM Agents --> Included --> arXiv 2026; associative memory graphs with active reconstruction mechanism; up to 23% improvement over baselines; explicitly reduces hallucinations from imprecise retrieval.**

**55. Forgetful but Faithful: A Cognitive Memory Architecture for Privacy-Aware Generative Agents (MaRS) --> Included --> arXiv 2025; cognitive memory architecture with six forgetting policies; FiFA benchmark with quantitative recall accuracy, coherence, and goal-completion metrics.**

**56. BioMem: Agentic Memory for Biomedical LLM Agents --> Included --> arXiv 2026; HMRU (Hierarchical Memory Retrieval and Utilization) framework for domain-specific memory; quantitative biomedical QA evaluation.**

**57. Oracle Agent Memory as an Enterprise Memory Substrate for Long-Horizon AI Agents --> Included --> arXiv 2026; database-native memory substrate with explicit memory lifecycle management; 93.8% accuracy with 10.7x fewer tokens vs. flat-history baseline.**

**58. Don't Just Trust Your Memory: Evidence-Linked Memory Reduces Memory-Induced Degradation in LLM Agents (WikiTrace) --> Included --> arXiv 2026; evidence-linked memory system directly addressing memory-induced degradation; quantitative evaluation across five benchmarks; open-source noted.**

**59. Parameters vs. Context: Fine-Grained Control of Knowledge Reliance in Language Models --> Included --> arXiv 2025; explicit mechanism governing reliance on parametric memory vs. context; reduces hallucination under knowledge conflict; quantitative Confidence Gain metric.**

**60. FIDES: Faithful Inference via Deep Evidence Signals for Retrieval-Memory Conflict in RAG --> Included --> arXiv 2026; training-free decoder for token-level retrieval-memory conflict; explicitly frames the problem as parametric-memory vs. retrieval; 92–94% context fidelity at 70B scale.**

**61. Investigating Context-Faithfulness in LLMs: The Roles of Memory Strength and Evidence Style --> Included --> arXiv 2024; explicitly quantifies "LLM memory strength" via response divergence; demonstrates how parametric memory overcomes external evidence; open code.**

**62. Rowen: Adaptive Retrieval-Augmented Generation for Hallucination Mitigation in LLMs --> Included --> arXiv 2024; explicitly balances parametric and external memory through adaptive retrieval activation; dedicated memory-switching subsystem; quantitative hallucination metrics.**

**63. Studying LLM Behaviors Under Context-Memory Conflicts With Real Documents --> Included --> arXiv 2024; directly studies context-parametric memory conflicts using real documents; taxonomy of conflict scenarios; quantitative parametric-bias measurements.**

**64. When Context Leads but Parametric Memory Follows in Large Language Models --> Included --> EMNLP 2024; investigates knowledge allocation between contextual (~70%) and parametric memory (~30%); WikiAtomic dataset; hallucination rates as a function of memory source.**

**65. Hallucination-Guided Unlearning: Using Hallucination Traces to Reveal Overfitted Memories --> Included --> arXiv 2026; uses hallucination failures to locate and unlearn overfitted parametric memories; sparse MLP neuron edits; quantitative benchmarks (TOFU, WMDP, MMLU).**

**66. WISE: Rethinking Knowledge Memory for Lifelong Model Editing --> Included --> NeurIPS 2024; dual parametric memory scheme (main + side memory) for lifelong editing; directly addresses memory reliability/generalization/locality; quantitative evaluation; open code.**

**67. Distilling Feedback into Memory-as-a-Tool --> Included --> arXiv 2026; converts feedback into persistent retrievable memory via file-based tool calls; explicit memory management architecture; quantitative Pareto-frontier analysis.**

**69. Towards Adaptive Memory-Based Optimization for Enhanced Retrieval-Augmented Generation --> Included --> arXiv 2025; abstract explicitly states "dynamically adjusting retrieval and memory management during generation"; dedicated memory management component; quantitative RAG benchmarks.**

**72. Understand Then Memory: A Cognitive Gist-Driven RAG Framework with Global Semantic Diffusion (CogitoRAG) --> Included --> arXiv 2026; extracts semantic gists before memory storage, reducing fragmentation-induced hallucinations; CogniRank algorithm; dedicated memory preprocessing subsystem.**

**73. MemGraphRAG: Memory-based Multi-Agent System for Graph Retrieval-Augmented Generation --> Included --> arXiv 2026; multi-agent architecture with shared graph-structured memory; explicit memory construction, conflict resolution, and retrieval pipeline; quantitative evaluation.**

**78. Knowledge Graph-Enhanced LLM Based on Question Decomposition and Atomic Retrieval (KELDaR) --> Included --> EMNLP 2024 (Findings); uses KG explicitly as "external structured memory" for atomic-level reasoning; dedicated memory query architecture; quantitative QA baselines.**

**79. Augmenting Language Models with Long-Term Memory (LongMem) --> Included --> arXiv/NeurIPS 2023 Workshop; persistent long-term memory augmentation with dedicated cached-attention memory module; enables faithful retrieval over extended interactions; quantitative results.**

**80. Reducing Hallucination in SPARQL Query Generation Using Post-Generation Memory Retrieval (PGMR) --> Included --> arXiv 2025; dedicated post-generation memory retrieval module separating URI resolution from query syntax; near-zero URI hallucination rate on LCQUAD 2.0 and QALD-10.**

**81. Decoding Memories: An Efficient Pipeline for Self-Consistency Hallucination Detection --> Included --> arXiv 2025; Decoding Memory Pipeline with explicit memory caching for multi-generation; 3x speedup without AUROC loss; dedicated memory mechanism for detection.**

**82. Generation Constraint Scaling Can Mitigate Hallucination --> Included --> arXiv 2024; explicitly scales "memory readout vectors" to constrain factual generation; directly manipulates parametric memory readout as an anti-hallucination mechanism; quantitative evaluation.**

**83. Look Twice Before You Answer: Memory-Space Visual Retracing for Hallucination Mitigation in Multimodal LLMs --> Included --> arXiv 2024; memory-space visual retracing reinjects visual tokens via FFN-based key-value memory; dedicated memory mechanism in MLLMs; +7.0% POPE, +15.6% CHAIR.**

**84. SAFE: A Sparse Autoencoder-Based Framework for Robust Query Enrichment and Hallucination Mitigation in LLMs --> Included --> arXiv 2025; sparse autoencoder probes parametric memory internals to enrich queries; directly targets parametric memory representations; +29.45% accuracy on TruthfulQA, BioASQ.**

**89. Mechanistic Understanding and Mitigation of Language Model Non-Factual Hallucinations --> Included --> EMNLP 2024 (Findings); explicitly "identifies two distinct failure modes in parametric memory" and mitigates via internal fact-retrieval restoration; quantitative evaluation.**

**92. In Prospect and Retrospect: Reflective Memory Management for Long-term Personalized Dialogue Agents --> Included --> ACL 2025; combines prospective and retrospective reflection explicitly for memory management; dedicated memory management system; >10% improvement on LongMemEval.**

**94. TRUSTMEM: Learning Trustworthy Memory Consolidation for LLM Agents with Long-Term Memory --> Included --> arXiv 2026; RL-based memory consolidation policy explicitly reducing hallucinated memory entries; dedicated memory lifecycle management; quantitative utility and reliability metrics.**

**95. From Storage to Experience: A Survey on the Evolution of LLM Agent Memory Mechanisms --> Included --> ACL 2026 (Findings); systematic survey with evolutionary taxonomy (Storage → Reflection → Experience) explicitly for LLM agent memory; establishes memory design principles; qualifies as memory-explicit survey.**

**96. A Survey of Agent Memory in the Second Half: Towards Self-Evolving and Long-Horizon Agents --> Included --> arXiv 2026; 50-author survey explicitly and entirely focused on agent memory across parametric, in-context, and external substrates; systematic analysis qualifies as memory-explicit survey.**

**97. Are We Ready For An Agent-Native Memory System? --> Included --> arXiv 2026; systematic empirical study of 12 agent memory architectures across five benchmarks; decomposes memory into representation, storage, extraction, update modules; quantitative hallucination-prone configuration analysis.**

**103. Explicit Working Memory Enhancement for Factuality (EWE) --> Included --> arXiv 2024; integrates a real-time working memory module refreshed via fact-checking and retrieval feedback; explicit working memory architecture; 2–6 point VeriScore improvement.**

**104. Efficient and Effective Internal Memory Retrieval for LLM-based Healthcare Prediction (BioMem) --> Included --> arXiv 2026; focuses on internal parametric memory retrieval in clinical settings; dedicated memory retrieval mechanism; quantitative healthcare prediction evaluation.**

**105. The Memory Trap: Language Agents Overgeneralize from Benign Interactions --> Included --> arXiv 2026; demonstrates that agent memory causes hallucination-like unsafe behaviour through overgeneralization; explicit memory failure mode study; quantitative behavioural analysis.**

**106. MemGuard: Preventing Memory Contamination in Long-Term Memory-Augmented LLMs --> Included --> arXiv 2026; type-aware memory organisation framework preventing heterogeneous memory contamination; dedicated memory integrity mechanism; quantitative factual-consistency evaluation.**

**110. Self-RAG: Learning to Retrieve, Generate, and Critique through Self-Reflection --> Included --> NeurIPS 2023; trains LM with dedicated reflection tokens that explicitly control external memory access decisions; on-demand retrieval with self-critique is a dedicated memory-access management subsystem; quantitative factuality benchmarks.**

**111. Active Retrieval Augmented Generation (FLARE) --> Included --> EMNLP 2023; actively decides when and what to retrieve using forward-looking predictions; dedicated active memory-access management mechanism; iterative query-and-regenerate with quantitative evaluation.**

**112. Corrective Retrieval Augmented Generation (CRAG, method) --> Included --> ICLR 2024; lightweight retrieval evaluator with confidence-based corrective actions (web search fallback); dedicated memory quality-management subsystem distinct from standard RAG; decompose-recompose algorithm; quantitative benchmarks.**

**114. Cognitive Architectures for Language Agents (CoALA) --> Included --> TMLR 2024; systematic framework with modular memory as a first-class component (working, episodic, semantic, procedural); provides architectural specification enabling reproducibility; widely adopted as a memory taxonomy reference.**

**116. Generative Agents: Interactive Simulacra of Human Behavior --> Included --> ACM UIST 2023; explicit memory architecture using natural language memory records, synthesized reflective summaries, and dynamic retrieval; memory is the primary architectural contribution; quantitative behavioural evaluation.**

**117. LSTM-MAS: A Long Short-Term Memory Inspired Multi-Agent System for Long-Context Understanding --> Included --> arXiv 2026; explicitly emulates LSTM gated memory with worker/filter/judge/manager agents; dedicated memory management architecture inspired by LSTM; quantitative evaluation on long-context tasks.**

**119. TeleMem: Building Long-Term and Multimodal Memory for Agentic AI --> Included --> arXiv 2026; unified long-term and multimodal memory system with narrative extraction and structured writing pipeline; 19% higher accuracy, 43% fewer tokens vs. Mem0; explicit memory architecture.**

**123. TC-RAG: Turing-Complete RAG's Case Study on Medical LLM Systems --> Included --> ACM MM 2024; Turing-complete system with explicit memory stack using Push/Pop operations for state variable management; dedicated memory-management subsystem; 7.20% accuracy improvement.**

**124. AssistRAG: Boosting the Potential of LLMs with an Intelligent Information Assistant --> Included --> NeurIPS 2024; abstract explicitly describes "memory building" as a component alongside tool usage and action execution; dedicated memory construction and management; curriculum learning; quantitative benchmarks.**

**126. Seeing through the Conflict: Transparent Knowledge Conflict Handling in RAG (TCR) --> Included --> arXiv 2026; dual contrastive encoders for semantic match and factual consistency; self-answerability estimation for parametric-retrieval conflict resolution; dedicated memory-conflict management subsystem; quantitative evaluation.**

---

# EXCLUDED PAPERS

**1. HaluEval: A Large-Scale Hallucination Evaluation Benchmark for LLMs --> Excluded --> Tests LLM hallucination recognition generally; no memory system, memory evaluation benchmark, or memory management subsystem; E2 applies.**

**2. FActScore: Fine-grained Atomic Evaluation of Factual Precision in Long Form Text Generation --> Excluded --> Evaluates factual precision in generation; no memory architecture or memory evaluation dimension; E2 applies.**

**3. FELM: Benchmarking Factuality Evaluation of Large Language Models --> Excluded --> Segment-level factuality evaluation benchmark; no memory system or memory-evaluation focus; E2 applies.**

**4. The Dawn After the Dark: An Empirical Study on Factuality Hallucination in LLMs (HaluEval 2.0) --> Excluded --> Systematic hallucination study without memory as a primary research object; covers detection, source, and mitigation broadly; E2 applies.**

**6. FaithBench: A Diverse Hallucination Benchmark for Summarization by Modern LLMs --> Excluded --> Hallucination benchmark for the summarisation task; no memory system, memory management, or memory evaluation dimension; E2 applies.**

**7. FactBench: A Dynamic Benchmark for In-the-Wild Language Model Factuality Evaluation --> Excluded --> Dynamic factuality evaluation from real-world usage; no memory architecture or memory-specific evaluation; E2 applies.**

**8. TruthfulQA: Measuring How Models Mimic Human Falsehoods --> Excluded --> Published 2022; fails strict date criterion (Criterion 1). Foundational but out of scope.**

**9. Factcheck-Bench: Fine-Grained Evaluation Benchmark for Automatic Fact-checkers --> Excluded --> Fine-grained factuality evaluation for fact-checkers; no memory system or memory-evaluation focus; E2 applies.**

**18. Ragas: Automated Evaluation of Retrieval Augmented Generation --> Excluded --> General-purpose RAG evaluation framework with standard retrieval metrics; no dedicated memory-management subsystem; E2 applies.**

**19. MIRAGE: Benchmarking Retrieval-Augmented Generation for Medicine --> Excluded --> Domain-specific standard RAG benchmark; evaluates retrieval and generation without a dedicated memory-management component; E2 applies.**

**20. CRAG — Comprehensive RAG Benchmark (NeurIPS 2024) --> Excluded --> General RAG performance benchmark across five domains; no dedicated memory management subsystem; standard retrieval evaluation; E2 applies. (Note: distinct from CRAG the corrective method, paper 112, which is included.)**

**21. RAGEval: Scenario Specific RAG Evaluation Dataset Generation Framework --> Excluded --> Schema-based RAG evaluation pipeline; standard RAG without dedicated memory management; Completeness/Hallucination/Irrelevance metrics do not address memory systems; E2 applies.**

**22. WikiContradict: A Benchmark for Evaluating LLMs on Real-World Knowledge Conflicts from Wikipedia --> Excluded --> Evaluates inter-context conflicts between Wikipedia sections; focus is context-context conflict reasoning rather than parametric memory management; E2 applies.**

**26. Knowledge Conflicts for LLMs: A Survey --> Excluded --> Systematic survey on knowledge conflict types including context-memory; however, presents no primary quantitative evaluation baselines of its own; E3 applies.**

**27. ERBench: An Entity-Relationship based Automatically Verifiable Hallucination Benchmark --> Excluded --> Automatically converts relational databases into hallucination benchmarks; no memory system or memory evaluation dimension; primary contribution is automatic verification via integrity constraints; E2 applies.**

**29. UHGEval: Benchmarking the Hallucination of Chinese Large Language Models --> Excluded --> General-purpose hallucination benchmark for Chinese LLMs; no memory system or memory evaluation dimension; E2 applies.**

**30. TofuEval: Evaluating Hallucinations of LLMs on Topic-Focused Dialogue Summarization --> Excluded --> Hallucination benchmark for dialogue summarisation; no memory system or memory management; E2 applies.**

**31. DiaHalu: A Dialogue-level Hallucination Evaluation Benchmark --> Excluded --> Dialogue-level hallucination benchmark across four domains; no dedicated memory system or memory evaluation dimension; E2 applies.**

**32. ToolBeHonest: A Multi-level Hallucination Diagnostic Benchmark for Tool-Augmented LLMs --> Excluded --> Hallucination diagnostic for tool-augmented LLMs; focus is tool execution fidelity, not memory systems; E2 applies.**

**33. MMRC: A Large-Scale Benchmark for Understanding Multimodal LLMs in Real-World Conversation --> Excluded --> General multimodal conversation benchmark; memory recall is one of six evaluated abilities, not the primary research object; Criterion 2 not met.**

**35. Long-form Factuality in Large Language Models (LongFact + SAFE) --> Excluded --> Long-form factuality evaluation using search-augmented claim verification; no dedicated memory management subsystem; SAFE uses Google Search as a retrieval oracle, not a memory architecture; E2 applies.**

**36. KIEval: A Knowledge-grounded Interactive Evaluation Framework for LLMs --> Excluded --> Addresses data contamination via interactive evaluation; no memory system focus; E2 applies.**

**40. DialFork: Going Beyond Factuality to Evaluate Procedural Hallucination in Conversational Agents --> Excluded --> Evaluates procedural hallucination (task-flow deviations); no memory system or memory evaluation dimension; E2 applies.**

**41. Beyond Facts: Evaluating Intent Hallucination in LLMs (FaithQA) --> Excluded --> Evaluates intent hallucination (query element omission/misinterpretation); no memory system or memory management component; E2 applies.**

**42. Hallucination Cascade: Analyzing Error Propagation in Multi-Agent LLM Systems --> Excluded --> Analyses hallucination propagation across sequential agent interactions; no memory system or dedicated memory management; E2 applies.**

**44. Hallucination Detection in LLMs: Fast and Memory-Efficient Fine-Tuned Models --> Excluded --> "Memory-efficient" refers to GPU memory, not LLM memory systems; fine-tuned detection models without memory management architecture; E2 applies.**

**68. RAG-DDR: Optimizing Retrieval-Augmented Generation Using Differentiable Data Rewards --> Excluded --> End-to-end RAG optimisation via differentiable rewards; no dedicated memory management subsystem; standard RAG with improved training signal; E2 applies.**

**70. Scaling Test-Time Inference with Policy-Optimized Dynamic RAG via KV Caching and Decoding --> Excluded --> KV-caching is used as an inference optimisation implementation detail, not a dedicated memory management subsystem; primary focus is test-time scaling; E2 applies.**

**71. Removal of Hallucination on Hallucination: Debate-Augmented RAG --> Excluded --> Multi-agent debate applied to RAG stages; no dedicated memory management subsystem; standard RAG with debate augmentation; E2 applies.**

**74. Reducing Hallucination in Structured Outputs via Retrieval-Augmented Generation --> Excluded --> Standard RAG applied to structured workflow generation; no dedicated memory management component; E2 applies.**

**75. ReEval: Automatic Hallucination Evaluation for RAG via Transferable Adversarial Attacks --> Excluded --> Adversarial evaluation framework for RAG; no memory management architecture; E2 applies.**

**76. Can Knowledge Graphs Reduce Hallucinations in LLMs? A Survey --> Excluded --> Survey reviewing KG-based external augmentation; no primary quantitative evaluation baselines; E3 applies.**

**77. Augmenting LLMs with Knowledge: A Survey on Hallucination Prevention --> Excluded --> Survey of external knowledge augmentation; no primary quantitative baselines; E3 applies.**

**85. Knowledge-Centric Hallucination Detection (RefChecker) --> Excluded --> Converts outputs into claim-triplets for fact-checking against knowledge sources; detection method without a dedicated memory subsystem; E2 applies.**

**86. Lookback Lens: Detecting and Mitigating Contextual Hallucinations Using Only Attention Maps --> Excluded --> Attention-weight-ratio-based detection; no memory management subsystem; E2 applies.**

**87. SIRIN: A Unified Toolkit for Detecting Contextual Hallucinations in RAG and Memory-Grounded LLM Systems --> Excluded --> Detection toolkit operating over memory-grounded systems; SIRIN itself has no memory management architecture, only detection paradigms; E2 applies.**

**88. Citation-Enhanced Generation for LLM-based Chatbots --> Excluded --> RAG + NLI post-hoc citation generation; no dedicated memory management subsystem; standard retrieval + verification; E2 applies.**

**90. Zero-Resource Hallucination Prevention for LLMs (SELF-FAMILIARITY) --> Excluded --> Pre-detection via self-evaluation of concept familiarity; closest to a prompting/self-evaluation technique; no dedicated memory subsystem; E2 applies.**

**91. Controlling Risk of Retrieval-Augmented Generation: A Counterfactual Prompting Framework --> Excluded --> Counterfactual prompting for RAG abstention; prompt engineering technique; E2 applies.**

**93. Learning from Hallucinations: Mitigating Hallucinations via Internal Representation Intervention --> Excluded --> "In-model anti-expert" method via representation intervention; no memory system; "Reduces GPU memory from 2.2x to 1.2x" refers to efficiency, not memory architecture; E2 applies.**

**98. Factuality of Large Language Models: A Survey --> Excluded --> General factuality survey; no primary quantitative contribution; memory not a primary research dimension; E3 applies.**

**99. A Comprehensive Survey of Hallucination in Large Language, Image, Video and Audio Foundation Models --> Excluded --> Broad multimodal hallucination survey; no memory system focus; no primary quantitative baselines; E3 applies.**

**100. Insights into Classifying and Mitigating LLMs' Hallucinations --> Excluded --> General hallucination classification and mitigation survey; no memory system focus; E2/E3 apply.**

**101. Mitigating Hallucination: A Capability-Oriented Survey on RAG, Reasoning, and Agentic Systems --> Excluded --> RAG/reasoning/agentic capability survey; memory is not a primary research dimension; general mitigation coverage; E3 applies.**

**102. Hallucinations in LLMs: A Lifecycle-Based Survey of Causes, Detection, Mitigation, and Prevention --> Excluded --> General lifecycle hallucination survey; no dedicated memory dimension; no primary quantitative baselines; E3 applies.**

**108. Retrieval-Augmented Generation for Large Language Models: A Survey --> Excluded --> Survey of Naive/Advanced/Modular RAG paradigms; no primary quantitative contribution; no dedicated memory management focus; E3 applies.**

**109. A Survey on Retrieval-Augmented Text Generation for Large Language Models --> Excluded --> General RAG survey across four retrieval categories; no primary quantitative contribution; E3 applies.**

**113. Chain-of-Note: Enhancing Robustness in Retrieval-Augmented Language Models --> Excluded --> Sequential reading notes are a prompting strategy for processing retrieved documents; no dedicated memory management subsystem; E2 applies.**

**115. A Survey on Large Language Model based Autonomous Agents --> Excluded --> Comprehensive general agent survey; memory is one component of a brain-perception-action framework, not the primary research object; E3 applies.**

**118. Check Your Facts and Try Again: Improving LLMs with External Knowledge (LLM-Augmenter) --> Excluded --> Plug-and-play external knowledge grounding with iterative revision; standard retrieval + feedback loop without a dedicated memory management subsystem; E2 applies.**

**120. From Local to Global: A Graph RAG Approach to Query-Focused Summarization (GraphRAG) --> Excluded --> Graph-based RAG for summarisation with precomputed community summaries; no dedicated agent memory management; E2 applies.**

**125. Improving Factuality and Reasoning in Language Models through Multiagent Debate --> Excluded --> Multi-agent debate consensus mechanism; non-memory anti-hallucination technique; E2 applies.**

**127. Siren's Song in the AI Ocean: A Survey on Hallucination in Large Language Models --> Excluded --> General hallucination survey (detection, explanation, mitigation); no memory system focus; no primary quantitative baselines; E3 applies.**

**128. A Survey on Hallucination in LLMs: Principles, Taxonomy, Challenges, and Open Questions --> Excluded --> General hallucination taxonomy survey; no memory focus; no primary quantitative baselines; E3 applies.**

---

# SUMMARY STATISTICS

| Category | Count |
|---|---|
| Total entries screened | 128 |
| Confirmed duplicates (not re-evaluated) | 3 (papers 107=45, 121=73, 122=72) |
| Unique papers evaluated | 125 |
| **Included** | **71** |
| **Excluded** | **54** |
| Inclusion rate (of unique papers) | **56.8%** |

### By Research Question

| | RQ1 Benchmarks | RQ2 Methods | Total |
|---|---|---|---|
| Entries in source | 51 | 77 | 128 |
| Included | 25 | 46 | 71 |
| Excluded | 26 | 28 | 54 |
| Inclusion rate | 49.0% | 62.2% | 56.8% |

### Primary Exclusion Reasons

| Reason | Count |
|---|---|
| E2: Generic hallucination benchmark (no memory focus) | 18 |
| E2: Standard RAG without memory management subsystem | 15 |
| E2: Non-memory anti-hallucination technique | 8 |
| E3: Survey without primary quantitative contribution | 10 |
| Criterion 1: Outside 2023–2026 date range | 1 |
| Criterion 2: Memory incidental / not primary research object | 2 |

### Corrections vs. First Pass (original SCREENING_RESULTS.md)

**Moved INCLUDED → EXCLUDED (14 papers):**
TruthfulQA (year), Ragas, MIRAGE, CRAG Benchmark, RAGEval, WikiContradict, MMRC, FaithQA, Hallucination Cascade, Chain-of-Note, SELF-FAMILIARITY, RefChecker, RAG-DDR, Survey on Autonomous Agents

**Moved EXCLUDED → INCLUDED (1 paper):**
ConflictBank (explicitly studies context-memory and intra-memory conflicts)

**Net change:** 84 → 71 included papers (−13)

---

**Screening Completed:** 2026-11-11 (revised)  
**Method:** Full re-read of all 128 abstracts; criteria applied paper-by-paper with consistent interpretation  
**Key interpretive rule applied:** "Memory" must be a *primary research dimension*, not incidental (e.g. "memory recall as 1 of 6 abilities" does not qualify; "five core long-term memory abilities" does qualify). Standard RAG without an explicit memory-management lifecycle component does not qualify.
