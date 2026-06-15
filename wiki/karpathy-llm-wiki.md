---
type: Methodology
title: Karpathy's LLM Wiki
description: Andrej Karpathy's conceptual pattern for compiling persistent, compounding personal knowledge bases using LLMs.
resource: raw/karpathy_llm_wiki.md
tags: [methodology, llm-wiki, rag]
timestamp: 2026-06-15T17:15:00Z
---

# Karpathy's LLM Wiki

**Summary**: A guide to Andrej Karpathy's conceptual pattern for compiling persistent, compounding personal knowledge bases using LLMs instead of simple query-time RAG.

**Sources**: `karpathy_llm_wiki.md`

**Last updated**: 2026-06-15

---

Andrej Karpathy's LLM Wiki is a paradigm shift in how AI-augmented personal knowledge bases are structured and managed (source: `karpathy_llm_wiki.md`).

## RAG vs. LLM Wiki
* **Traditional RAG**: Retrieval-Augmented Generation extracts raw text fragments dynamically on every query. The LLM is forced to "rediscover" and synthesize facts from scratch each time, meaning no knowledge is accumulated or compiled (source: `karpathy_llm_wiki.md`).
* **LLM Wiki**: An LLM agent incrementally builds and maintains an interlinked Markdown-based wiki. The knowledge is synthesized and compiled once, cross-referenced, and updated as new information arrives (source: `karpathy_llm_wiki.md`).

## The Three-Layer Architecture
The LLM Wiki framework is split into three modular tiers (source: `karpathy_llm_wiki.md`):
1. **Raw Sources**: The immutable input documents (notes, papers, PDFs) that act as the system's ground truth. The agent reads these but never edits them (source: `karpathy_llm_wiki.md`).
2. **The Wiki**: A structured, interlinked directory of Markdown files written and maintained entirely by the LLM agent (source: `karpathy_llm_wiki.md`).
3. **The Schema**: A configuration/rulebook file (like `Claude.md`) describing the formatting, workflows, and conventions the agent must adhere to (source: `karpathy_llm_wiki.md`).

## Core Agent Operations
An LLM agent collaborating on a wiki performs three distinct tasks (source: `karpathy_llm_wiki.md`):
* **Ingest**: Consuming a new raw document and propagating the changes/insights across all affected wiki pages (source: `karpathy_llm_wiki.md`).
* **Query**: Searching the index, reading relevant pages, and returning a structured answer. High-value answers can be written back into the wiki as new pages (source: `karpathy_llm_wiki.md`).
* **Lint**: Periodically auditing the wiki directory for broken links, orphan pages, contradictions, or data gaps (source: `karpathy_llm_wiki.md`).

## Related pages
- [[google-open-knowledge-format]]
- [[log]]
- [[index]]
