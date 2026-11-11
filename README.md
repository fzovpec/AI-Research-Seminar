# AI Research Seminar: LLM Memory & Hallucination Literature Review

A comprehensive literature review investigating benchmarks, datasets, and methods for addressing hallucinations in Large Language Model (LLM) memory systems.

## Overview

This repository contains a structured literature review exploring two interconnected research questions:

- **RQ1:** Benchmarks and Datasets for LLM Memory Hallucinations
- **RQ2:** Memory-Based Anti-Hallucination Methods and Taxonomies

The review covers papers published between **2023–2026** from top-tier venues including ICML, NeurIPS, KDD, AAAI, IJCAI, ACL, EMNLP, NAACL, ICLR, and leading journals.

## Project Status

| Metric | Value |
|--------|-------|
| **Total Papers Found** | 149+ |
| **Total PDFs Downloaded** | 150+ |
| **RQ1 Papers** | 84 |
| **RQ2 Papers** | 65 |
| **Databases Searched** | 4 (Semantic Scholar, arXiv, DBLP, ACL Anthology) |

## Repository Contents

### Core Documents

- **`MASTER_LITERATURE_REVIEW.md`** - Main comprehensive review document with detailed paper summaries, categorized by research question and search method (arXiv, Semantic Scholar, DBLP, ACL Anthology)
- **`DEDUPLICATED_PAPERS.md`** - Consolidated list of unique papers across all searches, with deduplication and ranking
- **`SCREENING_RESULTS.md`** - Screening process results, inclusion/exclusion criteria, and quality assessment

### Data

- **`papers/`** - Directory containing downloaded PDF files (organized by research question: `papers/RQ1/` and `papers/RQ2/`)

### Scripts

- **`fetch_rq2.py`** - Fetches and downloads RQ2 papers from Semantic Scholar
- **`download_rq2_pdfs.py`** - Downloads PDF files for RQ2 papers with retry logic

## How to Use

### Viewing the Review

1. Start with **`MASTER_LITERATURE_REVIEW.md`** for the complete review with paper summaries and findings
2. Reference **`DEDUPLICATED_PAPERS.md`** for a consolidated list of all unique papers
3. Check **`SCREENING_RESULTS.md`** for quality assessment and exclusion reasoning

### Running Data Collection Scripts

The repository includes Python scripts for fetching additional papers. To use them:

```bash
python fetch_rq2.py          # Fetch RQ2 paper metadata from Semantic Scholar
python download_rq2_pdfs.py  # Download PDF files for the papers
```

## Structure of Main Documents

Each document follows a consistent structure:

1. **Executive Summary** - Key metrics and overview
2. **Research Question Sections** - Organized by RQ1 and RQ2
3. **Database-Specific Results** - Results grouped by source (arXiv, Semantic Scholar, DBLP, ACL)
4. **Paper Details** - For each paper: authors, venue, arXiv/DOI links, abstracts, and key findings

## Research Questions Explained

### RQ1: Benchmarks and Datasets for LLM Memory Hallucinations
Focuses on evaluation frameworks, benchmarks, and datasets designed to measure and assess hallucinations in LLM memory systems. Covers operation-level evaluation, long-term memory assessment, and factuality benchmarking.

### RQ2: Memory-Based Anti-Hallucination Methods and Taxonomies
Explores methods, architectures, and approaches for mitigating hallucinations through memory mechanisms. Includes memory retrieval strategies, grounding approaches, and taxonomy frameworks.

## Target Venues

- **Conferences:** ICML, NeurIPS, KDD, AAAI, IJCAI, ACL, EMNLP, NAACL, ICLR
- **Journals:** IEEE Transactions, Nature, Science, JMLR, TACL, Computational Linguistics
- **Other:** Preprints from arXiv, DBLP, ACL Anthology

## Notes

- PDFs are not tracked in version control (see `.gitignore`)
- Python scripts are development tools and not tracked
- All dates are in YYYY-MM-DD format
- Last compiled: 2026-11-11

## Citation

If you use this literature review in your research, please cite the papers referenced in the review documents directly.
