# experiment

Claude Code skills for building presentations.

## Skills

### `presentation`

A custom skill (`.claude/skills/presentation/`) that turns a topic or document into a single self-contained HTML slide deck:

- Keyboard navigation (arrows/space), progress bar, slide counter
- Speaker notes hidden behind the `N` key
- Print-to-PDF support (`P` or Ctrl+P), one slide per page
- Seven layout types: title, section divider, content, two-column, big stat, quote, closing
- Theming through five CSS variables — no external assets, works offline

Files:
- `SKILL.md` — the workflow and content/design rules Claude follows
- `references/design.md` — typography scale, color, spacing, slide-count heuristics
- `assets/template.html` — the working deck template the skill copies from

### `frontend-slides`

Vendored from [zarazhangrui/frontend-slides](https://github.com/zarazhangrui/frontend-slides) (MIT License, © 2025 Zara Zhang) into `.claude/skills/frontend-slides/`, then **customized for the SUPER PAL brand**:

- `brand/` — SUPER PAL brand kit: inline-SVG logos (`super-pal-mark.svg`, `super-pal-logo.svg`) and `BRAND.md` (palette, typography, design-as-code voice)
- `bold-template-pack/templates/super-pal-terminal/` — the house template: emerald-on-void engineering-keynote style with terminal chrome (status bar, `// comment` captions, `[BRACKET]` chips, blinking block cursors), IBM Plex Mono headlines, IBM Plex Sans body. Inspired by Hermes-agent/xAI terminal minimalism and Airbnb-tech cleanliness.
- `SKILL.md` — brand-defaults section: new decks skip style discovery and use the SUPER PAL theme + logo automatically; say "show me styles" to get the stock 3-preview flow instead.

See `examples/super-pal-demo.html` for a live 6-slide demo of the theme (open in any browser, arrow keys to navigate).

## Usage

Clone this repo (or copy the `.claude/skills/` folders into your own project), open Claude Code, and ask for a presentation — e.g. *"make me a 12-slide deck about our Q3 results"*. Claude will pick up the matching skill automatically, or you can name one explicitly.
