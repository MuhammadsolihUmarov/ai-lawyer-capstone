# AI Lawyer — Capstone Diary

Public diary for the AI Mentorship Program, capturing weekly progress on **AI Lawyer**, my own startup idea: an AI legal assistant grounded in the laws of the Republic of Uzbekistan.

## Project

**AI Lawyer** is a bilingual (Uzbek / Russian) AI legal assistant. Users ask legal questions and the system answers with citations to the relevant articles of the Uzbek codes (Labor, Civil, Criminal, Tax, Family, Land, Housing, Administrative). It supports document analysis (upload a contract → get structured extraction of parties, dates, claims, obligations) and document drafting (generate a contract / claim / statement from a Jinja2 template, citation-verified).

This diary lives in a separate public repo per program rules:

> If your startup code is private, create a separate public diary repo.

- Code repo: **https://github.com/MuhammadsolihUmarov/AILawyer**
- Live app: **https://ailawyer-five.vercel.app**
- Backend health: **https://ailawyer-backend-zip3.onrender.com/health**

## How the project maps to Ilm AI's milestones

Per the program rule that "your product may not have a 'quiz mode' or a 'Telegram bot', but it should hit the equivalent stage at each milestone":

| Ilm AI feature | AI Lawyer equivalent |
|---|---|
| Personal knowledge base (user uploads study material) | Curated Uzbek legal corpus + per-user uploaded documents for analysis |
| AI learning companion | Multi-agent lawyer (router → retriever → lawyer/analyzer/drafter agent → citation grounding) |
| Quiz & practice mode | Document analyzer (parties / dates / claims / obligations) and drafter (5 templates) |
| Knowledge gap detection across sessions | Cross-conversation `UserMemory` on `LawyerAgent` / `AnalyzerAgent` |
| Telegram bot integration | Telegram bot for sign-up via deep-link + voice transcript echo |
| Payment & premium tier | Payme + Click checkout endpoints + webhook callbacks; subscription table with `monthly_queries_left` / `monthly_tokens_left` quotas |

## Tech stack

- **Backend:** FastAPI (Python 3.11), SQLAlchemy, Alembic, structlog, Prometheus
- **Frontend:** Next.js 15 (App Router) + Tailwind, "Justice & Order" theme (parchment + navy + brass)
- **DB:** PostgreSQL 16 + pgvector + Postgres FTS (tsvector + GIN + trigger)
- **LLM:** Gemini 2.5 Flash (default), pluggable provider (Anthropic / OpenAI / Ollama)
- **RAG:** Hybrid retrieval (vector + lexical, fused via Reciprocal Rank Fusion k=60), LLM reranker
- **Deploy:** Render (backend), Vercel (frontend), Neon (Postgres), GitHub Actions CI

## Diary format

Each entry follows the program rules:
- file: `diary/YYYY-MM-DD.md`
- sections: what I did / problems / solutions / next plan / time spent
- demo videos (when posted) embedded under `## Demo video`

Diary entries start from Week 2 of the program (the week of 19 May).
