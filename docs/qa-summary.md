# QA Summary — The Build Archive

> Public-safe QA summary. Final status and scores only — no raw test logs or implementation details.

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

Captured against [kaviyashre-portfolio.vercel.app](https://kaviyashre-portfolio.vercel.app/).

### Desktop

| Metric | Score |
|---|---|
| Performance | **98** |
| Accessibility | **100** |
| Best Practices | **100** |
| SEO | **100** |
| CLS | **0.087** |

![Lighthouse desktop](../assets/screenshots/lighthouse-desktop.png)

### Mobile

| Metric | Score |
|---|---|
| Performance | **86** |
| Accessibility | **100** |
| Best Practices | **100** |
| SEO | **100** |
| CLS | **0.078** |

![Lighthouse mobile](../assets/screenshots/lighthouse-mobile.png)

> Note: Lighthouse UI can vary slightly between runs. The tables above are the final QA proof numbers for this showcase. Screenshots are the captured report artifacts stored in the repo.

---

## Performance notes

| Area | What was done |
|---|---|
| Homepage CLS | Layout-stable hero and section mounting; CLS under 0.1 |
| Hash navigation | Lazy-mounted section scroll-jump regression fixed |
| Logmoth | Kept lightweight — no heavy client-side AI SDKs |
| Hero image | Prioritized for LCP / `fetchPriority` |
| Shelf Hop | Dynamically imported on 404 only |
| Reduced motion | Respected across animated surfaces |
| SEO surface | Metadata, canonical URL, sitemap/robots, Open Graph/Twitter readiness |
| Images | Optimized images; below-fold sections lazy-loaded |

---

## Security checklist

| Item | Status |
|---|---|
| Source code remains private | Confirmed |
| No client-exposed secrets | Confirmed |
| No public API keys in repository or client bundle | Confirmed |
| No private archive data in public responses | Confirmed |
| No confidential workplace details | Confirmed |
| Logmoth refuses private / inappropriate prompts | Confirmed |
| Azure credentials server-side only | Confirmed |
| No debug metadata or source cards in visitor UI | Confirmed |
| This showcase repo contains no secrets or env values | Confirmed |

---

## Feature QA

### Logmoth

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
| No chat TTS | Passed |

### Blog narration

| Test area | Status |
|---|---|
| Paragraph extraction | Passed |
| Play / Pause / Resume / Stop | Passed |
| Active paragraph highlight sync | Passed |
| Stop returns to Scroll Mode | Passed |
| Closing modal cancels narration | Passed |
| Web Speech API browser compatibility | Passed |

### Error page

| Test area | Status |
|---|---|
| Unknown route → branded 404 | Passed |
| Shelf Hop loads via dynamic import | Passed |
| Shelf Hop does not load on homepage | Passed |
| Reduced-motion static fallback | Passed |
| Recovery CTA routes to archive | Passed |

---

## Production-readiness summary

- All QA checks passed
- Lighthouse scores meet targets (100 a11y / SEO / best practices on both form factors)
- Security and privacy boundaries enforced
- Graceful degradation for Azure and browser speech
- Source code and private archive data remain private
- This public showcase documents decisions without exposing implementation

**Live:** [kaviyashre-portfolio.vercel.app](https://kaviyashre-portfolio.vercel.app/)
