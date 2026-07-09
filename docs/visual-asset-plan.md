# Visual Asset Plan — The Build Archive

> Checklist for screen captures and visual assets to complete this showcase repository.

## Asset inventory

| Asset | Path | Format | Capture notes |
|---|---|---|---|
| Hero preview | `assets/hero/build-archive-preview.gif` | GIF + optional MP4 | 8–12 sec cinematic overview of the full archive experience |
| Homepage overview | `assets/gifs/homepage-overview.gif` | GIF | Smooth scroll from hero through projects and experience |
| Logmoth interaction | `assets/gifs/logmoth-interaction.gif` | GIF | Open Logmoth, ask a recruiter-style question, show clean answer |
| Blog narration | `assets/gifs/blog-narration.gif` | GIF | Open a field note, press Play, show active paragraph highlight |
| Project modal | `assets/gifs/project-modal.gif` | GIF | Open SignalForge (or featured) case study modal |
| Theme switch | `assets/gifs/theme-switch.gif` | GIF | Toggle Soft mode → Space mode, show visual transition |
| Error page game | `assets/gifs/error-page-game.gif` | GIF | Navigate to unknown route, show 404 + Shelf Hop gameplay |
| Architecture flow | `assets/gifs/architecture-flow.gif` | GIF | Animated system flow (see storyboard below) |
| Desktop Lighthouse | `assets/screenshots/lighthouse-desktop.png` | PNG | Full Lighthouse report — desktop, production URL |
| Mobile Lighthouse | `assets/screenshots/lighthouse-mobile.png` | PNG | Full Lighthouse report — mobile, production URL |

---

## Capture specifications

### General

- **Source:** Production deployment at [kaviyashre-portfolio.vercel.app](https://kaviyashre-portfolio.vercel.app/)
- **Do not capture from local dev** — production build only
- **No private content** — verify no personal private details appear in any capture
- **Default theme:** Soft mode unless the asset specifically requires Space mode

### Viewports

| Form factor | Resolution | Use for |
|---|---|---|
| Desktop | 1440 × 900 | GIFs, hero preview, Lighthouse desktop |
| Mobile | 390 × 844 | Lighthouse mobile (optional mobile GIFs) |

### GIF settings

| Setting | Recommendation |
|---|---|
| Frame rate | 15–24 fps |
| Duration | 5–12 seconds per GIF |
| Tool | ScreenToGif, Kap, or LICEcap |
| Optimization | Compress after capture; target under 5 MB per GIF |

### PNG settings

| Setting | Recommendation |
|---|---|
| Lighthouse | Full report panel visible, not cropped to score numbers |
| Format | PNG for crisp text rendering |

---

## Per-asset capture guide

### Hero preview (`assets/hero/build-archive-preview.gif`)

1. Open production site in desktop viewport
2. Start recording at the loading page animation
3. Capture: load → hero reveal → brief scroll to projects → Logmoth peek
4. 8–12 seconds, cinematic pacing
5. Optional: export MP4 version for README embedding alternatives

### Homepage overview (`assets/gifs/homepage-overview.gif`)

1. Start at hero section
2. Smooth scroll through: about → projects → experience → blog → contact
3. Pause briefly on projects section
4. 8–10 seconds

### Logmoth interaction (`assets/gifs/logmoth-interaction.gif`)

1. Open Logmoth chat panel
2. Type a recruiter-style question (e.g., "What frontend technologies does Kaviya work with?")
3. Show the clean answer appearing — no debug metadata
4. 6–8 seconds

### Blog narration (`assets/gifs/blog-narration.gif`)

1. Navigate to a field note / blog post
2. Press Play on narration controls
3. Show active paragraph highlighting as speech progresses
4. Pause, then Stop — show return to scroll mode
5. 8–10 seconds

### Project modal (`assets/gifs/project-modal.gif`)

1. Click a featured project card (SignalForge recommended)
2. Show modal open with case-study content
3. Brief scroll within modal
4. Close modal
5. 6–8 seconds

### Theme switch (`assets/gifs/theme-switch.gif`)

1. Start in Soft mode
2. Toggle to Space mode — show full visual transition
3. Toggle back to Soft mode
4. 5–6 seconds

### Error page game (`assets/gifs/error-page-game.gif`)

1. Navigate to an unknown route (e.g., `/this-page-does-not-exist`)
2. Show branded 404 page
3. Play a few seconds of Shelf Hop
4. Show recovery CTA
5. 8–10 seconds

### Architecture flow (`assets/gifs/architecture-flow.gif`)

Animated diagram following the storyboard in [assets/diagrams/architecture-flow-storyboard.md](../assets/diagrams/architecture-flow-storyboard.md).

Can be produced as:
- Screen recording of a designed animation (Figma, After Effects)
- Programmatic animation exported as GIF
- Stepped reveal of a static diagram with motion

---

## Architecture flow storyboard reference

| Frame | Scene | Visual notes |
|---|---|---|
| 1 | Visitor opens The Build Archive | Browser chrome, loading animation |
| 2 | Next.js renders the archive shell | Hero and sections appear |
| 3 | Visitor opens Logmoth | Chat panel slides in, moth glow |
| 4 | Question moves into `/api/logmoth/ask` | Dotted connector line to API node |
| 5 | Local archive retrieval finds records | Soft archive cards highlight |
| 6 | Deterministic composer drafts answer | Text assembly visual |
| 7 | Azure refinement improves answer | Optional polish step, subtle glow |
| 8 | Local fallback handles failure | Fallback path shown as alternate route |
| 9 | Clean answer in UI | No debug metadata, clean bubble |

Visual style: soft archive cards, moth glow accents, dotted connector lines, step-by-step reveal. Not childish — editorial and technical.

---

## Completion checklist

- [ ] `assets/hero/build-archive-preview.gif`
- [ ] `assets/gifs/homepage-overview.gif`
- [ ] `assets/gifs/logmoth-interaction.gif`
- [ ] `assets/gifs/blog-narration.gif`
- [ ] `assets/gifs/project-modal.gif`
- [ ] `assets/gifs/theme-switch.gif`
- [ ] `assets/gifs/error-page-game.gif`
- [ ] `assets/gifs/architecture-flow.gif`
- [ ] `assets/screenshots/lighthouse-desktop.png`
- [ ] `assets/screenshots/lighthouse-mobile.png`
- [ ] Color palette values captured from production CSS → [design-system.md](./design-system.md)
