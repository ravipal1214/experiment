---
version: alpha
name: SUPER PAL Terminal
description: "The SUPER PAL house style: an engineering-keynote system on a near-black void with one emerald accent, where the deck chrome pretends to be a terminal and the content stays airy and simple. IBM Plex Mono headlines with blinking block cursors, IBM Plex Sans body for calm readability, a 6%-opacity emerald grid behind everything, and design-as-code idioms throughout — captions written as // comments, labels as [BRACKET] chips, section slides opened with a > prompt, and a status bar reading superpal@deck:~/section on every slide. Cultural references: Hermes agent / xAI terminal minimalism, Vercel and Linear dark surfaces, Airbnb Engineering blog cleanliness. Techno, but simpler: the terminal is the frame, never the noise."

colors:
  void: "#07090B"
  panel: "#0D1117"
  fg: "#E6EDF3"
  muted: "#7D8590"
  accent: "#00E38C"
  accent-dim: "rgba(0, 227, 140, 0.55)"
  grid: "rgba(0, 227, 140, 0.06)"
  line: "rgba(230, 237, 243, 0.14)"

color-aliases:
  bg: void
  rule: line

typography:
  display-hero:
    fontFamily: "IBM Plex Mono, ui-monospace, SFMono-Regular, Menlo, monospace"
    fontSize: "150px"
    fontWeight: 600
    lineHeight: 1.02
    letterSpacing: -0.02em
  display-closing:
    fontFamily: "IBM Plex Mono, ui-monospace, SFMono-Regular, Menlo, monospace"
    fontSize: "120px"
    fontWeight: 600
    lineHeight: 1.05
    letterSpacing: -0.015em
  display-chapter:
    fontFamily: "IBM Plex Mono, ui-monospace, SFMono-Regular, Menlo, monospace"
    fontSize: "104px"
    fontWeight: 600
    lineHeight: 1.05
    letterSpacing: -0.015em
  headline:
    fontFamily: "IBM Plex Mono, ui-monospace, SFMono-Regular, Menlo, monospace"
    fontSize: "68px"
    fontWeight: 600
    lineHeight: 1.12
    letterSpacing: -0.01em
  stat-numeral:
    fontFamily: "IBM Plex Mono, ui-monospace, SFMono-Regular, Menlo, monospace"
    fontSize: "300px"
    fontWeight: 600
    lineHeight: 1
    letterSpacing: -0.03em
  quote:
    fontFamily: "IBM Plex Mono, ui-monospace, SFMono-Regular, Menlo, monospace"
    fontSize: "60px"
    fontWeight: 400
    lineHeight: 1.3
  body-lede:
    fontFamily: "IBM Plex Sans, -apple-system, Segoe UI, sans-serif"
    fontSize: "34px"
    fontWeight: 400
    lineHeight: 1.5
  body:
    fontFamily: "IBM Plex Sans, -apple-system, Segoe UI, sans-serif"
    fontSize: "28px"
    fontWeight: 400
    lineHeight: 1.55
  panel-title:
    fontFamily: "IBM Plex Mono, ui-monospace, SFMono-Regular, Menlo, monospace"
    fontSize: "26px"
    fontWeight: 600
    lineHeight: 1.2
    letterSpacing: 0.02em
  mono-comment:
    fontFamily: "IBM Plex Mono, ui-monospace, SFMono-Regular, Menlo, monospace"
    fontSize: "22px"
    fontWeight: 400
    lineHeight: 1.4
    letterSpacing: 0.01em
  mono-chrome:
    fontFamily: "IBM Plex Mono, ui-monospace, SFMono-Regular, Menlo, monospace"
    fontSize: "18px"
    fontWeight: 400
    lineHeight: 1
    letterSpacing: 0.06em
  mono-chip:
    fontFamily: "IBM Plex Mono, ui-monospace, SFMono-Regular, Menlo, monospace"
    fontSize: "18px"
    fontWeight: 600
    lineHeight: 1
    letterSpacing: 0.08em
    textTransform: uppercase

spacing:
  edge: "96px"
  pad-top: "120px"
  pad-bottom: "120px"
  gap-lg: "56px"
  gap-md: "36px"
  gap-sm: "22px"
  gap-xs: "12px"

canvas:
  width: 1920
  height: 1080

components:
  emerald-grid:
    backgroundImage: "linear-gradient(to right, {colors.grid} 1px, transparent 1px), linear-gradient(to bottom, {colors.grid} 1px, transparent 1px)"
    backgroundSize: "64px 64px"
    description: "Permanent ::before pseudo on every stage: 64px graph grid in 6%-opacity emerald over the void. It reads as engineering paper in the dark. Never brighter than 8% — the grid is felt, not seen."
  status-bar:
    position: absolute
    top: "40px"
    left: "{spacing.edge}"
    right: "{spacing.edge}"
    borderBottom: "1px solid {colors.line}"
    paddingBottom: "16px"
    description: "Terminal status bar on every slide. Left: mono-chrome path 'superpal@deck:~/<section-slug>' with 'superpal' in {colors.accent}. Right: bracket index '[03/12]' in {colors.muted}. A 1px hairline runs beneath. This is the deck's signature frame."
  logo-corner:
    position: absolute
    left: "{spacing.edge}"
    bottom: "44px"
    height: "34px"
    opacity: 0.9
    description: "SUPER PAL square mark (inline SVG from brand/super-pal-mark.svg) bottom-left on every content slide. Title and closing slides use the full lockup (brand/super-pal-logo.svg) at 72-96px instead, placed in the composition."
  prompt-headline:
    description: "Section/chapter slides open with an accent '>' prompt glyph before the headline and end with a blinking block cursor: an inline-block 0.55em-wide, 0.95em-tall {colors.accent} rectangle animated with a 1.1s steps(2) opacity keyframe. Under prefers-reduced-motion the cursor stays solid, no blink."
  comment-caption:
    color: "{colors.muted}"
    description: "Every caption, annotation, and source line is written as a code comment: '// caption text' in mono-comment style. Two-slash prefix always, muted color, never italic."
  bracket-chip:
    border: "1px solid {colors.accent-dim}"
    color: "{colors.accent}"
    padding: "8px 14px"
    borderRadius: "6px"
    description: "Status chips rendered as mono-chip text in literal brackets: [OK], [WIP], [Q3], [v2.1]. Used as kickers above headlines and as inline status markers in tables/lists."
  code-panel:
    background: "{colors.panel}"
    border: "1px solid {colors.line}"
    borderRadius: "14px"
    padding: "36px 40px"
    description: "Raised card styled as an editor buffer: a slim header row with three 10px dots ({colors.muted} at 40%, one in {colors.accent-dim}) and a mono filename tag, then the content. Used for two-column comparisons, figures, code samples, and feature cards. Max 3 panels per slide."
  arrow-bullet:
    description: "List bullets are mono '->' glyphs in {colors.accent}, hanging in a 52px gutter; bullet text is body (Plex Sans). Never disc bullets. Max 5 items per list, one line each where possible."
  ascii-divider:
    color: "{colors.line}"
    description: "Horizontal separators built from box-drawing characters ('─' repeated) or a 1px {colors.line} rule with a short 60px {colors.accent} segment at the left end. Use the accent-segment variant under headlines."
  stat-block:
    description: "Big-number slides: stat-numeral in {colors.fg} with the key digit group or unit suffix in {colors.accent}, and a single comment-caption beneath ('// context for the number'). One stat per slide, centered, nothing else."
  inline-svg-charts:
    description: "Charts are inline SVG only. Axis lines and labels in {colors.muted} at mono-chrome size; data marks in {colors.accent}; non-focus series in {colors.line}. Grid-aligned, no gradients, no 3D, direct labels over legends."
  whoami-line:
    description: "Title-slide author line rendered as a shell exchange in mono-comment: '$ whoami' on one line, '→ SUPER PAL · <date>' on the next, with '$' and '→' in {colors.accent}."

rules:
  - "One accent. Emerald is the only hue in the deck; emphasis is size and weight, never a second color."
  - "Terminal chrome is a frame, not content: status bar, chips, comments, and cursor are small and quiet; headlines and whitespace dominate the composition."
  - "Body text is always Plex Sans. If a run of body text is set in mono, it must BE code, a path, or a command."
  - "Dark only. No light-mode variant; print exports keep the void background."
  - "Density: speaker-led decks max 3 arrow-bullets or 1 stat or 1 quote per slide; reading decks max 5 bullets or 3 code-panels."
  - "Load Google Fonts (IBM Plex Mono 400/600, IBM Plex Sans 400/500) with the documented fallback stacks so the deck degrades gracefully offline."

cjk:
  note: "For CJK decks swap body to 'IBM Plex Sans JP' (or system CJK sans) with letter-spacing 0 and line-height 1.7; keep headlines in IBM Plex Mono for Latin runs and never uppercase-transform CJK text."
