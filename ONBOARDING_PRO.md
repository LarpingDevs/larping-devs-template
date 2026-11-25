# Onboarding Prompt — AI Pro Members ("larping devs")

> **How to use:** Copy everything inside the prompt block below and paste it into a new Antigravity chat on your machine. Your Antigravity agent will set up your entire environment automatically.

````text
You are onboarding me as an **AI Pro** member of the 4-person hackathon & engineering team **"larping devs"** (GitHub org: `https://github.com/LarpingDevs`).
In our team, 2 members have AI Pro subscriptions and 2 have Free Google accounts. As an AI Pro member, I own architecture, backend/AI, `SPEC.md` contracts, complex debugging, PR reviews, and merge conflict resolution.

Execute the following setup steps in order. Ask me only when you need my input (e.g., my name/email for Git, or interactive `gh auth login`).

---

### Step 1: Verify & Configure Git + GitHub CLI (`gh`)
1. Check if `git` and `gh` are installed (`git --version`, `gh --version`). If `gh` is missing, install it using my OS package manager (e.g., `brew install gh` on macOS, `winget install GitHub.cli` on Windows, or `apt` on Linux) or give me the exact one-line command.
2. Check `git config --global user.name` and `git config --global user.email`. If either is empty, ask me for my name and GitHub email and set them. Also set `git config --global init.defaultBranch main` and `git config --global pull.rebase true`.
3. Run `gh auth status`. If I am not logged in, pause and ask me to run `gh auth login` in my terminal (HTTPS, login with browser), then continue once I confirm.
4. Verify I can access `https://github.com/LarpingDevs/larping-devs-template` (`gh repo view LarpingDevs/larping-devs-template`).

### Step 2: Set Up Workspace Directory & Clone Template
1. Create a clean projects directory (`~/Projects/LarpingDevs` on macOS/Linux or `~\Projects\LarpingDevs` on Windows) if it doesn't exist.
2. Clone `LarpingDevs/larping-devs-template` into `~/Projects/LarpingDevs/larping-devs-template` (or pull `main` if already cloned) so I have it locally as a reference.

### Step 3: Write My Global `~/.gemini/config/GEMINI.md`
Create or update `~/.gemini/config/GEMINI.md` with the following battle-tested rules for an AI Pro engineer (back up any existing `~/.gemini/config/GEMINI.md` to `GEMINI.md.bak` first if it exists):

```markdown
# Global Antigravity OS Core Rules (Pro Tier — larping devs)

## 1. Identity & Operating Mode
Operate as a senior autonomous software engineer. When given a clear task, ACT. Only ask for clarification when a required decision cannot be inferred, two materially different implementations are equally plausible, credentials are required, or an action is destructive.

## 2. Intent Lock & Source of Truth
- Restate the user's actual goal in one sentence internally before acting. Every step must serve that goal.
- Source-of-truth hierarchy: Actual running behavior > Existing source code > Tests > Config > Docs > Global rules.

## 3. Research & Deep Reasoning
Before implementing non-trivial changes:
1. Check existing codebase patterns, `SPEC.md`, and repo `GEMINI.md` first.
2. Read relevant `SKILL.md` or official docs before guessing APIs.
3. Consider >=2 approaches and address the top failure mode (edge cases, race conditions, state bugs) before coding.

## 4. Anti-Hallucination & Codebase Mimicry
- Never invent imports, file paths, flags, or API signatures—verify them first.
- Match the project's existing conventions (error handling, naming, folder structure, testing) before introducing new patterns.

## 5. Execution Engine & Subagents
Follow: INSPECT -> PLAN -> IMPLEMENT -> VERIFY -> REVIEW -> REPORT.
- Batch independent file reads/searches in parallel.
- For complex features, use Planning Mode (`/plan`) or `architect` / `planner` subagents.
- After writing non-trivial code, run tests/linters and use `code-reviewer` (and `security-reviewer` for auth/API/secrets).
- Never repeat the exact same failed fix twice—reassess upstream after 2 failures.

## 6. LarpingDevs Team Duties (Pro Tier)
- Keep `SPEC.md` updated *before* changing shared APIs, types, or schemas.
- Review PRs from Free-tier teammates promptly, resolve merge conflicts, and keep `main` green.
- Never commit `.env` or secrets; always document new env keys in `.env.example`.
```

### Step 4: Set Up Global Skills (`~/.gemini/config/skills/`) & Core Plugins
Antigravity auto-discovers skills from `~/.gemini/config/skills/<name>/SKILL.md` (global) and `<repo>/.agents/skills/<name>/SKILL.md` (shared via Git). Skills use progressive disclosure—only their name and description are loaded until triggered.

1. Create two global skills for my Pro-tier team duties:
   - `~/.gemini/config/skills/spec-kickoff/SKILL.md`:
     ```markdown
     ---
     name: spec-kickoff
     description: Run a 15-minute hackathon/project kickoff to populate SPEC.md and GEMINI.md with stack, commands, ownership matrix, data models, and API contracts.
     ---
     # Spec Kickoff
     1. Read `SPEC.md` and `GEMINI.md` in the repo root.
     2. Ask me for: project goal, tech stack, dev/test/lint commands, and which of the 4 LarpingDevs members owns each folder.
     3. Update `SPEC.md` (models, API endpoints, env vars) and `GEMINI.md` (stack + commands) cleanly, then commit and push to `main`.
     ```
   - `~/.gemini/config/skills/pr-review-merge/SKILL.md`:
     ```markdown
     ---
     name: pr-review-merge
     description: Review a teammate's PR against SPEC.md, run checks, resolve any merge conflicts, and merge cleanly to main.
     ---
     # Pro PR Review & Merge
     1. Fetch the PR branch (`gh pr checkout <number>` or `git fetch`).
     2. Diff against `main` (`git diff main...HEAD`) and verify: no `.env`/secrets, contracts match `SPEC.md`, and no unintended edits outside the author's module.
     3. Run the test/lint commands from `GEMINI.md`.
     4. Report any blockers clearly, or approve and squash-merge (`gh pr merge --squash`).
     ```
2. Check which plugins are currently installed in `~/.gemini/config/plugins/`.
3. Using the marketplace/plugin tools (or by listing what I should enable in Antigravity's Plugins Manager), recommend enabling:
   - `ecc-curated` (gives `code-reviewer`, `security-reviewer`, `tdd-guide`, `planner`, `/plan`, `/code-review`)
   - `chrome-devtools-plugin` (for frontend/API debugging)
   - `gemini-api` (for AI hackathon builds)
4. Briefly show me how to use `/plan`, `/grill-me`, `/compact`, `@SPEC.md`, and my new skills (`spec-kickoff`, `pr-review-merge`).

### Step 5: Verify Everything
Run a final check and print a concise summary confirming:
- `git` & `gh` auth status + access to `LarpingDevs`
- `~/.gemini/config/GEMINI.md` created
- `~/Projects/LarpingDevs/larping-devs-template` cloned and clean
- Recommended Antigravity settings (e.g., enable Terminal Sandbox / Request Review for unfamiliar commands, keep `larping-devs-template` as a reference).
````
