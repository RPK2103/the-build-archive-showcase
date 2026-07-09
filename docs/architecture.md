# Architecture — The Build Archive

> Public-safe architecture overview. No implementation code, secrets, or private archive content.

## Stack

| Layer | Technology |
|---|---|
| Framework | Next.js 16 (App Router) |
| UI | React, TypeScript, Tailwind CSS |
| Motion | Framer Motion |
| Hosting | Vercel |
| AI refinement | Azure AI Foundry / Azure OpenAI |
| Retrieval | Local deterministic archive search |
| Narration | Browser Web Speech API |

## Boundaries

- **Portfolio shell** — editorial sections, project modals, field notes
- **AI layer** — Logmoth chat UI + `/api/logmoth/ask`
- **Archive layer** — structured local records, never shipped to the client
- **Error layer** — `not-found.tsx`, custom error pages, dynamically imported Shelf Hop

---

## High-level product architecture

```mermaid
flowchart TB
  subgraph Client["Client Experience"]
    V[Visitor]
    UI[Portfolio UI Shell]
    SEC[Hero · About · Skills · Experience · Projects · Field Notes · Contact]
    CHAT[Logmoth Chat UI]
  end

  subgraph Server["Server / AI Route"]
    EDGE[Vercel Edge / Next.js App Router]
    API["/api/logmoth/ask"]
  end

  subgraph Answer["Answering Layer"]
    RET[Local Archive Retrieval]
    COMP[Deterministic Answer Composer]
    AZ[Azure AI Foundry Refinement]
  end

  subgraph Resilience["Resilience"]
    FB[Local Fallback]
    OUT[Clean Answer UI]
  end

  V --> EDGE --> UI
  UI --> SEC
  UI --> CHAT
  CHAT --> API
  API --> RET --> COMP
  COMP --> AZ
  COMP --> FB
  AZ --> OUT
  FB --> OUT
  OUT --> CHAT
```

---

## Logmoth answering pipeline

```mermaid
flowchart TD
  Q[Question] --> I[Intent classification]
  I --> B[Boundary check]
  B --> F{Fast local path?}
  F -->|Greetings / story / private refusals| L[Immediate local response]
  F -->|Professional / project questions| R[Archive retrieval]
  R --> C[Deterministic answer composition]
  C --> A{Azure refinement useful?}
  A -->|Yes| AZ[Optional Azure refinement]
  A -->|No| U[Clean UI response]
  AZ --> OK{Azure succeeds?}
  OK -->|Yes| U
  OK -->|No| FB[Fallback to local answer]
  FB --> U
  L --> U
  U --> X[No source cards / debug metadata]
```

### Internal modes

| Mode | Triggered by | Behavior |
|---|---|---|
| **Default Mode** | Project, skill, experience questions | Standard retrieval and composition |
| **Recruiter Mode** | Role-fit, hiring, strengths | Professional tone, hiring-relevant emphasis |
| **Story Mode** | Personality, build history | Warmer, story-led responses from archive records |

### Design principles

- Compose deterministically first; refine only when it adds value
- Never expose debug metadata, source cards, or raw archive records
- Fast-path greetings, story prompts, and private-boundary refusals
- All Azure calls are server-side; no client-exposed API keys

---

## Fallback flow

Azure refinement is an enhancement, not a dependency.

```mermaid
flowchart TD
  A[Composed answer ready] --> B{Refinement requested?}
  B -->|No| C[Return composed answer]
  B -->|Yes| D[Call Azure AI Foundry]
  D --> E{Success?}
  E -->|Yes| F[Return refined answer]
  E -->|No / timeout| G[Return composed answer as fallback]
  C --> H[Clean answer UI]
  F --> H
  G --> H
```

The visitor always receives a clean answer. Fallback is invisible — no “AI unavailable” messaging in the chat surface.

---

## Blog narration flow

```mermaid
flowchart TD
  A[Open Field Note] --> B[Extract paragraphs]
  B --> C[Scroll Mode]
  C --> D[Play]
  D --> E[Browser SpeechSynthesis]
  E --> F[Active paragraph highlight]
  F --> G{User action}
  G -->|Pause / Resume| E
  G -->|Stop| H[Return to Scroll Mode]
```

- Scroll Mode and Audio Mode are separate states
- Paragraph-level sync between speech and highlight
- No ElevenLabs, no paid TTS, no external audio API
- Closing the modal cancels narration

---

## Error page lazy-load flow

```mermaid
flowchart TD
  A[Unknown route] --> B[not-found.tsx]
  B --> C[Archive-themed 404]
  C --> D[Dynamic import Shelf Hop]
  D --> E{Reduced-motion check}
  E -->|Motion OK| F[Shelf Hop game]
  E -->|Reduced motion| G[Static fallback]
  F --> H[Recovery CTA]
  G --> H
```

- Shelf Hop is dynamically imported — zero homepage bundle cost
- `prefers-reduced-motion` bypasses the game
- Recovery CTA returns visitors to the main archive

---

## Performance architecture

| Technique | Purpose |
|---|---|
| Hero image priority / `fetchPriority` | LCP optimization |
| Lazy-mounted sections | Reduced initial JS and layout work |
| Hash navigation stability | CLS under 0.1 |
| Lightweight Logmoth client | No heavy AI SDKs in the browser |
| Dynamic import for Shelf Hop | Error delight isolated from main bundle |
| Reduced motion respect | Accessibility across animated surfaces |

Architecture animation → `assets/gifs/architecture-flow.gif` (+ `.mp4`)  
Storyboard → [architecture-flow-storyboard.md](../assets/diagrams/architecture-flow-storyboard.md)  
QA scores → [qa-summary.md](./qa-summary.md)
