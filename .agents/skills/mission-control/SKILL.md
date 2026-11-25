---
name: mission-control
description: Lead architect kickoff skill for Harrish. Takes a hackathon problem statement or project idea, builds the shared skeleton + design tokens + SPEC.md, and generates custom non-overlapping missions in MISSIONS.md for Jaggu, Harshini, and Joel.
---

# Mission Control (Harrish — Project Kickoff)

Use this skill at the start of every new hackathon or project:

1. **Understand the Goal:** Read `SPEC.md`, `GEMINI.md`, and `MISSIONS.md`. Ask Harrish for:
   - The hackathon problem statement or project idea
   - Chosen tech stack (default: Next.js + Tailwind, or Next.js + FastAPI if AI/Python heavy)
   - Any APIs/services being used (e.g., Gemini API, Supabase/Firebase)
2. **Design the Architecture & Contracts (`SPEC.md`):**
   - Define the 1 Demo Flow, Data Models, exact API Endpoints + JSON shapes, Design Vibe (colors, fonts, card/button style), and Environment Variables (`.env.example`).
3. **Build the Walking Skeleton on `main`:**
   - Scaffold the folder structure, install base packages, create the shared layout/navbar + global theme/colors + shared TypeScript types/mock data + `/api/health` route so the app runs cleanly on both macOS and Windows right away.
   - Verify the skeleton builds and runs with zero errors.
4. **Generate Custom Missions (`MISSIONS.md`):**
   - Split the remaining work into **3 strictly non-overlapping missions** for **Jaggu (Pro)**, **Harshini (Free)**, and **Joel (Free)**:
     - **Jaggu (Pro):** Secondary backend/API/DB routes or full data-connected pages (leverages Pro quota).
     - **Harshini (Free):** Isolated, well-scoped UI components with exact file paths and design tokens.
     - **Joel (Free):** Landing/static pages, mock/seed data, `README.md`, tests, and demo polish.
   - Every mission MUST specify: exact **Allowed Files**, exact **Tasks**, and **Done When** criteria.
5. **Update `GEMINI.md` commands** (`install`, `dev`, `lint`, `build`, `test`) and **push `main`** so all 3 teammates can pull and start immediately.
6. **Print a 1-line start message** Harrish can say out loud to the team: *"Pull main and tell Antigravity: Start my mission — I am <Name>."*
