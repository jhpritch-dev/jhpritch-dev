# John H. Pritchard

**AI Infrastructure Engineer | Local-First Inference | Agentic Systems & Evaluation | Privacy-First Architecture**

📍 Gainesville, FL (Remote) · 📧 jhpritch@hotmail.com

---

I help organizations run AI on their own terms — on their hardware, behind their firewall, under their control.

Most of my career has been in technical systems: embedded controllers, wireless telemetry, distributed architectures. Over the last decade that work converged with containerized infrastructure and local LLM deployment. I like the practical problems that come with running AI in resource-constrained, privacy-sensitive environments — where things have to run reliably, not just demo well.

---

## 🔧 What I'm Working On

### RAMEAU — Containerized Local-First Inference Platform `Apache-2.0`

The packaged, deployable release of BIFROST. Routing, agent pipelines, and verification in containers, built for on-premises deployment where data can't leave the building.

> **Pre-release.** Under active development. See the repo README for what works and what doesn't.

### BIFROST — Distributed AI Inference Router *(active development)*

> Route smarter. Infer locally. Escalate deliberately.

Privacy-first inference middleware that routes requests across a heterogeneous three-node AMD fleet by task complexity. Each request is classified into one of four bands (TRIVIAL / MODERATE / COMPLEX / FRONTIER) and dispatched to a named tier. Remote tiers are reached by explicit per-workload addressing rather than cascade overflow.

**Measured over a pinned 30-day window:**

| | |
|---|---|
| Tokens processed | 33.9M across 9,013 requests |
| Carried on local hardware | 69% |
| Metered inference spend | ~$0.06 for the window |
| When BIFROST orchestrates its own work | 100% of tokens stay local |
| Failed-tier escalations | 4 of 9,013 requests |
| Versioned releases since Feb 2026 | 158 |

**Core capabilities:**

- **Complexity router** — four-band classification with a learned NPU classifier; twelve local routing tiers (a tier is a routing target, not a server — two tiers may name one endpoint)
- **AUTOPILOT** — decomposes tasks into a dependency-ordered DAG, runs subtasks in parallel waves across the local tier hierarchy, and verifies before returning
- **Verification harness** — emptiness and refusal checks, stub detection, acceptance-criteria coverage, semantic-embedding drift, a blocking sandboxed unit-test gate, and an advisory compile check. Only the unit-test gate blocks; a failure there escalates with its evidence attached
- **Semantic routing cache** — shipped after 3.5 months in shadow mode (47,242 recorded counterfactuals). Serve share 0% → 48.7%, each hit avoiding a classifier call with a p50 of 3,434 ms
- **Arbiter** — fleet health and mode control (full-local / hybrid / zero-egress offline)
- **Micro-inference tier** — dedicated accelerators for embedding and classification, no contention with generative workloads
- **Portal** — React ops dashboard: fleet status, routing metrics, AUTOPILOT launcher, mode control

**Hardware-agnostic by design.** RDNA4, RDNA1, and an XDNA2 NPU across two inference runtimes. Most vendor harnesses are tied to specific silicon; this one isn't. All AMD, no NVIDIA.

`Python` `FastAPI` `LangGraph` `Pydantic v2` `Ollama` `llama.cpp` `ChromaDB` `Qdrant` `Prometheus` `Grafana` `Langfuse` `k3d` `MCP` `React`

---

### The work I'm proudest of is unglamorous

My routing classifier had been failing on 32% of requests for months, invisibly. Timed-out attempts stored a null latency — so no percentile computed over non-null values could contain a failure. The dashboard read *"p99 10.2s, zero calls over deadline."* Every word of that was true, and entirely compatible with a third of traffic failing.

I've also retired two of my own published numbers after auditing them against telemetry and finding I couldn't reproduce the derivation.

**A metric computed only over successes cannot measure failure.** That's now a standing check in how I read any latency panel.

---

## Other Systems

**Household Document RAG** — Paperless-ngx OCR → Ollama embeddings → Qdrant vector search → Open WebUI chat, with automated ingestion, a custom Python bridge for chunking, n8n workflow automation, and ntfy notifications. Dual-profile: GPU dev stack and a lean CPU-only production profile.

**Windows Docker Home Server** — 11-container production stack on Docker Desktop + WSL2: Immich (400K+ photo library on VectorChord-accelerated PostgreSQL), Home Assistant, ownCloud, Jellyfin, Duplicati backups, across a tiered 10TB storage architecture.

**Episcopal Bulletin Generation** — 7-container stack (Ollama, PostgreSQL, Redis, SurrealDB, Paperless-ngx, FastAPI, Flask) with an offline-first fallback system. Built to solve a real weekly workflow problem.

**Choir Meta** — SQLite/FTS5 full-text search, Express REST API, Electron desktop client, OCR catalog digitization, fuzzy deduplication.

**Lightroom Preset Automation** — Python pipeline generating 49 Adobe XMP presets from structured recipes. Template-driven, with multi-tier commercial packaging.

---

## 🛠 Tech Stack

| Domain | Tools |
|---|---|
| **AI / LLM** | Ollama, llama.cpp, LangGraph, MCP, RAG pipelines, ChromaDB, Qdrant, vector embeddings, NPU inference |
| **Inference** | Distributed routing, complexity classification, agent orchestration, evaluation harnesses, local-first deployment |
| **Infrastructure** | Docker, k3d/K3s, multi-service orchestration, 10TB+ storage, backup/DR |
| **Observability** | Prometheus, Grafana, Langfuse, cost tracking, incident response |
| **Data** | PostgreSQL, Redis, SurrealDB, SQLite/FTS5, Qdrant |
| **Networking** | Tailscale/WireGuard, VLANs, segmentation, zero-egress operation |
| **Automation** | n8n, coding agents under a verification harness, PowerShell/Bash |
| **Development** | Python, JavaScript/Node.js, FastAPI, React, Git |
| **Systems** | Linux (Ubuntu/Debian), Windows Server, WSL2, AMD ROCm |

---

## 📐 How I Got Here

My background is unconventional. I hold a doctorate from the University of South Carolina, where my research involved designing wireless telemetry systems and ad hoc WiFi networks for real-time data collection. I spent 30+ years maintaining CPU-driven embedded control systems — low-voltage wiring, relay logic, microprocessor switching — the kind of work where you learn to troubleshoot methodically because the system won't tell you what's wrong.

About a decade ago I started building home infrastructure out of genuine need: containerized services, software-defined storage, zero-trust networking. When local LLM deployment became practical, the pieces came together.

I build with coding agents as my default development mode, governed by a verification harness I wrote and a ruleset where each rule exists because something broke. I don't merge anything an agent produced that hasn't executed.

I've learned more from things that didn't work the first time than from things that did. That tends to happen when you're building real systems for actual use, not proofs of concept.

---

## 🎯 What I'm Looking For

Remote AI infrastructure, LLMOps, applied AI, or platform engineering roles where I can contribute to teams deploying AI thoughtfully — self-hosted, privacy-aware, and built to last.

I'm at my best when I can dig into a problem, build something that works, measure whether it actually worked, document it clearly, and hand it off so others can maintain it.

---

*I believe good infrastructure should be owned, not rented.*
