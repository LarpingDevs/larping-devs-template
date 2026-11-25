# larping devs — Zero-Friction Team Playbook

> Designed for **1 Vibe-Coding Lead (Harrish — M1 Pro, AI Pro)** + **3 Beginners (Jaggu — M1/M2 Air, AI Pro; Harshini & Joel — Mac & Windows Victus, Free Accounts)** sitting together.

---

## The 3-Phrase Rule (For Jaggu, Harshini, & Joel)
You do **not** need to memorize Git commands or coding jargon. Inside Antigravity, you only ever need **3 phrases**:
1. **`Start my mission — I am <Name>`** → Pulls `main`, makes a safe branch, reads your exact assignment from `MISSIONS.md`, builds it, and tests it.
2. **`Ship my work`** → Checks for leaked secrets, runs tests, commits, and opens a PR.
3. **`Check my PR`** → Checks if the Auto-Merge Bot merged it (or automatically fixes any error and pushes again).

---

## End-to-End Hackathon / Project Flow

### Phase 0: Minute 0–20 — Harrish Runs `mission-control`
1. Create a new repo from `LarpingDevs/larping-devs-template` and open it in Antigravity.
2. Paste the hackathon problem statement and tell Antigravity: **`Run mission-control`**.
3. Antigravity will:
   - Fill out `SPEC.md` (exact API shapes, models, Design Vibe, Demo Flow).
   - Build the **Walking Skeleton** on `main` (shared navbar, theme/colors, empty pages, `/api/health`) so everyone works inside the real app from Hour 1.
   - Generate 3 custom, conflict-free missions in `MISSIONS.md` for Jaggu, Harshini, and Joel.
   - Push everything to `main`.

### Phase 1: Minute 20 — Everyone Clones & Starts
1. All 3 teammates clone the repo, copy `.env.example` to `.env` (Harrish shares the keys), and open the folder in Antigravity.
2. Each person types: **`Start my mission — I am <Name>`**.

### Phase 2: The 1–2 Hour Build & Auto-Merge Loop
1. Whenever someone finishes a task, they say **`Ship my work`**.
2. **The GitHub Auto-Merge Bot** (`.github/workflows/pr-auto-merge.yml`) automatically checks for `.env` leaks, runs TypeScript/lint/build/tests, and **squash-merges** into `main`—Harrish doesn't have to review or click merge.
3. 30–60 seconds later, the teammate says **`Check my PR`**. If the bot blocked it, Antigravity reads the bot's error comment and fixes it automatically.
4. Once merged, they say out loud **"Merged!"** and Harrish refreshes the live preview on his screen so everyone sees the site evolving together.

---

## Maximizing 2 AI Pro + 2 Free Accounts
- **Harrish (Pro, Lead):** Architecture, `mission-control`, core AI/backend, live preview on his laptop.
- **Jaggu (Pro):** Backend CRUD / DB / full connected pages from `MISSIONS.md`.
- **Harshini & Joel (Free):** Scoped UI components, landing pages, mock data, docs, and demo polish. Always work on one mission per chat and start a fresh chat for the next mission.
