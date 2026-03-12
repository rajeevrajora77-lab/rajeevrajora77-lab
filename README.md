# Er. Rajeev Rajora

Founder & Principal Architect at **[Rajora AI](https://rajora.live)**
— building AI infrastructure that operates at the layer below applications.

Bengaluru · [rajora.live](https://rajora.live) · [rajeev@rajora.live](mailto:rajeev@rajora.live)

---

## What Rajora AI Builds

Revive-OS is the orchestration core — a multi-channel AI decision engine that routes intent, manages billing, and coordinates model serving across 9 scale tiers. Above it, AION acts as the desktop-native intelligence layer: a LangGraph agent running on FastAPI that controls the entire OS via natural language, routing requests through Claude, GPT, Gemini, or local Ollama depending on cost and capability. HopeSense-AI, WickerIndia, openlearn-ai, and finserve2india are vertical applications that consume this infrastructure — each domain-specific, each with its own data layer, but all sharing the same auth, rate-limiting, and model-serving primitives. The goal is a single AI infrastructure stack that any vertical business can deploy on, without rebuilding the same auth, billing, or inference plumbing from scratch.

---

## Ecosystem

| Repository | What it does | Stack |
|---|---|---|
| [revive-os](https://github.com/rajeevrajora77-lab/revive-os) 🔒 | AI Revenue Orchestration System — multi-channel decision engine across Voice + WhatsApp. 9 scale tiers. | Python · FastAPI · Redis |
| [Rajora.ai](https://github.com/rajeevrajora77-lab/Rajora.ai) 🔒 | AION ∞ — governed, agentic, AGI-oriented AI platform. Multi-platform. | Python |
| [AION-v1](https://github.com/rajeevrajora77-lab/AION-v1) 🔒 | Real-time chat, intelligent search, voice interaction. Production-ready AI web application. | JavaScript |
| [aion-bot](https://github.com/rajeevrajora77-lab/aion-bot) | Desktop AI agent. Controls entire OS via natural language — Claude, GPT, Gemini, Ollama. LangGraph agent graph, Playwright automation, WebSocket streaming, Razorpay billing. | Python · FastAPI · LangGraph |
| [rajora-slm-fine-tune-for-revive-os](https://github.com/rajeevrajora77-lab/rajora-slm-fine-tune-for-revive-os) | Inference and API gateway — RS256 JWT, Redis Lua token bucket, per-service circuit breakers, Stripe billing, Mistral-7B + Phi-3 via Together AI, optional vLLM. | Python · Redis · PostgreSQL |
| [HopeSense-AI](https://github.com/rajeevrajora77-lab/HopeSense-AI) 🔒 | Burnout detection platform — NLP, time-series ML, reinforcement learning, HIPAA-aligned. | Python · AWS |
| [openlearn-ai](https://github.com/rajeevrajora77-lab/openlearn-ai) | Open-source AI learning platform for CBSE, UPSC, JEE, SSC. RAG pipeline (Qdrant + BAAI/bge-m3), Faster-Whisper STT, Coqui XTTS TTS, spaced repetition, COPPA-compliant. | Python · Next.js · FastAPI |
| [WickerIndia](https://github.com/rajeevrajora77-lab/WickerIndia) | Full-stack e-commerce — product catalog, admin CMS, AWS S3 media, n8n webhook automation, Render deployment. | Python · FastAPI · MongoDB |
| [finserve2india](https://github.com/rajeevrajora77-lab/finserve2india) 🔒 | Financial services platform built for the Indian market. | TypeScript |
| [rajora-ai-institution-deploy](https://github.com/rajeevrajora77-lab/rajora-ai-institution-deploy) 🔒 | Institution deployment layer. | TypeScript |
| [tool-app](https://github.com/rajeevrajora77-lab/tool-app) | Static SPA — AI & developer tools intelligence directory. JSON-driven database, multi-filter UI (category, segment, type, free-tier), no backend. | React · TypeScript · Vite |

🔒 = Private repository

---

## Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                     AGI PLATFORM LAYER                          │
│  Rajora.ai / AION ∞  [Python · Multi-platform · Governed AGI]  │
└───────────────────────────┬─────────────────────────────────────┘
                            │
          ┌─────────────────┴──────────────────┐
          │                                    │
┌─────────▼──────────┐              ┌──────────▼──────────┐
│    AION-v1         │              │    aion-bot          │
│  Web AI App        │              │  Desktop AI Agent    │
│  [JavaScript]      │              │  FastAPI :8000       │
│  Real-time chat    │              │  LangGraph agent     │
│  Voice · Search    │              │  Playwright browser  │
└────────────────────┘              │  desktop_control     │
                                    │  WebSocket /ws       │
                                    └──────────┬───────────┘
                                               │
┌──────────────────────────────────────────────▼───────────────────┐
│                  ORCHESTRATION LAYER — Revive-OS                  │
│         Multi-channel (Voice + WhatsApp) · 9 scale tiers         │
│                   [Python · FastAPI · Redis]                      │
└──────────────────────────────────────────────┬───────────────────┘
                                               │
┌──────────────────────────────────────────────▼───────────────────┐
│              INFERENCE & API GATEWAY                              │
│        rajora-slm-fine-tune-for-revive-os  [v15.0.0]             │
│                                                                   │
│  auth_service :8001 │ inference_service :8002                    │
│  billing_service :8003 │ user_service :8004                      │
│  api_gateway (Nginx) │ ai_core │ scheduler_service               │
│                                                                   │
│  RS256 JWT · Redis Lua rate limit · Circuit breakers             │
│  Together AI (Mistral-7B · Phi-3) · vLLM (optional GPU)         │
│  Stripe billing · Qdrant vector DB · MinIO object storage        │
└──────────────────────────────────────────────┬───────────────────┘
                                               │
          ┌────────────────┬──────────────────┬┴──────────────────┐
          │                │                  │                   │
┌─────────▼──────┐ ┌───────▼──────┐ ┌────────▼──────┐ ┌─────────▼──────┐
│ HopeSense-AI🔒 │ │ WickerIndia  │ │ openlearn-ai  │ │finserve2india🔒│
│ Burnout detect │ │ E-commerce   │ │ Exam prep AI  │ │ Finance · IN   │
│ NLP · RL · AWS │ │ MongoDB · S3 │ │ RAG · STT·TTS │ │ TypeScript     │
│                │ │ n8n webhooks │ │ COPPA · RabbitMQ│               │
└────────────────┘ └──────────────┘ └───────────────┘ └────────────────┘
```

---

## Stack

**Core Languages** — Python · TypeScript · JavaScript · HCL · Shell

**AI / ML** — LangGraph · vLLM · Together AI · OpenAI · Anthropic Claude
              Google Gemini · Mistral-7B · Phi-3 · Ollama (local LLMs)
              BAAI/bge-m3 embeddings · Faster-Whisper · Coqui XTTS

**Backend** — FastAPI · Motor · PostgreSQL · MongoDB Atlas · Redis · RabbitMQ

**Frontend** — React 18 · Next.js 14 · TypeScript · Tailwind CSS · Vite · shadcn/ui

**Infrastructure** — AWS (EC2, S3, EB) · Docker · Kubernetes · Terraform
                     Nginx · GitHub Actions · Vercel · Railway · Render

**Security** — RS256 JWT · bcrypt · Redis Lua atomic rate limiting
               Circuit breakers · Prometheus · Grafana · Trivy · Jaeger

**Automation** — n8n · Playwright · Qdrant · MinIO

---

[![GitHub Stats](https://github-readme-stats.vercel.app/api?username=rajeevrajora77-lab&show_icons=true&theme=github_dark&hide_border=true&count_private=true&include_all_commits=true)](https://github.com/rajeevrajora77-lab)
[![Top Languages](https://github-readme-stats.vercel.app/api/top-langs/?username=rajeevrajora77-lab&layout=compact&theme=github_dark&hide_border=true)](https://github.com/rajeevrajora77-lab)
[![GitHub Streak](https://streak-stats.demolab.com?user=rajeevrajora77-lab&theme=github-dark-blue&hide_border=true)](https://github.com/rajeevrajora77-lab)

---

**Rajora AI** · Bengaluru, Karnataka, India
[rajora.live](https://rajora.live) · [rajeev@rajora.live](mailto:rajeev@rajora.live)
