# LLM Wiki (Personal Knowledge Base)

A persistent, compounding personal knowledge base maintained by an AI agent (Claude Code). This repository implements the **LLM Wiki pattern** proposed by Andrej Karpathy, structured using Google's **Open Knowledge Format (OKF)** specification.

---

## 🌟 Core Concepts

### Compile, Don't Just Retrieve (Karpathy's LLM Wiki Pattern)
Traditional Retrieval-Augmented Generation (RAG) is transient: when you ask a question, the LLM retrieves raw chunks, attempts to synthesize them, and then "forgets" the context.
By contrast, this **LLM Wiki** is a persistent, compounding artifact. When new source material is ingested, the AI agent compiles the information upfront:
1. It updates existing entity and concept pages.
2. It revises topic summaries.
3. It cross-links pages using `[[wiki-links]]`.
4. It notes contradictions or updates.

When querying the wiki, the LLM uses this pre-compiled, highly structured knowledge graph instead of raw, unorganized files, enabling faster, more accurate, and cross-document reasoning.

### Agent-Friendly Standardization (Google's Open Knowledge Format)
Google's **Open Knowledge Format (OKF)** is a minimalist, vendor-neutral specification to structure organizational knowledge for AI agents:
- **Concept-as-a-File**: Each concept/entity has its own Markdown file.
- **YAML Frontmatter**: Provides lightweight, queryable metadata fields (e.g., `type`, `title`, `description`).
- **Markdown Body**: Contains the actual content read by humans and parsed by agents.
- **Reserved Files**: Uses special index (`index.md`) and log (`log.md`) files for navigation and tracking changes.

---

## 📁 Repository Structure

```text
llm_wiki/
├── README.md         # This repository overview
├── Claude.md         # The Schema (rules, formats, and agent instructions)
├── raw/              # Immutable raw sources (PDFs, articles, notes) - NEVER modified
└── wiki/             # The compiled knowledge base (maintained by the LLM agent)
    ├── index.md      # Wiki Table of Contents & Navigation Map
    ├── log.md        # Append-only chronological history of updates
    └── *.md          # Individual wiki/concept pages
```

---

## ⚙️ How It Works (Ingest & Query Workflows)

### 📥 1. Ingestion Workflow
When a new source file is dropped into `raw/`:
1. The AI agent reads the source document.
2. The agent discusses key takeaways with the user.
3. The agent compiles it into `wiki/` by creating/updating concept pages.
4. The agent updates `wiki/index.md` and appends a log entry to `wiki/log.md`.

### 🔍 2. Query Workflow
When you ask a question:
1. The agent reads `wiki/index.md` to identify relevant concept files.
2. It traverses and parses those files to synthesize the answer.
3. Any new insights or comparisons generated can be saved back to the wiki as new pages.

### 🧼 3. Linting Workflow
Periodically, the agent audits the wiki to:
- Identify orphan pages (no inbound links).
- Identify missing links/cross-references.
- Find contradictions or outdated information across pages.

---

## 🛠️ References & Specifications
* **Karpathy's LLM Wiki Gist**: [raw/karpathy_llm_wiki.md](file:///k:/Tech/Projects/llm_wiki/raw/karpathy_llm_wiki.md) / Ingested page: [wiki/karpathy-llm-wiki.md](file:///k:/Tech/Projects/llm_wiki/wiki/karpathy-llm-wiki.md)
* **Google's Open Knowledge Format**: [raw/google_open_knowledge_format.md](file:///k:/Tech/Projects/llm_wiki/raw/google_open_knowledge_format.md) / Ingested page: [wiki/google-open-knowledge-format.md](file:///k:/Tech/Projects/llm_wiki/wiki/google-open-knowledge-format.md)
