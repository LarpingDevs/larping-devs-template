---
name: hackathon-sync
description: Safely sync with main, verify changes, and prepare a clean branch/PR for team review. Use when a teammate finishes a feature slice or wants to merge their work.
---

# Hackathon Sync & PR Workflow

Follow these steps in order when the user is ready to sync or open a PR:

1. **Check workspace status:** Run `git status` and `git diff --stat` to see all modified files.
2. **Verify no secrets:** Confirm `.env` or hardcoded API keys are NOT staged. If a new env var was added, ensure its name is in `.env.example`.
3. **Ensure feature branch:** If currently on `main`, create a descriptive branch: `git checkout -b feat/<short-name>`.
4. **Sync with `main`:** Run `git fetch origin && git rebase origin/main` (or merge `origin/main`). If conflicts occur, resolve them carefully preserving `SPEC.md` contracts.
5. **Run checks:** Execute the test/lint commands listed in `GEMINI.md` (if configured).
6. **Commit & push:** Stage changes, commit with a conventional message (`feat: ...`, `fix: ...`), and push (`git push -u origin HEAD`).
7. **Open PR:** If `gh` CLI or GitHub MCP is available, create a concise PR summarizing what changed, which module it touches, and how to test it.
