<div align="center">

<a href="https://rajora.live" target="_blank">
<img src="./banner.svg" alt="Rajora AI" width="100%"/>
</a>

<br/>

*One infrastructure. Every vertical. No rebuilding the plumbing.*

<br/>

[![Platform](https://img.shields.io/badge/Platform-rajora.live-0077FF?style=flat-square&logo=safari&logoColor=white&labelColor=0A0A2E)](https://rajora.live)
[![Location](https://img.shields.io/badge/Bengaluru%2C_Karnataka-India-FF9933?style=flat-square&logo=google-maps&logoColor=white&labelColor=1A0A00)](https://rajora.live)
[![Email](https://img.shields.io/badge/rajeev%40rajora.live-Contact-0055CC?style=flat-square&logo=gmail&logoColor=white&labelColor=001030)](mailto:rajeev@rajora.live)
[![Python](https://img.shields.io/badge/Python-3.11%2B-3776AB?style=flat-square&logo=python&logoColor=white&labelColor=1A1A2E)](https://rajora.live)
[![TypeScript](https://img.shields.io/badge/TypeScript-Frontend-3178C6?style=flat-square&logo=typescript&logoColor=white&labelColor=1A1A2E)](https://rajora.live)
[![LangGraph](https://img.shields.io/badge/Orchestration-LangGraph-00AAFF?style=flat-square&logoColor=white&labelColor=0A1A30)](https://rajora.live)
[![Repos](https://img.shields.io/badge/Repositories-13-FFFFFF?style=flat-square&logo=github&logoColor=white&labelColor=1A1A2E)](https://github.com/rajeevrajora77-lab)

</div>

---

<div align="center">

*Agentic AI platform built by one engineer in Bengaluru — production-deployed, multi-model, infrastructure-first.*

</div>

---

## What is Rajora AI?

Rajora AI is an AI infrastructure company based in Bengaluru, India. We build the foundational stack — orchestration, inference, auth, billing, model routing, and automation — so that domain-specific AI products can be launched without rebuilding the same foundation from scratch every time.

Every product we ship — from mental health analytics to e-commerce automation to exam preparation — runs on the same battle-tested core. LangGraph is the orchestration backbone. Claude, GPT-4, Gemini, and Ollama are model targets — routed dynamically by cost, capability, and latency at runtime. No vendor lock-in. No hardcoded dependencies.

**The problem we solve:** Most AI products spend the majority of their engineering time on infrastructure that has nothing to do with their domain — auth systems, billing logic, rate limiting, model serving, API key management. We built that once. Made it reusable. Then deployed it across 13 real repositories and multiple live production products.

---

## Platform Architecture

<div align="center">
<a href="https://rajora.live" target="_blank">
<img src="./architecture.svg" alt="Rajora AI Platform Architecture" width="100%"/>
</a>
</div>

---

## Core Products

### 🧠 AION ∞ — Agentic Intelligence Platform
> *Because no single LLM should be the ceiling of what your software can do.*

AION ∞ is Rajora AI's flagship agentic platform. It routes requests dynamically across Claude, GPT-4, Gemini, and local Ollama — selecting the right model by cost, capability, and latency at runtime. On the desktop, AION becomes a full OS-level AI agent that controls applications, automates workflows, captures screens across multiple monitors, generates PDF invoices, and manages GitHub repositories — all through natural language.

**Confirmed internals:**

| Component | Detail |
|---|---|
| Orchestration | LangGraph 0.2.60 — stateful multi-step agent graphs |
| LangChain | langchain-core + langchain-community 0.3.7 |
| Model targets | Claude 0.27.0 · GPT 1.30.3 · Gemini 0.5.4 · Ollama 0.1.8 (LLaMA3, Mistral, Phi-3) |
| OS control | PyAutoGUI 0.9.54 · mss 9.0.1 multi-monitor · pynput 1.7.6 |
| Screen vision | `vision_analyzer.py` (10KB) — AI-powered screen analysis |
| GitHub automation | `github_executor.py` (34.6KB) — full GitHub API coverage |
| Browser automation | Playwright 1.44.0 — `browser_executor.py` (10KB) |
| File system | `file_executor.py` (9.8KB) |
| Desktop shell | Tauri (Rust) — cross-platform native app |
| Database | SQLAlchemy 2.0.30 + Alembic 1.13.1 · asyncpg 0.29.0 · PostgreSQL |
| Encryption | AES-256-GCM via `cryptography` 42.0.0 — at rest |
| Payments | Razorpay 1.4.1 |
| Streaming | WebSocket real-time |
| PDF generation | ReportLab 4.2.0 |
| Caching | Redis 5.0.4 |
| Logging | loguru 0.7.2 structured logging |
| Safety system | 7 dedicated modules ↓ |

**7-module safety system:**
`intent_detector` · `safety_checker` · `safety_filter` · `content_filter` · `blocked_categories` · `audit_logger` · `SAFETY_SYSTEM.md`

**Code quality:** bandit 1.7.6 + safety 3.2.3 CVE scanning on every commit · pre-commit hooks · mypy 1.8.0 · black 23.12.1 · flake8 7.0.0 · pytest 8.2.0

---

### ⚙️ Revive-OS — Revenue Orchestration System
> *From 5,000 leads to 10,00,000 — the same system handles every tier.*

Revive-OS is the multi-channel AI decision engine for dormant lead reactivation. Routes customer intent across Voice and WhatsApp via Twilio, manages per-channel state with Redis, and coordinates model serving across 9 scale tiers. Built because the gap between a CRM export and actual revenue is a workflow problem — and workflow problems are exactly what AI orchestration solves.

**9 Scale Tiers:** T1 (5,000 leads) → T2 → T3 → T4 → T5 → T6 → T7 → T8 → T9 (10,00,000 leads)

| Layer | Technology |
|---|---|
| Channels | Twilio Voice + WhatsApp |
| Message queue | RabbitMQ |
| State management | Redis |
| Observability | Prometheus + Grafana |
| Deployment | Kubernetes + Helm charts |
| Cloud | Koyeb |

---

### 🔬 Rajora SLM — Custom Fine-Tuned Model Infrastructure
> *Infrastructure to stop calling someone else's API.*

The `rajora-slm` platform is Rajora AI's in-house fine-tuning infrastructure. Built on Mistral-7B and Phi-3 using HuggingFace Transformers + PEFT/LoRA with QLoRA 4-bit quantization. Each vertical platform gets its own model variant with self-generated API keys — zero dependency on third-party key infrastructure.

**8-component microservices architecture:**

| Component | Role |
|---|---|
| `ai_core` | Fine-tune pipeline · model evaluation · inference logic |
| `auth_service` | RS256 JWT · python-jose · per-platform API key generation |
| `inference_service` | Custom SLM · vLLM self-hosted inference (:8002) · Koyeb GPU |
| `billing_service` | Stripe · Redis Lua atomic ops · slowapi rate limiting |
| `user_service` | Supabase (PostgreSQL) · session management |
| `scheduler_service` | Cron-based job runner |
| `api_gateway` | Nginx · Qdrant · MinIO · Jaeger tracing · Trivy scanning |
| `shared/` + `sdk/` | Common utilities · Python SDK for consumers |

---

### 🔍 Rajora Search — 3-Layer Hybrid Search Engine
> *BM25 + FAISS + Cross-Encoder. Not a wrapper around any third-party search API.*

A custom hybrid search engine built inside `Rajora.ai` with agentic AI post-processing and SSE streaming. Built because keyword search misses semantics and pure vector search misses exact matches — so we combined both and let a Cross-Encoder decide.

| Layer | Technology | Weight |
|---|---|---|
| Layer 1 — Keyword | BM25 via `rank_bm25` | 40% |
| Layer 2 — Dense vector | FAISS IndexFlatL2 + SentenceTransformer `all-MiniLM-L6-v2` | 60% |
| Layer 3 — Reranking | CrossEncoder `ms-marco-MiniLM-L-6-v2` | Final pass |

**Post-search:** Agentic reasoning via `AgenticAISystem` · **Streaming:** SSE via `/search/stream` · **Fallback:** Wikipedia live crawl

---

## Vertical Products

> The same infrastructure. Different domains. Real businesses.

### 🏥 HopeSense-AI &nbsp;`🔒 Private` → AWS
**Why it exists:** Early-warning systems for employee burnout don't exist at scale. HR tools measure output — not cognitive load over time.

Burnout detection and mental health analytics for organizations. NLP + time-series ML + reinforcement learning feedback loop. HIPAA-aligned architecture deployed on AWS Elastic Beanstalk.

`Python · FastAPI · AWS S3/EB/CloudFront · Supabase (PostgreSQL)`

---

### 📚 openlearn-ai &nbsp;`Public`
**Why it exists:** JEE, UPSC, SSC — India's most competitive exams have zero AI-native preparation infrastructure. Every existing tool is a PDF viewer with a timer.

AI-powered exam preparation for CBSE, UPSC, JEE, and SSC. Full RAG pipeline (Qdrant + BAAI/bge-m3 embeddings), Faster-Whisper STT, Coqui XTTS text-to-speech, spaced repetition engine, COPPA-compliant, Kubernetes-deployed.

`Python · Next.js 14 · FastAPI · Qdrant · Supabase (PostgreSQL) · Kubernetes`

---

### 🛒 WickerIndia &nbsp;`Public` → [wicker.rajora.live](https://wicker.rajora.live/)
**Why it exists:** D2C furniture brands in India have no production-grade e-commerce infrastructure that isn't Shopify. We built ours.

Production e-commerce platform with 9 confirmed n8n automation workflows:

`Order Processing` · `Fraud Detection` · `Abandoned Cart Recovery` · `Inventory Monitoring` · `Customer Support Agent` · `Marketing Automation` · `Sales Analytics` · `Error Handler` · `Internal Business Automation`

`Python · FastAPI · React 18 + Vite · MongoDB Atlas · AWS S3/EB/CloudFront · Render · Vercel · GitHub Actions CI/CD · Nginx`

---

### 💰 finserve2india &nbsp;`🔒 Private` → [finserve2india.com](https://www.finserve2india.com/)
**Why it exists:** Financial services distribution in India is fragmented across brokers with no digital interface for tier-2 and tier-3 customers.

Compliance-aware financial services platform built for the Indian regulatory context. Lead management system, admin panel, and customer-facing product discovery — designed around RBI and SEBI distribution norms.

`TypeScript · Node.js · Static deployment · Compliance-aware architecture`

---

### 🌐 AION-v1 &nbsp;`Live` → [rajora.co.in](https://rajora.co.in/)
**Why it exists:** A public-facing demo that shows what the platform can do — chat, voice, and search — without requiring someone to install a desktop agent.

Real-time AI web interface with chat, voice interaction, and intelligent search. Blue-Green zero-downtime deployment via Shadow Routing on AWS Elastic Beanstalk. Terraform infrastructure-as-code.

`React 18 · Node.js · MongoDB Atlas · AWS EB · Terraform · Jest`

---

## Repository Index

| Repository | What It Does | Stack | Deployment | Access |
|---|---|---|---|---|
| `revive-os` | AI Revenue Orchestration — Twilio Voice+WA, 9 scale tiers T1(5K)→T9(10L leads), Helm/K8s | Python · FastAPI · Redis · RabbitMQ · Twilio | Koyeb | 🔒 |
| `Rajora.ai` | AION ∞ — agentic AI platform + 3-layer hybrid search (BM25+FAISS+CrossEncoder) | Python · LangGraph · FAISS · BM25 | Koyeb / Railway | 🔒 |
| `AION-v1` | Live AI web app — chat, voice, search, Blue-Green deploy in progress | React 18 · Node.js · MongoDB · AWS EB · Terraform | AWS EB → [rajora.co.in](https://rajora.co.in/) | 🔒 |
| `aion-bot` | Desktop AI agent — OS control, screen vision, GitHub automation (34.6KB), PDF invoices, AES-256 | Python · FastAPI · Tauri · LangGraph · SQLAlchemy | AWS | Public |
| `rajora-slm-fine-tune-for-revive-os` | Custom fine-tuned SLM — 8 microservices, QLoRA 4-bit pipeline, per-platform API keys, Python SDK | Python · vLLM · Supabase · Redis · Koyeb | Koyeb | Public |
| `HopeSense-AI` | Burnout detection — NLP + time-series ML + RL feedback loop, HIPAA-aligned | Python · AWS · FastAPI · Supabase | AWS EB | 🔒 |
| `openlearn-ai` | AI exam prep CBSE/UPSC/JEE/SSC — RAG, STT, TTS, spaced repetition, COPPA, K8s | Python · Next.js · FastAPI · Qdrant | Kubernetes | Public |
| `WickerIndia` | E-commerce — 9 n8n workflows, AWS S3+EB+CloudFront, GitHub Actions CI/CD | Python · FastAPI · MongoDB · boto3 | Render + Vercel | Public |
| `finserve2india` | Financial services India — lead management, admin panel, compliance-aware | TypeScript · Node.js | Static | 🔒 |
| `rajora-demoooo` | Institution showcase site | Next.js · Tailwind · Vercel | Vercel | 🔒 |
| `rajora-ai-institution-deploy` | Institution deployment layer | Next.js · TypeScript · Vercel | Vercel | 🔒 |
| `tool-app` | AI tools directory — JSON-driven, multi-filter SPA | React · TypeScript · Vite | Vercel | Public |
| `rajeevrajora77-lab` | Organization profile | Markdown | GitHub | Public |

---

## Technology Foundation

<table>
<tr>
<td valign="top" width="50%">

**AI / Orchestration**

![LangGraph](https://img.shields.io/badge/-LangGraph_0.2.60-0A1A30?style=flat-square&logoColor=00AAFF)
![LangChain](https://img.shields.io/badge/-LangChain_0.3.7-0A1A30?style=flat-square&logoColor=00AAFF)
![Claude](https://img.shields.io/badge/-Anthropic_Claude-1A0A20?style=flat-square&logoColor=CC88FF)
![OpenAI](https://img.shields.io/badge/-OpenAI_GPT-0A1A0A?style=flat-square&logo=openai&logoColor=74AA9C)
![Gemini](https://img.shields.io/badge/-Google_Gemini-0A1020?style=flat-square&logo=google&logoColor=4285F4)
![Ollama](https://img.shields.io/badge/-Ollama_Local-1A1A1A?style=flat-square&logoColor=AAAAAA)
![HuggingFace](https://img.shields.io/badge/-HuggingFace_Transformers-1A1200?style=flat-square&logo=huggingface&logoColor=FFD21E)
![vLLM](https://img.shields.io/badge/-vLLM_Inference-0A1A10?style=flat-square&logoColor=00DD88)
![FAISS](https://img.shields.io/badge/-FAISS_+_BM25_+_CrossEncoder-0A0A20?style=flat-square&logoColor=8888FF)
![Qdrant](https://img.shields.io/badge/-Qdrant_Vector_DB-1A0A10?style=flat-square&logoColor=DC143C)
![Whisper](https://img.shields.io/badge/-Faster--Whisper_STT-0A1A1A?style=flat-square&logoColor=00CCCC)
![XTTS](https://img.shields.io/badge/-Coqui_XTTS_TTS-0A1A1A?style=flat-square&logoColor=00CCCC)

**Backend & Languages**

![Python](https://img.shields.io/badge/-Python_3.11%2B-1A1A2E?style=flat-square&logo=python&logoColor=3776AB)
![FastAPI](https://img.shields.io/badge/-FastAPI_0.111.0-0A1A18?style=flat-square&logo=fastapi&logoColor=009688)
![NodeJS](https://img.shields.io/badge/-Node.js_+_Express-0A1A0A?style=flat-square&logo=node.js&logoColor=339933)
![TypeScript](https://img.shields.io/badge/-TypeScript-1A1A2E?style=flat-square&logo=typescript&logoColor=3178C6)
![Rust](https://img.shields.io/badge/-Rust_(Tauri)-1A0A0A?style=flat-square&logo=rust&logoColor=CE422B)
![SQLAlchemy](https://img.shields.io/badge/-SQLAlchemy_2.0_+_Alembic-1A1A1A?style=flat-square&logoColor=AAAAAA)
![Pydantic](https://img.shields.io/badge/-Pydantic_v2-1A1A1A?style=flat-square&logoColor=E92063)

**Frontend & Desktop**

![React](https://img.shields.io/badge/-React_18_+_Vite-0A1A2A?style=flat-square&logo=react&logoColor=61DAFB)
![Next.js](https://img.shields.io/badge/-Next.js_14-1A1A1A?style=flat-square&logo=next.js&logoColor=FFFFFF)
![Tailwind](https://img.shields.io/badge/-Tailwind_CSS-0A1A20?style=flat-square&logo=tailwindcss&logoColor=06B6D4)
![Tauri](https://img.shields.io/badge/-Tauri_(Rust_shell)-0A1A1A?style=flat-square&logo=tauri&logoColor=24C8D8)

</td>
<td valign="top" width="50%">

**Databases & Storage**

![MongoDB](https://img.shields.io/badge/-MongoDB_Atlas-0A1A0A?style=flat-square&logo=mongodb&logoColor=47A248)
![Supabase](https://img.shields.io/badge/-Supabase_(PostgreSQL)-0A1A10?style=flat-square&logo=supabase&logoColor=3ECF8E)
![Redis](https://img.shields.io/badge/-Redis_5.0.4-1A0A0A?style=flat-square&logo=redis&logoColor=DC382D)
![MinIO](https://img.shields.io/badge/-MinIO_Object_Storage-1A0A0A?style=flat-square&logo=minio&logoColor=C72E49)

**Infrastructure & DevOps**

![AWS](https://img.shields.io/badge/-AWS_S3_+_EB_+_CloudFront-1A0E00?style=flat-square&logo=amazon-aws&logoColor=FF9900)
![Docker](https://img.shields.io/badge/-Docker_+_Compose-0A1020?style=flat-square&logo=docker&logoColor=2496ED)
![Kubernetes](https://img.shields.io/badge/-Kubernetes_+_Helm-0A1020?style=flat-square&logo=kubernetes&logoColor=326CE5)
![Terraform](https://img.shields.io/badge/-Terraform-1A0A2A?style=flat-square&logo=terraform&logoColor=7B42BC)
![GitHub Actions](https://img.shields.io/badge/-GitHub_Actions_CI%2FCD-1A1A1A?style=flat-square&logo=github-actions&logoColor=FFFFFF)
![Nginx](https://img.shields.io/badge/-Nginx-0A1A0A?style=flat-square&logo=nginx&logoColor=009639)

**Security & Compliance**

![AES](https://img.shields.io/badge/-AES--256--GCM_Encryption-1A1A1A?style=flat-square&logoColor=AAAAAA)
![JWT](https://img.shields.io/badge/-RS256_JWT-1A1A1A?style=flat-square&logoColor=AAAAAA)
![bcrypt](https://img.shields.io/badge/-passlib_%5Bbcrypt%5D-1A1A1A?style=flat-square&logoColor=AAAAAA)
![HIPAA](https://img.shields.io/badge/-HIPAA--aligned-0A1A10?style=flat-square&logoColor=00CC66)
![COPPA](https://img.shields.io/badge/-COPPA--compliant-0A1A10?style=flat-square&logoColor=00CC66)
![bandit](https://img.shields.io/badge/-bandit_+_safety_CVE_scan-1A0A0A?style=flat-square&logoColor=FF4444)
![pytest](https://img.shields.io/badge/-pytest_+_mypy_+_black_+_flake8-1A1A1A?style=flat-square&logo=pytest&logoColor=AAAAAA)

**Observability & Automation**

![Prometheus](https://img.shields.io/badge/-Prometheus_+_Grafana-1A0A00?style=flat-square&logo=prometheus&logoColor=E6522C)
![Jaeger](https://img.shields.io/badge/-Jaeger_Tracing-1A1A1A?style=flat-square&logoColor=AAAAAA)
![Twilio](https://img.shields.io/badge/-Twilio_Voice_+_WhatsApp-1A0A10?style=flat-square&logo=twilio&logoColor=F22F46)
![n8n](https://img.shields.io/badge/-n8n_9_workflows-1A0A10?style=flat-square&logo=n8n&logoColor=EA4B71)
![Razorpay](https://img.shields.io/badge/-Razorpay-1A1A1A?style=flat-square&logoColor=2C8EF4)
![Stripe](https://img.shields.io/badge/-Stripe-0A0A1A?style=flat-square&logo=stripe&logoColor=008CDD)
![RabbitMQ](https://img.shields.io/badge/-RabbitMQ-1A0800?style=flat-square&logo=rabbitmq&logoColor=FF6600)
![Playwright](https://img.shields.io/badge/-Playwright_1.44.0-0A1A0A?style=flat-square&logo=playwright&logoColor=2EAD33)

</td>
</tr>
</table>

---

## Live Products

| Product | URL | Status |
|---|---|---|
| 🌐 AION-v1 — AI web interface | [rajora.co.in](https://rajora.co.in/) | ✅ Live |
| 🛒 WickerIndia — e-commerce platform | [wicker.rajora.live](https://wicker.rajora.live/) | ✅ Live |
| 💰 FinServe2India — financial services | [finserve2india.com](https://www.finserve2india.com/) | ✅ Live |
| 🛠️ Tool App — AI tools directory | [tools.rajora.live](https://tool-app-chi.vercel.app/) | ✅ Live |

---

## Founder

**Er. Rajeev Rajora** — Founder & Principal Architect, Rajora AI

13 repositories. 7 deployed products. 1 engineer.
Architect by design. Builder in execution. Bengaluru, India.

Every line of infrastructure documented here was designed, written, and deployed by one person — from the fine-tuning pipeline to the Kubernetes Helm charts to the 34.6KB GitHub automation engine inside `aion-bot`.

📍 Bengaluru, Karnataka, India &nbsp;·&nbsp; 🌐 [rajora.live](https://rajora.live/) &nbsp;·&nbsp; ✉️ [rajeev@rajora.live](mailto:rajeev@rajora.live)

---

<div align="center">

**Rajora AI**

*Built in India. Built for scale. Built to last.*

**If you're building an AI product and spending most of your time on infrastructure — [let's talk](mailto:rajeev@rajora.live).**

[![Visit Platform](https://img.shields.io/badge/rajora.live-Visit_Platform-0077FF?style=flat-square&logo=safari&labelColor=0A0A2E)](https://rajora.live/)

</div>
