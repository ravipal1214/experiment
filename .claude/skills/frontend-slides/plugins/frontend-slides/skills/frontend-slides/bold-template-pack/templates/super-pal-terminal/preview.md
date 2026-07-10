# SUPER PAL Terminal Preview Card

Use this small file for title-slide previews only. For final deck generation, read the full design doc listed below.

## Files

- Full design doc: `bold-template-pack/templates/super-pal-terminal/design.md`
- Preview card: `bold-template-pack/templates/super-pal-terminal/preview.md`
- Brand kit (logo SVGs, palette, voice): `brand/BRAND.md`

## Selection Metadata

- Slug: `super-pal-terminal`
- Tagline: The SUPER PAL house style — emerald-on-void engineering keynote where the deck chrome is a terminal and the content stays airy.
- Mood: techno, futuristic, engineering, minimal, terminal-native, confident
- Tone: precise, quietly-technical, modern, understated
- Formality: medium
- Density: low-to-medium
- Scheme: dark
- Best for: This is the OWNER'S DEFAULT BRAND TEMPLATE — use it for any SUPER PAL deck unless the user asks to explore other styles. Natural fit: tech talks, architecture reviews, product/eng updates, AI/agent demos, developer-facing pitches.
- Avoid for: Decks the user explicitly wants light-schemed, playful, or non-branded; formal print-first documents.

## Visual Snapshot

A near-black void (#07090B) carries a 6%-opacity emerald graph grid, like engineering paper in the dark. Every slide is framed by a terminal status bar — `superpal@deck:~/section` left, `[03/12]` right — over a 1px hairline. Headlines are IBM Plex Mono 600 with an emerald blinking block cursor on section slides; body text is IBM Plex Sans so long content stays calm and readable. Captions are `// code comments`, kickers are `[BRACKET]` chips, bullets are emerald `->` arrows, cards are editor-buffer panels with dot chrome. The SUPER PAL mark (terminal tile with prompt chevron and cursor) sits bottom-left of every content slide; the full `SUPER_PAL // design as code` lockup anchors title and closing slides. One accent, ever: emerald #00E38C.

## Preview Ingredients

- Palette: void #07090B; panel #0D1117; fg #E6EDF3; muted #7D8590; accent #00E38C
- Typography: IBM Plex Mono (display + chrome); IBM Plex Sans (body)
- Signature move: terminal status bar with deck path and bracket slide index on every slide.
- Signature move: blinking emerald block cursor ending section headlines (solid under reduced motion).
- Signature move: `// comment` captions and `[CHIP]` kickers as the labeling language.
- Signature move: 64px emerald graph grid at 6% opacity behind everything.
- Signature move: SUPER PAL inline-SVG logo — mark bottom-left on content slides, full lockup on title/closing.

## Preview Rules

- Build exactly one title slide at 1920x1080 inside the fixed-stage model.
- Include the full SUPER PAL lockup (inline SVG from `brand/super-pal-logo.svg`) and the `$ whoami → SUPER PAL` author line.
- Preserve the palette, type roles, and terminal chrome described above.
- Use the user's real title/subtitle/context; do not copy demo slide content.
- The rendered preview must look like a real first slide, not a template-selection card.
- Never place internal workflow text on the slide: no `preview`, `generated from`, `preview.md`, `template`, `preset`, `style option`, `Option A/B/C`, file names, paths, or source-doc labels.
- Never place the template name or slug on the slide itself; mention it only in the chat message.
- Use only real deck content for visible chrome: deck title, real section title, date, author, company, page number, or genuine content phrases from the user material.
- Do not read `template.html` for preview generation.
- Do not read other templates' `design.md` files.
- After the user picks this template for the full deck, read the full design doc AND `brand/BRAND.md` before generating final slides.
