# Linger — *a café, composed.*

### Brand & website design for a four-city slow-coffee café, built as an editorial magazine rather than a landing page.

> *Linger* is a concept brand for a specialty café with rooms in **London, Barcelona, Hong Kong and Singapore**. The self-set brief was simple to say and hard to do: make the website *feel* like the café — unhurried, composed, quietly luxurious. Visiting it should feel less like browsing a site and more like turning the pages of a faintly-grained magazine. The whole project is an exercise in **restraint** — the discipline of leaving things out until only the essential, beautiful things remain.

---

## At a glance

| | |
|---|---|
| **Role** | Concept · art direction · UI design · front-end (solo) |
| **Type** | Brand expression + responsive website (concept project) |
| **Sector** | Specialty coffee / hospitality |
| **Year** | 2026 |
| **Pages** | 3 — Home, Menu, and an interactive *Make your own coffee* |
| **Build** | Hand-coded vanilla **HTML / CSS / JS** — no frameworks, no build step |
| **Type** | Quicksand + Jost (Google Fonts) |
| **North stars** | **OURA** (editorial restraint) · Apple *Liquid Glass* (frosted surfaces) · Starbucks Reserve (warmth) |
| **Keywords** | Web design · UI/UX · Brand · Editorial · Minimalism · Motion · Hospitality |

---

## 01 · The idea

Most café websites shout: hero slogans, bright buttons, a wall of food photos. Linger does the opposite. The concept is **"a café, composed."** — the site is *art-directed like a print magazine*, where empty space is the design and atmosphere does the selling.

Three words guided every decision:

- **Restraint** — if a section feels empty, it's correct. Resist filling it.
- **Minimal** — one statement per view; hierarchy comes from space, not from competing type.
- **Control** — nothing is accidental. Every margin, weight and easing curve is deliberate.

The brand promise is *time*: "slow coffee and unhurried hours." The interface had to embody that — slow transitions, generous whitespace, a quiet voice — so the medium *is* the message.

---

## 02 · The feeling we wanted to give

A visitor should feel they've stepped somewhere **calm, considered and a little luxurious** — the digital equivalent of a well-lit corner table on a slow morning. The emotional targets:

- **Composed, not busy.** Air around everything. The eye is never crowded.
- **Warm, not cold minimalism.** The palette and grain keep it human — "quiet luxury," never clinical.
- **Unhurried.** Motion settles like steam; nothing snaps or bounces.
- **Printed, not pixel.** A constant paper grain makes the screen feel like a page.
- **Confident and quiet.** No exclamation marks, no hard sell. The brand is sure of itself.

---

## 03 · Design principles (the rulebook)

A short constitution kept the work honest:

1. **Whitespace leads.** Empty space *is* the composition.
2. **One statement per view.** Never two competing display headings in the same frame.
3. **Restraint over flourish.** No gradient buttons, no drop-shadow card soup, no glow, no emoji, no exclamation marks.
4. **Photography is full-frame and framed** — centred magazine "plates," never edge-to-edge clutter. Type stays off the lit subject.
5. **Print, not screen.** A fine grain + warm-neutral paper makes the page feel printed.
6. **Motion is steam, not spring.** Everything slow, long and settling.

---

## 04 · Art direction

### 04.1 · Colour

A near-monochrome, warm-neutral scheme. The two sages are the **only** accents — there is no second colour and never a saturated hue. Black is deliberately avoided in favour of a soft espresso ink so nothing reads as harsh.

| Token | Value | Role |
|---|---|---|
| `--paper` | `#FFFFFF` | Page background |
| `--paper-2` | `#F3F3F1` | Faint panel / image placeholder |
| `--ink` | `#26211B` | Primary text — *espresso, never pure black* |
| `--ink-soft` | `rgba(38,33,27,.60)` | Secondary text |
| `--ink-faint` | `rgba(38,33,27,.38)` | Tertiary / captions |
| `--hair` | `rgba(38,33,27,.16)` | Hairline rules & dividers |
| `--sage` | `#7E8A6B` | The accent — underlines, the dot, active states |
| `--sage-deep` | `#5F6B4F` | Accent on hover / prices |
| *(footer)* | `#26211B` ground · `#F4F1EA` text | Inverted "dark room" footer |
| *(selection)* | `rgba(126,138,107,.26)` | Text-selection tint (sage) |

**Why these choices:** warm greys + a single muted sage read as *organic and calm* — coffee, linen, olive. Using `rgba` ink tints (rather than separate greys) keeps every secondary tone in the same warm family, so the palette never feels "designed by committee." The brand's canonical north-star palette (`#000000 / #878676 / #A2A8A3 / #F5F7F8`) informed the direction; the live build softens black to espresso for warmth.

### 04.2 · Typography

Two geometric faces, two voices.

| Use | Typeface | Treatment |
|---|---|---|
| **Display / titles / item names** | **Quicksand** (300 / 400 / 500) | Rounded, light geometric. Display at weight **300**, tight tracking. |
| **Body / labels / prices** | **Jost** (300 / 400 / 500) | Clean geometric. Body 300, labels 500 uppercase, prices tabular. |
| **Wordmark** | custom serif lockup `linger.` | The one serif note — paired with a sage dot. |

**The scale** (responsive `clamp()` so it breathes between mobile and desktop):

| Element | Size | Weight | Tracking |
|---|---|---|---|
| Hero display | `clamp(44px, 9vw, 120px)` | 300 | `-0.012em` |
| Section / menu titles | `clamp(30px, 5vw, 58px)` | 300 | `-0.012em` |
| Lede | `clamp(20px, 2.6vw, 30px)` | 300 | tight |
| Eyebrow / label | `11px` | 500 | `+2.6px` UPPERCASE |
| Nav links | `10.5px` | 500 | `+1.8px` UPPERCASE |
| Menu item name | `clamp(14px, 1.15vw, 16px)` | 400 | `-0.01em` |
| Description | `11.5px` | 300 | — |
| Price | `12px` | 500 | `+0.5px`, **tabular-nums** |
| Sub-label | `10px` | 500 | `+2.2px` UPPERCASE |

**The thinking:** the elegance comes from *contrast of register* — huge, airy, light display type set against tiny, tightly-tracked uppercase labels. That range is the luxury. Prices use `font-variant-numeric: tabular-nums` so digits align in a column like a printed menu. Letter-spacing is negative on big type (to feel set and intentional) and positive on small labels (to feel engraved). The font request is trimmed to only the three weights actually used and italics dropped — fewer files, faster paint.

### 04.3 · Photography

Editorial, warm, atmospheric — real rooms and rituals, soft light, a little motion blur welcomed. Images live inside centred **framed plates** with explicit aspect ratios, never stretched (cover-crop only), the grain unifying them. Crucially, photography is used **sparingly** — a few plates as breathing moments, never a photo per item.

### 04.4 · Texture — the "printed page"

The signature that stops it feeling like flat web:

- **Grain** — a fixed, full-page SVG `feTurbulence` (fractal noise, `baseFrequency .62`), `opacity ≈ 0.055`, `mix-blend-mode: multiply`. It sits over everything like paper tooth.
- **Vignette** — a whisper-soft radial darkening at the edges for depth.

Both are `position: fixed`, so they stay still as content scrolls beneath — exactly like ink on a held page.

### 04.5 · The dot

A single **sage dot** is the brand's quietest motif: the period in the `linger.` wordmark, the breathing scroll cue under the hero, and the divider between sections. One mark, reused — a thread of identity that never raises its voice.

---

## 05 · Layout & grid

- **Gutter:** `clamp(22px, 5vw, 72px)` — the page's breathing margin, scaling with the viewport.
- **Reading measures:** body columns sit narrow; the menu broadsheet caps at `1180px`, editorial spreads at `1060px` — so lines never sprawl.
- **Framed plates:** photography is centred within margins with fixed aspect ratios, like magazine plates.
- **Vertical rhythm:** large section padding (`clamp(54–110px)`) gives air between "movements," like spreads in a magazine.
- **Asymmetry on purpose:** spreads alternate (text-left/image-right, then image-left/text-right) so the eye keeps moving — the oldest trick in editorial layout.

---

## 06 · Voice & copy

The words are as art-directed as the type. **Composed, warm, a little poetic, never precious.** Lowercase restraint; no clichés ("passionate about coffee" is banned); no exclamation marks.

> *"a café, composed."*
> *"Stay a while."*
> *"Slow coffee and unhurried hours — the same quiet idea in London, Barcelona, Hong Kong and Singapore."*

Even the menu descriptions read like a quiet sommelier: *"Double espresso, velvety oat milk, and a whisper of dark Madagascar vanilla."*

---

## 07 · The pages

### 07.1 · Home

A single, slow scroll in three movements:

1. **The hero** — one large 16:9 framed plate of the room, sized so the image *and* the welcome line fit in one viewport without scrolling. Beneath it: the eyebrow *Stay a while*, the lede *A café, composed.* (with a sage period), the four-city dateline, and a breathing scroll dot.
2. **What's New / "Just Landed"** — a two-product editorial spread. The active drink sits centred; the other rests as a small, *desaturated* thumbnail on the opposite side; its description slides to the matching side. Click the thumbnail and image, copy and emphasis swap in one synchronised move.
3. **Branches / "Where to linger" — "the Atlas"** — an asymmetric spread: a single plate cross-fades through the four city photographs while a faded thumbnail strip sits alongside. Selecting a city swaps the photo *and* its details — name, address, a real **latitude/longitude coordinate**, and a directions link — all cross-fading together.

A lone sage **dot divider** marks the seam between movements, and the page closes on an **inverted, dark "back room" footer**.

### 07.2 · Menu

Deliberately **header-less** — it opens straight into the food, its first line aligned to the *exact same 150px* as the home hero so the two pages feel cut from one sheet.

- A **two-column broadsheet** so ~70% reads in a glance: *Coffee* (Signatures · Shaken & Blended · Latte & Cappuccino · Espresso Classics · Americano · Mocha) and *The Kitchen* (Pastry & Cakes · Spaghetti · Still Water).
- **Large, light course titles** with tiny tracked eyebrows (*To drink* / *To eat*) — the type-contrast that carries the elegance while the rows stay compact.
- Each row: name (Quicksand) · tabular price (sage) · one-line description (Jost), separated by hairlines.

**The signature feature — a branch selector.** Four café tabs (London · Barcelona · Hong Kong · Singapore). Choosing one does two things at once:

- **Currency follows the city** — prices convert live from a single base and render in `S$ / £ / € / HK$` with sensible rounding.
- **The menu itself varies** — *London* drops three items, *Barcelona* one, *Singapore* shows the full list, and *Hong Kong* gains an exclusive (a *Yuenyeung* — milk tea married to espresso). One menu, four subtly different rooms.

### 07.3 · Make your own coffee

A playful counterpoint to the stillness — a clean, single-column barista mini-game ("The Bench") that walks through Grind → Pull → Steam → Pour. It proves the brand can be warm and human, not just elegant.

---

## 08 · Signature components

- **Nav** — fixed, transparent over the hero; on scroll it **frosts** into a translucent blur (`backdrop-filter: blur(16px) saturate(140%)`, background `rgba(255,255,255,.80)`), tightens its padding, and grows a hairline. Apple "Liquid Glass," quietly.
- **Framed plate** — the reusable photographic unit: panel background, hairline border, soft long shadow.
- **Editorial spread** — text on one side, a hero image offset to the other, a desaturated secondary thumbnail beyond. One control choreographs several elements at once.
- **The Atlas** — a single plate that turns through places, with a gliding sense of selection.
- **Menu broadsheet** — two balanced, explicitly-placed columns (no fragile auto-balancing), each course a block.
- **Inverted footer** — the one place the full `linger.` lockup appears, in a calm dark room with airy link columns.

---

## 09 · Interaction & motion

**The governing idea:** *one control choreographs several things, slowly and in concert.* Click a thumbnail and the image, the copy, the emphasis and the active marker all move together — never a lone, mechanical toggle.

**The easing signature** is one custom curve used everywhere — `cubic-bezier(.2, .7, .2, 1)` — long and decelerating, so motion *arrives and settles* like steam, never snapping.

| Interaction | What happens | Duration |
|---|---|---|
| **Reveal on scroll** | soft fade + 16–18px upward lift, staggered, fires once | `1.1s` |
| **Nav frost** | transparent → blurred glass + hairline on scroll | `.5–.6s` |
| **What's New swap** | active image slides, thumbnail recedes, copy crosses over | `.85s` |
| **Atlas switch** | plate cross-fades with a faint scale-settle (1.06→1); details cross-fade | `.95s / 1.3s` |
| **Thumbnail state** | grayscale + 45% opacity → full colour when active | `.5s` |
| **Hover (links/rows)** | a sage underline draws in; colour warms to sage | `.35–.45s` |
| **Scroll dot** | gentle "breathing" pulse (opacity + scale) | `3.4s` loop |

Hover never uses scale-pops, glows or springs — only a drawing underline and a quiet colour shift. Reveals fire **once** (via `IntersectionObserver`), so scrolling back up doesn't re-trigger animation — calm, not restless.

### Microinteractions & details

- The **sage underline** that grows beneath nav links, menu rows and the "Get directions" / "Order now" micro-links.
- **Live coordinates** under each branch (`51.524° N, 0.078° W`) — an atlas detail an ordinary site never bothers with.
- **Tabular figures** so prices line up like a printed bill.
- The **breathing dot** that echoes the wordmark's period.
- Em-dashes, mid-dots and en-dashes used as deliberate typographic punctuation, never hyphens-as-dashes.

---

## 10 · Responsive behaviour

- Fluid everything — `clamp()` on type, gutters and spacing means the design *interpolates* between sizes rather than snapping at breakpoints.
- The hero is sized against viewport height so it always fits one screen.
- At ≤ 820px the two-column spreads and the menu broadsheet collapse to a single, centred column; image-and-thumbnail strips restack image-first; the nav links step aside.
- Touch is respected — controls are real buttons with comfortable hit areas (thumbnails ≥ 46px).

---

## 11 · Performance engineering

Polish a visitor *feels* without seeing:

- **No load "pop."** The hero is sized with `min(1112px, 92vw, (100vh − 380px) × 16/9)` and uses `vh` (not `svh`) after a diagnosis showed the small-viewport unit resolved late on first paint and caused a visible resize. Switching the unit made the hero render at its final size on the first frame.
- **Priority loading.** The hero photo and the logo are `preload`-ed with `fetchpriority="high"`; every below-the-fold image is `loading="lazy"`, so the most important pixels arrive first.
- **Zero layout shift.** The logo carries explicit `width`/`height` so its box is reserved before it downloads — no nudging the nav when it lands.
- **Leaner fonts.** The Google Fonts request is trimmed to the three weights actually used and italics removed, behind `preconnect` + `display=swap`.

---

## 12 · Accessibility & robustness

- **Works without JavaScript.** Reveal animations are gated behind a `.js` class added at the top of `<head>`, so if scripts fail the content is simply *visible* — never a blank page.
- **`prefers-reduced-motion`** collapses transitions and removes transforms for visitors who ask for calm.
- **Honest semantics.** Real `<button>`s for toggles, `aria-pressed` on tabs, `aria-label` on icon controls, `role="group"` on selectors, and `inert` on hidden cross-fade panels so off-screen links leave the tab order.
- **Anchored scrolling** uses `scroll-padding-top` so jump-links never hide under the fixed nav.
- **Warm, not harsh contrast** — espresso ink on warm paper instead of pure black on pure white.

---

## 13 · Technical approach

- **Vanilla & self-contained.** Each page is a single hand-written HTML file with inline CSS and a small vanilla-JS footer script. No frameworks, no bundler, no dependencies beyond two webfonts — fast, portable, and fully under control.
- **Design tokens.** Colour, type, easing and spacing live as CSS custom properties (`--ink`, `--sage`, `--ease`, `--gutter`…) so the whole system is tuned from one place and stays consistent across pages.
- **Shared furniture.** Nav, footer, grain, tokens and the reveal system are identical across pages, so the three files read as one site.

---

## 14 · Selected decisions & trade-offs

Design is what you choose *not* to do. A few telling calls:

- **Killed the "Brand Story" page.** For a truly minimal brand the story is carried by voice, photography and atmosphere — a separate page of "our story" text would only invite cliché. Two pages of menu + home say more by saying less.
- **One menu, four cafés.** Rather than four menu pages, a single broadsheet *reconfigures* by branch — currency and availability shift on selection. Less to maintain, more delightful to use.
- **The menu earned its elegance twice.** A first pass was too dense and uniform; the fix wasn't to abandon the compact two-column grid but to **restore type contrast and air** — large light course titles over tight rows. Density *and* composure.
- **English-only.** Earlier passes flirted with Chinese accent characters; they were removed for a single, clean, all-English voice.
- **Removed a "nice" animation.** The hero originally eased in with a 3.5% scale; on every refresh it read as a load glitch. Cutting it made the page feel *solid* — proof that the most considered motion is sometimes none.

---

## 15 · Outcome

A small, complete brand world — three pages that feel like one held object: a home you scroll like a magazine, a menu that quietly changes city, and a coffee you can "make" yourself. Every value in it — each hex, weight, easing curve and millisecond — was chosen on purpose, in service of one feeling:

> **Stay a while.**

---

### Colophon

Designed and built by hand — concept, art direction, UI and front-end. Typeset in **Quicksand** & **Jost**. Vanilla HTML / CSS / JS. Photography for atmosphere; everything else drawn from the system above.

**Tags:** Web Design · UI/UX · Brand Identity · Editorial · Art Direction · Motion Design · Front-end · Minimalism · Hospitality · Specialty Coffee
