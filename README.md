# UX Impulse 2026

An animated homepage for the **UX Impulse 2026** design conference. The title is revealed through hundreds of hand-drawn crayon strokes painted live on screen.

## How to open

Just double-click `index.html` — no server, no dependencies, no build step. Works in any modern browser.

## How it works

1. The text "UX IMPULSE / 2026" is rendered offscreen to a hidden canvas using the **Jost** typeface.
2. The pixel buffer is sampled to build a pool of ~12,000 points that fall inside the letterforms.
3. 800 short SVG paths are generated — each a slightly wobbly curved stroke seeded from a random letter pixel.
4. Each stroke animates from its start point to its end point using `stroke-dashoffset` — exactly like a brush being dragged across paper.
5. Strokes are staggered with a `0.004s` delay so the text builds up progressively over ~3 seconds.
6. Each stroke has a two-colour gradient (from the vivid palette) with a faded tip, simulating wet paint.

## Tweaking

| What | Where | Values |
|---|---|---|
| Number of strokes | `var TOTAL = 800` | 400–1200 |
| Animation speed | `delay: i * 0.004` | lower = faster |
| Stroke duration | `duration: 0.25 + rnd(0.35)` | adjust range |
| Stroke thickness | `2.5 + rnd(4.5)` | px values |
| Easing | `ease: 'power2.inOut'` | any GSAP ease |
| Background colour | `background: #ece7dc` in CSS | any hex |
| Font size | `W * 0.17` / `H * 0.23` | scale factors |

## Dependencies

- [GSAP 3.12.5](https://gsap.com) — loaded from CDN, no install needed
- [Jost](https://fonts.google.com/specimen/Jost) — loaded from Google Fonts

## Files

```
ux-impulse-2026/
└── index.html   # everything is in here
```
