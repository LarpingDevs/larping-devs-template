---
name: hackathon-sync
description: Safely sync with main, verify changes, open a PR, or check and fix a blocked/failed PR. Use when a teammate finishes a feature slice, wants to merge, or says their PR failed.
---

# Hackathon Sync & PR Workflow

## Mode 1: Ship Work & Open a PR
Follow these steps in order when the user is ready to sync or open a PR:

1. **Check workspace status:** Run `git status` and `git diff --stat` to see all modified files.
2. **Verify no secrets:** Confirm `.env` or hardcoded API keys are NOT staged. If a new env var was added, ensure its name is in `.env.example`.
3. **Ensure feature branch:** If currently on `main`, create a descriptive branch: `git checkout -b feat/<short-name>`.
4. **Sync with `main`:** Run `git fetch origin && git rebase origin/main` (or merge `origin/main`). If conflicts occur, resolve them carefully preserving `SPEC.md` contracts.
5. **Run checks:** Execute the test/lint commands listed in `GEMINI.md` (if configured).
6. **Commit & push:** Stage changes, commit with a conventional message (`feat: ...`, `fix: ...`), and push (`git push -u origin HEAD`).
7. **Open PR:** If `gh` CLI or GitHub MCP is available, create a concise PR summarizing what changed, which module it touches, and how to test it.
8. **Remind the user:** Tell them the Auto-Merge Bot will check and merge the PR in ~30–60 seconds, and they can ask **"check my PR status"** if they want Antigravity to verify it merged or fix any issues.

## Mode 2: Check & Fix a Blocked / Failed PR
Follow these steps when the user asks to check their PR or says the bot blocked it:

1. **Check PR status & bot comments:** Run `gh pr view --json state,mergeable,comments,statusCheckRollup`.
2. **If `state` is `MERGED`:** Tell the user it merged! Switch back to `main` and pull (`git checkout main && git pull origin main`).
3. **If `mergeable` is `CONFLICTING`:** Run `git fetch origin && git rebase origin/main`, resolve conflicts preserving `SPEC.md`, and push (`git push --force-with-lease`).
4. **If checks failed:** Run `gh run list --branch $(git branch --show-current) --limit 1` and `gh run view <run-id> --log-failed`, fix the lint/build/test/env error, commit, and `git push` so the Auto-Merge Bot re-runs and merges it.
