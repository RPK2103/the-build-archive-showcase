# QA Summary — The Build Archive

> Public-safe QA summary. This documents final status and scores — not raw test logs or implementation details.

## Final QA status

All checks passed before launch.

| Check | Status |
|---|---|
| TypeScript compile (`tsc`) | Passed |
| Lint | Passed |
| Production build | Passed |
| Local production build | Passed |
| Browser routing QA | Passed |
| Logmoth smoke tests | Passed |
| Blog reader checks | Passed |
| Loading page checks | Passed |
| Error page checks | Passed |
| Security / privacy review | Passed |

---

## Lighthouse scores

Captured against the production deployment at [kaviyashre-portfolio.vercel.app](https://kaviyashre-portfolio.vercel.app/).

### Desktop

| Metric | Score |
|---|---|
| Performance | **98** |
| Accessibility | **100** |
| Best Practices | **100** |
| SEO | **100** |
| CLS | **0.087** |

### Mobile

| Metric | Score |
|---|---|
| Performance | **86** |
| Accessibility | **100** |
| Best Practices | **100** |
| SEO | **100** |
| CLS | **0.078** |

Screenshots to be added:

- `assets/screenshots/lighthouse-desktop.png`
- `assets/screenshots/lighthouse-mobile.png`

---

## Performance notes

| Area | What was done |
|---|---|
| Homepage CLS | Layout-stable hero and section mounting; CLS under 0.1 on both form factors |
| Hash navigation | Lazy-mounted section scroll-jump regression fixed |
| Logmoth | Kept lightweight — no heavy client-side AI SDKs |
| Hero image | Prioritized for LCP |
| Shelf Hop | Dynamically imported on 404 only — zero homepage cost |
| Reduced motion | `prefers-reduced-motion` respected across all animated surfaces |

---

## Security checklist

| Item | Status |
|---|---|
| Source code remains private | Confirmed |
| No client-exposed secrets | Confirmed |
| No public API keys in repository or client bundle | Confirmed |
| No private archive data in public responses | Confirmed |
| No confidential workplace details in archive or responses | Confirmed |
| Logmoth refuses private / inappropriate prompts | Confirmed |
| Azure credentials server-side only | Confirmed |
| No debug metadata or source cards in visitor-facing UI | Confirmed |
| This showcase repo contains no secrets or env values | Confirmed |

---

## Logmoth QA

| Test area | Status |
|---|---|
| Greeting responses | Passed |
| Project questions (Default Mode) | Passed |
| Role-fit questions (Recruiter Mode) | Passed |
| Story / personality questions (Story Mode) | Passed |
| Private-boundary refusals | Passed |
| Azure refinement path | Passed |
| Local fallback when Azure unavailable | Passed |
| No debug/source metadata in UI | Passed |
| Clean answer formatting | Passed |

---

## Blog narration QA

| Test area | Status |
|---|---|
| Paragraph extraction | Passed |
| Play / pause / resume / stop controls | Passed |
| Active paragraph highlight sync | Passed |
| Stop returns to scroll mode | Passed |
| Web Speech API browser compatibility | Passed |

---

## Error page QA

| Test area | Status |
|---|---|
| Unknown route → branded 404 | Passed |
| Shelf Hop loads via dynamic import | Passed |
| Shelf Hop does not load on homepage | Passed |
| Reduced-motion static fallback | Passed |
| Recovery CTA routes to archive | Passed |

---

## Production-readiness summary

The Build Archive is production-ready:

- All QA checks passed
- Lighthouse scores meet or exceed targets (100 a11y/SEO/BP on both form factors)
- Security and privacy boundaries enforced
- Graceful degradation for Azure and browser speech API
- Source code and private archive data remain in the private repository
- This public showcase repository documents decisions without exposing implementation

**Live:** [kaviyashre-portfolio.vercel.app](https://kaviyashre-portfolio.vercel.app/)
