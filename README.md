<div align="center">

<a href="https://rajora.live" target="_blank">
<img src="./banner.svg" alt="Rajora AI" width="100%"/>
</a>

<br/>

One infrastructure. Every vertical. No rebuilding the plumbing.

<br/>

[![Platform](https://img.shields.io/badge/Platform-rajora.live-0A0A2E?style=flat-square&logo=safari&logoColor=0077FF&labelColor=05050D)](https://rajora.live)
[![India](https://img.shields.io/badge/Bengaluru%2C_Karnataka-India-FF9933?style=flat-square&logo=google-maps&logoColor=white&labelColor=05050D)](https://rajora.live)
[![Email](https://img.shields.io/badge/rajeev%40rajora.live-Contact-0055CC?style=flat-square&logo=gmail&logoColor=white&labelColor=05050D)](mailto:rajeev@rajora.live)
[![Claude](https://img.shields.io/badge/Anthropic-Claude-0D1117?style=flat-square&logoColor=00D4FF&labelColor=05050D)](https://anthropic.com)
[![Python](https://img.shields.io/badge/Python-Core-0D1117?style=flat-square&logo=python&logoColor=3776AB&labelColor=05050D)](https://rajora.live)
[![TypeScript](https://img.shields.io/badge/TypeScript-Frontend-0D1117?style=flat-square&logo=typescript&logoColor=3178C6&labelColor=05050D)](https://rajora.live)

</div>

---

## What is Rajora AI?

Rajora AI is an AI infrastructure company based in Bengaluru, India.

We build the foundational stack — orchestration, inference, auth, billing, model routing, and automation — so that domain-specific AI products can be launched without rebuilding the same foundation from scratch every time.

Every product we ship — from mental health analytics to e-commerce automation to exam preparation — runs on the same battle-tested core.

**The problem we solve:** Most AI products spend the majority of their engineering time on infrastructure that has nothing to do with their domain — auth systems, billing logic, rate limiting, model serving, API key management. We built that once and made it reusable across every vertical.

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
> Route intelligence across models. Never get locked into one provider.

AION ∞ is Rajora AI's flagship agentic platform deployed on AWS. It routes requests dynamically across Claude, GPT-4, Gemini, and local Ollama — selecting the right model by cost, capability, and latency at runtime. No vendor lock-in. No hardcoded model dependencies.

On the desktop, AION becomes a full OS-level AI agent — controlling applications, automating workflows, capturing screens, generating invoices, managing GitHub repositories, all through natural language.

**What's confirmed inside:**
- LangGraph + LangChain — stateful multi-step agent orchestration
- AES-256-GCM encryption at rest
- Full OS control — PyAutoGUI, mss multi-monitor capture, pynput keyboard/mouse
- AI-powered screen vision — `vision_analyzer.py`
- GitHub automation — `github_executor.py`
- PDF invoice generation — ReportLab
- SQLAlchemy + Alembic — relational DB with migrations
- Tauri (Rust) desktop shell
- Razorpay billing · WebSocket streaming
- 7 dedicated safety modules — intent detection, content filtering, audit logging
- 7 backend documentation guides written

---

### ⚙️ Revive-OS — Revenue Orchestration System
> From 5,000 leads to 10,00,000 — the same system handles it.

Revive-OS is the multi-channel AI decision engine. Routes customer intent across Voice and WhatsApp via Twilio, manages per-channel billing, and coordinates model serving across 9 scale tiers — T1 (5K leads) through T9 (10L leads).

**What's confirmed inside:**
- Voice + WhatsApp channels via Twilio
- RabbitMQ message queue
- Redis state management
- Prometheus + Grafana observability
- Kubernetes deployment via Helm charts
- Koyeb cloud deployment
- `docs/architecture.md` — full system documentation

---

### 🔬 Rajora SLM — Custom Fine-Tuned Model Infrastructure
> Infrastructure to stop calling someone else's API. Training our own models.

The `rajora-slm` platform is Rajora AI's in-house fine-tuning infrastructure. Built on Mistral-7B and Phi-3 using HuggingFace Transformers + PEFT/LoRA (QLoRA 4-bit). Each vertical platform gets its own model variant with self-generated API keys — zero dependency on third-party key infrastructure.

The training pipeline, evaluation framework, and deployment architecture are complete. Fine-tuning in progress.

**8-component microservices architecture:**

| Component | Role |
|---|---|
| `ai_core` | Fine-tune pipeline · model logic |
| `auth_service` | RS256 JWT · python-jose · per-platform API key generation |
| `inference_service` | Custom SLM · vLLM · Koyeb GPU inference |
| `billing_service` | Stripe · Redis Lua · slowapi rate limiting |
| `user_service` | Supabase (PostgreSQL) · session management |
| `scheduler_service` | Cron-based job execution |
| `api_gateway` | Nginx · Qdrant · MinIO · Jaeger · Trivy |
| `shared/` + `sdk/` | Common utilities · Python SDK for consumers |

---

### 🔍 Rajora Search — Hybrid Search Engine
> BM25 + FAISS + Cross-Encoder. Not a wrapper around Google.

A custom 3-layer hybrid search engine built inside Rajora.ai with agentic AI post-processing.

| Layer | Tech | Weight |
|---|---|---|
| Keyword search | BM25 via `rank_bm25` | 40% |
| Dense vector search | FAISS + SentenceTransformer `all-MiniLM-L6-v2` | 60% |
| Reranking | CrossEncoder `ms-marco-MiniLM-L-6-v2` | Final pass |

- Agentic reasoning post-search via `AgenticAISystem`
- SSE streaming results via `/search/stream`
- Wikipedia live crawl fallback

---

## Vertical Products

> The same infrastructure. Different domains. Real businesses.

### 🏥 HopeSense-AI `🔒 Private` — AWS
Burnout detection and mental health analytics for organizations. NLP + time-series ML + reinforcement learning feedback loop. HIPAA-aligned. Built because early warning systems for burnout don't exist anywhere at scale.

### 📚 openlearn-ai `Public`
AI-powered exam preparation for CBSE, UPSC, JEE, and SSC — India's most competitive exams. Full RAG pipeline (Qdrant + BAAI/bge-m3), Faster-Whisper STT, Coqui XTTS TTS, spaced repetition engine. COPPA-compliant. Kubernetes-deployed.

### 🛒 WickerIndia `Public` → [wicker.rajora.live](https://wicker.rajora.live/)
Production e-commerce platform with 9 confirmed automation workflows via n8n: Order Processing · Fraud Detection · Abandoned Cart Recovery · Inventory Monitoring · Customer Support Agent · Marketing Automation · Sales Analytics · Error Handling · Internal Business Automation. AWS S3 + CloudFront CDN · Backend: Render · Frontend: Vercel · GitHub Actions CI/CD.

### 💰 finserve2india `🔒 Private` → [finserve2india.com](https://www.finserve2india.com/)
Financial services platform built specifically for the Indian market and its regulatory context.

### 🌐 AION-v1 `Live` → [rajora.co.in](https://rajora.co.in/)
Real-time AI web interface — chat, voice interaction, intelligent search. React 18 + Node.js + MongoDB Atlas. Blue-Green zero-downtime deployment via Shadow Routing on AWS Elastic Beanstalk.

---

## Repository Index

| Repository | What It Does | Stack | Access |
|---|---|---|---|
| `revive-os` | Revenue Orchestration — Voice + WhatsApp, 9 tiers, K8s/Helm | Python · Redis · RabbitMQ · Twilio | 🔒 |
| `Rajora.ai` | AION ∞ — agentic AI platform + hybrid search engine | Python · LangGraph · FAISS · BM25 | 🔒 |
| `AION-v1` | Live AI web app → [rajora.co.in](https://rajora.co.in/) | React 18 · Node.js · MongoDB · AWS EB | 🔒 |
| `aion-bot` | Desktop AI agent — OS control, vision, invoices, GitHub | Python · FastAPI · Tauri · LangGraph | Public |
| `rajora-slm-fine-tune-for-revive-os` | Custom SLM — 8 services, QLoRA, self-generated API keys | Python · vLLM · Supabase · Redis | Public |
| `HopeSense-AI` | Burnout detection — NLP · RL · HIPAA · AWS | Python · AWS · FastAPI | 🔒 |
| `openlearn-ai` | AI exam prep — RAG · STT · TTS · K8s | Python · Next.js · FastAPI · Qdrant | Public |
| `WickerIndia` | E-commerce — 9 n8n workflows · AWS · Render · Vercel | Python · FastAPI · MongoDB · boto3 | Public |
| `finserve2india` | Financial services India → [finserve2india.com](https://www.finserve2india.com/) | HTML · CSS | 🔒 |
| `rajora-demoooo` | Institution showcase → [rajora-ai-institution-website.vercel.app](https://rajora-ai-institution-website.vercel.app/) | Next.js · Tailwind · Vercel | Public |
| `rajora-ai-institution-deploy` | Institution deployment layer | Next.js · TypeScript · Vercel | 🔒 |
| `tool-app` | AI tools directory → [tool-app-chi.vercel.app](https://tool-app-chi.vercel.app/) | React · TypeScript · Vite | Public |

---

## Technology Foundation

<table>
<tr>
<td valign="top" width="50%">

**Languages**

![Python](https://img.shields.io/badge/-Python-05050D?style=flat-square&logo=python)
![TypeScript](https://img.shields.io/badge/-TypeScript-05050D?style=flat-square&logo=typescript)
![JavaScript](https://img.shields.io/badge/-JavaScript-05050D?style=flat-square&logo=javascript)
![Rust](https://img.shields.io/badge/-Rust-05050D?style=flat-square&logo=rust)
![Shell](https://img.shields.io/badge/-Shell-05050D?style=flat-square&logo=gnubash)

**AI & Agent Stack**

![LangGraph](https://img.shields.io/badge/-LangGraph-05050D?style=flat-square)
![LangChain](https://img.shields.io/badge/-LangChain-05050D?style=flat-square)
![Claude](https://img.shields.io/badge/-Anthropic_Claude-05050D?style=flat-square)
![OpenAI](https://img.shields.io/badge/-OpenAI-05050D?style=flat-square&logo=openai)
![Gemini](https://img.shields.io/badge/-Google_Gemini-05050D?style=flat-square&logo=google)
![Ollama](https://img.shields.io/badge/-Ollama-05050D?style=flat-square)
![vLLM](https://img.shields.io/badge/-vLLM-05050D?style=flat-square)
![Qdrant](https://img.shields.io/badge/-Qdrant-05050D?style=flat-square)
![FAISS](https://img.shields.io/badge/-FAISS-05050D?style=flat-square)

**Backend**

![FastAPI](https://img.shields.io/badge/-FastAPI-05050D?style=flat-square&logo=fastapi)
![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-05050D?style=flat-square&logo=postgresql)
![MongoDB](https://img.shields.io/badge/-MongoDB-05050D?style=flat-square&logo=mongodb)
![Redis](https://img.shields.io/badge/-Redis-05050D?style=flat-square&logo=redis)
![RabbitMQ](https://img.shields.io/badge/-RabbitMQ-05050D?style=flat-square&logo=rabbitmq)
![Supabase](https://img.shields.io/badge/-Supabase-05050D?style=flat-square&logo=supabase)

</td>
<td valign="top" width="50%">

**Frontend & Desktop**

![React](https://img.shields.io/badge/-React_18-05050D?style=flat-square&logo=react)
![Next.js](https://img.shields.io/badge/-Next.js_14-05050D?style=flat-square&logo=next.js)
![Tailwind](https://img.shields.io/badge/-Tailwind_CSS-05050D?style=flat-square&logo=tailwindcss)
![Vite](https://img.shields.io/badge/-Vite-05050D?style=flat-square&logo=vite)
![Tauri](https://img.shields.io/badge/-Tauri_(Rust)-05050D?style=flat-square&logo=tauri)

**Infrastructure & Deployment**

![AWS](https://img.shields.io/badge/-AWS-05050D?style=flat-square&logo=amazon-aws)
![Docker](https://img.shields.io/badge/-Docker-05050D?style=flat-square&logo=docker)
![Kubernetes](https://img.shields.io/badge/-Kubernetes-05050D?style=flat-square&logo=kubernetes)
![GitHub Actions](https://img.shields.io/badge/-GitHub_Actions-05050D?style=flat-square&logo=github-actions)
![Vercel](https://img.shields.io/badge/-Vercel-05050D?style=flat-square&logo=vercel)
![Koyeb](https://img.shields.io/badge/-Koyeb-05050D?style=flat-square)
![Nginx](https://img.shields.io/badge/-Nginx-05050D?style=flat-square&logo=nginx)

**Security & Code Quality**

![JWT](https://img.shields.io/badge/-RS256_JWT-05050D?style=flat-square)
![AES](https://img.shields.io/badge/-AES--256--GCM-05050D?style=flat-square)
![Prometheus](https://img.shields.io/badge/-Prometheus-05050D?style=flat-square&logo=prometheus)
![Grafana](https://img.shields.io/badge/-Grafana-05050D?style=flat-square&logo=grafana)
![Trivy](https://img.shields.io/badge/-Trivy-05050D?style=flat-square)
![Jaeger](https://img.shields.io/badge/-Jaeger-05050D?style=flat-square)

**Payments & Automation**

![Razorpay](https://img.shields.io/badge/-Razorpay-05050D?style=flat-square)
![Stripe](https://img.shields.io/badge/-Stripe-05050D?style=flat-square&logo=stripe)
![n8n](https://img.shields.io/badge/-n8n-05050D?style=flat-square&logo=n8n)
![Playwright](https://img.shields.io/badge/-Playwright-05050D?style=flat-square&logo=playwright)
![PyAutoGUI](https://img.shields.io/badge/-PyAutoGUI-05050D?style=flat-square)
![Twilio](https://img.shields.io/badge/-Twilio-05050D?style=flat-square&logo=twilio)

</td>
</tr>
</table>

---

## Live Products

| Product | URL |
|---|---|
| 🌐 AION-v1 — AI web interface | [rajora.co.in](https://rajora.co.in/) |
| 🛒 WickerIndia — e-commerce | [wicker.rajora.live](https://wicker.rajora.live/) |
| 💰 FinServe2India — finance | [finserve2india.com](https://www.finserve2india.com/) |
| 🛠️ Tool App — AI tools directory | [tool-app-chi.vercel.app](https://tool-app-chi.vercel.app/) |
| 🏫 Institution site | [rajora-ai-institution-website.vercel.app](https://rajora-ai-institution-website.vercel.app/) |
| 🚀 Institution deploy | [rajora-ai-institution-deploy.vercel.app](https://rajora-ai-institution-deploy.vercel.app/) |
| 🔗 Rajora portal | [rajora.netlify.app](https://rajora.netlify.app/) |

---

## Founder

**Er. Rajeev Rajora** — Founder & Principal Architect, Rajora AI

Building production-grade AI infrastructure from Bengaluru — one system at a time.

📍 Bengaluru, Karnataka, India &nbsp;·&nbsp; 🌐 [rajora.live](https://rajora.live/) &nbsp;·&nbsp; ✉️ [rajeev@rajora.live](mailto:rajeev@rajora.live)

---

<div align="center">

**Rajora AI**

*Built in India. Built for scale. Built to last.*

[![Visit](https://img.shields.io/badge/rajora.live-Visit_Platform-0077FF?style=flat-square&logo=safari&labelColor=05050D)](https://rajora.live/)

</div>
