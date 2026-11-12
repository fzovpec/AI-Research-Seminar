# Paper-Level Mapping: RQ2 Methods → RQ1 Failure Modes

**44 papers × 3 failure modes** · what each method claims to target, grounded in paper evidence

**Legend:**
- **✓** = main target — paper explicitly states this as primary contribution
- **◑** = partial — paper addresses this as secondary concern or implicit claim
- *(blank)* = none — paper does not target this failure mode

**Columns (RQ1 failure modes):**
- **P** = Parametric Recall — model fails to surface facts from training weights
- **L** = Long-term Memory — memory degrades across sessions / extended contexts
- **E** = External Integration — faithfulness to retrieved content, or arbitration between parametric and retrieved knowledge (including agentic pipeline failures)

---

## Category 1: Parametric Memory Control

| Paper | P | L | E |
|-------|---|---|---|
| WISE | ✓ | ◑ | |
| Hallucination-Guided Unlearning | ✓ | | ◑ |
| Parameters vs. Context | ◑ | | ✓ |
| Generation Constraint Scaling | | | |
| ParamMute | ✓ | | ✓ |
| Mechanistic Understanding | ✓ | | |
| SAFE | ✓ | | ◑ |
| Investigating Context-Faithfulness | ◑ | | ✓ |
| When Context Leads | ◑ | | ✓ |
| EWE | ◑ | | ✓ |
| Decoding Memories | ✓ | | |

---

## Category 2: Dedicated Memory Architecture

| Paper | P | L | E |
|-------|---|---|---|
| MemGPT | | ✓ | ◑ |
| MemBook | | ✓ | ◑ |
| Synthius-Mem | | ✓ | ◑ |
| Memory is Reconstructed, Not Retrieved | | ✓ | ◑ |
| MaRS (Forgetful but Faithful) | | ✓ | |
| BioMem (Agentic) | ◑ | ✓ | ✓ |
| Oracle Agent Memory | | ✓ | ◑ |
| Generative Agents | | ◑ | ◑ |
| LSTM-MAS | | ✓ | ◑ |
| LongMem | | ✓ | ◑ |
| Efficient Internal Memory Retrieval | ✓ | | |
| The Memory Trap | | ◑ | |
| TeleMem ⚠️ | | ✓ | ◑ |

---

## Category 3: Retrieval & Access Management

| Paper | P | L | E |
|-------|---|---|---|
| Self-RAG | | | ✓ |
| FLARE | ◑ | | ✓ |
| CRAG (Corrective RAG) | | | ✓ |
| Rowen | ✓ | | ✓ |
| FIDES | ◑ | | ✓ |
| CogitoRAG | | | ✓ |
| MemGraphRAG | | | ✓ |
| TC-RAG | | | ✓ |
| AssistRAG | | | ✓ |
| PGMR | ✓ | | ◑ |
| Adaptive Memory Optimization | | | ✓ |
| KELDaR | | | ✓ |
| TCR (Seeing through the Conflict) | ◑ | | ✓ |
| Studying Context-Memory Conflicts | ◑ | | ✓ |

---

## Category 4: Memory Maintenance & Quality Management

| Paper | P | L | E |
|-------|---|---|---|
| Reflective Memory Management | | ✓ | ◑ |
| TRUSTMEM | | ◑ | |
| Distilling Feedback (Memory-as-a-Tool) | | ◑ | |
| WikiTrace (Evidence-Linked Memory) | | | |
| MemGuard | | ◑ | ◑ |
| CoALA | | ◑ | ◑ |

---

## Evidence Detail

Each paper's ratings are grounded in the following evidence drawn from the PDF (or MASTER abstract where PDF unavailable).

---

### WISE
- **P (main):** WISE directly targets knowledge update failures in LLM parameters, aiming to correct hallucinated responses by editing model weights through a dual memory system with knowledge sharding and routing.
- **L (partial):** The paper frames the core challenge as "lifelong model editing" where repeated edits degrade reliability, generalization, and locality over time — implying degradation across many sequential updates.

### Hallucination-Guided Unlearning
- **P (main):** The paper's core goal is to identify and remove overfitted memorized content from model weights using hallucination traces as diagnostic signals, targeting internal MLP neurons responsible for unsupported factual claims.
- **E (partial):** The method uses retrieved trusted evidence to localize hallucinated spans by comparing model outputs against external documents, but this is a diagnostic tool for unlearning rather than the primary failure mode being addressed.

### Parameters vs. Context
- **P (partial):** The paper measures "Memory Recall" to quantify how much models rely on internal parametric knowledge, implying parametric recall failures are a motivating concern.
- **E (main):** The paper's core focus is on RAG systems where conflicts arise between parametric knowledge and retrieved external context, proposing CK-PLUG to control which source the model relies on.

### Generation Constraint Scaling
- *(No main target in 3-category framework — paper targets hallucinations during read/write operations on an external episodic memory system in Larimar, which mapped to the removed Agent Operations category.)*

### ParamMute
- **P (main):** The paper's core contribution is identifying "knowledge-critical FFNs" — mid-to-deep FFN layers that over-activate during unfaithful generation — and suppressing them at inference time to causally reduce parametric memory override. FFN layers are explicitly framed as the substrate of parametric knowledge storage.
- **E (main):** Directly targets the context-memory conflict failure mode (Sub-type A): RAG scenarios where accurate retrieved evidence contradicts the model's parametric knowledge and the model defaults to its weights. Introduces CoFaithfulQA, a benchmark of exactly this conflict, built from 6 open-domain QA datasets. Achieves +6.17 Context Recall on CoFaithfulQA and +54.63 on ConFiQA.

### Mechanistic Understanding
- **P (main):** The paper explicitly targets hallucinations caused by failures in the LM's internal fact recall pipeline — specifically insufficient subject attribute knowledge in lower-layer MLPs and failure to select correct object attributes in upper-layer attention heads.

### SAFE
- **P (main):** "Our core intuition is that mitigating hallucinations does not require injecting new knowledge into LLMs; instead, it involves steering the model to leverage its existing knowledge more effectively by selecting the most relevant features learned during the pre-training phase."
- **E (partial):** The paper briefly discusses RAG as a related input-side technique and contrasts its own approach with it, but does not target faithfulness to retrieved documents as a primary problem.

### Investigating Context-Faithfulness
- **P (partial):** The paper measures "memory strength" — how consistently LLMs recall facts from parametric weights — as a variable influencing context faithfulness, but internal recall failure is not the primary target.
- **E (main):** The paper directly investigates RAG context faithfulness, specifically how LLMs fail to follow retrieved external evidence when it conflicts with internal memory, and what factors (memory strength, evidence style) govern this failure.

### When Context Leads
- **P (partial):** The paper measures how much parametric knowledge (~30%) LLMs contribute beyond provided context, studying hallucination when parametric recall adds information not entailed by the context.
- **E (main):** The paper's central investigation is how LLMs prioritize and balance contextual (external, retrieved) knowledge versus parametric knowledge, and how hallucinations emerge from this arbitration.

### EWE
- **P (partial):** EWE targets hallucination in long-form generation by augmenting LLMs with working memory and fact-checking feedback, implicitly addressing failures of parametric recall but not as the primary framing.
- **E (main):** EWE integrates a working memory refreshed via real-time retrieval and fact-checking models, directly targeting unfaithfulness and factuality failures when combining parametric knowledge with externally retrieved content.

### Decoding Memories
- **P (main):** The paper targets factual hallucinations where "the model produces outputs that are grammatically correct and fluent, yet factually inaccurate," evaluating on factual QA benchmarks (TriviaQA, NQ-Open, SQuAD) to detect failures in parametric knowledge recall.

---

### MemGPT
- **L (main):** The paper explicitly targets multi-session chat where "LLMs bound by limited conversation windows lack context awareness, persona consistency, and long-term memory during extended conversations."
- **E (partial):** The paper evaluates MemGPT on document analysis where it must faithfully answer questions grounded in retrieved external documents, using an LLM judge to ensure "the answer was properly derived from the provided text (rather than from the model weights)."

### MemBook
- **L (main):** "Unlike transient generation errors, such memory-level errors can persist across sessions and repeatedly influence future responses," benchmarked on HaluMem-Long and LongMemEval for ultra-long-term interaction.
- **E (partial):** Systems relying on vector similarity "may inadvertently reinforce hallucinations by repeatedly surfacing semantically plausible but factually irrelevant memories."

### Synthius-Mem
- **L (main):** Explicitly targets hallucination-resistant long-term persona memory across multi-session conversations, benchmarked on LoCoMo which spans long conversations (1,813 questions) with memory degradation as the core failure mode.
- **E (partial):** The system uses CategoryRAG to retrieve structured persona facts, and adversarial robustness (99.55%) measures resistance to hallucinating facts never disclosed.

### Memory is Reconstructed, Not Retrieved
- **L (main):** Explicitly targets "long interaction histories" and benchmarks on LOCOMO and LongMemEval, which test memory reasoning across extended multi-session conversations spanning 100+ turns.
- **E (partial):** Critiques RAG-style external retrieval systems (e.g., MemoryBank, Mem0, A-Mem), noting their failure to faithfully reason over retrieved content when multi-hop or associative inference is required.

### MaRS (Forgetful but Faithful)
- **L (main):** Explicitly targets agents operating across "hours or days" and "months-long" interactions, introducing MaRS and the FiFA benchmark to measure "narrative coherence across turns" and multi-session memory degradation under budget constraints.

### BioMem (Agentic)
- **P (partial):** "Biomedical applications often depend on information that is patient-specific, evolving, or distributed across multiple sources, which cannot be fully captured by knowledge encoded in model parameters alone."
- **L (main):** Explicitly evaluates "long-term conversational memory" as a primary setting — HMRU "reduces conversational answer errors by 24.9% and closes 48.0% of the performance gap to full-context inference."
- **E (main):** Identifies "evidence retrieval, information fidelity, and memory utilization as distinct but interconnected challenges," targeting failures where "iterative memory evolution is associated with the emergence and persistence of source-unsupported information."

### Oracle Agent Memory
- **L (main):** Explicitly targets "retention of task state across extended conversations, recovery of user-specific facts and preferences across sessions," benchmarking on LongMemEval with 93.8% accuracy.
- **E (partial):** The architecture integrates retrieval-augmented patterns (dense vector search over stored records) but faithfulness to retrieved content versus parametric conflict is not the primary stated concern.

### Generative Agents
- **L (partial):** Agents require conditioning on "a vast amount of past experience," which is a poor fit for models with limited context windows, motivating their memory architecture.
- **E (partial):** The architecture retrieves past experiences dynamically and mixes them with current context and plans, which "may either reinforce or contradict each other."

### LSTM-MAS
- **L (main):** Explicitly targets hallucination propagation and error accumulation across long contexts processed sequentially by chained agents, with gated memory mechanisms designed to "preserve long-range information" and "avoid error accumulation and hallucination propagation" across extended text segments.
- **E (partial):** Briefly references RAG as a baseline, but the core focus is on the multi-agent chaining problem rather than unfaithfulness to retrieved documents.

### LongMem
- **L (main):** Explicitly proposes LongMem to enable LLMs to "memorize long history" beyond the fixed input length limit, caching up to 65k tokens of past context in a non-differentiable memory bank.
- **E (partial):** The decoupled SideNet retrieves cached attention key-value pairs from the memory bank and fuses them into current language modeling, implicitly addressing faithfulness to retrieved external context.

### Efficient Internal Memory Retrieval
- **P (main):** Focuses on efficient internal memory retrieval for clinical settings, reducing hallucinations through parametric knowledge grounding — directly targeting failures in recalling facts from training weights.

### The Memory Trap
- **L (partial):** The unsafe behavior arises from memories persisted across interactions, implying cross-session or long-horizon memory persistence is a prerequisite for the trap to activate.

### TeleMem ⚠️ (multimodal — may be out of scope)
- **L (main):** Explicitly targets "long-term interactive settings" where "models struggle to allocate attention to distant yet critical information, leading to degraded recall of user-specific facts."
- **E (partial):** Conventional RAG pipelines "treat memories as independent fragments and lack principled mechanisms for consolidation, update, and causal organization, leading to fragmented context and unstable long-horizon reasoning."

---

### Self-RAG
- **E (main):** Primary contribution is training an LM to adaptively retrieve, evaluate relevance of retrieved passages, and self-reflect on whether generated output is fully supported by retrieved documents. The paper pivots immediately from generic hallucination motivation to RAG design problems; every mechanism (retrieval tokens, critique tokens, segment-level beam search) operates on the retrieved-context layer with no engagement with parametric weights.

### FLARE
- **P (partial):** FLARE's retrieval trigger is architecturally grounded in the model's parametric uncertainty: low token probability is explicitly defined as evidence that the LM's parametric knowledge is insufficient for the upcoming span, citing calibration literature (Kadavath et al., 2022; Jiang et al., 2021). The when-to-retrieve decision is not arbitrary — it operationalizes parametric recall failure as the signal to fetch external evidence.
- **E (main):** Directly targets hallucinations in retrieval-augmented generation by actively deciding when and what to retrieve, regenerating sentences that contain low-confidence tokens using externally retrieved documents.

### CRAG (Corrective RAG)
- **E (main):** Directly targets failures where retrieved/external documents are inaccurate or irrelevant. The paper explicitly states its scope: "this paper particularly studies the scenarios where the retriever returns inaccurate results." Every component — the retrieval evaluator, confidence-based Correct/Incorrect/Ambiguous triggers, web-search fallback, decompose-then-recompose algorithm — operates on retrieval quality, not on parametric weights. The parametric knowledge sentence in the abstract is standard RAG-motivation boilerplate shared by essentially all retrieval papers.

### Rowen
- **P (main):** Explicitly targets "internal hallucination" caused by "the limited knowledge of LLMs" when relying on parametric knowledge, using consistency-based uncertainty detection to identify when the model's internal reasoning fails.
- **E (main):** Explicitly targets "external hallucination" caused by irrelevant retrieved documents being incorporated into generation.

### FIDES
- **P (partial):** Acknowledges parametric memory bias as the source of "stubborn hallucination," but treats it as a background condition to be suppressed rather than a failure mode to fix in isolation.
- **E (main):** Directly targets the failure mode where models "ignore retrieved evidence and default to memorized priors" during RAG, proposing a token-level decoding method to enforce faithfulness to retrieved context.

### CogitoRAG
- **E (main):** "The inherent discrete representation of text in existing frameworks often results in a loss of semantic integrity, leading to retrieval deviations" — the core focus is faithfully integrating and reasoning over retrieved external documents.

### MemGraphRAG
- **E (main):** The entire paper targets failures where retrieved graph contexts are noisy, logically inconsistent, or thematically irrelevant — i.e., the model fails to faithfully use or is misled by retrieved external content.

### TC-RAG
- **E (main):** A Turing-Complete memory stack that controls retrieval halting, removes erroneous/noisy retrieved content via Push/Pop/Backtrack operations, and mitigates accumulation of "erroneous knowledge" introduced by external retrieval. "Outdated knowledge" appears only as motivation for using RAG in general; the word "parametric" appears only as a contrast term. Every mechanism operates on the retrieved-context layer — no component touches internal weights.

### AssistRAG
- **E (main):** Core contribution is an intelligent assistant that retrieves external knowledge, evaluates its usefulness, extracts relevant snippets, and decides whether to provide retrieved content to the main LLM. The hallucination sentence in the abstract is generic boilerplate; the paper's design rationale, problem formulation, and all experiments target retrieval quality and context integration — the "memory management" component refers to episodic interaction history, not parametric weights.

### PGMR
- **P (main):** Directly targets hallucinations arising from LLMs relying on "opaque internal parametric knowledge" to recall KG URIs (e.g., Wikidata identifiers like Q937), causing incorrect or non-existent identifiers to be generated from parametric memory.
- **E (partial):** PGMR is compared against RAG (pre-generation retrieval), noting that RAG still fails to eliminate hallucinations because the LLM is not strictly constrained to rely on retrieved context.

### Adaptive Memory Optimization
- **E (main):** Core contribution directly targets faithfulness to retrieved content, proposing the Multi-granular Content Filter to reduce noise from retrieved documents and the Agent-based Memory Updater to synthesize retrieved information coherently. The parametric memory sentence is standard RAG motivation boilerplate — no component of the system diagnoses, detects, or compensates for parametric weight failures; it is entirely an external retrieval/context-management architecture.

### KELDaR
- **E (main):** Core contribution retrieves KG subgraphs and grounds LLM reasoning in external structured knowledge to reduce hallucinations and improve faithfulness to retrieved facts during KGQA. Hallucinations are framed entirely as a gap-in-external-knowledge problem; parametric memory is treated as an invisible background assumption with no method component targeting or diagnosing it.

### TCR (Seeing through the Conflict)
- **P (partial):** TCR addresses this by estimating "self-answerability to gauge confidence in internal memory," but this is secondary to its RAG conflict focus.
- **E (main):** Directly targets the RAG failure mode where "conflicts between implicitly stored internal knowledge and retrieved external information remain a critical issue, often causing inconsistent or incorrect outputs."

### Studying Context-Memory Conflicts
- **P (partial):** Studies cases where the model's parametric knowledge is incorrect and fails to be overridden by context, revealing a "parametric bias" where incorrect parametric answers negatively affect reading comprehension.
- **E (main):** Primary focus is RAG-based context-memory conflicts — specifically when LLMs fail to update their incorrect parametric knowledge with correct information from retrieved real documents in a RAG setting.

---

### Reflective Memory Management
- **L (main):** Explicitly targets LLMs' inability to retain and retrieve relevant information from long-term, multi-session interactions, evaluating on benchmarks like LongMemEval and MSC designed for sustained personalized dialogue.
- **E (partial):** The Retrospective Reflection component iteratively refines retrieval to address failures when fixed retrievers incorporate irrelevant context that degrades response quality.

### TRUSTMEM
- **L (partial):** Situates itself within long-term memory for LLM agents that "transcend finite context windows to preserve user preferences, historical facts, and reasoning trajectories."

### Distilling Feedback (Memory-as-a-Tool)
- **L (partial):** The long-horizon mixed-task experiment (H=12, interleaved tasks) tests whether knowledge persists across extended sequences, implicitly addressing performance degradation over many turns.

### WikiTrace (Evidence-Linked Memory)
- *(No main target in 3-category framework — paper targets hallucinations during CRUD operations on an explicit external memory store of agent trajectories, which mapped to the removed Agent Operations category.)*

### MemGuard
- **L (partial):** Targets "long-term memory-augmented LLMs," implying multi-session or extended memory persistence is a context for the problem.
- **E (partial):** Hallucination arises from "semantically mixed memories causing factually inconsistent retrieval," touching on faithfulness failures when retrieving from an external memory store.

### CoALA
- **L (partial):** Identifies long-term memory management across extended agent operation as a key architectural component.
- **E (partial):** Explicitly categorizes retrieval as a core action type and identifies "integration of decision-making and retrieval as an important future direction."

---

## Coverage Summary

| Failure Mode | Main Target (✓) | Partial (◑) | None |
|---|---|---|---|
| **P: Parametric Recall** | 10 | 10 | 24 |
| **L: Long-term Memory** | 13 | 12 | 19 |
| **E: External Integration** | 20 | 14 | 10 |

**Key observations:**
1. **External Integration is the most targeted failure mode** (19 main) — almost entirely by Category 3 (Retrieval & Access Management).
2. **Long-term Memory** (13 main) is dominated by Category 2 (Dedicated Architecture); Category 3 almost completely ignores it — a structural gap.
3. **Parametric Recall is the least covered** (9 main) — only Category 1 papers explicitly address this, with near-zero coverage from Categories 2–4.
4. **Category 4 (Maintenance) papers largely miss all three failure modes** — TRUSTMEM, WikiTrace, Distilling Feedback have no main target in this framework, revealing they were primarily addressing agentic memory operations, which is not a distinct RQ1 failure mode.
5. **Generation Constraint Scaling** (Category 1) also has no main target — it too targeted external memory CRUD operations rather than parametric recall.

---

*Generated: 2026-11-12, updated 2026-11-12 | All 44 papers read from PDF (or MASTER abstract where PDF unavailable)*
*PDF fallbacks used for: WISE, EWE, Efficient Internal Memory Retrieval, The Memory Trap, MemGuard*
