# Case Study — The Build Archive

## Problem

Most developer portfolios fall into one of two traps: they look like generic templates, or they read like static resumes with no depth. Recruiters need to scan quickly. Engineers want to see real technical thinking. Visitors curious about fit have no way to ask questions without scheduling a call.

I needed a portfolio that could do all three — scan fast, go deep, and answer questions — without feeling like a SaaS landing page or a support chatbot.

## Why I built it

I wanted to treat my portfolio as a **shipped product**, not a weekend side project. That meant:

- Editorial storytelling instead of bullet-point résumé dumps
- A grounded AI assistant that knows my public work — not a generic ChatGPT wrapper
- Performance and accessibility scores that prove production discipline
- Branded error states and loading experiences that show care in every surface
- A visual identity that is premium, minimal, slightly strange, and unmistakably mine

The name **The Build Archive** reflects the core idea: this site is both a personal archive of projects and builds, and a living case study of how I think about product and engineering.

## Product thinking

### Portfolio as product

Every section was designed with a specific visitor intent:

| Visitor | Need | Design response |
|---|---|---|
| Recruiter | Fast scan of role fit and projects | Editorial single-page layout, clear hierarchy |
| Hiring manager | Depth on technical decisions | Case-study modals with architecture context |
| Engineer peer | Proof of craft | QA scores, architecture docs, AI pipeline design |
| Curious visitor | Interactive exploration | Logmoth — Ask The Archive |

### Logmoth as archive-native assistant

**Logmoth** is not a chatbot widget. It is a tiny archive-native entity — part moth, part librarian — that answers public-safe questions about my projects, experience, skills, role-fit, personality, blogs, and build history.

Key product constraints:

- Answers must be grounded in a local archive, not hallucinated
- No debug metadata or source cards visible to visitors
- Private, inappropriate, or out-of-scope prompts are refused
- The assistant should feel like part of the archive, not a third-party embed

### Delight without bundle cost

Creative surfaces — loading page, 404 page, **Logmoth Shelf Hop** mini game — are isolated from the homepage bundle. Error-page delight does not tax first paint.

## Technical decisions

| Decision | Rationale |
|---|---|
| **Next.js 16 App Router** | Server components, API routes, and modern routing for a single-page editorial experience |
| **Local deterministic retrieval** | Fast, predictable, fallback-safe — answers grounded before any cloud call |
| **Deterministic answer composer** | Structured responses from archive records, not raw LLM output |
| **Azure AI Foundry refinement** | Professional wording when useful; skipped when not needed |
| **Local fallback** | Graceful degradation if Azure is unavailable |
| **Web Speech API for narration** | Free, browser-native blog narration without paid TTS |
| **Framer Motion** | Soft, archive-appropriate motion with reduced-motion respect |
| **Dynamic import for Shelf Hop** | Error-page game never loads on the homepage |
| **Private source code** | Public showcase repo documents decisions; implementation stays private |

## Final outcome

**Live:** [kaviyashre-portfolio.vercel.app](https://kaviyashre-portfolio.vercel.app/)

**Lighthouse (final QA):**

| Metric | Desktop | Mobile |
|---|---|---|
| Performance | 98 | 86 |
| Accessibility | 100 | 100 |
| Best Practices | 100 | 100 |
| SEO | 100 | 100 |
| CLS | 0.087 | 0.078 |

**QA passed:** TypeScript compile, lint, production build, browser routing, Logmoth smoke tests, blog reader checks, loading/error page checks, security and privacy review.

The portfolio reads as a product. Recruiters can scan it in under a minute. Engineers can go deep through this showcase repository. Visitors can ask Logmoth questions and get grounded, professional answers — with safe refusals when they shouldn't.

This repository is the public face of that work: architecture, visuals, and proof — without exposing private source code or archive data.
