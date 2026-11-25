# larping devs — Project Brain (`GEMINI.md`)

> **Shared Antigravity Context:** Every team member's Antigravity agent reads this file automatically. Keep it accurate and up to date in Git.

## 1. Team & Role Split ("larping devs")
We are a 4-person classmate team led by **Harrish (`h4rysh`)** with **2 AI Pro accounts** and **2 Free Google accounts**:

| Member | Tier | Role & Owns | How to Work with Antigravity |
| :--- | :--- | :--- | :--- |
| **Harrish (`h4rysh`)** | **AI Pro (Lead)** | Architecture, repo skeleton, `SPEC.md`, core AI/backend, PR reviews, conflict resolution | Heavy multi-file generation, `/plan`, `code-reviewer`, unblocking teammates, merging PRs to `main`. |
| **Jaggu** | **AI Pro** | Secondary backend/CRUD routes, DB wiring, or full feature pages defined in `SPEC.md` | Use Antigravity Pro with `@SPEC.md` to generate & test well-defined modules step-by-step. |
| **Harshini** | **Free** | Isolated `frontend/` UI components, styling, forms, responsive polish | Always `@`-mention `SPEC.md` + target component file. One component per chat. |
| **Joel** | **Free** | `frontend/` static/landing pages, seed/mock data, `docs/`, unit tests, pitch/demo prep | Always `@`-mention `SPEC.md` + target file. One task per chat; sync via `hackathon-sync`. |

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
