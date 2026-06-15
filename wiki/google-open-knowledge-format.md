---
type: Specification
title: Google Open Knowledge Format (OKF)
description: Google Cloud's open specification for standardizing directory-based Markdown knowledge bundles with YAML frontmatter for AI agents.
resource: raw/google_open_knowledge_format.md
tags: [specification, google, okf, metadata]
timestamp: 2026-06-15T17:15:00Z
---

# Google Open Knowledge Format (OKF)

**Summary**: A summary of Google Cloud's Open Knowledge Format (OKF) spec, standardizing agent-ready personal and enterprise knowledge bases.

**Sources**: `google_open_knowledge_format.md`

**Last updated**: 2026-06-15

---

The Open Knowledge Format (OKF) (v0.1 Draft) is an open-source, vendor-neutral specification published by Google Cloud to standardise how knowledge is represented and shared across AI agents and systems (source: `google_open_knowledge_format.md`).

## Core Principles
* **Readable & Parseable**: Files must be standard Markdown documents, readable by humans using common text tools and parseable by AI agents without specialized SDKs (source: `google_open_knowledge_format.md`).
* **Diffable & Portable**: Knowledge bases are managed in directory trees (bundles) that can be version-controlled (e.g., in git) and cloned across systems (source: `google_open_knowledge_format.md`).

## Bundle Directory Structure
OKF organizes concepts in directories where files represent unique concepts:
* **Knowledge Bundle**: A directory tree containing concept files. The Concept ID is the file path minus the `.md` suffix (source: `google_open_knowledge_format.md`).
* **Reserved Files**: Filenames `index.md` (directory listings/contents) and `log.md` (chronological update history) are reserved and cannot be concept names (source: `google_open_knowledge_format.md`).

## Concept Document Schema
Each concept file is a UTF-8 Markdown file containing two components (source: `google_open_knowledge_format.md`):
1. **YAML Frontmatter**: Delimited by `---`, requiring a `type` string (e.g., `Methodology`, `Table`, `Metric`) and recommending `title`, `description`, `resource`, `tags`, and `timestamp` (source: `google_open_knowledge_format.md`).
2. **Markdown Body**: Free-form content describing the concept with standard Markdown structure and links (source: `google_open_knowledge_format.md`).

## Related pages
- [[karpathy-llm-wiki]]
- [[log]]
- [[index]]
