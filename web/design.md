# Linger — Web Design System

> *a café, composed.*
> The public brand site. An editorial **magazine** experience — not a landing page. Visiting should feel like reading a high‑quality, faintly‑grained magazine: 克制 (restraint) · 极简 (minimal) · 控制 (control). Quiet luxury. Atmosphere is the vibe.

Reference north star: OURA — generous white space, centred framed photography, thin letter‑spaced labels, large light display type, narrow reading columns.

---

## 1. Principles

1. **Whitespace leads.** Empty space is the design. If a section feels empty, it's correct — resist filling it.
2. **One statement per view.** Never stack two big display headings in the same viewport. Hierarchy comes from space, not from competing type.
3. **Restraint over flourish.** No loud CTAs, no drop‑shadow card soup, no gradients, no emoji, no exclamation marks. The voice is quiet and assured.
4. **Photography is full‑frame, framed.** Images are centred within margins (magazine plates), not edge‑to‑edge clutter. Let the photograph breathe; keep type out of its lit subject.
5. **Print, not screen.** A constant fine grain + warm‑neutral paper makes the page feel printed.

---

## 2. Colour

### Canonical brand palette (official)
| Token | Hex | Role |
|---|---|---|
| Black | `#000000` | Primary text / ink |
| Olive‑sage grey | `#878676` | Muted accent (active, hairlines, detail) |
| Sage grey | `#A2A8A3` | Lighter neutral (secondary text, dividers) |
| Off‑white | `#F5F7F8` | Page background |

A near‑monochrome, muted scheme. The two sage‑greys are the **only** accents — no second colour, never a saturated hue.

### Currently in the build (to migrate → canonical)
The live `index.html` still uses warm near‑equivalents from the earlier pass:
`--paper:#FFFFFF` · `--ink:#26211B` · `--sage:#7E8A6B` / `--sage-deep:#5F6B4F` · `--paper-2:#F3F3F1`.
**Next step:** swap to the canonical palette — `--paper → #F5F7F8`, `--ink → #000000`, `--sage → #878676`, `--sage-deep`/secondary → `#A2A8A3`, hairlines from `#878676` at low alpha.

> Never use pure black on pure white as harsh slabs — let the off‑white ground and grain soften it.

---

## 3. Typography

Two faces, two voices. (Fraunces retired.)

| Use | Font | Notes |
|---|---|---|
| **Titles / display** | **Quicksand** (300–700) | Rounded geometric. Display weight **300**, tight tracking (`-1.5px`) at large sizes. |
| **Body & labels** | **Jost** (300–500, + italic) | Geometric, clean. Body weight **300**, generous leading (~1.9). Italic for pull‑quotes (Quicksand has no italic). |

### Scale (responsive, `clamp`)
- **Display** `clamp(44px, 9vw, 120px)` · weight 300 · `letter-spacing:-1.5px` · `line-height:0.96`
- **Lede** `clamp(20px, 2.6vw, 30px)` · weight 300 (Quicksand)
- **Prose / body** `clamp(15px, 1.2vw, 18px)` · weight 300 · `line-height:1.9` (Jost)
- **Eyebrow / labels** `11px` · weight 500 · `letter-spacing:2.6px` · UPPERCASE (Jost)
- **Nav links / CTA** `10.5px` · weight 500 · `letter-spacing:1.8px` · UPPERCASE, **bottom‑aligned**
- **Menu name** `clamp(20px, 2.4vw, 27px)` (Quicksand) · **description** `13.5px` Jost
- **Footer mark** Quicksand 38px with sage dot

Chinese characters are **accents only** — never a headline, never carrying meaning the English doesn't already give.

---

## 4. Layout

- **Gutter:** `--gutter: clamp(22px, 5vw, 72px)` — the page's left/right breathing margin.
- **Reading measure:** body columns ~46–60ch; menu list `max-width:760px`; hero/welcome copy `max-width:600px`.
- **Framed plates:** photography lives in `.frame` (centred, `max-width:880px`), with explicit aspect ratios per slot.
- **Vertical rhythm:** large section padding, `clamp(90–200px)` — air between movements like magazine spreads.
- **Grid:** asymmetric where used (Brand Story = `0.9fr / 1.6fr` quote‑vs‑prose). Single column on mobile (`≤820px`).

---

## 5. Texture & motion

- **Grain:** fixed full‑page SVG `feTurbulence`, `opacity:0.05`, `mix-blend-mode:multiply`. The signature "printed page" feel. Keep ≤ 0.06.
- **Easing:** everything slow and long — `cubic-bezier(.2,.7,.2,1)`, ~1s. Motion should feel like steam settling, never snappy or springy.
- **Reveal on scroll:** soft fade + 16px upward lift, staggered (`.d1`/`.d2` delays). IntersectionObserver, fires once.
- **Nav:** transparent over hero → frosts to translucent blur on scroll (`backdrop-filter`), hairline appears.
- **Scroll dot:** a single sage dot that breathes (slow opacity/scale pulse) — echoes the wordmark's dot.
- **Hover:** quiet underline drawing in (sage hairline) on links; gentle 2–4px lift on menu rows. No glow, no scale pop.

---

## 6. Components

- **Nav (fixed):** logo PNG left → links (Home · Menu · Brand Story) immediately left, **bottom‑aligned** → "Make your own coffee" CTA pinned right (underlined in sage). Mobile: links hide.
- **Image frame / slot:** `.frame` placeholder (numbered `01/02/03`, captioned with intended ratio) until a photo is dropped in; add `has-img` + `<img>` to fill. `object-fit:cover`.
- **Display heading:** big light Quicksand, left‑aligned, often overlapping the plate below it.
- **Eyebrow:** uppercase tracked label above each heading.
- **Pull‑quote:** italic Jost in the narrow left margin column, with an uppercase attribution.
- **Menu row:** name (Quicksand) + one‑line description (Jost) left, price right (`S$`, tabular), hairline divider, sage underline grows on hover.
- **Footer:** inverted (ink ground), the `linger.` wordmark + sage dot (the one place the full lockup appears), airy link columns.

---

## 7. Imagery

Editorial, warm, atmospheric, unhurried. Real rooms and rituals, soft light, a little motion blur is welcome.

| Slot | Section | Ratio | Current |
|---|---|---|---|
| **01** | Hero | 16:9 (cinematic band) | `Web pictures/Image1.jpg` |
| **02** | Brand Story | 16:9 wide | placeholder |
| **03** | Make Your Own Coffee | 5:4 | placeholder (interactive to be wired) |

Treatment: keep the lit subject uncovered by type; never stretch (preserve aspect, `cover`‑crop only); let the grain unify them.

---

## 8. Voice

Composed, warm, a little poetic, never precious. Avoid clichés ("passionate about coffee"). Lowercase restraint. Examples already in tone:
- *"a café, composed."*
- *"We didn't design a café. We designed the hour you spend in it."*
- *"Stay as long as the coffee's warm. Then stay a little longer."*

---

## 9. Don'ts

- No pure‑black/white harsh slabs · no second accent colour · no saturated hues.
- No stock‑SaaS patterns: gradient buttons, icon feature grids, logo walls, countdowns.
- No fast/bouncy/springy motion · no scroll‑jacking · no parallax‑heavy effects.
- No emoji, no exclamation marks, no all‑caps body shouting.
- Don't crowd photographs with text · don't fill negative space with ornament.
- The `linger.` lockup stays **off** the app home; on web it's fine in nav + footer.

---

## 10. Files

```
Linger/
├── app/            ← mobile app (index.html, splash.html)
├── web/            ← THIS site
│   ├── index.html
│   ├── design.md   ← this doc
│   ├── favicon.png / favicon-32.png  (white square, fitted wordmark)
├── Web pictures/   ← site photography (Image1–9)
├── CoffeePictures/ ← editorial coffee photos
└── Ref Picture/    ← linger-wordmark.png + references
```

Single self‑contained `index.html` — vanilla HTML/CSS/JS + inline SVG. No frameworks. Fonts: Quicksand + Jost (Google Fonts) only.
