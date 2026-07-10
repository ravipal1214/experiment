# SUPER PAL — Brand Kit

This is the repo owner's brand. When generating a deck with the `super-pal-terminal` template (the default), apply everything in this file.

## Logo

Two assets, both zero-dependency inline SVG (paste the markup directly into the deck — never `<img src>` a file path):

- `brand/super-pal-mark.svg` — square mark (terminal tile + prompt chevron + cursor). Use small, bottom-left corner of every content slide at ~34px height, opacity 0.9.
- `brand/super-pal-logo.svg` — full lockup (mark + `SUPER_PAL` wordmark + `// design as code` tagline). Use on the title slide and closing slide only, ~72–96px height.

On light surfaces (rare in this brand) keep the tile's dark fill — the logo carries its own background and works anywhere.

## Palette

| Token | Value | Role |
|---|---|---|
| `--void` | `#07090B` | Canvas. Near-black, blue-leaning. Never pure #000. |
| `--panel` | `#0D1117` | Raised surfaces: code panels, cards, table rows |
| `--fg` | `#E6EDF3` | Primary text |
| `--muted` | `#7D8590` | Comments, captions, chrome, secondary text |
| `--accent` | `#00E38C` | THE emerald. Prompts, cursors, key data, links, logo |
| `--accent-dim` | `rgba(0,227,140,0.55)` | Accent at rest: ticks, borders of active elements |
| `--grid` | `rgba(0,227,140,0.06)` | Background grid lines |
| `--line` | `rgba(230,237,243,0.14)` | Hairlines, panel borders, dividers |

One accent hue only. Emphasis comes from size, weight, and the accent — never from adding colors.

### Named schemes

The palette above is the **emerald** scheme, the default. Four alternates are defined in the template's `design.md` under `schemes:` — request by name:

| Scheme | Look | When |
|---|---|---|
| `emerald` | Green on void (default) | Everyday decks |
| `blueprint` | Signal orange on mission-control blue, blueprint-blue grid | Flagship/keynote decks |
| `light` | Deep green on white | Print, handouts, bright rooms |
| `cyan` | Ice cyan on void | Infra/data topics |
| `amber` | Phosphor amber on void | Retro-futurist skin |

Scheme swaps change color tokens only — type, layout, chrome, and logo placement never change. On the `light` scheme, render logo tiles with light fill (`#F7F8F6`), dark chevron, and the scheme's green for stroke/cursor; reference renders live in `examples/super-pal-demo-*.html` in the repo root.

## Typography

- Display & headlines: **IBM Plex Mono**, weight 600, tight tracking. Monospace headlines ARE the brand.
- Body: **IBM Plex Sans**, weight 400 — keeps long text readable so the deck stays "techno but simpler".
- Chrome, tags, captions, data: **IBM Plex Mono**, weight 400.
- Fallback stacks: `'IBM Plex Mono', ui-monospace, SFMono-Regular, Menlo, Consolas, monospace` and `'IBM Plex Sans', -apple-system, 'Segoe UI', sans-serif`.

## Voice / design-as-code idioms

- Captions are code comments: `// shipped in v2.1`
- Labels are bracket chips: `[OK]` `[WIP]` `[03/12]`
- Section prompts: `> section_name` with a blinking block cursor `▮` (disable blink under `prefers-reduced-motion`)
- Deck path in the status bar: `superpal@deck:~/<section-slug>`
- Author line on title slides: `$ whoami → SUPER PAL`
