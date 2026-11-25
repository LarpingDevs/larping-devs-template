---
name: run-mission
description: Zero-jargon skill for Jaggu, Harshini, and Joel. Automatically pulls main, creates a feature branch, reads only their assigned section in MISSIONS.md and SPEC.md, implements it, runs checks, and prepares it to ship. Trigger when a user says "Start my mission" or "Do my mission".
---

# Run My Mission (Zero-Knowledge Teammate Flow)

Follow these steps automatically without asking the user Git questions:

1. **Identify the teammate:** If the user didn't state their name (Jaggu, Harshini, or Joel), ask: *"Which team member are you?"*
2. **Sync & Branch safely:**
   - Check `git status`. If there are uncommitted changes from an old task, ask before discarding or stashing.
   - Run `git checkout main && git pull origin main`.
   - Read `MISSIONS.md` and extract the **Branch** name for that teammate (if that branch exists locally/remotely, append `-v2` or a short suffix). Create & switch to it: `git checkout -b <branch-name>`.
3. **Read ONLY needed context (Quota-Friendly):**
   - Read `SPEC.md`, `GEMINI.md`, that teammate's section in `MISSIONS.md`, and ONLY the files listed under **Allowed Files** (plus shared types/theme if referenced).
4. **Build the Mission:**
   - Follow `SPEC.md` types, API shapes, and the **Design Vibe** strictly.
   - Do NOT modify files outside **Allowed Files**.
   - Ensure loading, empty, and error states are handled cleanly.
5. **Verify before finishing:**
   - Run the lint/typecheck/build/test commands listed in `GEMINI.md`. Fix any errors before reporting done.
6. **Tell the user in plain English:**
   - Summarize what you built in 3 short bullets and tell them: *"When you're happy with it, just tell me: **Ship my work**."*
