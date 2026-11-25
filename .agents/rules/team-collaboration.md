---
trigger: always_on
---
# Team Collaboration Rules ("larping devs")

1. **Read `SPEC.md`, `MISSIONS.md`, and `GEMINI.md` first** before writing code that touches shared interfaces, APIs, or data models.
2. **Respect module boundaries:** Only modify files listed in your **Allowed Files** in `MISSIONS.md` (or your assigned scope) unless explicitly asked by Harrish.
3. **Contract changes require a `SPEC.md` update:** If you add or change an API endpoint, payload, or database schema, update `SPEC.md` in the same change.
4. **Never commit secrets:** Never hardcode API keys, tokens, or credentials. Use environment variables and document new keys in `.env.example` (without values).
5. **Keep PRs small and verifiable:** Run the project's lint/test command (from `GEMINI.md`) before reporting a task done.
6. **Quota efficiency:** When working on scoped UI or component tasks, read only the target files and `SPEC.md` rather than scanning unrelated directories.
