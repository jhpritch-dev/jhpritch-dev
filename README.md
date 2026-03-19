# John H. Pritchard

**AI Infrastructure Engineer | Distributed Inference Systems | Self-Hosted LLM Deployment | Privacy-First Architecture**

📍 Gainesville, FL (Remote) · 📧 jhpritch@hotmail.com

---

I help organizations run AI on their own terms — on their hardware, behind their firewall, under their control.

Most of my career has been in technical systems: embedded controllers, wireless telemetry, distributed architectures. Over the last decade, that work converged with containerized infrastructure and local LLM deployment. I enjoy solving the practical problems that come with running AI in resource-constrained, privacy-sensitive environments — the kind of work where things need to actually run reliably, not just demo well.

---

## 🔧 What I'm Working On

### [BIFROST — Distributed AI Inference Router](https://github.com/jhpritch-dev/bifrost-platform) *(Active Development)*

> Route smarter. Infer locally. Escalate only when necessary.

Privacy-first inference middleware that routes AI requests across a heterogeneous 3-node GPU fleet based on cognitive complexity — achieving **85–92% cost savings** versus cloud-only approaches. Every request is classified into one of four complexity bands (TRIVIAL / MODERATE / COMPLEX / FRONTIER) and dispatched to the most capable available local model before any cloud API is considered.

**Core capabilities:**
- **Complexity Router** — LangGraph-based routing pipeline with learned NPU classifier; four-band dispatch with structured handoff artifacts between tiers
- **AUTOPILOT** — Autonomous parallel execution engine: decomposes tasks into a dependency-ordered DAG, runs subtasks in parallel waves across the local tier hierarchy, applies four-level semantic verification, and escalates to cloud only after exhausting local capacity
- **Arbiter** — Fleet health monitor and mode controller (JARVIS full-local / WORKSHOP hybrid / WORKSHOP-OFFLINE zero-egress privacy mode)
- **Micro-inference tier** — Dedicated accelerators for embedding and classification (Vega 8 iGPU + XDNA 2 NPU) with zero contention against generative inference workloads
- **BIFROST Portal** — React ops dashboard: live fleet status, routing metrics, AUTOPILOT launcher, profile switching, and mode control

**Fleet:** RX 9070 XT (16GB, Tier 1a) · RX 5700 XT + Vega 8 (Tier 1a-hearth + micro-inference, 24/7 UPS) · Radeon 8060S 96GB unified + XDNA 2 NPU (Tier 1b / 2 / 2.5 + classifier)

`Python` `FastAPI` `LangGraph` `Pydantic v2` `Ollama` `ChromaDB` `Prometheus` `Grafana` `FluxCD` `k3d` `FastMCP` `React`

---

### [Bifrost Docs — Household Document RAG System](https://github.com/jhpritch-dev/bifrost--docs)
End-to-end document intelligence pipeline: monitors a shared network drive for incoming documents, OCRs and classifies them via Paperless-ngx, generates vector embeddings through Ollama, and provides semantic search and AI-powered chat through Open WebUI + Qdrant. Dual-profile architecture — a full GPU-accelerated dev stack (AMD ROCm on RX 9070) and a lean CPU-only production server profile running ~6-7GB RAM. Includes a custom Python bridge service for document chunking and embedding, n8n workflow automation for bill due-date extraction, and ntfy push notifications.

### [Windows Docker Home Server Stack](https://github.com/jhpritch-dev/windows-docker-homeserver)
Production Docker Compose stack running 11 containers on Windows 10/11 Pro with Docker Desktop + WSL2. Manages Immich (400K+ photo library with VectorChord-accelerated PostgreSQL), Home Assistant for smart home automation, ownCloud for file sync, Jellyfin for media streaming, and automated backups via Duplicati — all orchestrated across a tiered storage architecture (10TB media pool, SSD databases, HDD caches). Includes setup automation, database backup scripts, and VHDX maintenance tooling.

### [AI-Powered Episcopal Bulletin Generation System](https://github.com/jhpritch-dev/church-ai-infrastructure)
7-container Docker Compose stack (Ollama, PostgreSQL, Redis, SurrealDB, Paperless-NGX, FastAPI, Flask) with 48GB managed memory and an offline-first 4-tier fallback system. Built to solve a real weekly workflow problem — automating document production that used to take hours of manual effort.

### [AI-Powered Choral Anthem Planning System (Choir Meta)](https://github.com/jhpritch-dev/choir-meta)
Three-tier architecture: SQLite with FTS5 full-text search, Express.js REST API, Electron desktop client. Includes an OCR pipeline for catalog digitization, fuzzy deduplication, and AI agent integration for recommendations.

### [Automated Photography Preset Generation System](https://github.com/jhpritch-dev/lightroom-preset-automation)
Python automation producing 49 Adobe XMP preset files from structured recipes. Template-driven generation pipeline with multi-tier commercial packaging — similar patterns to infrastructure-as-code workflows.

---

## 🛠 Tech Stack

| Domain | Tools |
|---|---|
| **AI/ML** | Ollama, LangGraph, RAG pipelines, ChromaDB, Qdrant, vector embeddings, document processing, NPU inference |
| **Inference** | Distributed routing, complexity classification, autonomous agent orchestration, local-first LLM deployment |
| **Infrastructure** | Docker, k3d, FluxCD, multi-service orchestration, 10TB+ storage architecture, backup/DR, system monitoring |
| **Data** | PostgreSQL, Redis, SurrealDB, SQLite/FTS5, Qdrant, Prometheus, Grafana |
| **Networking** | Tailscale/WireGuard, VPN gateway, VLANs, network segmentation, 2.5GbE |
| **Automation** | n8n, FastMCP, Watchtower, PowerShell/Bash scripting, CI/CD |
| **Development** | Python, JavaScript/Node.js, FastAPI, Express.js, React, Git |
| **Systems** | Linux (Ubuntu/Debian), Windows Server, WSL2, Docker Desktop, AMD ROCm/Vulkan |

---

## 📐 How I Got Here

My background is unconventional. I hold a doctorate from the University of South Carolina, where my research involved designing wireless telemetry systems and ad hoc WiFi networks for real-time data collection. I've spent 30+ years maintaining CPU-driven embedded control systems — low-voltage wiring, relay logic, microprocessor switching — the kind of work where you learn to troubleshoot methodically because the system won't tell you what's wrong.

About a decade ago I started building home infrastructure out of genuine need: containerized services, software-defined storage, zero-trust networking. When local LLM deployment became practical, the pieces came together naturally. The infrastructure experience, the systems thinking, the preference for solutions you can maintain yourself — it all pointed in the same direction.

I've learned more from things that didn't work the first time than from things that did. That tends to happen when you're building real systems for actual use, not just proofs of concept.

---

## 🎯 What I'm Looking For

Remote AI Infrastructure, DevOps, or Platform Engineering roles where I can contribute to teams deploying AI capabilities thoughtfully — self-hosted, privacy-aware, and built to last.

I'm at my best when I can dig into a problem, build something that works, document it clearly, and hand it off so others can maintain it. If that sounds useful to your team, I'd welcome the conversation.

---

*I believe good infrastructure should be owned, not rented.*
