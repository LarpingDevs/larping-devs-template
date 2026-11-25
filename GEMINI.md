# larping devs — Project Brain (`GEMINI.md`)

> **Shared Antigravity Context:** Every team member's Antigravity agent reads this file automatically. Keep it accurate and up to date in Git.

## 1. Team & Role Split ("larping devs")
We are a 4-person team with **2 AI Pro accounts** and **2 Free Google accounts**. Route work to protect Free-tier quota and maximize velocity:

| Role Tier | Members | Owns | How to Use Antigravity |
| :--- | :--- | :--- | :--- |
| **Pro Tier (2x)** | Pro 1, Pro 2 | `backend/`, `ai/`, architecture, `SPEC.md` contracts, complex debugging, PR reviews & conflict resolution | Heavy multi-file generation, Planning Mode, cross-module refactors, final integration. |
| **Free Tier (2x)** | Free 1, Free 2 | `frontend/` UI components, styling, `docs/`, tests, pitch/demo prep | Scoped single-component/single-file tasks referencing `@SPEC.md`. Avoid broad codebase exploration. |

## 2. Project Overview
- **Project Name:** `<PROJECT_NAME>`
- **Mode:** `Hackathon Mode` *(switch to `Project Mode` for multi-week builds)*
- **Tech Stack:** `<e.g., Next.js + Tailwind / FastAPI / Supabase>`
- **Source of Truth for Contracts:** [SPEC.md](./SPEC.md)

## 3. Module Ownership (Anti-Conflict Boundaries)
Do **not** edit files outside your assigned directory without coordinating in team chat and updating `SPEC.md`:
- `frontend/` — UI pages, components, client hooks
- `backend/` — API routes, services, auth
- `shared/` — Shared types, schemas, constants
- `docs/` — Architecture notes, pitch, demo script

## 4. Common Commands
Fill these in during project setup:
- **Install:** `<e.g., npm install / uv sync>`
- **Dev server:** `<e.g., npm run dev>`
- **Test:** `<e.g., npm test / pytest>`
- **Lint / Typecheck:** `<e.g., npm run lint>`

## 5. Non-Negotiable Rules
1. **Never commit secrets.** Put keys in `.env` (gitignored) and document variable names in `.env.example`.
2. **Contract first.** Update [SPEC.md](./SPEC.md) before changing any API route, payload, or database schema.
3. **Never push directly to `main`.** Always work on a short-lived branch (`feat/<name>`, `fix/<name>`).
