# Architecture Flow — GIF Storyboard

> Visual storyboard for the architecture flow animation.  
> Public-safe — no private implementation details.

## Final asset paths found

| Asset | Path | Status |
|---|---|---|
| Architecture flow GIF | `assets/gifs/architecture-flow.gif` | Present — used in README |
| Architecture flow MP4 | `assets/gifs/architecture-flow.mp4` | Present — linked below GIF |
| Static architecture PNG/SVG | — | Not present; Mermaid diagrams used instead |

---

## Architecture animation story

The animation should tell one clear product story:

**Visitor opens the archive → the shell renders → Logmoth is asked a question → the server route retrieves and composes → Azure may refine → fallback stays safe → a clean answer returns.**

It is a pipeline story, not a feature montage. Tone: editorial, technical, soft moth glow — not childish, not SaaS-generic.

---

## Frame-by-frame sequence

### Frame 1 — Visitor opens The Build Archive

**Scene:** Browser window with the production URL loading.

**Visual notes:**
- Loading page animation visible (archive-themed, not a spinner)
- Soft background, editorial typography emerging
- Moth motif subtly present in loading choreography

---

### Frame 2 — Next.js renders the archive shell

**Scene:** Hero section and portfolio layout appear.

**Visual notes:**
- Hero image prioritized and visible
- Section hierarchy clear: hero → about → projects
- Soft card surfaces for project tiles
- Transition from loading to shell is a gentle reveal

---

### Frame 3 — Visitor opens Logmoth

**Scene:** Logmoth chat panel opens.

**Visual notes:**
- Chat panel slides in from the archive edge
- Moth avatar with soft glow accent
- “Ask The Archive” / Ask Archive header visible
- Panel feels native to the archive, not an embedded third-party widget

---

### Frame 4 — Question moves into `/api/logmoth/ask`

**Scene:** User’s question travels from UI to API route.

**Visual notes:**
- Question text in a chat bubble
- Dotted connector line from chat UI to API node
- API node labeled `/api/logmoth/ask` — server-side boundary clear
- Moth glow traces the connection path

---

### Frame 5 — Local archive retrieval finds relevant records

**Scene:** Archive search matches records to the question.

**Visual notes:**
- Soft archive cards arranged in a grid or stack
- Matching cards highlight with moth glow
- Non-matching cards fade to lower opacity
- Label: “Local Archive Retrieval” — no record content shown
- Fast, deterministic — no cloud icon at this stage

---

### Frame 6 — Deterministic composer drafts the answer

**Scene:** Retrieved records assemble into a structured answer.

**Visual notes:**
- Highlighted archive cards feed into a composition node
- Answer text assembles line by line (not random generation visual)
- Label: “Deterministic Answer Composer”
- Structured, predictable — contrast with chaotic LLM visual tropes

---

### Frame 7 — Azure refinement improves professional answers when useful

**Scene:** Optional refinement step polishes the composed answer.

**Visual notes:**
- Dotted connector to Azure node (subtle)
- Label: “Azure AI Foundry Refinement”
- Framed as optional — dashed line or “when useful” annotation
- Answer text subtly refines (wording polish, not new facts)
- This step can be skipped visually in an alternate path

---

### Frame 8 — Local fallback handles failure safely

**Scene:** If Azure is unavailable, the composed answer returns directly.

**Visual notes:**
- Alternate path from Frame 6 bypassing Frame 7
- Label: “Local Fallback”
- Composed answer flows straight to UI — no error state
- Fallback path shown as a clean alternate route, not a failure visual
- Visitor experience is identical regardless of path

---

### Frame 9 — UI returns a clean answer with no debug metadata

**Scene:** Final answer appears in the Logmoth chat panel.

**Visual notes:**
- Clean message bubble with professional answer text
- No source cards, no debug panels, no confidence scores
- No archive record IDs or field names visible
- Moth glow settles — interaction complete
- Visitor can ask another question or close the panel

---

## Animation pacing

| Frames | Duration | Pacing |
|---|---|---|
| 1–2 | ~2 sec | Slow reveal — cinematic open |
| 3–4 | ~1.5 sec | Quick — user action to API |
| 5–6 | ~2 sec | Deliberate — retrieval and composition |
| 7–8 | ~1.5 sec | Branch — refinement or fallback |
| 9 | ~1 sec | Clean landing — answer in UI |
| **Total** | **~8–10 sec** | |

---

## Visual style guide

- Soft archive cards — rounded, warm surfaces for record representations
- Moth glow — subtle accent on Logmoth nodes and active steps
- Dotted connector lines — flow between pipeline stages
- Step-by-step reveal — each frame builds on the previous
- Editorial tone — technical but not sterile; strange but not childish
- No private details — generic labels only

---

## Notes for future replacement

The current `architecture-flow.gif` / `.mp4` pair is present and linked from the README. If a future pass replaces it:

1. Keep the same basenames so README links stay valid:
   - `assets/gifs/architecture-flow.gif`
   - `assets/gifs/architecture-flow.mp4`
2. Prefer a clearer stepped pipeline reveal over atmospheric-only motion
3. Match Soft/Space archive palette from production CSS (do not invent hex in docs)
4. Keep file size practical after compression
5. A static Mermaid diagram remains the source of truth for readable architecture; the GIF is the cinematic companion
6. If the current video/GIF feels rough, replace it — do not leave broken paths or invent alternate filenames in the README

## Production notes

- Export as `assets/gifs/architecture-flow.gif`
- Optional companion: `assets/gifs/architecture-flow.mp4`
- Can be produced in Figma, After Effects, or a programmatic animation
- Test with `prefers-reduced-motion` in mind — Mermaid / static stepped diagram is a valid reduced-motion alternative
