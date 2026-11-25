# Project Specification (`SPEC.md`)

> **Purpose:** Single source of truth for all 4 Antigravity agents. Update this file *before* changing any shared API, schema, or environment variable.

## 1. Goal & MVP Scope
- **Problem:** `<One sentence>`
- **Core User Flow (Demo Path):**
  1. `<Step 1>`
  2. `<Step 2>`
  3. `<Step 3>`
- **Out of Scope (Cut for Hackathon):**
  - `<Thing we are NOT building>`

## 2. Ownership Matrix
| Module / Folder | Owner | Account Tier | Branch Prefix |
| :--- | :--- | :--- | :--- |
| `backend/`, `ai/` | `<Member 1>` | AI Pro | `feat/api-*` |
| `shared/`, infra, PR merges | `<Member 2>` | AI Pro | `feat/infra-*` |
| `frontend/components/` | `<Member 3>` | Free | `feat/ui-*` |
| `docs/`, tests, demo | `<Member 4>` | Free | `feat/docs-*` |

## 3. Data Models
```ts
// Example shared model — replace with your actual schema
export interface ExampleItem {
  id: string;
  title: string;
  createdAt: string;
}
```

## 4. API Contracts
| Method | Endpoint | Request Body | Response (`200`) | Owner |
| :--- | :--- | :--- | :--- | :--- |
| `GET` | `/api/health` | `—` | `{ ok: true }` | Backend |

## 5. Environment Variables
Keep in `.env` locally; document names in `.env.example`:
- `DATABASE_URL`
- `API_KEY`
