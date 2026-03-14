<div align="center">

<img src="./banner.svg" alt="Rajora AI" width="100%"/>

<br/>

[![Platform](https://img.shields.io/badge/Platform-rajora.live-0A0A2E?style=flat-square&logo=safari&logoColor=0077FF&labelColor=05050D)](https://rajora.live)
[![India](https://img.shields.io/badge/Bengaluru%2C_Karnataka-India-FF9933?style=flat-square&logo=google-maps&logoColor=white&labelColor=05050D)](https://rajora.live)
[![Email](https://img.shields.io/badge/rajeev%40rajora.live-Contact-0055CC?style=flat-square&logo=gmail&logoColor=white&labelColor=05050D)](mailto:rajeev@rajora.live)
[![Claude](https://img.shields.io/badge/Anthropic-Claude-0D1117?style=flat-square&logoColor=00D4FF&labelColor=05050D)](https://anthropic.com)
[![Python](https://img.shields.io/badge/Python-Core-0D1117?style=flat-square&logo=python&logoColor=3776AB&labelColor=05050D)](https://rajora.live)
[![TypeScript](https://img.shields.io/badge/TypeScript-Frontend-0D1117?style=flat-square&logo=typescript&logoColor=3178C6&labelColor=05050D)](https://rajora.live)

</div>

---

## Mission

> **Rajora AI builds the shared infrastructure layer beneath domain-specific AI applications — so vertical builders never have to re-implement auth, billing, rate limiting, or model serving from scratch.**

One stack. Every domain. No rebuilding the plumbing.

We construct a unified AI platform across four layers: **AGI orchestration → interface agents → multi-channel routing → inference gateway**. Every vertical product we ship — healthcare, education, finance, commerce — runs on the same battle-tested primitives.

---

## Platform Architecture

<div align="center">
<img src="./architecture.svg" alt="Rajora AI Architecture" width="100%"/>
</div>

---

## Core Infrastructure

### `Revive-OS` — AI Revenue Orchestration System
The routing backbone. Manages intent across **Voice and WhatsApp** with a 9-tier scaling architecture, per-channel billing, and model serving coordination.

- Multi-channel decision engine with session management
- 9 scale tiers from prototype to enterprise traffic
- Redis-backed state, circuit breakers, observability-first

---

### `AION ∞` — Agentic Intelligence Platform
A governed, AGI-oriented AI platform. Routes requests dynamically across **Claude, GPT, Gemini, and local Ollama** based on cost and capability. Runs on the desktop as a full OS-control agent.

- LangGraph agent graph for stateful multi-step reasoning
- Playwright browser and OS automation
- WebSocket streaming with Razorpay billing integration

---

### `rajora-slm-fine-tune-for-revive-os` — Inference & API Gateway
The security and inference boundary for the entire platform. Current version: **v15.0.0**

| Service | Port | Responsibility |
|---|---|---|
| `auth_service` | :8001 | RS256 JWT · bcrypt |
| `inference_service` | :8002 | Mistral-7B · Phi-3 · vLLM |
| `billing_service` | :8003 | Stripe · Redis Lua rate limiting |
| `user_service` | :8004 | PostgreSQL · session management |
| `api_gateway` | Nginx | Circuit breakers · routing |

---

## Vertical Applications

### `HopeSense-AI` 🔒
**Domain:** Mental health and workplace burnout detection  
**Why it exists:** Organizations lack early-warning systems for employee burnout before it becomes a crisis.  
NLP pipeline + time-series ML + reinforcement learning feedback loop. HIPAA-aligned, AWS-deployed.

---

### `openlearn-ai`
**Domain:** AI-powered exam preparation — CBSE, UPSC, JEE, SSC  
**Why it exists:** Quality exam prep in India is expensive and inaccessible for most students.  
Full RAG pipeline (Qdrant + BAAI/bge-m3), Faster-Whisper STT, Coqui XTTS TTS, spaced repetition, COPPA-compliant.

---

### `WickerIndia`
**Domain:** E-commerce  
Full-stack product catalog, admin CMS, AWS S3 media handling, n8n webhook automation, deployed on Render.

---

### `finserve2india` 🔒
**Domain:** Financial services for the Indian market  
Compliance-aware, built for Indian regulatory and user context. TypeScript full-stack.

---

## Repository Index

| Repository | Description | Stack | Access |
|---|---|---|---|
| `revive-os` | AI Revenue Orchestration — Voice + WhatsApp, 9 scale tiers | Python · FastAPI · Redis | 🔒 |
| `Rajora.ai` | AION ∞ — governed, agentic, multi-platform AGI | Python | 🔒 |
| `AION-v1` | Real-time chat · voice · intelligent search web app | JavaScript | 🔒 |
| `aion-bot` | Desktop AI agent — OS control, LangGraph, Playwright | Python · FastAPI | Public |
| `rajora-slm-fine-tune-for-revive-os` | Inference gateway — JWT, rate limiting, SLM models | Python · Redis · PostgreSQL | Public |
| `HopeSense-AI` | Burnout detection — NLP, RL, HIPAA-aligned | Python · AWS | 🔒 |
| `openlearn-ai` | AI exam prep — RAG, STT, TTS, spaced repetition | Python · Next.js · FastAPI | Public |
| `WickerIndia` | E-commerce — catalog, CMS, S3, n8n automation | Python · FastAPI · MongoDB | Public |
| `finserve2india` | Financial services — Indian market | TypeScript | 🔒 |
| `rajora-ai-institution-deploy` | Institution deployment layer | TypeScript | 🔒 |
| `tool-app` | AI tools directory — JSON-driven, multi-filter SPA | React · TypeScript · Vite | Public |

---

## Technology Stack

<table>
<tr>
<td valign="top" width="50%">

**Languages**

![Python](https://img.shields.io/badge/-Python-05050D?style=flat-square&logo=python)
![TypeScript](https://img.shields.io/badge/-TypeScript-05050D?style=flat-square&logo=typescript)
![JavaScript](https://img.shields.io/badge/-JavaScript-05050D?style=flat-square&logo=javascript)
![Shell](https://img.shields.io/badge/-Shell-05050D?style=flat-square&logo=gnubash)
![HCL](https://img.shields.io/badge/-HCL-05050D?style=flat-square&logo=terraform)

**AI / ML**

![LangGraph](https://img.shields.io/badge/-LangGraph-05050D?style=flat-square)
![Claude](https://img.shields.io/badge/-Anthropic_Claude-05050D?style=flat-square)
![OpenAI](https://img.shields.io/badge/-OpenAI-05050D?style=flat-square&logo=openai)
![Gemini](https://img.shields.io/badge/-Google_Gemini-05050D?style=flat-square&logo=google)
![Ollama](https://img.shields.io/badge/-Ollama-05050D?style=flat-square)
![vLLM](https://img.shields.io/badge/-vLLM-05050D?style=flat-square)
![Qdrant](https://img.shields.io/badge/-Qdrant-05050D?style=flat-square)

**Backend**

![FastAPI](https://img.shields.io/badge/-FastAPI-05050D?style=flat-square&logo=fastapi)
![PostgreSQL](https://img.shields.io/badge/-PostgreSQL-05050D?style=flat-square&logo=postgresql)
![MongoDB](https://img.shields.io/badge/-MongoDB-05050D?style=flat-square&logo=mongodb)
![Redis](https://img.shields.io/badge/-Redis-05050D?style=flat-square&logo=redis)
![RabbitMQ](https://img.shields.io/badge/-RabbitMQ-05050D?style=flat-square&logo=rabbitmq)

</td>
<td valign="top" width="50%">

**Frontend**

![React](https://img.shields.io/badge/-React_18-05050D?style=flat-square&logo=react)
![Next.js](https://img.shields.io/badge/-Next.js_14-05050D?style=flat-square&logo=next.js)
![Tailwind](https://img.shields.io/badge/-Tailwind_CSS-05050D?style=flat-square&logo=tailwindcss)
![Vite](https://img.shields.io/badge/-Vite-05050D?style=flat-square&logo=vite)

**Infrastructure**

![AWS](https://img.shields.io/badge/-AWS-05050D?style=flat-square&logo=amazon-aws)
![Docker](https://img.shields.io/badge/-Docker-05050D?style=flat-square&logo=docker)
![Kubernetes](https://img.shields.io/badge/-Kubernetes-05050D?style=flat-square&logo=kubernetes)
![Terraform](https://img.shields.io/badge/-Terraform-05050D?style=flat-square&logo=terraform)
![GitHub Actions](https://img.shields.io/badge/-GitHub_Actions-05050D?style=flat-square&logo=github-actions)
![Nginx](https://img.shields.io/badge/-Nginx-05050D?style=flat-square&logo=nginx)

**Security & Observability**

![JWT](https://img.shields.io/badge/-RS256_JWT-05050D?style=flat-square)
![Prometheus](https://img.shields.io/badge/-Prometheus-05050D?style=flat-square&logo=prometheus)
![Grafana](https://img.shields.io/badge/-Grafana-05050D?style=flat-square&logo=grafana)
![Jaeger](https://img.shields.io/badge/-Jaeger-05050D?style=flat-square)
![Trivy](https://img.shields.io/badge/-Trivy-05050D?style=flat-square)

**Automation & Data**

![n8n](https://img.shields.io/badge/-n8n-05050D?style=flat-square&logo=n8n)
![Playwright](https://img.shields.io/badge/-Playwright-05050D?style=flat-square&logo=playwright)
![MinIO](https://img.shields.io/badge/-MinIO-05050D?style=flat-square)

</td>
</tr>
</table>

---

## Ecosystem Links

| | Platform | URL |
|---|---|---|
| 🌐 | Official Platform | [rajora.live](https://rajora.live) |
| 🇮🇳 | Rajora India | [rajora.co.in](https://rajora.co.in) |
| 🛒 | Wicker India | [wicker.rajora.live](https://wicker.rajora.live) |
| 💰 | FinServe2India | [finserve2india.com](https://www.finserve2india.com) |
| 🛠️ | AI Tools Guide | [toolsguidebyrajoraai.netlify.app](https://toolsguidebyrajoraai.netlify.app) |
| 🔗 | Rajora Portal | [rajora.netlify.app](https://rajora.netlify.app) |

---

## Founder

**Er. Rajeev Rajora** — Founder & Principal Architect, Rajora AI

Building the infrastructure layer beneath AI applications — so every vertical can deploy intelligence without rebuilding the foundation.

📍 Bengaluru, Karnataka, India &nbsp;·&nbsp; 🌐 [rajora.live](https://rajora.live) &nbsp;·&nbsp; ✉️ [rajeev@rajora.live](mailto:rajeev@rajora.live)

---

<div align="center">

**Rajora AI** &nbsp;·&nbsp; Bengaluru, Karnataka, India

*AI infrastructure for the next generation of vertical applications.*

</div>