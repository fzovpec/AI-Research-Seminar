# Benchmark Taxonomy: RQ1
## How do existing benchmarks quantify hallucinations in LLM memory systems, and what specific memory failure modes do they evaluate?

**Date:** 2026-11-12
**Scope:** 21 included RQ1 benchmarks, organized into 3 thematic categories

---

## Overview

Across the included benchmarks, three distinct memory failure modes emerge. Each category reflects a structurally different way memory can break down in LLMs — from forgetting a training fact, to losing track of a conversation 300 turns ago, to misreading or misusing a retrieved document.

---

## Category 1: Parametric Memory Recall Failures

**Core question:** Does the model correctly surface knowledge stored in its weights at training time?

This is the most foundational failure mode. The model has the information — it was trained on it — but generates a falsehood anyway. These benchmarks probe the reliability of internal, implicit memory.

| Paper | What They Measure | Key Signal |
|-------|-------------------|------------|
| **HalluLens** | Distinguishes *extrinsic* hallucinations (contradicting parametric memory) from *intrinsic* (contradicting given context) | Extrinsic rate = parametric memory failure |
| **What Matters in Memorizing and Recalling Facts** | Multi-angle probing of fact recall via BELIEF framework + MyriadLAMA | Accuracy under varied prompting reveals recall instability |
| **PRISM** | Disentangles four hallucination dimensions including *source memory* | Source memory error rate isolates parametric failures |
| **Med-HALT** | Explicitly includes *memory-based hallucination tests* alongside reasoning tests | Medical domain reveals factual gaps in specialist knowledge |

**Shared metric pattern:** accuracy on factual recall tasks; benchmarks typically compare performance across model families to surface parametric knowledge depth.

---

## Category 2: Long-Term Episodic Memory Failures

**Core question:** Can the model maintain coherent memory across many turns, sessions, or extended time periods?

This category addresses temporal degradation — the model encounters information early in an interaction (or in a prior session) and fails to retrieve or consistently apply it later. It is the most practically impactful failure mode for dialogue agents and assistants.

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

**Shared metric pattern:** cross-session accuracy, memory consistency scores, recall@k across conversation windows.

---

## Category 3: External Memory Integration Failures

**Core question:** When a model has access to retrieved or external content, does it integrate it correctly — and when that content conflicts with its parametric knowledge, does it arbitrate correctly?

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

**Shared metric pattern:** conflict-resolution accuracy; sycophancy rate; faithfulness scores (NLI-based or annotation-based); per-operation error rates for agentic sub-type.

---

## Cross-Cutting Observations

**1. Temporal memory is the most-studied failure mode (11 of 23 benchmarks).** Long-term episodic memory degrades in ways that standard context-window benchmarks miss. The 30%+ accuracy drop documented in LongMemEval is the most cited quantitative anchor.

**2. External memory integration splits into three related sub-failures.** Conflict benchmarks (ConflictBank, RECALL, Adaptive Chameleon) measure *arbitration*. Faithfulness benchmarks (RAGTruth) measure *grounding compliance*. Agentic benchmarks (HaluMem, MCPHallu) measure *pipeline-level failure* — which specific operation in an active memory management system introduced the error. All three stem from the same root: the model's internal generative tendencies overriding or distorting external content.

**3. Parametric recall benchmarks remain the smallest category (4 papers).** The field has moved toward measuring failures in externalized and long-term memory systems, leaving internal parametric recall comparatively underexplored at the benchmark level.

**4. Measurement granularity varies sharply across categories.** Parametric recall benchmarks measure aggregate accuracy. Agentic external memory benchmarks (Sub-type C) isolate failure to specific operations. The field still lacks a unified failure taxonomy applied consistently across all three categories.

---

## Summary Table

| Category | # Benchmarks | Core Failure Mode | Representative Benchmark |
|----------|-------------|-------------------|--------------------------|
| **1. Parametric Memory Recall** | 4 | Model fails to surface knowledge from training weights | HalluLens, PRISM |
| **2. Long-Term Episodic Memory** | 11 | Memory degrades across sessions or extended contexts | LongMemEval, LoCoMo, Towards Root Memory |
| **3. External Memory Integration** | 6 | Conflict arbitration, retrieval unfaithfulness, or agentic pipeline failures | ConflictBank, RAGTruth, HaluMem |
| **Total** | **21** | | |

> *Note: MemoryRewardBench and TWIST evaluate memory management quality across extended contexts, placing them within the long-term episodic category. HaluMem and MCPHallu isolate failures within active memory pipelines, placing them in External Integration (Sub-type C) rather than as a standalone agentic category.*
