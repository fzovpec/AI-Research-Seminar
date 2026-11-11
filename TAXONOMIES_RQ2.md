# Method Taxonomy: RQ2
## What memory-based architectures and methods reduce hallucination in LLMs, and how can they be taxonomized?

**Date:** 2026-11-11  
**Scope:** ~46 included RQ2 papers, organized into 4 thematic categories + surveys  
**Note:** Papers involving non-textual modalities (MemVR, TeleMem) are flagged below — consistent with RQ1 scope restriction.

---

## Overview

Across the included methods, four distinct strategies emerge for using memory to suppress hallucination. The key structural distinction is *which type of memory* the method intervenes on: the model's internal parametric weights, an external structured memory store, the access pathway between them, or the ongoing maintenance of memory quality over time.

---

## Category 1: Parametric Memory Control

**Core strategy:** Directly modify, probe, or govern what the model retains in its own weights — the implicit knowledge baked in during training.

This is the most fundamental intervention layer. Rather than adding external memory, these methods operate on the model's internal knowledge representation — either editing it, suppressing incorrect entries, constraining how it surfaces at generation time, or studying its failure mechanics.

| Paper | Mechanism | Anti-Hallucination Contribution |
|-------|-----------|----------------------------------|
| **WISE** | Dual parametric memory: main weights + side memory for edits | Prevents knowledge conflicts from corrupting primary parametric memory |
| **Hallucination-Guided Unlearning** | Uses hallucination traces to identify overfitted memories; sparse MLP edits | Removes the specific parametric entries that cause systematic hallucinations |
| **Parameters vs. Context** | Fine-grained control over when model relies on parametric vs. context memory | Reduces hallucination under knowledge conflict by explicit reliance arbitration |
| **Generation Constraint Scaling** | Scales memory readout vectors at inference to constrain generation | Training-free; steers output toward factual content already encoded in weights |
| **Mechanistic Understanding of Non-Factual Hallucinations** | Identifies two distinct failure modes in parametric memory; restores internal fact-retrieval | Provides mechanistic diagnosis + targeted fix rather than blanket suppression |
| **SAFE** | Sparse Autoencoder probes model internals; enriches queries via identified features | Surfaces latent parametric knowledge to reduce generation that conflicts with weights |
| **Investigating Context-Faithfulness** | Quantifies "memory strength" via response divergence across evidence conditions | Diagnostic: maps which questions trigger parametric override of external evidence |
| **When Context Leads but Parametric Memory Follows** | Measures context vs. parametric allocation (~70%/30%) across question types | Empirical grounding for understanding when parametric dominance causes hallucination |
| **EWE (Explicit Working Memory Enhancement)** | Integrates real-time working memory refreshed via fact-checking and retrieval feedback | Explicitly maintains a refreshable working memory buffer alongside parametric generation |
| **Decoding Memories** | Decoding Memory Pipeline caching multiple generations for self-consistency check | Treats redundancy in multi-response sampling as a memory consistency signal |

**Shared design pattern:** These methods treat hallucination as a symptom of parametric memory malfunction — either stale knowledge, overfitted associations, or failure to suppress internal priors when external evidence contradicts them.

---

## Category 2: Dedicated Memory Architecture

**Core strategy:** Design an explicit, structured memory system external to model weights — with its own storage format, retrieval logic, and lifecycle.

Rather than relying on the model's internal knowledge, these papers build memory as a first-class system component. The memory store is inspectable, updatable, and architecturally separate from the generation mechanism.

| Paper | Architecture Type | Anti-Hallucination Contribution |
|-------|------------------|----------------------------------|
| **MemGPT** | OS-inspired virtual context with paged memory tiers | Prevents long-context hallucination by explicitly managing what stays in active context |
| **MemBook** | Hierarchical time-aware store: Sessions → Chapters → Memory Points | Hierarchical retrieval suppresses cross-stage hallucination propagation |
| **Synthius-Mem** | Brain-inspired memory across six cognitive domains | 94.4% on LoCoMo; adversarial robustness shows structured domains resist noise injection |
| **Memory is Reconstructed, Not Retrieved** | Associative memory graphs; active reconstruction at retrieval time | Reconstruction from graph connections reduces hallucination from imprecise retrieval |
| **MaRS** | Cognitive memory with six forgetting policies (FiFA benchmark) | Selective forgetting prevents stale memories from causing factual inconsistency |
| **BioMem (Agentic)** | HMRU: Hierarchical Memory Retrieval and Utilization for biomedical domain | Domain-specific structure reduces out-of-domain hallucination in clinical QA |
| **Oracle Agent Memory** | Database-native memory substrate with structured schemas | 93.8% accuracy; structured indexing reduces hallucination from unstructured flat history |
| **Generative Agents** | Natural language memory records + synthesized reflections + dynamic retrieval | Memory reflection and retrieval pipeline grounds agent behavior in stored experience |
| **LSTM-MAS** | LSTM-inspired gated memory across worker/filter/judge/manager agents | Gated memory prevents error accumulation and hallucination propagation across agent chain |
| **LongMem** | Cached attention key-value pairs as persistent long-term memory | Extends faithful retrieval beyond context window without hallucinating from truncated history |
| **Efficient Internal Memory Retrieval (BioMem)** | Internal memory retrieval via parametric knowledge grounding in clinical settings | Reduces hallucination by anchoring generation to retrieved parametric knowledge |
| **The Memory Trap** | Empirical study of benign interaction memories causing overgeneralization | Diagnostic: identifies when stored memories become a hallucination *source* rather than fix |

> ⚠️ **TeleMem** ("Building Long-Term and Multimodal Memory for Agentic AI") is included in screening but involves multimodal memory components — flag for exclusion if scope is restricted to text-only systems.

**Shared design pattern:** Hallucination is treated as a retrieval or storage problem. The fix is an explicit, structured memory system that makes memory inspectable and separates storage from generation.

---

## Category 3: Retrieval & Access Management

**Core strategy:** Control *when*, *what*, and *how* external memory is retrieved during generation — rather than modifying what is stored.

These methods take the memory store as given and optimize the access layer: deciding when retrieval is needed, what to retrieve, how to rank it, and how to integrate it into generation without distortion.

| Paper | Access Strategy | Anti-Hallucination Contribution |
|-------|----------------|----------------------------------|
| **Self-RAG** | Reflection tokens govern when to retrieve and how to weight retrieved passages | Adaptive memory access; avoids both over- and under-retrieval via self-critique |
| **FLARE** | Predicts upcoming low-confidence tokens as trigger for proactive retrieval | Retrieves exactly when parametric memory is likely to fail — forward-looking signal |
| **CRAG (Corrective RAG)** | Lightweight retrieval evaluator with confidence-based corrective actions | Prevents hallucination from low-quality retrievals by triggering fallback to web search |
| **Rowen** | Dynamic balance between parametric and external memory via adaptive retrieval activation | Decides per-query whether to activate external memory or rely on parametric knowledge |
| **FIDES** | Training-free decoder identifies token-level retrieval-memory conflicts | 92–94% context fidelity at 70B scale; resolves conflicts at the decoding level |
| **CogitoRAG** | Semantic "gist" extraction before storage; CogniRank algorithm for reranking | Memory is indexed by meaning, not raw text — reduces hallucination from fragmented retrieval |
| **MemGraphRAG** | Multi-agent shared memory; graph construction with logical conflict resolution | Shared structured memory across agents reduces independent hallucination propagation |
| **TC-RAG** | Turing-Complete memory stack with Push/Pop actions for state management | State-variable memory prevents hallucination from inconsistent retrieval across turns |
| **AssistRAG** | Intelligent assistant managing memory via tool use, action execution, memory building | Explicit memory construction loop ensures generation is grounded in actively managed store |
| **PGMR** | Post-generation memory retrieval grounds generated output against structured knowledge | Verification step after generation; near-zero URI hallucination rate on LCQUAD 2.0 |
| **Adaptive Memory-Based Optimization** | Dynamically adjusts retrieval and memory management policies during generation | Memory management as a learnable policy, not a fixed pipeline |
| **KELDaR** | KG as external structured memory; question decomposition for atomic retrieval | Structured knowledge graph as memory reduces hallucination from unstructured free-form retrieval |
| **Seeing through the Conflict (TCR)** | Dual contrastive encoders for conflict detection; SNR-weighted soft-prompt | Explicitly surfaces and resolves parametric-retrieval conflicts during generation |
| **Studying LLM Behaviors Under Context-Memory Conflicts** | Real-document conflict taxonomy; parametric bias measurement | Diagnostic: maps which conflict types most reliably induce hallucination |

**Shared design pattern:** Hallucination is treated as a retrieval timing or quality problem. The fix is a smarter access layer that retrieves at the right moment, from the right source, with conflict detection.

---

## Category 4: Memory Maintenance & Quality Management

**Core strategy:** Ensure memory remains accurate, consistent, and coherent over time — preventing degradation, contamination, and overgeneralization from accumulated interactions.

These papers address the lifecycle problem: memory that was accurate when written can become stale, contradictory, or adversarially corrupted. The methods here focus on ongoing memory curation rather than one-shot retrieval.

| Paper | Maintenance Mechanism | Anti-Hallucination Contribution |
|-------|----------------------|----------------------------------|
| **In Prospect and Retrospect (Reflective Memory Management)** | Prospective summarization + retrospective RL-based refinement | Dual reflection loop actively corrects memory errors; >10% improvement on LongMemEval |
| **TRUSTMEM** | RL-based credit assignment for memory consolidation policies | Learns which memories to keep/discard to minimize hallucinated entries |
| **Distilling Feedback into Memory-as-a-Tool** | Converts transient critiques into persistent retrievable guidelines | Error feedback becomes a structured memory entry — prevents repeated hallucinations |
| **WikiTrace (Evidence-Linked Memory)** | Links each stored lesson to its originating trajectory as evidence | Memory entries carry provenance; hallucinated generalization caught via evidence mismatch |
| **MemGuard** | Type-aware memory organization; prevents heterogeneous memory contamination | Structural separation of memory types prevents cross-type factual inconsistency |
| **CoALA (Cognitive Architectures for Language Agents)** | Systematic framework with modular memory, structured action space | Provides principled architectural constraints that prevent ad-hoc memory misuse |

**Shared design pattern:** Hallucination is treated as a memory integrity problem. The fix is active curation — reflecting on what was stored, pruning contradictions, and linking memories to their evidence.

---

## Surveys & Taxonomies

These papers do not propose a single method but provide the conceptual frameworks within which the above methods can be positioned.

| Paper | Contribution |
|-------|-------------|
| **From Storage to Experience: A Survey on the Evolution of LLM Agent Memory Mechanisms** | Evolutionary taxonomy: Storage → Reflection → Experience; design principles for each stage |
| **A Survey of Agent Memory in the Second Half** | 50-author survey across parametric, in-context, external substrates; most comprehensive scope |
| **Are We Ready For An Agent-Native Memory System?** | Empirical study of 12 architectures across 5 benchmarks; reveals hallucination-prone configurations |

---

## Cross-Cutting Observations

**1. The intervention layer determines the tradeoff.** Parametric methods (Cat 1) are model-intrinsic and don't require runtime infrastructure but can't be updated without retraining. Architecture methods (Cat 2) are updatable but require external system management. The field hasn't converged on which layer should "own" anti-hallucination.

**2. Retrieval management (Cat 3) is the most populated category (~14 papers).** This reflects the dominance of RAG-based systems in deployment, but also a potential gap: retrieval management presupposes a memory store exists and is accurate — it doesn't address how to build or maintain that store.

**3. Memory maintenance (Cat 4) is the most underexplored relative to its importance.** Only 6 dedicated papers address the lifecycle problem, despite the fact that all other categories eventually depend on memory quality over time. TRUSTMEM and WikiTrace represent the leading edge.

**4. Parametric and external memory are increasingly treated as complementary rather than competing.** Papers like Parameters vs. Context, Rowen, and FIDES explicitly model the interaction between both types — a shift from earlier work that treated RAG as a replacement for parametric knowledge.

**5. Two papers require a scope decision:**
- **MemVR** (Look Twice Before You Answer) — memory-space *visual* retracing in MLLMs; non-textual modality
- **TeleMem** — explicitly long-term and *multimodal* memory; non-textual component

---

## Summary Table

| Category | # Papers | Core Strategy | Key Papers |
|----------|----------|---------------|------------|
| **1. Parametric Memory Control** | 10 | Modify/probe/govern internal model knowledge | WISE, Hallucination-Guided Unlearning, EWE |
| **2. Dedicated Memory Architecture** | 12 | Build explicit external memory systems | MemGPT, MemBook, Generative Agents |
| **3. Retrieval & Access Management** | 14 | Control when/how external memory is queried | Self-RAG, FLARE, CRAG, CogitoRAG |
| **4. Memory Maintenance & Quality** | 6 | Curate and correct memory over time | Reflective Memory Mgmt, TRUSTMEM, MemGuard |
| **Surveys / Frameworks** | 3 | Taxonomize the design space | From Storage to Experience |
| **Flagged (non-textual)** | 2 | Pending scope decision | MemVR, TeleMem |
| **Total (text-only)** | **45** | | |
