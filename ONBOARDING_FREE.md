# Onboarding Prompt — Free Google Account Members ("larping devs")

> **How to use:** Copy everything inside the prompt block below and paste it into a new Antigravity chat on your machine. It sets up a fast, **quota-friendly** Antigravity configuration tailored for Free-tier accounts.

````text
You are onboarding me as a **Free Google Account** member of the 4-person hackathon & engineering team **"larping devs"** (GitHub org: `https://github.com/LarpingDevs`).
In our team, 2 members have AI Pro subscriptions and 2 have Free Google accounts. My goal is to ship clean, scoped work (frontend UI components, styling, docs, unit tests, demo prep) **without wasting my Free-tier quota** on huge context scans or unnecessary multi-agent loops.

Execute the following setup steps in order. Keep your output concise and only pause to ask me when you need my input (e.g., my name/email for Git, or interactive `gh auth login`).

---

### Step 1: Verify & Configure Git + GitHub CLI (`gh`)
1. Check if `git` and `gh` are installed (`git --version`, `gh --version`). If `gh` is missing, install it using my OS package manager (e.g., `brew install gh` on macOS, `winget install GitHub.cli` on Windows, or `apt` on Linux) or give me the exact one-line command.
2. Check `git config --global user.name` and `git config --global user.email`. If either is empty, ask me for my name and GitHub email and set them. Also set `git config --global init.defaultBranch main` and `git config --global pull.rebase true`.
3. Run `gh auth status`. If I am not logged in, pause and ask me to run `gh auth login` in my terminal (HTTPS, login with browser), then continue once I confirm.
4. Verify I can access `https://github.com/LarpingDevs/larping-devs-template` (`gh repo view LarpingDevs/larping-devs-template`).

### Step 2: Set Up Workspace Directory & Clone Template
1. Create a clean projects directory (`~/Projects/LarpingDevs` on macOS/Linux or `~\Projects\LarpingDevs` on Windows) if it doesn't exist.
2. Clone `LarpingDevs/larping-devs-template` into `~/Projects/LarpingDevs/larping-devs-template` (or pull `main` if already cloned).

### Step 3: Write a Lean, Quota-Friendly `~/.gemini/config/GEMINI.md`
Create or update `~/.gemini/config/GEMINI.md` (back up any existing `GEMINI.md` to `GEMINI.md.bak` first if it exists). Keep it **short and high-signal** so it doesn't waste context tokens on every turn:

```markdown
# Global Rules (Free Tier — larping devs)

1. **Be quota-efficient:** Read ONLY `SPEC.md`, `GEMINI.md`, and the exact files I `@`-mention or ask about. Never scan the whole repository unless I explicitly ask.
2. **Scoped edits only:** Only modify files in my assigned module/component. Do not refactor unrelated files.
3. **Contract first:** Follow `SPEC.md` strictly for API shapes, types, and env vars. If a shared contract needs to change, tell me so a Pro teammate can update `SPEC.md`.
4. **Verify before reporting:** Never guess imports, paths, or APIs—check the target file first. Run the project's lint/test command after edits when applicable.
5. **Git & Secrets safety:** Never push directly to `main` (always use `feat/<name>` branches) and never commit `.env` or hardcoded API keys.
6. **Escalate heavy work:** If a task requires a large cross-repo refactor or complex merge conflict resolution, stop and summarize what's needed so an AI Pro teammate can handle it.
```

### Step 4: Keep Plugins Minimal (Protect Context & Quota)
Do NOT install heavy plugin bundles with dozens of background rules/agents on my Free account—our repo's `.agents/rules/team-collaboration.md` and `.agents/skills/hackathon-sync/SKILL.md` already give me what I need.
Teach me these 3 quota-saving habits in 4–5 bullet points:
- Always `@`-mention specific files (e.g., `@SPEC.md @frontend/components/Card.tsx`) instead of broad prompts.
- Work on one component/task per chat, and start a fresh chat for the next component.
- Use `hackathon-sync` (or ask Antigravity to branch, test, commit, and open a PR) every 1–2 hours so Pro teammates can review and merge quickly.

### Step 5: Verify Everything
Run a final check and print a short checklist confirming:
- `git` & `gh` auth status + access to `LarpingDevs`
- `~/.gemini/config/GEMINI.md` created (and concise)
- `~/Projects/LarpingDevs/larping-devs-template` cloned and ready.
````
