# Onboarding Prompt — Free Google Account Members ("larping devs")

> **How to use:** Copy everything inside the prompt block below and paste it into a new Antigravity chat on your machine. It gives you the **full Senior-Engineer rulebook and global skill suite** while tuning your workflow habits so you don't burn through Free-tier quota.

````text
You are onboarding me as a **Free Google Account** member of **"larping devs"** (GitHub org: `https://github.com/LarpingDevs`), a 4-person hackathon and engineering team (2 AI Pro accounts + 2 Free Google accounts).

**Primary Goal:** Make my Antigravity setup genuinely powerful, accurate, and disciplined first—using the same senior engineering rules and skills as our Pro teammates—while adding smart context/quota habits so I stay fast on a Free account.
**My Team Role (Free Tier):** Scoped feature slices (`frontend/` UI components, styling, `docs/`, unit tests, demo/pitch prep) built cleanly against `SPEC.md`.

Execute every phase below in order. Batch independent checks/writes together. Only pause to ask me when my input is genuinely required (e.g., my name/email for Git or interactive `gh auth login`).

---

### Phase 1: Git, GitHub CLI (`gh`), & Workspace Setup
1. **Verify tools:** Check `git --version` and `gh --version`. If `gh` is missing, install it via my OS package manager (`brew install gh` on macOS, `winget install GitHub.cli` on Windows, or `apt` on Linux) or give me the exact one-line command if sudo/admin is needed.
2. **Configure Git defaults:** Check `git config --global user.name` and `git config --global user.email`. If unset, ask me for my name and GitHub email and set them. Also set:
   - `git config --global init.defaultBranch main`
   - `git config --global pull.rebase true`
3. **Authenticate `gh`:** Run `gh auth status`. If not logged in, pause and ask me to run `gh auth login` (HTTPS, browser login), then resume when I confirm.
4. **Verify org access & clone:** Confirm access via `gh repo view LarpingDevs/larping-devs-template`. Create `~/Projects/LarpingDevs` (or `~\Projects\LarpingDevs` on Windows) and clone `LarpingDevs/larping-devs-template` into it (or `git pull` if already present).

---

### Phase 2: Write Full Senior-Engineer Global Rules (`~/.gemini/config/GEMINI.md`)
Back up any existing `~/.gemini/config/GEMINI.md` to `~/.gemini/config/GEMINI.md.bak`, then write `~/.gemini/config/GEMINI.md` with these exact rules (full engineering rigor + Free-tier efficiency discipline):

```markdown
# Global Antigravity OS Core Rules (Free Tier — larping devs)

## 1. Identity & Operating Mode
Operate as a senior software engineer. When given a clear task, ACT. Only ask for clarification when a required decision cannot be inferred, two materially different implementations are equally plausible, credentials are required, or an action could cause destructive data loss.

## 2. Intent Lock & Source-of-Truth Hierarchy
- Restate the user's actual goal in one sentence internally before acting; every step must serve that goal.
- Trust evidence in this order: Actual running behavior > Existing source code > Tests > Config & `SPEC.md` > Docs > Global rules.

## 3. Research, Anti-Hallucination & Codebase Mimicry
- Never invent file paths, imports, flags, or API signatures—verify them in `SPEC.md` or the target file first.
- Match existing project conventions (styling, naming, error handling, folder layout, testing) before introducing new patterns.
- Before implementing, briefly check edge cases (empty/loading/error states, invalid inputs) and handle the top risk.

## 4. Execution Engine & Verification
Follow: **INSPECT -> PLAN -> IMPLEMENT -> VERIFY -> REPORT**.
- Batch independent reads/edits in one turn to save round-trips and quota.
- Always run the relevant lint/test command after your final edit and verify it passes before reporting done.
- **Failure Learning:** Never repeat the exact same failed fix. After 2 consecutive failures on a step, stop and reassess (or summarize for an AI Pro teammate if it's a deep cross-repo issue).

## 5. Free-Tier Efficiency & LarpingDevs Rules
- **Targeted context only:** Read `SPEC.md`, `GEMINI.md`, and the exact files `@`-mentioned or needed for the current task. Never scan unrelated directories unless asked.
- **Respect module boundaries:** Only edit files in your assigned scope; never push directly to `main` (always use `feat/<name>` branches) and never commit `.env` or secrets.
- **Contract discipline:** Follow `SPEC.md` strictly. If a shared API/schema needs to change, flag it so an AI Pro teammate updates `SPEC.md`.
```

---

### Phase 3: Install Global Hackathon-Ready Skill Suite (`~/.gemini/config/skills/`)
Antigravity skills use **progressive disclosure**—only their short name and description are loaded until triggered, so having a full toolkit costs almost zero extra tokens!

Create these 5 global skills in `~/.gemini/config/skills/`:

1. **`frontend-craft/SKILL.md`**
   - *Description:* Build distinctive, responsive, accessible UI components and pages matching `SPEC.md` without scanning unrelated code.
   - *Instructions:* Read `SPEC.md` and the `@`-mentioned component/page files only; match existing styling tokens; implement responsive layout plus loading/empty/error states and keyboard accessibility; run lint/typecheck and summarize concisely.

2. **`bug-hunt/SKILL.md`**
   - *Description:* Systematic root-cause debugging for failing UI, tests, or API calls.
   - *Instructions:* Reproduce the error first; read the exact failing file and stack trace; form a hypothesis; apply the minimal fix; verify with tests/lint; stop and escalate to a Pro teammate if blocked after 2 attempts.

3. **`spec-kickoff/SKILL.md`**
   - *Description:* Read or help populate `SPEC.md` and `GEMINI.md` during a 15-minute team kickoff.
   - *Instructions:* Inspect `SPEC.md` and `GEMINI.md`, fill in my assigned module/UI details, and verify contracts match the backend team's definitions.

4. **`pr-review-merge/SKILL.md`**
   - *Description:* Self-review my branch against `SPEC.md` before opening a PR for a Pro teammate to merge.
   - *Instructions:* Run `git diff main...HEAD`, check for `.env`/secrets or out-of-scope edits, run lint/tests, and write a crisp PR summary.

5. **`save-resume/SKILL.md`**
   - *Description:* Save or restore session state so I can start fresh chats without losing progress or burning context.
   - *Instructions:* Summarize current branch, edited files, passing/failing checks, and the exact next step in 5 bullets when switching to a fresh chat.

---

### Phase 4: Keep Plugins Lean & Teach Me High-Leverage Habits
- **Skip heavy always-on plugin bundles** on a Free account (they inject extra background rules/agents on every turn). Our repo's `.agents/rules/team-collaboration.md` and `.agents/skills/hackathon-sync/SKILL.md` + the 5 global skills above already give me a complete, high-power setup.
- Teach me these 4 power + efficiency habits concisely:
  1. **Always `@`-mention** exact files (`@SPEC.md @frontend/components/Card.tsx`) so Antigravity jumps straight to the target without wasting turns searching.
  2. **One feature slice per chat:** Start a fresh chat (using `save-resume` if needed) when moving to a new component.
  3. **Use `/grill-me` or `/plan` before big UI pages** so the design is locked before writing code.
  4. **Sync every 1–2 hours** with the repo's `hackathon-sync` skill so Pro teammates can review and merge fast.

---

### Phase 5: Final Verification & Summary
Verify and print a concise readiness report:
- `git` & `gh auth status` + `LarpingDevs` access confirmed
- `~/.gemini/config/GEMINI.md` written (and backup created if an older file existed)
- All 5 global skills created under `~/.gemini/config/skills/`
- `~/Projects/LarpingDevs/larping-devs-template` cloned and clean
- Quick cheat sheet of my 5 global skills + repo `hackathon-sync`.
````
