# Benchmark Taxonomy: RQ1
## How do existing benchmarks quantify hallucinations in LLM memory systems, and what specific memory failure modes do they evaluate?

**Date:** 2026-11-12
**Scope:** 21 included RQ1 benchmarks, organized into 3 thematic categories

---

## Overview

Across the included benchmarks, three distinct memory failure modes emerge. Each category reflects a structurally different way memory can break down in LLMs — from forgetting a training fact, to losing track of a conversation 300 turns ago, to misreading or misusing a retrieved document.

The three categories are **mutually exclusive on primary target**: a benchmark is placed in the category whose failure mode it was *designed* to isolate, not categories it touches tangentially. Where a benchmark spans multiple failure modes (e.g., PRISM's reasoning axis, Med-HALT's reasoning tests), we place it by its *memory-relevant* contribution and note the boundary explicitly.

---

## Category 1: Parametric Memory Recall Failures

**Core question:** Does the model correctly surface knowledge stored in its weights at training time?

**What distinguishes this category:** No external memory, no retrieved documents, no multi-session dialogue. The model is given a question and must answer from weights alone. Failure = the fact was in training data but didn't come out. These benchmarks probe the reliability of internal, implicit memory.

**What rules a benchmark OUT of this category:** If the failure requires external context to manifest (Cat 3), or if it requires extended temporal interaction to manifest (Cat 2), it doesn't belong here. A benchmark that only shows a failure in a conversation spanning multiple sessions is testing episodic degradation, not parametric recall.

| Paper | What They Measure | Key Signal |
|-------|-------------------|------------|
| **HalluLens** | Distinguishes *extrinsic* hallucinations (contradicting parametric memory) from *intrinsic* (contradicting given context) | Extrinsic rate = parametric memory failure |
| **What Matters in Memorizing and Recalling Facts** | Multi-angle probing of fact recall via BELIEF framework + MyriadLAMA | Accuracy under varied prompting reveals recall instability |
| **PRISM** | Disentangles four hallucination dimensions; KE and KM target parametric knowledge | KE/KM error rates isolate parametric failures from reasoning/instruction failures |
| **Med-HALT** | Explicitly includes *memory-based hallucination tests* alongside reasoning tests | Medical domain reveals factual gaps in specialist knowledge |

### Placement rationale

**HalluLens.** The paper's central distinction — extrinsic vs intrinsic hallucinations — explicitly maps extrinsic failures to parametric memory contradictions. Even though HalluLens also measures intrinsic (context-based) hallucinations, its original contribution and the dimension that motivates its inclusion is the extrinsic axis, which measures parametric failures directly. *Not Cat 3* because the extrinsic axis is designed to probe the weights alone — no retrieved content is required for the failure to manifest; the intrinsic axis exists as a complement, not as a retrieval-integration study.

**What Matters in Memorizing and Recalling Facts.** The BELIEF framework systematically probes whether facts encoded during training can be reliably recalled across paraphrased prompts. MyriadLAMA extends LAMA-style probing with multi-angle prompting. Both are pure parametric probes — no external evidence, no long-term interaction, no retrieval pipeline. This is the textbook Cat 1 benchmark.

**PRISM.** PRISM is a diagnostic benchmark with four orthogonal dimensions: Knowledge Error (KE), Knowledge Missing (KM), Reasoning Error (RE), and Instruction Following Error (IFE). The memory-relevant contribution is the KE/KM axis — the paper explicitly frames these as failures of parametric knowledge (model's weights contain incorrect or missing facts). *Partial fit, correctly placed in Cat 1* because the memory-dimension of the benchmark is strictly parametric; RE and IFE are reasoning and instruction failures that would not be measured by any Cat 2 or Cat 3 benchmark either. Noting the boundary: PRISM's reasoning and instruction dimensions fall outside our memory taxonomy entirely.

**Med-HALT.** The benchmark bundles memory-based tests with reasoning tests in a medical QA setting. The *memory-based test dimension* — which probes whether domain-specialist medical facts are reliably surfaced from weights — is why it qualifies for this review. *Not Cat 3* because the memory tests do not involve external medical records or retrieved documents; the model must answer from pre-trained medical knowledge. *Not Cat 2* because there is no extended dialogue or session structure; failures manifest in single-turn QA.

---

## Category 2: Long-Term Episodic Memory Failures

**Core question:** Can the model maintain coherent memory across many turns, sessions, or extended time periods?

**What distinguishes this category:** Failures only manifest over *time*. A model can pass the equivalent of a Cat 1 probe on these facts in isolation — it's the accumulation, forgetting, or cross-session retrieval that breaks. The core variable is temporal distance between information encoding and information use.

**What rules a benchmark OUT of this category:** If the benchmark tests single-turn QA (Cat 1), or if the "memory" is an external store retrieved via RAG rather than conversational history (Cat 3), it doesn't belong here. Long-term here means *conversational/interactional* memory: content the model was given, not content it looked up.

| Paper | What They Measure | Key Signal |
|-------|-------------------|------------|
| **LongMemEval** | Five core long-term memory abilities across sessions | 30% accuracy drop across sessions; identifies specific ability breakdowns |
| **LoCoMo** | 300-turn, 9K-token-avg conversations spanning up to 35 sessions | LLM performance vs. human recall across session boundaries |
| **MemBench** | Agent memory across effectiveness, efficiency, and capacity axes; factual vs. reflective memory | First benchmark distinguishing factual from reflective memory failure |
| **LOCCO** | Memory decay curves over time; memory preferences across information categories | Quantifies rate and pattern of episodic memory degradation |
| **RealMem** | 2,000+ cross-session dialogues grounded in realistic project scenarios | Agents fail at tracking long-term project state |
| **ES-MemEval** | Five memory capabilities in long-term emotional support contexts | Memory fragmentation and disclosure-tracking failures |
| **Locomo-Plus** | Cognitive memory beyond factual accuracy — constraint-consistency, timeline coherence | Surfaces qualitative failures standard QA accuracy misses |
| **MemoryBench** | Continual learning + long-term memory across 8K–128K token contexts | Memory–context-length scaling behavior |
| **Towards Root Memory** | Divergence between semantic and logical relevance in personalized LLM memory retrieval (IMLogic) | Retrieval succeeds by similarity but fails by logic — a failure mode invisible to embedding-based metrics |
| **MemoryRewardBench** | Whether reward models can correctly evaluate long-term memory management quality (8K–128K tokens) | Surfaces reward model blind spots in memory-quality scoring across extended contexts |
| **TWIST** | Intervention quality in conversational memory: contradiction detection, draft vetting, belief updating | Evaluates memory *correction* capabilities across long dialogues, not just retrieval |

### Placement rationale

**LongMemEval.** The canonical Cat 2 benchmark. Explicitly defines five long-term memory abilities (information extraction, multi-session reasoning, temporal reasoning, knowledge updates, abstention) and measures them across multi-session chat assistant interactions. The 30%+ accuracy drop across sessions is the field's most-cited quantitative anchor for long-term memory degradation.

**LoCoMo.** 300-turn conversations spanning up to 35 sessions with ~9K-token averages. Explicitly compares LLM recall to human recall across session boundaries. The benchmark exists precisely because these failures can't surface in short context benchmarks — they require temporal depth.

**MemBench.** Evaluates agent memory across effectiveness, efficiency, and capacity. *Not Cat 3-C* despite being agent-oriented, because MemBench tests what the agent *remembers* across extended interactions, not failures within specific memory CRUD operations. The "agent" framing is about operational context, not about pipeline-step failures.

**LOCCO.** Implants memory via supervised fine-tuning (parametric), then measures decay over time. A boundary case because the memory mechanism is parametric — but the *failure mode measured* is temporal decay of recently-encoded information, which is the Cat 2 criterion. *Not Cat 1* because Cat 1 benchmarks test pre-trained knowledge recall in isolation; LOCCO specifically tests how recently-fine-tuned information degrades over subsequent interactions.

**RealMem.** 2,000+ cross-session dialogues grounded in realistic project scenarios where agents must track long-term project state. Textbook Cat 2 — the failures emerge from cross-session tracking, not from parametric gaps or retrieval misintegration.

**ES-MemEval.** Five memory capabilities in long-term emotional support contexts (EvoEmo dataset). Specifically measures disclosure-tracking and fragmentation across extended emotional support dialogues. Domain-specific but the failure mode is pure Cat 2 — emotional context accumulates over sessions and must be coherently referenced.

**Locomo-Plus.** Extends LoCoMo with cognitive memory dimensions beyond factual QA: constraint-consistency, timeline coherence. Same long-term conversational substrate, different measurement dimensions. Correctly Cat 2.

**MemoryBench.** Continual learning + long-term memory across 8K–128K token contexts. The scaling axis (context length) is the memory variable — the benchmark surfaces how memory degrades as content accumulates. Clear Cat 2.

**Towards Root Memory.** The IMLogic benchmark tests personalized LLM memory retrieval where semantic similarity succeeds but logical relevance fails. *Borderline Cat 2 vs Cat 3*: the "retrieval" involves an external personalized memory store, which sounds Cat 3. But the memory being retrieved is *user-specific, accumulated-over-time personal context*, not a generic knowledge base — it's an episodic record of the user. The failure is about logical inference over personal memory, not about arbitrating with parametric knowledge or faithfulness to retrieved documents. Placed in Cat 2 because the memory substrate is episodic-personal rather than knowledge-base-external. This is the most contestable placement in the category.

**MemoryRewardBench.** Evaluates whether reward models can correctly score long-term memory management quality across 8K–128K token contexts. *Not Cat 3-C* despite being about memory management operations, because the benchmark measures *reward model evaluation accuracy*, not where in a memory pipeline hallucinations are introduced. The substrate is long-term memory; the probed object is the reward model's ability to score that memory's quality.

**TWIST.** Evaluates intervention quality in conversational memory: contradiction detection, draft vetting, belief updating across long dialogues. *Could arguably be Cat 3-C* since it's about memory operations — but TWIST's operations are specifically *conversational correction* operations over long-term dialogue memory, not generic CRUD operations on an external memory store. The temporal/conversational substrate makes Cat 2 the right home. Noted as a boundary case.

---

## Category 3: External Memory Integration Failures

**Core question:** When a model has access to retrieved or external content, does it integrate it correctly — and when that content conflicts with its parametric knowledge, does it arbitrate correctly?

**What distinguishes this category:** The benchmark explicitly introduces *external content* (retrieved documents, injected facts, counterfactual passages, memory store operations) and measures how the model handles the interaction between that external content and its own generation. The failure is about external-internal integration, not about single-source recall or temporal persistence.

**What rules a benchmark OUT of this category:** If the "memory" being tested is purely parametric (Cat 1) or purely conversational/episodic (Cat 2), it doesn't belong here. A benchmark that gives the model a long conversation is Cat 2; a benchmark that gives the model a retrieved document is Cat 3.

This category covers three related sub-failures that all stem from the same structural problem: the model must reconcile what it "knows" internally with what it has been given externally.

**Sub-type A — Memory–context conflict:** The model has valid parametric knowledge AND valid retrieved context, but they disagree. The right behavior depends on which source is more reliable, and these benchmarks measure how (and how often) models get that wrong.

**Sub-type B — Retrieval faithfulness failure:** The model has the right document in context and simply fails to stay faithful to it during generation — not because of a conflict, but because its own generative tendencies override the retrieved content.

**Sub-type C — Agentic external memory failure:** The model is actively managing an external memory store (extracting, updating, retrieving), and hallucinations are introduced at a specific operation in that pipeline — not just at generation time.

| Paper | Sub-type | What They Measure | Key Signal |
|-------|----------|-------------------|------------|
| **ConflictBank** | Conflict | Three conflict types: context-memory, inter-context, intra-memory; 7.4M claim-evidence pairs | Largest conflict benchmark; reveals systematic biases across conflict types |
| **RECALL** | Conflict | Robustness when external context contains deliberately false information | Models struggle to maintain parametric knowledge under counterfactual pressure |
| **Adaptive Chameleon or Stubborn Sloth** | Conflict | Parametric memory behavior under constructed counter-evidence | Quantifies confirmation bias; models over-conform to partially aligned evidence |
| **RAGTruth** | Faithfulness | ~18K naturally generated RAG responses with word-level hallucination annotations | Hallucination rate and type within retrieved-document-grounded responses |
| **HaluMem** | Agentic | Operation-level hallucinations: extraction, updating, QA; 15K memory points | First benchmark to isolate *which* operation in the memory pipeline introduces hallucination |
| **MCPHallu** | Agentic | Hallucinations along reasoning, execution, and **memory** axes in MCP agents | Memory axis isolated from reasoning/execution failures in a multi-agent tool-use setting |

### Placement rationale

**ConflictBank (Sub-type A).** The largest conflict benchmark to date — 7.4M claim-evidence pairs, 553K QA pairs. Explicitly studies three conflict types (context-memory, inter-context, intra-memory) in a single framework. Sub-type A fits because the core measurement is *arbitration accuracy* when parametric and retrieved content disagree. *Not Cat 1* because without the external conflicting content, there is no failure to measure — the conflict is constitutive.

**RECALL (Sub-type A).** Specifically measures robustness when external context contains deliberately false (counterfactual) information. Tests whether parametric knowledge can withstand adversarial external pressure. Sub-type A because the probed failure is arbitration between weights and externally-injected false content.

**Adaptive Chameleon or Stubborn Sloth (Sub-type A).** Constructs counter-evidence to measure parametric memory behavior under pressure. Quantifies confirmation bias and over-conformance to partially-aligned evidence. Same arbitration measurement as ConflictBank and RECALL but with a sharper focus on *behavioral bias* (chameleon-like vs. sloth-like).

**RAGTruth (Sub-type B).** 18K naturally generated RAG responses with word-level hallucination annotations. *Distinct from Sub-type A* because the retrieved document is presumed correct — the failure is the model generating content not supported by the document, not arbitration between conflicting sources. This is pure grounding compliance: did the generation stay faithful to retrieved content? *Not Cat 1* because without the retrieved document, the task doesn't exist.

**HaluMem (Sub-type C).** The first benchmark to isolate hallucinations to *specific operations* in an agentic memory pipeline: extraction, updating, QA. 15K memory points. Sub-type C because the unit of measurement is not "did the final output hallucinate" but "which pipeline operation introduced the error." This operational decomposition is what distinguishes Sub-type C from Sub-types A and B. *Not Cat 2* because the memory being managed is an explicit external store with CRUD operations, not conversational history.

**MCPHallu (Sub-type C).** Evaluates three hallucination axes — reasoning, execution, and memory — in MCP (Model Context Protocol) agents. 358 tasks across five domains, 14 LLMs. Sub-type C because the memory axis is isolated from reasoning and execution failures within a tool-use pipeline — the same operation-level isolation as HaluMem but in a multi-agent tool-use setting rather than a memory-CRUD setting.

---

## Cross-Cutting Observations

**1. Temporal memory is the most-studied failure mode (11 of 21 benchmarks).** Long-term episodic memory degrades in ways that standard context-window benchmarks miss. The 30%+ accuracy drop documented in LongMemEval is the most cited quantitative anchor.

**2. External memory integration splits into three related sub-failures.** Conflict benchmarks (ConflictBank, RECALL, Adaptive Chameleon) measure *arbitration*. Faithfulness benchmarks (RAGTruth) measure *grounding compliance*. Agentic benchmarks (HaluMem, MCPHallu) measure *pipeline-level failure* — which specific operation in an active memory management system introduced the error. All three stem from the same root: the model's internal generative tendencies overriding or distorting external content.

**3. Parametric recall benchmarks remain the smallest category (4 papers).** The field has moved toward measuring failures in externalized and long-term memory systems, leaving internal parametric recall comparatively underexplored at the benchmark level.

**4. Measurement granularity varies sharply across categories.** Parametric recall benchmarks measure aggregate accuracy. Agentic external memory benchmarks (Sub-type C) isolate failure to specific operations. The field still lacks a unified failure taxonomy applied consistently across all three categories.

**5. Boundary cases cluster at Cat 2 / Cat 3-C.** Benchmarks that measure "memory operations" can plausibly belong to either depending on whether the operations are on conversational history (Cat 2) or on an explicit external memory store (Cat 3-C). Our placement principle: if the memory substrate is *generated through interaction* (dialogue, tasks completed), it is Cat 2; if the memory substrate is *an external store the agent reads from and writes to via distinct operations*, it is Cat 3-C. This is the principle that distinguishes MemBench/TWIST (Cat 2) from HaluMem/MCPHallu (Cat 3-C).

---

## Summary Table

| Category | # Benchmarks | Core Failure Mode | Representative Benchmark |
|----------|-------------|-------------------|--------------------------|
| **1. Parametric Memory Recall** | 4 | Model fails to surface knowledge from training weights | HalluLens, PRISM |
| **2. Long-Term Episodic Memory** | 11 | Memory degrades across sessions or extended contexts | LongMemEval, LoCoMo, Towards Root Memory |
| **3. External Memory Integration** | 6 | Conflict arbitration, retrieval unfaithfulness, or agentic pipeline failures | ConflictBank, RAGTruth, HaluMem |
| **Total** | **21** | | |

> *Note: MemoryRewardBench and TWIST evaluate memory management quality across extended contexts, placing them within the long-term episodic category. HaluMem and MCPHallu isolate failures within active memory pipelines, placing them in External Integration (Sub-type C) rather than as a standalone agentic category. Towards Root Memory is a Cat 2 / Cat 3 boundary case resolved toward Cat 2 because the retrieved substrate is user-personalized episodic memory rather than a generic external knowledge base.*
