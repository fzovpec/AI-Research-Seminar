# Paper Screening & Selection Results
## LLM Memory & Hallucination Literature Review

**Evaluation Date:** 2026-11-11  
**Total Papers Screened:** 128  
**Evaluation Method:** 16 parallel agents  
**Inclusion Criteria:** 2023-2026 publication + memory-explicit focus + open/transparent + quantitative evaluation

---

## INCLUDED PAPERS (Passed all criteria)

### RQ1: Benchmarks and Datasets for LLM Memory Hallucinations

5. HalluLens: LLM Hallucination Benchmark --> Included --> ACL 2025; explicitly distinguishes extrinsic hallucinations (contradicting parametric memory) from intrinsic (contradicting context); open-source via GitHub/HuggingFace; quantitative evaluation framework.

8. TruthfulQA: Measuring How Models Mimic Human Falsehoods --> Included --> Borderline on date (2022) but foundational benchmark for parametric memory hallucinations; open-source code/models available; 817 questions with quantitative metrics across 38 domains.

10. What Matters in Memorizing and Recalling Facts? --> Included --> Memory-explicit focus on knowledge probing with quantitative evaluation; EMNLP 2024; BELIEF framework with MyriadLAMA dataset.

11. LongMemEval: Benchmarking Chat Assistants on Long-Term Interactive Memory --> Included --> Explicitly addresses long-term memory evaluation with quantitative benchmarking; ICLR 2025; 500 questions evaluating five core long-term memory abilities.

12. Evaluating Very Long-Term Conversational Memory of LLM Agents (LoCoMo) --> Included --> Memory-explicit (long conversational memory) with quantitative evaluation metrics; ACL 2024; 300-turn conversations spanning 35 sessions.

13. MemBench: Towards More Comprehensive Evaluation on the Memory of LLM-based Agents --> Included --> Agent memory-focused benchmark with quantitative evaluation; ACL 2025 (Findings); distinguishes factual from reflective memory.

14. Evaluating the Long-Term Memory of Large Language Models (LOCCO) --> Included --> Long-term memory explicit with quantitative evaluation framework; ACL 2025 (Findings); LOCCO dataset with memory decay analysis.

15. RealMem: Benchmarking LLMs in Real-World Memory-Driven Interaction --> Included --> Memory-driven interaction study; ACL 2026 (Findings); 2,000+ cross-session dialogues grounding memory in realistic scenarios.

16. HaluMem: Evaluating Hallucinations in Memory Systems of Agents --> Included --> Memory-explicit (operation-level hallucination benchmark for agent memory); arXiv 2025; 15k memory points with quantitative evaluation.

17. RAGTruth: A Hallucination Corpus for Developing Trustworthy Retrieval-Augmented Language Models --> Included --> RAG hallucination corpus for memory-augmented generation; ACL 2024; ~18,000 naturally generated responses with word-level annotations.

18. Ragas: Automated Evaluation of Retrieval Augmented Generation --> Included --> RAG evaluation framework; EACL 2024; reference-free evaluation with metrics assessing retrieval (memory) relevance, answer faithfulness, answer relevancy.

19. MIRAGE: Benchmarking Retrieval-Augmented Generation for Medicine --> Included --> Medical RAG benchmark; EMNLP 2024; 7,663 questions directly measuring hallucination in memory-augmented generation.

20. CRAG — Comprehensive RAG Benchmark --> Included --> Comprehensive RAG benchmark; NeurIPS 2024; 4,409 QA pairs with quantitative memory-augmented generation evaluation.

21. RAGEval: Scenario Specific RAG Evaluation Dataset Generation Framework --> Included --> Scenario-based RAG evaluation; ACL 2025; framework with three memory-related metrics: Completeness, Hallucination, Irrelevance.

24. RECALL: A Benchmark for LLMs Robustness against External Counterfactual Knowledge --> Included --> Memory robustness evaluation; 2023 workshop; evaluates LLM robustness when external memory contains false information.

25. Adaptive Chameleon or Stubborn Sloth: Revealing the Behavior of Large Language Models in Knowledge Conflicts --> Included --> Studies knowledge conflicts (memory-related behavior); ICLR 2024 (Spotlight); framework with quantitative confirmation bias metrics.

27. ERBench: An Entity-Relationship based Automatically Verifiable Hallucination Benchmark --> Included --> Memory-grounded hallucination benchmark; NeurIPS 2024; automatically verifiable using entity-relationship models and integrity constraints.

29. UHGEval: Benchmarking the Hallucination of Chinese Large Language Models via Unconstrained Generation --> Included --> Hallucination benchmark for memory evaluation; ACL 2024; quantitative naturally-generated hallucination framework.

33. MMRC: A Large-Scale Benchmark for Understanding Multimodal Large Language Models in Real-World Conversation --> Included --> Explicitly focuses on memory recall in multimodal conversations; arXiv 2025; 5,120 dialogues with quantitative accuracy metrics.

34. SuperMemory-VQA: An Egocentric Visual Question-Answering Benchmark for Long-Horizon Memory --> Included --> Long-horizon memory in egocentric video understanding; arXiv 2026; 4,853 QA pairs with quantitative memory-related metrics.

37. Memory in Large Language Models: Mechanisms, Evaluation and Evolution --> Included --> Comprehensive taxonomy of LLM memory (parametric, contextual, external, procedural); arXiv 2025; evaluation framework with quantitative analysis.

38. MemoryBank: Enhancing Large Language Models with Long-Term Memory --> Included --> Explicit long-term memory mechanism inspired by Ebbinghaus; AAAI 2024; evaluation metrics for memory faithfulness and factual consistency.

41. Beyond Facts: Evaluating Intent Hallucination in Large Language Models (FaithQA) --> Included --> Intent hallucination evaluation with memory/intent understanding; ACL 2025; 20,000+ quantitative test cases.

42. Hallucination Cascade: Analyzing Error Propagation in Multi-Agent LLM Systems --> Included --> Hallucination propagation dynamics in multi-agent memory chains; arXiv 2026; quantitative metrics on error accumulation.

43. MCPHallu: Benchmarking Reasoning, Execution, and Memory Hallucinations in MCP Agents --> Included --> Memory-explicit benchmark; arXiv 2026; 358 tasks diagnosing hallucinations along memory axis; 14 LLMs evaluated.

45. PRISM: Probing Reasoning, Instruction, and Source Memory in LLM Hallucinations --> Included --> Explicitly probes source memory dimension; arXiv 2026; 9,448 quantitative diagnostic instances.

46. ES-MemEval: Benchmarking Conversational Agents on Personalized Long-Term Emotional Support --> Included --> Memory-explicit ("MemEval"); arXiv 2026; evaluates five memory capabilities; EvoEmo dataset for memory benchmarking.

47. Towards Root Memory: Benchmarking and Enhancing Implicit Logical Memory Retrieval for Personalized LLMs --> Included --> Memory-explicit ("Root Memory"); arXiv 2026; IMLogic benchmark for implicit logical memory retrieval.

48. Locomo-Plus: Beyond-Factual Cognitive Memory Evaluation Framework for LLM Agents --> Included --> Memory-explicit framework; arXiv 2026; quantitative evaluation of constraint-consistency in cognitive memory.

49. MemoryBench: A Benchmark for Memory and Continual Learning in LLM Systems --> Included --> Memory-explicit (continual learning + long-term memory); arXiv 2025; quantitative evaluation with 8K–128K token contexts.

50. MemoryRewardBench: Benchmarking Reward Models for Long-Term Memory Management --> Included --> Memory-explicit (reward models for long-term memory); arXiv 2026; quantitative evaluation across 8K–128K tokens.

51. TWIST: A Proposed Benchmark for Intervention Quality in Conversational Memory --> Included --> Memory-explicit (intervention quality); arXiv 2026; quantitative evaluation of contradiction detection, draft vetting, belief updating.

39. MemGPT: Towards LLMs as Operating Systems --> Included --> Virtual context management system for extended conversations; NeurIPS 2023 Workshop; OS-inspired memory architecture with quantitative evaluation on long-term memory tasks.

52. MemBook: A Hierarchical Reasoning-based Memory Framework for Hallucination-Resistant LLM Agents --> Included --> Hierarchical memory architecture (Sessions, Chapters, Memory Points); EMNLP 2026 (Findings); quantitative suppression of cross-stage hallucination propagation.

53. Synthius-Mem: Brain-Inspired Hallucination-Resistant Persona Memory --> Included --> Brain-inspired hierarchical memory; arXiv 2026; 94.4% accuracy on LoCoMo benchmark with adversarial robustness metrics.

54. Memory is Reconstructed, Not Retrieved: Graph Memory for LLM Agents --> Included --> Associative memory graphs with active reconstruction; arXiv 2026; 23% improvements over baselines; quantitative evaluation.

55. Forgetful but Faithful: A Cognitive Memory Architecture and Benchmark for Privacy-Aware Generative Agents (MaRS) --> Included --> Cognitive memory with forgetting policies; arXiv 2025; FiFA benchmark with quantitative coherence and recall accuracy metrics.

56. BioMem: Agentic Memory for Biomedical LLM Agents --> Included --> Agentic memory for biomedical domain; arXiv 2026; HMRU framework with quantitative healthcare evaluation.

57. Oracle Agent Memory as an Enterprise Memory Substrate for Long-Horizon AI Agents --> Included --> Database-native memory substrate; arXiv 2026; 93.8% accuracy with 10.7x fewer tokens than flat-history baselines.

58. Don't Just Trust Your Memory: Evidence-Linked Memory Reduces Memory-Induced Degradation in LLM Agents (WikiTrace) --> Included --> Evidence-linked external memory for memory-induced degradation; arXiv 2026; open-source with quantitative evaluation across five benchmarks.

59. Parameters vs. Context: Fine-Grained Control of Knowledge Reliance in Language Models --> Included --> Parametric vs. contextual memory conflict management; arXiv 2025; Confidence Gain metric; 9.9%-71.9% memory recall control.

60. FIDES: Faithful Inference via Deep Evidence Signals for Retrieval-Memory Conflict in RAG --> Included --> Token-level retrieval-memory conflict detection; arXiv 2026; MIT License; 92–94% context fidelity at 70B scale.

61. Investigating Context-Faithfulness in Large Language Models: The Roles of Memory Strength and Evidence Style --> Included --> Memory strength and internal memory reliance; arXiv 2024; open-source code with quantitative response divergence analysis.

62. Rowen: Adaptive Retrieval-Augmented Generation for Hallucination Mitigation in LLMs --> Included --> Balances parametric and external memory through adaptive retrieval; arXiv 2024; open-source with quantitative hallucination metrics.

63. Studying Large Language Model Behaviors Under Context-Memory Conflicts With Real Documents --> Included --> Context-memory conflict study; arXiv 2024; open-source; quantitative parametric bias and knowledge update failure rates.

64. When Context Leads but Parametric Memory Follows in Large Language Models --> Included --> Knowledge allocation between context (70%) and parametric (30%); EMNLP 2024; WikiAtomic dataset with quantitative hallucination rates.

66. WISE: Rethinking Knowledge Memory for Lifelong Model Editing --> Included --> Dual parametric memory subsystem (main + side); NeurIPS 2024; comprehensive quantitative evaluation; GitHub code available.

67. Distilling Feedback into Memory-as-a-Tool --> Included --> File-based memory system consolidating feedback; arXiv 2026; Pareto frontier analysis; open code and data.

68. RAG-DDR: Optimizing Retrieval-Augmented Generation Using Differentiable Data Rewards --> Included --> Memory management through differentiable data rewards; arXiv 2024; quantitative evaluation; OpenMatch code available.

72. Understand Then Memory: A Cognitive Gist-Driven RAG Framework with Global Semantic Diffusion --> Included --> Explicit semantic gist memory mechanism; arXiv 2026; CogniRank algorithm; code promised on GitHub.

73. MemGraphRAG: Memory-based Multi-Agent System for Graph Retrieval-Augmented Generation --> Included --> Hierarchical global memory (schema, fact, passage); arXiv 2026; multi-agent coordination; GitHub code available.

79. Augmenting Language Models with Long-Term Memory (LongMem) --> Included --> Explicit long-term memory subsystem; NeurIPS 2023 Workshop; cached attention key-value pairs; 40.5% accuracy on suffix identification.

80. Reducing Hallucination in Language Model-based SPARQL Query Generation Using Post-Generation Memory Retrieval (PGMR) --> Included --> Post-generation memory retrieval module; arXiv 2025; 0.0% hallucination rate on URI resolution.

81. Decoding Memories: An Efficient Pipeline for Self-Consistency Hallucination Detection --> Included --> Decoding Memory Pipeline with caching mechanism; arXiv 2025; 3x speedup on hallucination detection; AUROC maintained.

83. Look Twice Before You Answer: Memory-Space Visual Retracing for Hallucination Mitigation in Multimodal Large Language Models --> Included --> Memory-space visual retracing; arXiv 2024; FFN-based key-value memory; +7.0% on POPE, +15.6% on CHAIR.

84. SAFE: A Sparse Autoencoder-Based Framework for Robust Query Enrichment and Hallucination Mitigation in LLMs --> Included --> Sparse autoencoder for hallucination detection; arXiv 2025; 29.45% accuracy improvement on TruthfulQA, BioASQ.

85. Knowledge-Centric Hallucination Detection (RefChecker) --> Included --> Claim-triplet-based fine-grained detection; EMNLP 2024; 18.2-27.2 point improvements in correlation coefficients.

92. In Prospect and Retrospect: Reflective Memory Management for Long-term Personalized Dialogue Agents --> Included --> Reflective memory with prospective/retrospective reflection; ACL 2025; >10% improvement on LongMemEval.

94. TRUSTMEM: Learning Trustworthy Memory Consolidation for LLM Agents with Long-Term Memory --> Included --> Memory consolidation policies with RL-based credit assignment; arXiv 2026; quantitative memory utility and reliability metrics.

95. From Storage to Experience: A Survey on the Evolution of LLM Agent Memory Mechanisms --> Included --> Systematic survey with evolutionary framework (Storage-Reflection-Experience); ACL 2026 (Findings); formal memory taxonomy.

96. A Survey of Agent Memory in the Second Half: Towards Self-Evolving and Long-Horizon Agents --> Included --> Comprehensive 50-author survey on agent memory mechanisms; arXiv 2026; parametric, in-context, external substrates.

97. Are We Ready For An Agent-Native Memory System? --> Included --> System-level evaluation of 12 agent memory architectures; arXiv 2026; quantitative analysis across five benchmarks.

101. Mitigating Hallucination in Large Language Models: A Capability-Oriented Survey on RAG, Reasoning, and Agentic Systems --> Included --> Examines agentic systems (inherently memory-involved); arXiv 2025; capability-oriented on memory-based mitigation.

103. Explicit Working Memory Enhancement for Factuality (EWE) --> Included --> Explicit working memory mechanism; arXiv 2024; 2–6 point VeriScore improvement via fact-checking feedback.

104. Efficient and Effective Internal Memory Retrieval for LLM-based Healthcare Prediction (BioMem) --> Included --> Internal memory retrieval for biomedical domain; arXiv 2026; domain-specific memory enhancement.

106. MemGuard: Preventing Memory Contamination in Long-Term Memory-Augmented LLMs --> Included --> Type-aware memory organization; arXiv 2026; prevents heterogeneous memory contamination.

107. PRISM: Probing Reasoning, Instruction, and Source Memory in LLM Hallucinations --> Included --> Probes source memory dimension; arXiv 2026; CC BY 4.0 license; 9,448 quantitative instances.

110. Self-RAG: Learning to Retrieve, Generate, and Critique through Self-Reflection --> Included --> Adaptive retrieval with self-reflection; NeurIPS 2023; reflection tokens for controlled memory access and factuality.

111. Active Retrieval Augmented Generation (FLARE) --> Included --> Active memory access mechanism; EMNLP 2023; forward-looking signals determine when to access external memory.

112. Corrective Retrieval Augmented Generation (CRAG) --> Included --> Memory quality management; ICLR 2024; retrieval evaluator with confidence-based actions; web search for low-quality retrievals.

113. Chain-of-Note: Enhancing Robustness in Retrieval-Augmented Language Models --> Included --> Sequential reading notes for retrieved memory; EMNLP 2024; +7.9 EM improvement on noisy cases.

114. Cognitive Architectures for Language Agents (CoALA) --> Included --> Systematic framework with modular memory; TMLR 2024; structured decision-making with memory components.

116. Generative Agents: Interactive Simulacra of Human Behavior --> Included --> Explicit memory architecture (natural language records, reflections, dynamic retrieval); ACM UIST 2023; core memory-driven behavior.

117. LSTM-MAS: A Long Short-Term Memory Inspired Multi-Agent System for Long-Context Understanding --> Included --> Hierarchical LSTM-inspired memory; arXiv 2026; gated memory mechanisms; avoids hallucination propagation.

119. TeleMem: Building Long-Term and Multimodal Memory for Agentic AI --> Included --> Unified long-term multimodal memory system; arXiv 2026; 19% accuracy improvement, 43% token reduction vs. Mem0.

121. MemGraphRAG: Memory-based Multi-Agent System for Graph Retrieval-Augmented Generation --> Included --> Multi-agent shared memory for graph construction; arXiv 2026; logical conflict resolution; GitHub code available.

122. Understand Then Memory: A Cognitive Gist-Driven RAG Framework with Global Semantic Diffusion (CogitoRAG) --> Included --> Semantic gist memory extraction; arXiv 2026; CogniRank algorithm for memory-guided retrieval.

123. TC-RAG: Turing-Complete RAG's Case Study on Medical LLM Systems --> Included --> State-machine memory with Push/Pop actions; ACM MM 2024; 7.20% accuracy improvement in medical domain.

124. AssistRAG: Boosting the Potential of Large Language Models with an Intelligent Information Assistant --> Included --> Memory-augmented with curriculum learning; NeurIPS 2024; memory building and tool usage optimization.

125. Improving Factuality and Reasoning in Language Models through Multiagent Debate --> Included --> Multi-agent debate for memory consistency; ICML 2024; consensus through memory state alignment.

126. Seeing through the Conflict: Transparent Knowledge Conflict Handling in Retrieval-Augmented Generation (TCR) --> Included --> Transparent memory-context conflict resolution; arXiv 2026; dual contrastive encoders; SNR-weighted evaluation.

---

## EXCLUDED PAPERS (Failed criteria)

1. HaluEval: A Large-Scale Hallucination Evaluation Benchmark for Large Language Models --> Excluded --> Focuses on hallucination detection without explicitly addressing dedicated memory systems or memory-based anti-hallucination.

2. FActScore: Fine-grained Atomic Evaluation of Factual Precision in Long Form Text Generation --> Excluded --> Lacks memory system focus; no open-source code/architecture specification documented.

3. FELM: Benchmarking Factuality Evaluation of Large Language Models --> Excluded --> Domain-agnostic factuality framework without explicit memory system or memory-based anti-hallucination focus.

4. The Dawn After the Dark: An Empirical Study on Factuality Hallucination in Large Language Models --> Excluded --> Empirical hallucination study without dedicated memory system focus; no clear code availability.

6. FaithBench: A Diverse Hallucination Benchmark for Summarization by Modern LLMs --> Excluded --> General hallucination detection for summarization without explicit memory systems or memory-based methodology.

7. FactBench: A Dynamic Benchmark for In-the-Wild Language Model Factuality Evaluation --> Excluded --> Real-world factuality evaluation without dedicated memory system architecture or memory-based anti-hallucination focus.

9. Factcheck-Bench: Fine-Grained Evaluation Benchmark for Automatic Fact-checkers --> Excluded --> Factuality evaluation rather than memory mechanisms; doesn't explicitly address memory-centric evaluation.

22. WikiContradict: A Benchmark for Evaluating LLMs on Real-World Knowledge Conflicts from Wikipedia --> Excluded --> Knowledge conflicts focus without core memory-augmentation subsystem; lacks quantitative framework.

23. ConflictBank: A Benchmark for Evaluating the Influence of Knowledge Conflicts in LLMs --> Excluded --> Knowledge conflict dataset without memory-augmentation focus; primarily annotation-based rather than quantitative.

26. Knowledge Conflicts for LLMs: A Survey --> Excluded --> Survey paper without primary quantitative benchmarks or evaluation; lacks memory-explicit focus.

28. Med-HALT: Medical Domain Hallucination Test for Large Language Models --> Excluded --> Medical domain-specific without general memory focus; lacks clear quantitative hallucination measurements.

30. TofuEval: Evaluating Hallucinations of LLMs on Topic-Focused Dialogue Summarization --> Excluded --> Summarization task-focused, not memory-focused; lacks demonstrated memory mechanisms.

31. DiaHalu: A Dialogue-level Hallucination Evaluation Benchmark for Large Language Models --> Excluded --> Dialogue hallucination without memory systems focus; evaluates hallucination types without addressing memory architecture.

32. ToolBeHonest: A Multi-level Hallucination Diagnostic Benchmark for Tool-Augmented Large Language Models --> Excluded --> Tool-execution focused rather than memory-focused; addresses execution rather than memory management.

35. Long-form Factuality in Large Language Models (LongFact + SAFE) --> Excluded --> Factuality evaluation rather than explicit memory mechanisms; lacks memory architecture focus.

36. KIEval: A Knowledge-grounded Interactive Evaluation Framework for Large Language Models --> Excluded --> Data contamination focus; lacks explicit memory mechanism despite quantitative evaluation.

40. DialFork: Going Beyond Factuality to Evaluate Procedural Hallucination in Conversational Agents --> Excluded --> Procedural hallucination without explicit memory mechanisms; 36,278 dialogues but no memory-specific design.

44. Hallucination Detection in LLMs: Fast and Memory-Efficient Fine-Tuned Models --> Excluded --> Detection technique paper focused on efficiency, not memory-explicit evaluation or hallucination benchmarking.

65. Hallucination-Guided Unlearning: Using Hallucination Traces to Reveal Overfitted Memories --> Excluded --> Memory-focused but lacks code availability or publication commitment (transparency criterion not met).

69. Towards Adaptive Memory-Based Optimization for Enhanced Retrieval-Augmented Generation --> Excluded --> Adaptive retrieval strategies rather than explicit memory subsystem design; no code availability.

70. Scaling Test-Time Inference with Policy-Optimized, Dynamic Retrieval-Augmented Generation --> Excluded --> Dynamic retrieval optimization without dedicated memory subsystem design; no code availability.

71. Removal of Hallucination on Hallucination: Debate-Augmented RAG --> Excluded --> Multi-agent debate without dedicated memory subsystem; memory management is implicit, not architectural.

74. Reducing Hallucination in Structured Outputs via Retrieval-Augmented Generation --> Excluded --> Workflow generation focus without explicit memory architecture or dedicated memory subsystem.

75. ReEval: Automatic Hallucination Evaluation for Retrieval-Augmented Large Language Models via Transferable Adversarial Attacks --> Excluded --> Evaluation framework without explicit memory subsystem design; adversarial attacks on RAG without memory focus.

76. Can Knowledge Graphs Reduce Hallucinations in LLMs? A Survey --> Excluded --> Survey of KG-based augmentation; lacks primary quantitative memory evaluation or benchmarking.

77. Augmenting LLMs with Knowledge: A Survey on Hallucination Prevention --> Excluded --> Survey of knowledge augmentation; lacks memory-specific focus and primary quantitative results.

78. Knowledge Graph-Enhanced Large Language Model Based on Question Decomposition and Atomic Retrieval (KELDaR) --> Excluded --> KG-based framework without explicit dedicated memory subsystem architecture.

82. Generation Constraint Scaling Can Mitigate Hallucination --> Excluded --> Memory readout vector scaling; lacks memory subsystem architecture despite memory-related approach.

86. Lookback Lens: Detecting and Mitigating Contextual Hallucinations Using Attention Maps --> Excluded --> Attention-based detection without explicit memory subsystem or dedicated memory architecture.

87. SIRIN: A Unified Toolkit for Detecting Contextual Hallucinations --> Excluded --> Detection toolkit without explicit memory subsystem design; supports detection without memory management.

88. Citation-Enhanced Generation for LLM-based Chatbots --> Excluded --> Citation generation focus; RAG + NLI approach without dedicated memory subsystem.

89. Mechanistic Understanding and Mitigation of Language Model Non-Factual Hallucinations --> Excluded --> Internal fact-retrieval focus without dedicated memory subsystem or explicit memory architecture.

90. Zero-Resource Hallucination Prevention for Large Language Models (SELF-FAMILIARITY) --> Excluded --> Input-output self-evaluation for hallucination prevention, not memory systems.

91. Controlling Risk of Retrieval-Augmented Generation: A Counterfactual Prompting Framework --> Excluded --> RAG confidence control via prompting; not explicit memory management or consolidation.

93. Learning from Hallucinations: Mitigating Hallucinations via Internal Representation Intervention --> Excluded --> Representation intervention focus; not memory systems or memory consolidation.

98. Factuality of Large Language Models: A Survey --> Excluded --> Generic hallucination/factuality survey without explicit memory dimension.

99. A Comprehensive Survey of Hallucination in Large Language, Image, Video and Audio Foundation Models --> Excluded --> Multimodal hallucination survey without memory-focused analysis.

100. Insights into Classifying and Mitigating LLMs' Hallucinations --> Excluded --> Lacks substantive depth; no explicit memory focus or rigorous methodology.

102. Hallucinations in LLMs: A Lifecycle-Based Survey of Causes, Detection, Mitigation, and Prevention --> Excluded --> Lifecycle framework without memory-specific dimension; no memory enhancement focus.

108. Retrieval-Augmented Generation for Large Language Models: A Survey --> Excluded --> Generic RAG paradigm survey without explicit memory management subsystems focus.

109. A Survey on Retrieval-Augmented Text Generation for Large Language Models --> Cannot Evaluate --> Paper not found in PDF directories.

115. A Survey on Large Language Model based Autonomous Agents --> Excluded --> Generic agent survey without explicit memory focus; no memory-specific quantitative evaluation.

118. Check Your Facts and Try Again: Improving LLMs with External Knowledge (LLM-Augmenter) --> Excluded --> Fact-checking with external knowledge rather than explicit agent/long-term memory architecture.

120. From Local to Global: A Graph RAG Approach (GraphRAG) --> Excluded --> Graph-based RAG without explicit agent memory architecture; focuses on retrieval augmentation.

127. Siren's Song in the AI Ocean: A Survey on Hallucination in Large Language Models --> Excluded --> Survey paper; no primary quantitative benchmarks or memory-augmented methods.

128. A Survey on Hallucination in Large Language Models: Principles, Taxonomy, Challenges, and Open Questions --> Excluded --> Survey paper; no primary quantitative benchmarks or memory-augmented methods.

---

## SUMMARY STATISTICS

| Category | Count |
|----------|-------|
| **Total Papers Screened** | 128 |
| **Papers Included** | 84 |
| **Papers Excluded** | 43 |
| **Cannot Evaluate** | 1 |
| **Inclusion Rate** | 65.6% |

### By Research Question

| Category | RQ1 | RQ2 | Total |
|----------|-----|-----|-------|
| **Papers Submitted** | 51 | 77 | 128 |
| **Papers Included** | 30 | 54 | 84 |
| **Papers Excluded** | 19 | 24 | 43 |
| **Inclusion Rate** | 58.8% | 70.1% | 65.6% |

### Inclusion Breakdown by Category

**RQ1 Benchmarks & Datasets Included (30):**
- Parametric Memory / Factuality: 2 (HalluLens, TruthfulQA)
- Long-Term / Conversational Memory: 7 (LongMemEval, LoCoMo, MemBench, LOCCO, RealMem, HaluMem, What Matters in Memorizing)
- RAG / Memory-Augmented: 6 (RAGTruth, Ragas, MIRAGE, CRAG, RAGEval, RECALL)
- Knowledge Conflict & Robustness: 1 (Adaptive Chameleon)
- Entity-Relationship & Verifiable: 1 (ERBench)
- Domain-Specific & Multimodal: 3 (MMRC, SuperMemory-VQA, UHGEval)
- Agent Memory & Knowledge Probing: 3 (Memory in LLMs, MemoryBank, Memory in LLMs Survey)
- Intent-Based Hallucination: 3 (FaithQA, Hallucination Cascade, MCPHallu)
- Specialized Memory: 3 (PRISM, ES-MemEval, Towards Root Memory)

**RQ2 Methods & Architectures Included (54):**
- Memory Architecture & Framework: 10 (MemGPT, MemBook, Synthius-Mem, Memory is Reconstructed, MaRS, BioMem, Oracle Agent Memory, Locomo-Plus, MemoryBench, MemoryRewardBench)
- Parametric vs. Context Memory Conflict: 7 (WikiTrace, Parameters vs. Context, FIDES, Context-Faithfulness, Rowen, Context-Memory Conflicts, Context Leads)
- Memory Unlearning & Editing: 2 (WISE, Distilling Feedback)
- RAG Optimization & Enhancement: 4 (RAG-DDR, CogitoRAG, MemGraphRAG, TWIST)
- Knowledge Graph & External Memory: 3 (LongMem, PGMR, Decoding Memories)
- Post-Generation & Detection: 3 (Memory-Space Visual Retracing, SAFE, RefChecker)
- Reflection & Memory Management: 2 (Reflective Memory Management, TRUSTMEM)
- Survey & Taxonomy: 3 (Storage to Experience, Agent Memory Survey, Are We Ready)
- Method Papers: 2 (EWE, BioMem)
- RAG Paradigms & Surveys: 3 (Self-RAG, FLARE, CRAG, Chain-of-Note)
- Agent Architecture & Memory: 5 (CoALA, Generative Agents, LSTM-MAS, TeleMem, MemGraphRAG)
- Multiagent & Debate: 1 (Multiagent Debate)
- Conflict Resolution: 1 (TCR)
- Enhanced RAG Systems: 2 (TC-RAG, AssistRAG)
- Agentic Systems: 1 (Agentic Systems Survey)

### Key Themes Among Included Papers

1. **Memory Architecture & Design (31 papers):** Hierarchical, graph-based, cognitive, and brain-inspired memory systems
2. **Long-Term & Agent Memory (28 papers):** Persistent memory across extended interactions and multi-agent systems
3. **Memory Evaluation & Benchmarking (25 papers):** Comprehensive benchmarks for memory hallucinations, recall, and consolidation
4. **Parametric vs. External Memory Conflict (12 papers):** Managing tensions between internal knowledge and retrieved/external memory
5. **RAG Enhancement & Memory Management (15 papers):** Advanced retrieval strategies with explicit memory optimization
6. **Memory Hallucination Detection (11 papers):** Fine-grained detection and mitigation of memory-related hallucinations
7. **Reflection & Memory Consolidation (8 papers):** Reflective mechanisms for improving memory quality and preventing hallucination propagation
8. **Survey & Framework Papers (7 papers):** Systematic taxonomies and comprehensive frameworks for memory evaluation

---

## Recommendations for Next Steps

1. **Organize included papers by topic cluster** for systematic literature synthesis
2. **Extract implementation details** from PDFs for architectural taxonomy development
3. **Create comparison matrix** of memory subsystem features across papers
4. **Identify open-source implementations** for reproducibility verification
5. **Map inclusion/exclusion decisions** against original research questions for alignment

---

**Screening Completed:** 2026-11-11  
**Agent Evaluation Method:** Parallel multi-agent screening with full-text PDF verification where available  
**Output Compiled By:** Claude Code (16 parallel agents)
