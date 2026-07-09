# Design System — The Build Archive

> Visual identity and design principles for the portfolio. Color values to be captured from production CSS.

## Brand identity

The Build Archive is designed to feel:

| Attribute | Expression |
|---|---|
| **Premium** | Generous whitespace, refined typography, no clutter |
| **Minimal** | Every element earns its place; no decorative noise |
| **Editorial** | Story-led layout, magazine-quality hierarchy |
| **Technical** | Architecture docs, case studies, engineering proof |
| **Soft** | Rounded surfaces, gentle gradients, warm neutrals |
| **Slightly strange** | Moth motif, archive metaphors, unexpected delight |
| **Archive-native** | Card-based records, shelf metaphors, field notes |
| **Recruiter-ready** | Scannable hierarchy, clear CTAs, role-fit answers |

### What it is not

- Not template-like
- Not SaaS-generic
- Not support-chatbot-like
- Not a dark-mode-only developer cliché (Soft mode and Space mode coexist)

---

## Visual principles

### Layout

- Single-page editorial flow with hash-navigated sections
- Clear visual hierarchy: hero → about → projects → experience → blog → contact
- Project case studies open in modals — depth without page navigation
- Consistent card language across projects, blog posts, and Logmoth surfaces

### Typography

- Editorial heading scale with strong contrast between display and body
- Readable body text optimized for long-form field notes
- Monospace accents for technical metadata where appropriate

### The moth motif

**Logmoth** — the archive-native assistant — uses a subtle moth glow as its accent. The motif appears in:

- Logmoth chat avatar and accent glow
- Loading page animation
- Error page Shelf Hop game
- Soft accent highlights on interactive elements

The moth is strange enough to be memorable, soft enough to not feel gimmicky.

---

## Color palette

> Values to be captured from production CSS. Do not use invented hex codes in documentation.

| Token | Role | Value |
|---|---|---|
| Archive background | Main page surface (Soft mode) | To be captured from production CSS |
| Ink foreground | Primary text | To be captured from production CSS |
| Moth glow | Logmoth accent, interactive highlights | To be captured from production CSS |
| Soft card | Card surfaces, project tiles | To be captured from production CSS |
| Space mode surface | Dark theme background | To be captured from production CSS |
| Border haze | Subtle dividers and card borders | To be captured from production CSS |

### Theme modes

| Mode | Character |
|---|---|
| **Soft mode** | Default — warm, editorial, archive-paper feel |
| **Space mode** | Dark — deep surfaces, moth glow accents, night-archive atmosphere |

Theme switch should be captured in `assets/gifs/theme-switch.gif`.

---

## Motion principles

| Principle | Application |
|---|---|
| **Soft entrance** | Sections fade and slide in gently on scroll |
| **Moth glow pulse** | Subtle accent animation on Logmoth interactive elements |
| **Loading choreography** | Creative loading page with archive-themed animation |
| **Error delight** | Shelf Hop game with archive-appropriate physics |
| **Reduced motion** | All animations respect `prefers-reduced-motion`; Shelf Hop bypassed entirely |

Motion should feel archive-native — deliberate reveals, not bouncy SaaS transitions.

---

## Accessibility principles

| Principle | Implementation |
|---|---|
| **Lighthouse 100** | Accessibility score on both desktop and mobile |
| **Keyboard navigation** | All interactive elements reachable and operable |
| **Focus indicators** | Visible focus rings on all interactive surfaces |
| **Color contrast** | Text meets WCAG contrast requirements in both themes |
| **Reduced motion** | `prefers-reduced-motion` disables animations and Shelf Hop |
| **Semantic HTML** | Proper heading hierarchy, landmarks, and ARIA where needed |
| **Screen reader** | Logmoth chat accessible; blog narration does not block reading |

---

## Component language

| Component | Visual character |
|---|---|
| Project cards | Soft card surface, hover lift, tech stack tags |
| Project modal | Full case-study overlay with editorial layout |
| Logmoth chat | Compact panel, moth avatar, clean message bubbles |
| Field notes | Long-form reading surface with narration controls |
| 404 page | Archive-themed with recovery CTA and optional Shelf Hop |
| Loading page | Branded animation, not a generic spinner |

---

## Asset capture notes

When capturing visual assets for this showcase repository:

1. **Use production build** — capture from the deployed Vercel site, not local dev
2. **Both themes** — capture Soft mode as default; include Space mode in theme-switch GIF
3. **Consistent viewport** — 1440×900 for desktop captures, 390×844 for mobile
4. **GIF frame rate** — 15–24 fps for smooth but reasonable file sizes
5. **No private content** — ensure no personal private details appear in screenshots
6. **Lighthouse reports** — capture full report screenshots, not cropped scores

Full asset checklist → [visual-asset-plan.md](./visual-asset-plan.md)
