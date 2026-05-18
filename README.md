# Closed-Loop Agentic OS

A guide to building a personal agentic operating system that captures, recalls, reasons, produces, and learns in a continuous loop.

## What Is This?

Most AI tools are open-loop. You prompt, you get a response, it's gone. A closed-loop agentic OS is different:

1. **Captures** meetings, notes, research, and decisions automatically
2. **Recalls** relevant context on demand through semantic search and structured memory
3. **Reasons** through staged pipelines that break complex questions into structured analysis
4. **Produces** branded deliverables (decks, memos, reports) ready to share
5. **Learns** by feeding outputs back into memory so the system improves over time

The "closed" part: every output becomes an input. Your system gets smarter as you use it.

## Who Is This For?

Business leaders, product managers, strategy consultants, and operators who want to multiply their capacity with AI without writing production software.

You don't need a CS degree. You need a clear mental model of what the system does and the willingness to configure it.

## The Five Pillars

Every agentic OS needs these five capabilities, regardless of tooling:

| Pillar | Metaphor | What It Does |
|--------|----------|--------------|
| **Agent Harness** | The Brain | Orchestrates, reasons, plans, and routes tasks to the right workflow |
| **Knowledge + Search** | The Memory | Structured notes, vector search, conversation archives, cross-source recall |
| **Data Layer** | The Senses | Web research, enterprise APIs, document ingestion |
| **Output Engine** | The Hands | Branded documents, slide decks, reports, messages (not just text responses) |
| **Self-Maintenance** | The Nervous System | Scheduled health checks, index refreshes, staleness alerts |

All five are powered by a foundation model (Claude, GPT, Gemini, etc.) that provides reasoning and generation. The model is the engine. The pillars are the vehicle.

## The Closed Loop

```
┌─────────────────────────────────────────────────────────┐
│                                                         │
│   CAPTURE ──→ STORE ──→ RECALL ──→ REASON ──→ PRODUCE  │
│      ↑                                           │      │
│      └───────────── FEEDBACK ←───────────────────┘      │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

- **Capture**: Meeting notes, transcripts, documents, and web research flow in
- **Store**: Content gets chunked, embedded, and indexed into semantic memory (RAG)
- **Recall**: A query fans out across memory tiers to surface relevant context
- **Reason**: Conductor pipelines stage the analysis (intelligence, assessment, sizing, recommendation)
- **Produce**: The output engine generates stakeholder-ready deliverables
- **Feedback**: Deliverables and decisions feed back into memory. Pressure-test results inform the next pass.

## Memory Architecture (Five Tiers)

| Tier | What It Holds | How It's Accessed | Lifespan |
|------|---------------|-------------------|----------|
| **Working** | Current session context | Automatic (agent window) | Session |
| **Structured** | Notes, wikis, project docs | File navigation, search | Persistent |
| **Compiled** | Per-engagement research folders | Direct path access | Engagement |
| **Semantic** | Embedded document chunks | Vector similarity search (RAG) | Refreshed on schedule |
| **Episodic** | Past conversations and transcripts | Pattern search, weekly reviews | Pruned by age |

The power comes from layering. A single query can pull from structured notes, semantic search, and episodic memory at the same time.

## The Wiki (How Knowledge Compounds)

The wiki is where raw information becomes reusable knowledge. Every engagement gets a three-tier folder structure:

```
{engagement}/
├── research/       # Raw sources, findings, phase outputs (immutable once complete)
├── wiki/           # Compiled synthesis: entities, concepts, evolving thesis
│   ├── index.md    # Entry point (always kept current)
│   ├── log.md      # One-line append after every session
│   ├── entities/   # Named things: products, companies, people, systems
│   ├── concepts/   # Ideas, frameworks, market dynamics
│   └── synthesis/  # Evolving thesis documents
└── deliverables/   # Final stakeholder-ready outputs
```

**How it works:**

- **Research stays raw.** Findings go into `research/` and don't get edited after a stage completes. This is your audit trail.
- **The wiki synthesizes.** After each session, the agent checks: did this session produce a new fact, resolved question, or corrected belief? If yes, it updates the relevant wiki page and logs the change. If no, it moves on.
- **Cross-references link everything.** Wiki pages use `[[wikilinks]]` so concepts, entities, and synthesis documents connect to each other. Over time this builds a knowledge graph for the engagement.
- **The index is the front door.** `wiki/index.md` is always the first place to look. It summarizes the current state of what you know.

**What does NOT go in the wiki:**
- Deliverable output (decks, docs, HTML). Those are outputs, not inputs.
- Daily messages (emails, Slack, chat). Not engagement knowledge.
- Sessions where nothing new was learned.

The wiki is what makes the loop "closed." Without it, every session starts from scratch. With it, each session builds on the last.

This wiki pattern is inspired by Andrej Karpathy's [LLM Wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) concept.

## Engagement Tiers

Not everything needs the full stack.

| Tier | Input | What Fires | Output |
|------|-------|------------|--------|
| **Tracking** | "I had a meeting" | Capture + Memory | Filed notes, action items |
| **Research** | "What do we know about X?" | Capture + Memory + Reasoning | Synthesized memo |
| **Standard** | "Build a strategy for Y" | All five pillars | Branded deck or document |
| **Investment-Grade** | "Build a business case" | All five pillars + multiple pipeline stages | Full deliverable package with financial model |

Start simple. Most days are Tier 1. The system scales when you need it.

## Design Principles

- **One strong model.** No fine-tuning, no model routing. Pick one frontier model and use it well.
- **Skill-based architecture.** Each workflow is a self-contained "skill" (a prompt + instructions + constraints). Add capabilities by adding skills, not rewriting the system.
- **Human-in-the-loop.** The operator approves at every decision point. This is augmentation, not automation.
- **Model-independent.** Swap the LLM by changing one setting. Everything else continues.
- **Self-maintaining.** Scheduled health checks, index refreshes, and staleness alerts keep it running without daily intervention.

## Getting Started

### 1. Pick your harness
Choose an AI agent as your orchestration layer: Cursor, Claude Code, Codex, Windsurf, or similar. This is your "brain."

### 2. Set up structured memory
Create a notes vault (Obsidian, Notion, or plain markdown folders). Establish a convention for meeting notes, project wikis, and action items.

### 3. Add semantic search (RAG)
Index your notes into a vector database (ChromaDB, Pinecone, or similar) using an embedding model. Expose it to your agent via MCP or tool integration.

### 4. Write your first skill
A skill is a markdown file that tells your agent how to handle a specific workflow. Examples: "file meeting notes," "research a topic," "draft a follow-up." Start with one.

### 5. Build an output template
Create a branded template (HTML, PPTX, or DOCX) so your system produces stakeholder-ready artifacts, not raw text.

### 6. Close the loop
Configure your system so outputs (filed notes, research, deliverables) feed back into memory automatically. This is what turns a collection of tools into an operating system.

## Example Tool Choices (Not Prescriptive)

| Pillar | Options |
|--------|---------|
| Agent Harness | Cursor, Claude Code, Codex, Windsurf, Aider, LangGraph |
| Knowledge | Obsidian, Notion, ChromaDB, Pinecone, Weaviate |
| Data Layer | Tavily, Firecrawl, Playwright, Jira API, Confluence API |
| Output Engine | python-pptx, python-docx, HTML/CSS, Pandoc |
| Self-Maintenance | cron/launchd, scheduled scripts, health-check skills |

The architecture is tool-agnostic. Pick what fits your workflow and budget.

## What This Repo Does NOT Include

- Production code or a runnable application
- Proprietary data, credentials, or org-specific content
- A complete plug-and-play system

This is a guide and reference architecture. The real value comes from building your own system on top of these patterns, tuned to your role, your domain, and your tools.

---

*Designed by [Sandy Leung](https://github.com/s8ndyleung)*
