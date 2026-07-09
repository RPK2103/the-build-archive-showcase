# Visual Asset Plan — The Build Archive

> Inventory of assets actually present in this repository, how they are used, and what remains optional to capture.

## Actual assets found

### Hero

| File | Type |
|---|---|
| `assets/hero/build-archive-preview.gif` | GIF |
| `assets/hero/build-archive-preview.mp4` | MP4 |
| `assets/hero/.gitkeep` | placeholder |

### GIFs + matching MP4s

| File | Matching MP4 |
|---|---|
| `assets/gifs/homepage-overview.gif` | `homepage-overview.mp4` |
| `assets/gifs/logmoth-interaction.gif` | `logmoth-interaction.mp4` |
| `assets/gifs/blog-narration.gif` | `blog-narration.mp4` |
| `assets/gifs/project-modal.gif` | `project-modal.mp4` |
| `assets/gifs/error-page-game.gif` | `error-page-game.mp4` |
| `assets/gifs/architecture-flow.gif` | `architecture-flow.mp4` |
| `assets/gifs/.gitkeep` | — |

### Screenshots

| File | Purpose |
|---|---|
| `hero-section.png` | Static hero proof |
| `homepage-desktop-light.png` | Soft mode desktop |
| `homepage-desktop-space.png` | Space mode desktop |
| `homepage-mobile-light.png` | Soft mode mobile |
| `homepage-mobile-space.png` | Space mode mobile |
| `about-section.png` | About section |
| `capability-graph.png` | Skills / capability graph |
| `experience-section.png` | Experience section |
| `projects-section.png` | Projects grid |
| `signalforge-project-modal.png` | Project modal static proof |
| `field-notes-section.png` | Field notes section |
| `blog-narration-modal.png` | Narration modal static proof |
| `logmoth-greeting.png` | Logmoth greeting |
| `logmoth-recruiter-answer.png` | Recruiter-mode answer |
| `logmoth-story-answer.png` | Story-mode answer |
| `loading-page.png` | Creative loading page |
| `error-page-game.png` | 404 / Shelf Hop static |
| `lighthouse-desktop.png` | Desktop Lighthouse report |
| `lighthouse-mobile.png` | Mobile Lighthouse report |
| `assets/screenshots/.gitkeep` | placeholder |

### Diagrams

| File | Purpose |
|---|---|
| `assets/diagrams/architecture-flow-storyboard.md` | Frame-by-frame architecture animation notes |

---

## Assets used in README

| Asset | File used | Purpose |
|---|---|---|
| Hero preview | `build-archive-preview.gif` (+ MP4 link) | Cinematic open |
| Homepage overview | `homepage-overview.gif` (+ MP4) | Visual walkthrough |
| Logmoth interaction | `logmoth-interaction.gif` (+ MP4) | Visual walkthrough |
| Blog narration | `blog-narration.gif` (+ MP4) | Visual walkthrough + narration section |
| Project modal | `project-modal.gif` (+ MP4) | Visual walkthrough |
| Theme switch | `homepage-desktop-light.png` + `homepage-desktop-space.png` | Static Soft/Space proof (no GIF) |
| Error page game | `error-page-game.gif` (+ MP4) | Visual walkthrough |
| Architecture flow | `architecture-flow.gif` (+ MP4) | Architecture section |
| Logmoth answer proof | `logmoth-recruiter-answer.png` | Logmoth section |
| Blog narration proof | `blog-narration-modal.png` | Narration section |
| Lighthouse desktop | `lighthouse-desktop.png` | QA section |
| Lighthouse mobile | `lighthouse-mobile.png` | QA section |

Supporting docs also reference additional screenshots where useful (design system Soft/Space, loading page, SignalForge modal).

---

## Missing optional assets

| Asset | Status | Workaround |
|---|---|---|
| `assets/gifs/theme-switch.gif` (+ MP4) | Missing | Soft/Space static screenshots used instead |
| Repository social preview (`repository-open-graph.png`, `repo-card.png`, `social-preview.png`, etc.) | Missing | No social-preview note embedded in README |
| Dedicated palette / token screenshot with hex values | Missing | Descriptive tokens only — no invented hex |
| Architecture diagram PNG/SVG (static) | Missing | Mermaid diagrams + architecture-flow GIF used |

### To capture later

- [ ] `theme-switch.gif` (+ optional MP4) — Soft → Space → Soft, 5–6 sec
- [ ] Repository social preview card for GitHub sharing (final branding, not a template with placeholder text)
- [ ] Optional: polished replacement for `architecture-flow.gif` if the current animation feels rough
- [ ] Optional: palette strip screenshot once production CSS tokens are exported

---

## Recommended capture specs

### General

- **Source:** Production only — [kaviyashre-portfolio.vercel.app](https://kaviyashre-portfolio.vercel.app/)
- **No private content** in any frame
- **Default theme:** Soft mode unless the asset requires Space mode

### Viewports

| Form factor | Resolution | Use for |
|---|---|---|
| Desktop | 1440 × 900 | GIFs, hero, Lighthouse desktop |
| Mobile | 390 × 844 | Mobile screenshots, Lighthouse mobile |

### GIF settings

| Setting | Recommendation |
|---|---|
| Frame rate | 15–24 fps |
| Duration | 5–12 seconds |
| Tool | ScreenToGif, Kap, or LICEcap |
| Size | Compress; prefer under ~5 MB per GIF when practical |

### PNG settings

| Setting | Recommendation |
|---|---|
| Lighthouse | Full report panel visible |
| Format | PNG for crisp text |

---

## Naming convention

```
assets/
  hero/
    build-archive-preview.gif
    build-archive-preview.mp4
  gifs/
    <feature-name>.gif
    <feature-name>.mp4
  screenshots/
    <section-or-state>.png
  diagrams/
    <diagram-name>.md | .png | .svg
```

Rules:

- kebab-case only
- no spaces in filenames
- matching GIF/MP4 pairs share the same basename
- do not invent filenames in docs before the file exists

---

## MP4 / GIF usage rule

1. Prefer **GIF inline** in README for visual walkthroughs (GitHub renders GIFs natively).
2. Add an **MP4 link below** when a matching `.mp4` exists.
3. Use **PNG screenshots** for static proof (Lighthouse, Soft/Space, Logmoth answer states).
4. Use **Mermaid** for architecture diagrams in markdown.
5. Use existing diagram PNG/SVG only if present — do not invent paths.
6. Never embed a social-preview template that still shows GitHub placeholder text; mark templates as reference-only if added later.
7. If a GIF is missing but a screenshot exists, use the screenshot. If both are missing, keep the section text-only.

---

## Category map (requested → actual)

| Category | Asset used |
|---|---|
| Hero preview | `assets/hero/build-archive-preview.gif` (+ `.mp4`) |
| Homepage overview | `assets/gifs/homepage-overview.gif` (+ `.mp4`) |
| Logmoth interaction | `assets/gifs/logmoth-interaction.gif` (+ `.mp4`) |
| Blog narration | `assets/gifs/blog-narration.gif` (+ `.mp4`) / `blog-narration-modal.png` |
| Project modal | `assets/gifs/project-modal.gif` (+ `.mp4`) / `signalforge-project-modal.png` |
| Theme switch | Soft/Space PNGs (GIF missing) |
| Error page / Shelf Hop | `assets/gifs/error-page-game.gif` (+ `.mp4`) / `error-page-game.png` |
| Architecture flow | `assets/gifs/architecture-flow.gif` (+ `.mp4`) |
| Lighthouse desktop | `assets/screenshots/lighthouse-desktop.png` |
| Lighthouse mobile | `assets/screenshots/lighthouse-mobile.png` |
| Mobile screenshots | `homepage-mobile-light.png` / `homepage-mobile-space.png` |
| Repository social preview | Not present |
