# AI/SHIP

A seven-day AI-to-ecommerce sprint for Indian youth aged 12 to 30. Built by parents, for kids. Presented by Capt. HTTPS.

**Live URL:** [www.aiship.in](https://www.aiship.in)

---

## What this repo contains

A single-file static website (`index.html`) plus a folder of brand assets. Everything renders from one HTML file with inline CSS. No build step.

```
.
├── index.html              Single-file site — all CSS inline, no JS framework
├── ASSET_LIST.md           Specification for what images go where
├── canva_mascots/          Capt. HTTPS badge PNGs (6 poses + named slots)
├── founders/               4 founder portraits
└── pexels/                 Stock photography (Pexels-licensed)
```

## Who built it

The four founders:
- **Sachin Uppal** — Founder. Engineer turned digital marketer turned operator. Built Workswarm, NexoCircle, Telecallers.ai.
- **Theresa Ronnie** — Co-founder. Behaviourist + brand. Founder of Bombay Breed. Strategy across Microsoft, KPMG, Ford.
- **Arjun Vaidya** — Co-founder, V3 Ventures. Built and sold Dr Vaidya's.
- **Abhishek Shah** — Co-founder, D2C Insider. Runs India's largest D2C founder community.

Two of the four (Sachin and Ronnie) have 14-year-olds at home. The programme was built for their own kids first.

## The mascot

**Capt. HTTPS** — an astronaut character on a maroon enamel-pin disc, rose-gold copper inset, "AI/SHIP" curving across the top. Presented through the site as the host. Six poses: Backflip, Jetpack, Jumping, Running, Skateboard, Victory.

## Distribution rule

Internet-housed brand only. No school channels (schools take 50% commission and AI/SHIP will not give up half its margin).

## Stack

- HTML5 + inline CSS (no build, no bundler, no JS framework)
- Pexels CDN hotlinks fallback to local copies in `pexels/` when present
- thum.io API for live screenshots of the six "Built by us" sites
- Inter (Google Fonts) + JetBrains Mono + Noto Sans Devanagari

## Live built-by-us proof points

Six real sites linked in the catalog:
- `buyblacktshirt.com` — built by Veer Uppal, age 14
- `lifaafa.com` — built by Damian Melvin Jacob, age 14
- `bombaybreed.com` — Theresa Ronnie
- `evolutionaryhabits.com` — Theresa + Sachin + Sandeep
- `nexocircle.app` — Sachin Uppal
- `workswarm.ai` — Sachin Uppal

## Local dev

```bash
# Just open the file
open index.html
# Or serve with python
python3 -m http.server 8000
```

## License

© 2026 AI/SHIP. Built by parents, for kids. All rights reserved.
