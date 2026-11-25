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
| Architecture, `SPEC.md`, `ai/`, PR merges | **Harrish (`h4rysh`)** | AI Pro (Lead) | `feat/core-*` |
| `backend/` CRUD, DB wiring, secondary routes | **Jaggu** | AI Pro | `feat/api-*` |
| `frontend/components/` (UI components, styling) | **Harshini** | Free | `feat/ui-*` |
| `frontend/pages/` (landing/static), `docs/`, tests, demo | **Joel** | Free | `feat/docs-*` |

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

## 6. Design Vibe & UI Consistency
*(Filled by Harrish's `mission-control` at kickoff so all 4 agents style the website identically)*
- **Theme:** `<e.g., Dark slate / Clean light>`
- **Colors:** Background `<#...>`, Surface `<#...>`, Primary Accent `<#...>`, Text `<#...>`
- **Typography & Radius:** `<e.g., Inter / Geist, rounded-xl cards, subtle borders>`
- **Shared Layout:** `<e.g., Top navbar in app/layout.tsx — do not duplicate headers inside subpages>`
