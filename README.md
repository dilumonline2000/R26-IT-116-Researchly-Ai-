# R26-IT-116-Researchly-Ai-
AI-Powered Research &amp; Integrity Assistant for Enhancing Undergraduate Research

Researchly AI — R26-IT-116
AI-Powered Research Paper Assistant & Collaboration Platform for SLIIT.

Team
Team Member	Module
K D T Kariyawasam	Module 1 — Research Integrity & Compliance
S P U Gunathilaka	Module 2 — Collaboration & Recommendation
N V Hewamanne	Module 3 — Data Collection & Management
H W S S Jayasundara	Module 4 — Performance Analytics
Architecture
┌─────────────┐    ┌──────────────┐    ┌──────────────────┐
│ Next.js 14  │───▶│ API Gateway  │───▶│ Python ML (x4)   │
│ (Frontend)  │    │ (Express.ts) │    │ FastAPI services │
└─────────────┘    └──────┬───────┘    └────────┬─────────┘
      │                   │                     │
      └───────────────────┴─────────────────────┘
                          │
                  ┌───────▼────────┐
                  │    Supabase    │
                  │ PG + pgvector  │
                  │ Auth + Storage │
                  └────────────────┘
Repo Layout
apps/
  web/            Next.js 14 App Router frontend
  api-gateway/    Express.js API Gateway (TypeScript)
services/
  shared/         Shared Python utilities
  module1-integrity/     FastAPI — Citations, gaps, proposals, plagiarism
  module2-collaboration/ FastAPI — Supervisor/peer matching, sentiment
  module3-data/          FastAPI — Data pipeline, topics, summarizer
  module4-analytics/     FastAPI — Trends, quality, predictions, mind maps
ml/
  notebooks/      Jupyter notebooks for training experiments
  training/       Training scripts for 10 models
  evaluation/     Model evaluation scripts
supabase/
  migrations/     SQL migrations (schema, pgvector, RLS)
scripts/          Data scraping + preprocessing orchestration
docker/           Compose files + Dockerfiles
Getting Started
Prereqs: Node ≥18.17, pnpm ≥9, Python ≥3.10, Docker Desktop, Supabase account.

# 1. Install JS dependencies
pnpm install

# 2. Copy env template
cp .env.example .env
# → fill in Supabase keys

# 3. Run Supabase migrations
pnpm db:migrate

# 4. Start frontend + gateway
pnpm dev

# 5. Start Python ML services (separate terminal)
pnpm dev:ml
Frontend: http://localhost:3000
API Gateway: http://localhost:3001
ML services: http://localhost:8001-8004
Development Phases
Foundation Setup — monorepo, schemas, shell pages (in progress)
Data Collection — scrape 15K+ papers → Supabase pgvector
ML Model Training — 10 models (spaCy NER, SBERT, SciBERT, BART, LoRA, ARIMA/Prophet, XGBoost, GCN)
Module Development — parallel implementation of all 4 modules
Integration & Deployment — Vercel + Railway + Supabase Cloud
See R26-IT-116_Cursor_AI_Full_Development_Prompt.md for the full spec.

License
SLIIT Research — Academic use.