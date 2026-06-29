# AI/SHIP Website — Asset Drop List (v3 — Mascot Badge System)

The site is now wired with **Socialtel-style mascot badges across 14 placements**. Every badge tries to load a PNG from `canva_mascots/`; if not present, a consistent SVG fallback shows. So the site works today, and auto-upgrades the moment you drop the badges in.

---

## Folder structure

```
AiShip.in/
  index.html                 (already built — v3 with mascot badge system)
  canva_mascots/             (the badge files go here — top priority)
  founders/                  (4 founder portraits)
  pexels/                    (local copies of stock photos — optional)
  brand/                     (favicons + og-image)
```

---

## 1 / Mascot Badges — TOP PRIORITY (16 files)

Folder: `canva_mascots/`

All circular PNGs with **transparent background**, ~800x800px each, ~100KB max. Brand palette only (coral #F08597, orange #F89A4D, sun #FFBA25, ink #1A1A1A, cream #FBF7F0). Each badge should feel like a sticker — the same character family, different poses, different colourways.

**The bear-equivalent for AI/SHIP**: same character, different moods, in coral / orange / sun / cream disc backgrounds. Every badge should have a small AI/SHIP text mark somewhere (bottom of the disc usually).

### Tier 1 — Iconic stamps (used in nav, hero, chapters, footer)

| Filename | Use | Pose suggestion |
|---|---|---|
| `badge-curious.png` | Nav bar (32px) | Mascot face looking inquisitive, head tilted |
| `badge-building.png` | Hero photo corner sticker (large) | Mascot mid-action, tools in hand |
| `badge-thinking.png` | Chapter 04 + 08 | Mascot with hand on chin |
| `badge-wave.png` | Chapter 01 | Mascot waving hello |
| `badge-thumbsup.png` | Chapter 03 | Mascot thumbs up |
| `badge-pointing.png` | Chapter 05 | Mascot pointing toward you |
| `badge-heart.png` | Chapter 06 | Mascot with heart |
| `badge-money.png` | Chapter 07 | Mascot holding ₹ |
| `badge-celebrating.png` | Footer signature (large) | Mascot arms up, confetti |

### Tier 3a — "Built by one of us" stamp (kid-built cards)

| Filename | Use | Spec |
|---|---|---|
| `badge-kid.png` | Veer's + Damian's cards | Circular badge with mascot face in centre, "BUILT BY ONE OF US" text curving around the edge. Coral background. Higher detail than other badges since it sits prominently. |

### Tier 3b — Founder role badges (corner of each founder card)

| Filename | Founder | Pose |
|---|---|---|
| `badge-strategy.png` | Theresa Ronnie (Brand & Strategy) | Mascot with strategy book / lightbulb |
| `badge-product.png` | Sachin Uppal (Product & GTM) | Mascot with laptop / wrench |
| `badge-investor.png` | Arjun Vaidya (V3 Ventures) | Mascot with magnifying glass / chart |
| `badge-community.png` | Abhishek Shah (D2C Insider) | Mascot with people / hands up |

### Tier 3c — "What you walk out with" 4-cell stat block

| Filename | Cell | Pose |
|---|---|---|
| `badge-shop.png` | The Shop | Mascot in front of a small storefront |
| `badge-friends.png` | The Pack | Mascot with arms around two others |
| `badge-club.png` | The Club | Mascot holding a membership card |
| `badge-rupee.png` | The Rupee | Mascot holding a ₹ coin |

### Tier 3d — 7-day spine badges (one per day)

| Filename | Day | Suggested pose |
|---|---|---|
| `spine-01.png` | Day 01 / The Hunt | Mascot with binoculars |
| `spine-02.png` | Day 02 / The Pick | Mascot pointing at a choice |
| `spine-03.png` | Day 03 / The Build | Mascot at a laptop |
| `spine-04.png` | Day 04 / The Look | Mascot with a camera |
| `spine-05.png` | Day 05 / The Plumbing | Mascot with a wrench |
| `spine-06.png` | Day 06 / The Launch | Mascot waving from a launch pad |
| `spine-07.png` | Day 07 / The First Customer | Mascot with cash, big grin |

---

## 2 / Founder Photos (1 still missing)

Folder: `founders/`

| Filename | Status |
|---|---|
| `theresa-ronnie.jpg` | **MISSING** — pull from https://www.evolutionaryhabits.com/assets/theresa.jpg |
| `sachin-uppal.jpg` | In place |
| `arjun-vaidya.jpg` | In place |
| `abhishek-shah.jpg` | In place (clean version, no #HIRING overlay) |

---

## 3 / Pexels Stock (already hotlinked, local copies optional)

| Filename | Pexels URL |
|---|---|
| `pexels/hero-kid.jpg` | Pexels 15598845 by Sanket Mishra |
| `pexels/family-laptop.jpg` | Pexels 4308093 by Ketut Subiyanto |

Currently hotlinking from Pexels CDN. Drop local copies for speed.

---

## 4 / Brand & Social (4 files)

| Filename | Spec |
|---|---|
| `brand/favicon.svg` | 32x32, AI/SHIP wordmark |
| `brand/favicon.ico` | 32x32 legacy |
| `brand/og-image.png` | 1200x630, WhatsApp/LinkedIn share |
| `brand/apple-touch-icon.png` | 180x180, solid coral, white wordmark |

---

## How the fallback system works

Every badge has the same drop-in pattern:

```html
<span class="badge badge-md badge-coral">
  <img src="canva_mascots/badge-X.png" alt="" onerror="this.remove()">
  <svg><use href="#m-face"/></svg>
</span>
```

If the PNG loads, it covers the SVG (z-index: 2). If it fails, `this.remove()` deletes the img element silently and the coloured disc + SVG mascot face shows. The site is never broken, never has a placeholder image icon.

The shared SVG symbols (`#m-face`, `#m-wave`, `#m-wink`, `#m-builtbyus`) are defined once at the top of `<body>` and reused everywhere — consistent fallback character across all 14 placements.

---

## Priority order for Canva production

[Certain] If you can only export a few, ship them in this order:

1. **`badge-kid.png`** — Veer's and Damian's "Built by one of us" stamp. This is the single highest-leverage badge — it's the trust anchor on the cards parents look at hardest.
2. **`badge-celebrating.png`** + **`badge-building.png`** — Footer signature + hero photo sticker. Frames the entire visit.
3. **`badge-curious.png`** — Nav. First impression.
4. **Tier 3d (7 spine badges)** — The narrative arc of the program made visual.
5. **Tier 3a (4 founder role badges)** — Differentiates the four founders' roles instantly.
6. **Tier 3c (4 walkout badges)** — Reinforces what the buyer is buying.
7. **Tier 1 chapter badges** — Adds rhythm to the catalog feel.

---

_Generated by Claude for AI/SHIP, 29 June 2026. Tied to `index.html` v3 (mascot badge system + Pentagram-register copy)._
