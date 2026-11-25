# larping devs — Starter Template

Shared workspace template for **larping devs** (4-person team using Antigravity: 2 AI Pro + 2 Free Google accounts).

## What's Inside
- `GEMINI.md` — Shared project brain read automatically by every teammate's Antigravity agent.
- `SPEC.md` — Shared contracts (models, API endpoints, ownership matrix).
- `TEAM_WORKFLOW.md` — Role split (2 Pro / 2 Free), Hackathon Mode vs Project Mode, and Git loop.
- `ONBOARDING_PRO.md` — Copy-paste setup prompt for **AI Pro** teammates.
- `ONBOARDING_FREE.md` — Copy-paste, quota-friendly setup prompt for **Free Google Account** teammates.
- `.agents/rules/team-collaboration.md` — Guardrails for all 4 agents.
- `.agents/skills/hackathon-sync/SKILL.md` — Reusable skill for syncing branches and opening PRs.
- `.gitignore` & `.env.example` — Secret protection and stack ignores.

## New Member Setup (First Time Only)
Before your first project, paste the onboarding prompt matching your Antigravity account into a fresh Antigravity chat:
- **AI Pro accounts (2x):** [ONBOARDING_PRO.md](./ONBOARDING_PRO.md)
- **Free Google accounts (2x):** [ONBOARDING_FREE.md](./ONBOARDING_FREE.md)

## Quickstart (Every Hackathon / Project)
1. Create a new repository from this template under the `LarpingDevs` GitHub org (`https://github.com/LarpingDevs`).
2. Clone locally, run `cp .env.example .env`, and open the folder in Antigravity.
3. Fill out `SPEC.md` and `GEMINI.md` together in 15 minutes, then branch and build!
