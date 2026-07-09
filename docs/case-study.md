# Case Study — The Build Archive

## Problem

Most developer portfolios either look like templates or read like static resumes. Recruiters need to scan quickly. Engineers want real technical thinking. Curious visitors have no way to ask questions without scheduling a call.

I needed one surface that could do all three — scan fast, go deep, and answer questions — without feeling like a SaaS landing page or a support chatbot.

## Why I built it

I treated the portfolio as a **shipped product**, not a weekend side project:

- Editorial storytelling instead of résumé dumps
- A grounded AI assistant that knows public work — not a generic ChatGPT wrapper
- Performance and accessibility scores that prove production discipline
- Branded loading and error states that show care on every surface
- A visual identity that is premium, minimal, slightly strange, and unmistakably archive-native

**The Build Archive** is both a personal archive of builds and a living case study of how I think about product and engineering.

## Product thinking

| Visitor | Need | Design response |
|---|---|---|
| Recruiter | Fast scan of role fit and projects | Editorial single-page layout, clear hierarchy |
| Hiring manager | Depth on technical decisions | Case-study modals with architecture context |
| Engineer peer | Proof of craft | QA scores, architecture docs, AI pipeline design |
| Curious visitor | Interactive exploration | Logmoth — Ask The Archive |

**Logmoth** is a tiny archive-native entity — part moth, part librarian. Product constraints:

- Answers grounded in a local archive, not hallucinated
- No debug metadata or source cards in the visitor UI
- Private, inappropriate, or out-of-scope prompts refused
- Feels like part of the archive, not a third-party embed

Creative surfaces (loading page, 404, **Logmoth Shelf Hop**) stay isolated from the homepage bundle. Delight does not tax first paint.

## Technical decisions

| Decision | Rationale |
|---|---|
| Next.js 16 App Router | Server components, API routes, modern routing for an editorial single-page product |
| Local deterministic retrieval | Fast, predictable, fallback-safe grounding before any cloud call |
| Deterministic answer composer | Structured responses from archive records, not raw LLM output |
| Azure AI Foundry refinement | Professional wording when useful; skipped when not needed |
| Local fallback | Graceful degradation if Azure is unavailable |
| Web Speech API for narration | Free, browser-native field-note narration without paid TTS |
| Framer Motion | Soft archive motion with reduced-motion respect |
| Dynamic import for Shelf Hop | Error-page game never loads on the homepage |
| Private source code | Public showcase documents decisions; implementation stays private |

## Outcome

**Live:** [kaviyashre-portfolio.vercel.app](https://kaviyashre-portfolio.vercel.app/)

| Metric | Desktop | Mobile |
|---|---|---|
| Performance | 98 | 86 |
| Accessibility | 100 | 100 |
| Best Practices | 100 | 100 |
| SEO | 100 | 100 |
| CLS | 0.087 | 0.078 |

QA passed: TypeScript compile, lint, production build, browser routing, Logmoth smoke tests, blog reader checks, loading/error page checks, security and privacy review.

Recruiters can scan it in under a minute. Engineers can go deep through this showcase repository. Visitors can ask Logmoth grounded questions — with safe refusals when they shouldn't.

This repository is the public face of that work: architecture, visuals, and proof — without exposing private source code or archive data.
