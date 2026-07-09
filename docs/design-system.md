# Design System — The Build Archive

> Visual identity and design principles. Exact hex values live in production CSS and are not invented here.

## Brand identity

| Attribute | Expression |
|---|---|
| **Premium** | Generous whitespace, refined typography, no clutter |
| **Minimal** | Every element earns its place |
| **Editorial** | Story-led layout, clear hierarchy |
| **Technical** | Architecture docs, case studies, engineering proof |
| **Soft** | Rounded surfaces, gentle gradients, warm neutrals |
| **Slightly strange** | Moth motif, archive metaphors, unexpected delight |
| **Archive-native** | Record cards, shelf metaphors, field notes |
| **Recruiter-ready** | Scannable hierarchy, clear CTAs, role-fit answers |

### What it is not

- Not template-like
- Not SaaS-generic
- Not support-chatbot-like
- Not dark-mode-only (Soft mode and Space mode coexist)

---

## Visual principles

**Layout** — Single-page editorial flow with hash-navigated sections. Project case studies open in modals. Consistent card language across projects, field notes, and Logmoth.

**Typography** — Strong contrast between display and body. Readable long-form for field notes. Monospace accents only where technical metadata needs it.

**The moth motif** — Logmoth’s soft glow appears in the chat avatar, loading choreography, Shelf Hop, and interactive accents. Strange enough to remember; soft enough not to feel gimmicky.

---

## Color tokens

| Token | Role |
|---|---|
| Archive background | Main Soft-mode page surface |
| Ink foreground | Primary text |
| Moth glow | Logmoth accent and interactive highlights |
| Soft card | Project tiles and archive surfaces |
| Space mode surface | Dark theme background |
| Border haze | Subtle dividers and card edges |
| Editorial accent | Emphasis in headlines and active states |

### Theme modes

| Mode | Character | Proof asset |
|---|---|---|
| **Soft mode** | Warm, editorial, archive-paper feel | `assets/screenshots/homepage-desktop-light.png` |
| **Space mode** | Deep surfaces, moth glow, night-archive atmosphere | `assets/screenshots/homepage-desktop-space.png` |

A dedicated `theme-switch.gif` is not in the repository yet. Soft/Space proof currently uses the static homepage screenshots above. Mobile Soft/Space captures also exist:

- `assets/screenshots/homepage-mobile-light.png`
- `assets/screenshots/homepage-mobile-space.png`

---

## Motion principles

| Principle | Application |
|---|---|
| Soft entrance | Sections fade and slide gently on scroll |
| Moth glow pulse | Subtle accent on Logmoth interactive elements |
| Loading choreography | Archive-themed loading page (`loading-page.png`) |
| Error delight | Shelf Hop on error pages only |
| Reduced motion | Animations and Shelf Hop respect `prefers-reduced-motion` |

Motion should feel archive-native — deliberate reveals, not bouncy SaaS transitions.

---

## Accessibility principles

| Principle | Implementation |
|---|---|
| Lighthouse 100 | Accessibility score on desktop and mobile |
| Keyboard navigation | Interactive elements reachable and operable |
| Focus indicators | Visible focus on interactive surfaces |
| Color contrast | Text meets WCAG requirements in both themes |
| Reduced motion | Disables animations and Shelf Hop |
| Semantic HTML | Heading hierarchy, landmarks, ARIA where needed |
| Screen reader | Logmoth chat accessible; narration does not block reading |

---

## Component language

| Component | Visual character |
|---|---|
| Project cards | Soft card surface, hover lift, tech stack tags |
| Project modal | Full case-study overlay (`signalforge-project-modal.png`) |
| Logmoth chat | Compact panel, moth avatar, clean message bubbles |
| Field notes | Long-form reading surface with narration controls |
| 404 page | Archive-themed recovery + optional Shelf Hop |
| Loading page | Branded animation, not a generic spinner |

---

## Capture notes

1. Capture from production: [kaviyashre-portfolio.vercel.app](https://kaviyashre-portfolio.vercel.app/)
2. Soft mode as default; Space mode for theme proof
3. Desktop 1440×900 · Mobile 390×844
4. No private content in any capture
5. Do not invent hex codes in documentation

Full asset inventory → [visual-asset-plan.md](./visual-asset-plan.md)
