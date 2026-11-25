# larping devs — Team Playbook

## 1. Setup for a New Hackathon or Project
1. On GitHub, click **Use this template** → create a new repo under the `LarpingDevs` organization (`https://github.com/LarpingDevs`).
2. All 4 members clone the repo and open it in Antigravity:
   ```bash
   git clone <repo-url>
   cd <repo-name>
   cp .env.example .env
   ```
3. Spend **15 minutes together** filling out `SPEC.md` and `GEMINI.md` (stack, commands, module owners), then push to `main`.

---

## 2. Maximizing 2 AI Pro + 2 Free Accounts
- **AI Pro Members (2):**
  - Own `backend/`, `ai/`, database schemas, and `SPEC.md`.
  - Handle cross-file refactors, tricky debugging, and **all PR reviews / merge conflict resolution**.
- **Free Google Account Members (2):**
  - Own well-scoped `frontend/` components, styling, `docs/`, unit tests, and demo/pitch assets.
  - **Quota-saving habit:** Always `@`-mention specific files (`@SPEC.md @frontend/components/Card.tsx`) instead of asking the agent to scan the whole repo. Keep prompts focused on one component or task per turn.

---

## 3. Two Git Modes

### Mode A: Hackathon Mode (24–48h sprints)
- **Branching:** Short-lived branches (`feat/navbar`, `feat/auth-api`).
- **Cadence:** Open small PRs every **1–2 hours**. Never hoard 6 hours of work on one branch.
- **Auto-Merge Bot:** `.github/workflows/pr-auto-merge.yml` automatically checks for committed `.env` files, runs lint/build/tests, squash-merges clean PRs into `main`, and deletes the feature branch. If there's a conflict, the bot comments on the PR telling the author to rebase.
- **Sync:** Everyone runs `git pull origin main` after the bot merges a PR.

### Mode B: Project Mode (Multi-week / Production)
- **Branch protection:** Require PR + at least 1 approval + passing CI/tests before merging to `main`.
- **Code review:** Run Antigravity's review/test checks before opening a PR.
- **Conventional commits:** `feat:`, `fix:`, `refactor:`, `docs:`, `test:`, `chore:`.

---

## 4. Secrets & Environment Sharing
- **Never** paste API keys into chat logs that get committed, or into `GEMINI.md` / `.agents/`.
- Share `.env` values over a secure channel (password manager or encrypted DM) and keep `.env` in `.gitignore`.
