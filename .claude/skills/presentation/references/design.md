# Deck design reference

## Typography

Use a two-font system: a display font for headlines, a body font for everything else. The template defaults to system stacks so the file stays self-contained:

- `--font-display`: `"Avenir Next", "Segoe UI", system-ui, sans-serif`
- `--font-body`: same stack, regular weight

Scale (slides are 1280×720 design units, scaled to fit the window):

| Element | Size | Weight |
|---|---|---|
| Title-slide title | 72px | 700 |
| Section divider heading | 64px | 700 |
| Slide headline (h2) | 44px | 650 |
| Body / bullets | 28px | 400 |
| Captions, footers | 18px | 400 |
| Stat number | 160px | 750 |

Line-height: 1.15 for headlines, 1.45 for body. Never let a headline wrap past two lines — shorten the words instead of the type.

## Color

Define everything from five variables in `:root`:

- `--bg` — slide background. Near-white (`#fafaf8`) or near-black (`#101014`), never pure.
- `--fg` — primary text. ≥ 4.5:1 contrast against `--bg`.
- `--muted` — secondary text, captions. ~60% blend of fg toward bg.
- `--accent` — one saturated hue for emphasis: stat numbers, section numbers, links, the progress bar.
- `--accent-soft` — the accent at ~12% opacity, for tinted panels and highlights.

Rules:
- One accent hue per deck. Vary emphasis with size and weight, not extra colors.
- Dark decks read better on projectors for technical audiences; light decks for print-heavy or executive audiences.
- Accent on text only when large (≥ 44px) or bold, so contrast holds.

## Spacing and layout

- Slide padding: 80px sides, 64px top/bottom. Content never touches edges.
- Vertical rhythm: 24px between bullets, 40px between headline and body.
- Left-align by default. Center only title, section, stat, quote, and closing layouts.
- White space is a feature: a slide that looks empty at arm's length is usually right.

## Charts (inline SVG)

- Axis lines and labels in `--muted`; data marks in `--accent`; highlight one series or bar at full accent and mute the rest.
- No 3D, no gradients on data marks, no legend if direct labeling fits.
- Numbers on the chart in body size; the takeaway belongs in the headline, not the chart title.

## Slide-count heuristics

- Lightning talk (5 min): 6–8 slides
- Standard talk (15–20 min): 12–18 slides
- Deep dive (45 min): 25–35 slides, section dividers every 5–7 slides
- Roughly 1 minute per content slide; stat and section slides take ~15 seconds.
