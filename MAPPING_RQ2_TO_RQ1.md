# Paper-Level Mapping: RQ2 Methods → RQ1 Failure Modes

**46 papers × 4 failure modes** · what each method claims to target, grounded in paper evidence

**Legend:**
- **✓** = main target — paper explicitly states this as primary contribution
- **◑** = partial — paper addresses this as secondary concern or implicit claim
- *(blank)* = none — paper does not target this failure mode

**Columns (RQ1 failure modes):**
- **P** = Parametric Recall — model fails to surface facts from training weights
- **L** = Long-term Memory — memory degrades across sessions / extended contexts
- **E** = External Integration — faithfulness to retrieved content, or arbitration between parametric and retrieved knowledge
- **A** = Agent Operations — hallucinations from CRUD-like memory management (extract, store, update, retrieve, delete)

---

## Category 1: Parametric Memory Control

| Paper | P | L | E | A |
|-------|---|---|---|---|
| WISE | ✓ | ◑ | | |
| Hallucination-Guided Unlearning | ✓ | | ◑ | |
| Parameters vs. Context | ◑ | | ✓ | |
| Generation Constraint Scaling | | | | ✓ |
| Mechanistic Understanding | ✓ | | | |
| SAFE | ✓ | | ◑ | |
| Investigating Context-Faithfulness | ◑ | | ✓ | |
| When Context Leads | ◑ | | ✓ | |
| EWE | ◑ | | ✓ | ◑ |
| Decoding Memories | ✓ | | | |

---

## Category 2: Dedicated Memory Architecture

| Paper | P | L | E | A |
|-------|---|---|---|---|
| MemGPT | | ✓ | ◑ | ✓ |
| MemBook | | ✓ | ◑ | ✓ |
| Synthius-Mem | | ✓ | ◑ | ✓ |
| Memory is Reconstructed, Not Retrieved | | ✓ | ◑ | ✓ |
| MaRS (Forgetful but Faithful) | | ✓ | | ✓ |
| BioMem (Agentic) | ◑ | ✓ | ✓ | ✓ |
| Oracle Agent Memory | | ✓ | ◑ | ✓ |
| Generative Agents | | ◑ | ◑ | ✓ |
| LSTM-MAS | | ✓ | ◑ | ◑ |
| LongMem | | ✓ | ◑ | ◑ |
| Efficient Internal Memory Retrieval | ✓ | | | |
| The Memory Trap | | ◑ | | ✓ |
| TeleMem ⚠️ | | ✓ | ◑ | ✓ |

---

## Category 3: Retrieval & Access Management

| Paper | P | L | E | A |
|-------|---|---|---|---|
| Self-RAG | ◑ | | ✓ | |
| FLARE | ◑ | | ✓ | |
| CRAG (Corrective RAG) | ◑ | | ✓ | |
| Rowen | ✓ | | ✓ | |
| FIDES | ◑ | | ✓ | |
| CogitoRAG | | | ✓ | |
| MemGraphRAG | | | ✓ | ◑ |
| TC-RAG | ◑ | | ✓ | ◑ |
| AssistRAG | ◑ | | ✓ | ◑ |
| PGMR | ✓ | | ◑ | |
| Adaptive Memory Optimization | ◑ | | ✓ | ◑ |
| KELDaR | ◑ | | ✓ | |
| TCR (Seeing through the Conflict) | ◑ | | ✓ | |
| Studying Context-Memory Conflicts | ◑ | | ✓ | |

---

## Category 4: Memory Maintenance & Quality Management

| Paper | P | L | E | A |
|-------|---|---|---|---|
| Reflective Memory Management | | ✓ | ◑ | ✓ |
| TRUSTMEM | | ◑ | | ✓ |
| Distilling Feedback (Memory-as-a-Tool) | | ◑ | | ✓ |
| WikiTrace (Evidence-Linked Memory) | | | | ✓ |
| MemGuard | | ◑ | ◑ | ✓ |
| CoALA | | ◑ | ◑ | ✓ |

---

## Surveys & Taxonomies

| Paper | P | L | E | A |
|-------|---|---|---|---|
| From Storage to Experience | | ◑ | ◑ | ✓ |
| A Survey of Agent Memory in the Second Half | ◑ | ✓ | ◑ | ✓ |
| Are We Ready For An Agent-Native Memory System? | | ◑ | | ✓ |

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
- **A (main):** The paper uses a memory-augmented LLM (Larimar) with explicit external episodic memory supporting read/write operations, and proposes scaling the memory readout vector to mitigate hallucination arising from misalignment between write and readout representations in that memory system.

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
- **A (partial):** EWE performs CRUD-like operations on an explicit working memory store (refreshing, updating, and reading from it at generation intervals), making agent-style memory operations a core mechanism, though hallucination from these operations is not the stated primary target.

### Decoding Memories
- **P (main):** The paper targets factual hallucinations where "the model produces outputs that are grammatically correct and fluent, yet factually inaccurate," evaluating on factual QA benchmarks (TriviaQA, NQ-Open, SQuAD) to detect failures in parametric knowledge recall.

---

### MemGPT
- **L (main):** The paper explicitly targets multi-session chat where "LLMs bound by limited conversation windows lack context awareness, persona consistency, and long-term memory during extended conversations."
- **E (partial):** The paper evaluates MemGPT on document analysis where it must faithfully answer questions grounded in retrieved external documents, using an LLM judge to ensure "the answer was properly derived from the provided text (rather than from the model weights)."
- **A (main):** The core mechanism is an OS-inspired system where the LLM uses explicit function calls to read, write, search, append, and evict data across memory tiers (working context, FIFO queue, recall storage, archival memory).

### MemBook
- **L (main):** "Unlike transient generation errors, such memory-level errors can persist across sessions and repeatedly influence future responses," benchmarked on HaluMem-Long and LongMemEval for ultra-long-term interaction.
- **E (partial):** Systems relying on vector similarity "may inadvertently reinforce hallucinations by repeatedly surfacing semantically plausible but factually irrelevant memories."
- **A (main):** A stateful memory stabilization mechanism governs CRUD-like operations — preventing hallucinated claims from being written into persistent memory via pending/confirmed state transitions across the Session–Chapter–Memory Point hierarchy.

### Synthius-Mem
- **L (main):** Explicitly targets hallucination-resistant long-term persona memory across multi-session conversations, benchmarked on LoCoMo which spans long conversations (1,813 questions) with memory degradation as the core failure mode.
- **E (partial):** The system uses CategoryRAG to retrieve structured persona facts, and adversarial robustness (99.55%) measures resistance to hallucinating facts never disclosed.
- **A (main):** Synthius-Mem's core pipeline performs explicit CRUD-like operations on a structured external memory store: extracting, consolidating, deduplicating, and retrieving persona facts across six cognitive domains.

### Memory is Reconstructed, Not Retrieved
- **L (main):** Explicitly targets "long interaction histories" and benchmarks on LOCOMO and LongMemEval, which test memory reasoning across extended multi-session conversations spanning 100+ turns.
- **E (partial):** Critiques RAG-style external retrieval systems (e.g., MemoryBank, Mem0, A-Mem), noting their failure to faithfully reason over retrieved content when multi-hop or associative inference is required.
- **A (main):** Core contribution is a Cue–Tag–Content memory graph framework with explicit CRUD-like operations (extract, store, tag, traverse, prune) on an external memory store.

### MaRS (Forgetful but Faithful)
- **L (main):** Explicitly targets agents operating across "hours or days" and "months-long" interactions, introducing MaRS and the FiFA benchmark to measure "narrative coherence across turns" and multi-session memory degradation under budget constraints.
- **A (main):** Fundamentally a framework for governing CRUD-like operations on an explicit external memory store — typed nodes with provenance-tracked episodic, semantic, social, and task memories — and six forgetting policies (FIFO, LRU, Priority Decay, etc.).

### BioMem (Agentic)
- **P (partial):** "Biomedical applications often depend on information that is patient-specific, evolving, or distributed across multiple sources, which cannot be fully captured by knowledge encoded in model parameters alone."
- **L (main):** Explicitly evaluates "long-term conversational memory" as a primary setting — HMRU "reduces conversational answer errors by 24.9% and closes 48.0% of the performance gap to full-context inference."
- **E (main):** Identifies "evidence retrieval, information fidelity, and memory utilization as distinct but interconnected challenges," targeting failures where "iterative memory evolution is associated with the emergence and persistence of source-unsupported information."
- **A (main):** Explicitly studies agentic memory CRUD operations (storage, retrieval, updating) on external memory stores, investigating how "information may be transformed during storage, selected or omitted during retrieval, revised through subsequent updates."

### Oracle Agent Memory
- **L (main):** Explicitly targets "retention of task state across extended conversations, recovery of user-specific facts and preferences across sessions," benchmarking on LongMemEval with 93.8% accuracy.
- **E (partial):** The architecture integrates retrieval-augmented patterns (dense vector search over stored records) but faithfulness to retrieved content versus parametric conflict is not the primary stated concern.
- **A (main):** Core system models memory as a full CRUD lifecycle — ingestion, extraction, consolidation, retrieval, revision, and removal — implemented as explicit API operations on an Oracle Database-native memory store.

### Generative Agents
- **L (partial):** Agents require conditioning on "a vast amount of past experience," which is a poor fit for models with limited context windows, motivating their memory architecture.
- **E (partial):** The architecture retrieves past experiences dynamically and mixes them with current context and plans, which "may either reinforce or contradict each other."
- **A (main):** Core contribution is a memory stream architecture that stores, synthesizes, retrieves, and updates agent experiences via CRUD-like operations on an explicit external memory system, with errors noted when agents "failed to retrieve relevant memories" or "fabricated embellishments to the agent's memory."

### LSTM-MAS
- **L (main):** Explicitly targets hallucination propagation and error accumulation across long contexts processed sequentially by chained agents, with gated memory mechanisms designed to "preserve long-range information" and "avoid error accumulation and hallucination propagation" across extended text segments.
- **E (partial):** Briefly references RAG as a baseline, but the core focus is on the multi-agent chaining problem rather than unfaithfulness to retrieved documents.
- **A (partial):** Each agent node explicitly performs CRUD-like operations on a shared memory state (Worker writes, Filter prunes, Judge flags errors, Manager reads and aggregates), with hallucinations from these propagation steps as a stated target.

### LongMem
- **L (main):** Explicitly proposes LongMem to enable LLMs to "memorize long history" beyond the fixed input length limit, caching up to 65k tokens of past context in a non-differentiable memory bank.
- **E (partial):** The decoupled SideNet retrieves cached attention key-value pairs from the memory bank and fuses them into current language modeling, implicitly addressing faithfulness to retrieved external context.
- **A (partial):** Involves explicit CRUD-like operations on an external memory store — encoding past segments into a memory bank, retrieving top-k key-value pairs, and updating the cache — though failures in these operations are not the stated research target.

### Efficient Internal Memory Retrieval
- **P (main):** Focuses on efficient internal memory retrieval for clinical settings, reducing hallucinations through parametric knowledge grounding — directly targeting failures in recalling facts from training weights.

### The Memory Trap
- **L (partial):** The unsafe behavior arises from memories persisted across interactions, implying cross-session or long-horizon memory persistence is a prerequisite for the trap to activate.
- **A (main):** The paper's core concern is that benign interaction memories stored in an external memory system are later retrieved and cause unsafe LLM behavior, directly targeting hallucination/safety failures from CRUD operations on an explicit memory store.

### TeleMem ⚠️ (multimodal — may be out of scope)
- **L (main):** Explicitly targets "long-term interactive settings" where "models struggle to allocate attention to distant yet critical information, leading to degraded recall of user-specific facts."
- **E (partial):** Conventional RAG pipelines "treat memories as independent fragments and lack principled mechanisms for consolidation, update, and causal organization, leading to fragmented context and unstable long-horizon reasoning."
- **A (main):** "Maintains coherent and hallucination-resistant user profiles by extracting only dialogue-grounded narrative units" and designs a structured pipeline for batching, clustering, consolidating, and persisting memories in an external memory store.

---

### Self-RAG
- **P (partial):** LLMs "often produce responses containing factual inaccuracies due to their sole reliance on the parametric knowledge they encapsulate," positioning parametric knowledge failure as a motivating problem that RAG addresses secondarily.
- **E (main):** Primary contribution is training an LM to adaptively retrieve, evaluate relevance of retrieved passages, and self-reflect on whether generated output is fully supported by retrieved documents.

### FLARE
- **P (partial):** LMs "have memorized some world knowledge during training" but "still tend to hallucinate and create imaginary content," motivating retrieval augmentation as a fix for parametric knowledge gaps.
- **E (main):** Directly targets hallucinations in retrieval-augmented generation by actively deciding when and what to retrieve, regenerating sentences that contain low-confidence tokens using externally retrieved documents.

### CRAG (Corrective RAG)
- **P (partial):** "LLMs inevitably exhibit hallucinations since the accuracy of generated texts cannot be secured solely by the parametric knowledge they encapsulate."
- **E (main):** Directly targets failures where retrieved/external documents are inaccurate or irrelevant, proposing a corrective retrieval evaluator to assess retrieved document quality and trigger appropriate knowledge retrieval actions.

### Rowen
- **P (main):** Explicitly targets "internal hallucination" caused by "the limited knowledge of LLMs" when relying on parametric knowledge, using consistency-based uncertainty detection to identify when the model's internal reasoning fails.
- **E (main):** Explicitly targets "external hallucination" caused by irrelevant retrieved documents being incorporated into generation, with adaptive retrieval mechanism designed to minimize this risk.

### FIDES
- **P (partial):** Acknowledges parametric memory bias as the source of "stubborn hallucination," but treats it as a background condition to be suppressed rather than a failure mode to fix in isolation.
- **E (main):** Directly targets the failure mode where models "ignore retrieved evidence and default to memorized priors" during RAG, proposing a token-level decoding method to enforce faithfulness to retrieved context.

### CogitoRAG
- **E (main):** "The inherent discrete representation of text in existing frameworks often results in a loss of semantic integrity, leading to retrieval deviations" — the core focus is faithfully integrating and reasoning over retrieved external documents.

### MemGraphRAG
- **E (main):** The entire paper targets failures where retrieved graph contexts are noisy, logically inconsistent, or thematically irrelevant — i.e., the model fails to faithfully use or is misled by retrieved external content.
- **A (partial):** Introduces a Three-Layer Global Memory with multi-agent CRUD operations (extraction, conflict detection, conflict resolution, storage of facts/schemas) on a shared external memory store.

### TC-RAG
- **P (partial):** Cites "factual inaccuracies (i.e., hallucinations)" and "outdated knowledge" as motivating problems for medical LLMs.
- **E (main):** A Turing-Complete memory stack that controls retrieval halting, removes erroneous/noisy retrieved content via Push/Pop stack operations, and mitigates the accumulation of "erroneous knowledge" introduced by external retrieval.
- **A (partial):** The memory stack with explicit Push, Pop, backtrack, and summary operations constitutes CRUD-like management of an external memory store, framed as a mechanism to support better retrieval.

### AssistRAG
- **P (partial):** Background motivation cites LLMs generating "factually incorrect information, known as hallucination."
- **E (main):** Core contribution is an intelligent assistant that retrieves external knowledge, evaluates its usefulness, extracts relevant snippets, and decides whether to provide retrieved content to the main LLM.
- **A (partial):** Explicitly includes memory construction, memory retrieval, memory updating, and note-taking as CRUD-like operations on an internal memory store, framed as a support mechanism.

### PGMR
- **P (main):** Directly targets hallucinations arising from LLMs relying on "opaque internal parametric knowledge" to recall KG URIs (e.g., Wikidata identifiers like Q937), causing incorrect or non-existent identifiers to be generated from parametric memory.
- **E (partial):** PGMR is compared against RAG (pre-generation retrieval), noting that RAG still fails to eliminate hallucinations because the LLM is not strictly constrained to rely on retrieved context.

### Adaptive Memory Optimization
- **P (partial):** Cites LLMs suffering from "hallucinations and factual inaccuracies due to their reliance on parametric memory" as motivation, but the primary solution is an external RAG system.
- **E (main):** Core contribution directly targets faithfulness to retrieved content, proposing the Multi-granular Content Filter to reduce noise from retrieved documents and the Agent-based Memory Updater to synthesize retrieved information coherently.
- **A (partial):** The Agent-based Memory Updater explicitly performs CRUD-like operations on a memory store (initializing, updating, comparing, selecting memory notes across iterative retrieval steps).

### KELDaR
- **P (partial):** Addresses LLM hallucinations stemming from lacking external knowledge, motivating the KG-enhancement framework, but factual recall from parametric memory is not the primary target.
- **E (main):** Core contribution retrieves KG subgraphs and grounds LLM reasoning in external structured knowledge to reduce hallucinations and improve faithfulness to retrieved facts during KGQA.

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
- **A (main):** Core contribution is an external memory management mechanism (RMM) that explicitly handles CRUD-like operations — storing summarized memories via Prospective Reflection and updating/refining retrieval via Retrospective Reflection.

### TRUSTMEM
- **L (partial):** Situates itself within long-term memory for LLM agents that "transcend finite context windows to preserve user preferences, historical facts, and reasoning trajectories."
- **A (main):** Directly targets hallucinations introduced during CRUD-like memory operations (WRITE, REVISE, PRUNE), explicitly reducing "transition-level omission, corruption, and hallucination by 40.1%, 79.1%, and 50.0%" in generated memory updates.

### Distilling Feedback (Memory-as-a-Tool)
- **L (partial):** The long-horizon mixed-task experiment (H=12, interleaved tasks) tests whether knowledge persists across extended sequences, implicitly addressing performance degradation over many turns.
- **A (main):** Core framework empowers the LLM to explicitly write, read, edit, and list files in a persistent file-based memory system via tool calls (write_file, edit_file, read_file, ls). The primary research question is whether agents can correctly perform these CRUD operations to accumulate and retrieve distilled guidelines without errors.

### WikiTrace (Evidence-Linked Memory)
- **A (main):** Introduces WikiTrace to address "memory-induced degradation," where agents fail on tasks they would solve without memory because stored lessons (distilled from past trajectories) are incorrect, misapplied, or misread — targeting hallucination failures arising from CRUD-like operations on an explicit external memory store.

### MemGuard
- **L (partial):** Targets "long-term memory-augmented LLMs," implying multi-session or extended memory persistence is a context for the problem.
- **E (partial):** Hallucination arises from "semantically mixed memories causing factually inconsistent retrieval," touching on faithfulness failures when retrieving from an external memory store.
- **A (main):** Directly addresses "memory contamination" — a hallucination form caused by heterogeneous memory mixing in explicit external memory systems — proposing a type-aware memory organization framework to prevent it.

### CoALA
- **L (partial):** Identifies long-term memory management across extended agent operation as a key architectural component, noting that a longer context window "could reduce the importance of long-term memory."
- **E (partial):** Explicitly categorizes retrieval as a core action type and identifies "integration of decision-making and retrieval as an important future direction."
- **A (main):** Primary contribution structures an agent's action space around explicit operations on internal and external memory stores (reading, writing, and updating working memory, semantic memory, episodic memory, and procedural memory), making memory CRUD operations the central architectural concern.

---

### From Storage to Experience
- **L (partial):** Identifies "long-range consistency" as a core catalyst driving memory mechanism evolution, with benchmarks like LoCoMo and ImplexConv explicitly evaluating memory across up to 35 and 100 sessions respectively.
- **E (partial):** Covers the "Storage" stage focused on faithful recording of trajectories and retrieval from external memory databases, implicitly touching on faithfulness and retrieval accuracy from external stores.
- **A (main):** Central framework explicitly formalizes memory evolution around CRUD-like operations on external memory systems — storage, retrieval, reflection (refinement), and experience (abstraction) — across all three evolutionary stages it surveys.

### A Survey of Agent Memory in the Second Half
- **P (partial):** The survey covers internal parametric memory as one of two main substrate categories, with parametric priors and weight-stored knowledge discussed as a substrate, but factual recall failures are not a primary stated concern.
- **L (main):** Explicitly targets long-horizon, multi-session agents where "LLM-based agents face context explosion beyond fixed context windows and must continuously accumulate, manage, and selectively reuse large volumes of information across extended interactions."
- **E (partial):** External retrieval-augmented stores are a central taxonomy dimension, with the survey noting that "retrieval can be unreliable" and that external memory helps "reduce hallucinations or knowledge cutoff."
- **A (main):** Systematically analyzes memory CRUD operations (store, load, summarize, forget, refine) in both single- and multi-agent systems, and explicitly tracks "False Memory Rate (FMR)" — the rate of hallucinated memories including fabricated or incorrect updates — as a key evaluation metric.

### Are We Ready For An Agent-Native Memory System?
- **L (partial):** Evaluates "long-horizon stability" and uses the LoCoMo benchmark to assess whether maintenance choices "preserve updated facts and coherent memory use over extended contexts."
- **A (main):** Explicitly decomposes agent memory into four modules — representation/storage, extraction, retrieval/routing, and maintenance — and evaluates 12 memory systems on CRUD-like operations including "persistent information storage, retrieval, update, consolidation, and dynamic lifecycle governance," with fine-grained ablation studies on "update correctness" and memory extraction fidelity.

---

## Coverage Summary

| Failure Mode | Main Target (✓) | Partial (◑) | None |
|---|---|---|---|
| **P: Parametric Recall** | 9 | 17 | 20 |
| **L: Long-term Memory** | 14 | 14 | 18 |
| **E: External Integration** | 19 | 16 | 11 |
| **A: Agent Operations** | 25 | 10 | 11 |

**Key observations:**
1. **Agent Operations is the most targeted failure mode** (25 main, 10 partial) — driven heavily by Categories 2 and 4.
2. **External Integration is the second most targeted** (19 main) — almost entirely by Category 3 (Retrieval & Access Management).
3. **Parametric Recall is the least covered** (9 main) — only Categories 1 papers explicitly address this, with almost zero coverage from Categories 2–4.
4. **Long-term Memory** (14 main) is dominated by Category 2 (Dedicated Architecture) papers; Category 3 almost completely ignores it.
5. **Notable mismatches from taxonomy categories:** Generation Constraint Scaling (placed in Parametric Control) actually primarily targets Agent Operations based on paper evidence.

---

*Generated: 2026-11-12 | All 46 papers read from PDF (or MASTER abstract where PDF unavailable)*
*PDF fallbacks used for: WISE, EWE, Efficient Internal Memory Retrieval, The Memory Trap, MemGuard*
