---
name: presentation
description: Create polished, self-contained HTML slide decks. Use when the user asks for a presentation, slide deck, pitch deck, slides, or a talk on any topic. Produces a single HTML file with keyboard navigation, speaker notes, and print-to-PDF support.
---

# Presentation Skill

Turn a topic, document, or set of notes into a professional slide deck delivered as **one self-contained HTML file** the user can open in any browser, present full-screen, and print to PDF.

## Workflow

1. **Understand the ask.** Identify topic, audience, purpose (inform / persuade / teach), desired length, and tone. If the user gave source material (a doc, code, data), read it first. Only ask a clarifying question if the topic itself is ambiguous — otherwise pick sensible defaults (10–14 slides, professional tone) and proceed.

2. **Outline before building.** Draft the slide list as a short outline (title → agenda/hook → 3–5 content sections → summary/call-to-action → closing). Show the outline to the user in your reply, but do not block on approval unless they asked to review it first.

3. **Build the deck.** Copy `assets/template.html` from this skill directory as the starting point — it contains working navigation, progress bar, speaker-notes toggle, and print styles. Replace the example slides with real content. Do not rewrite the JS or the CSS framework; only edit slide markup and the theme variables at the top of the stylesheet.

4. **Deliver.** Save the file as `<topic-slug>-slides.html` in the user's requested location (or the current project). Send it to the user with SendUserFile (display: render) if available, and tell them the controls: arrow keys / space to navigate, `N` for speaker notes, `P` or Ctrl+P to print to PDF.

## Content rules

- **One idea per slide.** If a slide needs a paragraph to explain, split it.
- **Headlines carry the message.** Write assertion headlines ("Latency dropped 40% after caching"), not labels ("Results").
- **Max ~5 bullets, ~8 words each.** Move detail into speaker notes (`<aside class="notes">`), not onto the slide.
- **Numbers get big-stat slides.** A key metric deserves its own slide in huge type with one line of context.
- **Every deck ends with an action.** Summary, next steps, or a question — never trail off on a content slide.

## Slide layouts

The template provides these layout classes on `<section class="slide ...">`:

| Class | Use for |
|---|---|
| `layout-title` | Opening slide: title, subtitle, author/date |
| `layout-section` | Section divider: numbered, oversized heading |
| `layout-content` | Default: headline + bullets or short prose |
| `layout-two-col` | Comparison, before/after, text + figure |
| `layout-stat` | One huge number + one-line caption |
| `layout-quote` | Pull quote with attribution |
| `layout-closing` | Thank-you / call-to-action / contact |

## Design rules

- Set the deck's personality only via the CSS custom properties in the `:root` block (`--accent`, `--bg`, `--fg`, `--font-display`, `--font-body`). Pick an accent that fits the topic; keep contrast ratio ≥ 4.5:1.
- Charts and diagrams must be inline SVG — no external images or CDN scripts; the file must work offline.
- If the user supplies brand colors or a logo (as SVG/data URI), apply them in the theme variables and title slide.
- Read `references/design.md` before styling for typography scale, spacing, and color guidance.

## Speaker notes

Put presenter-facing detail in `<aside class="notes">…</aside>` inside each slide. Notes are hidden during presentation and toggle with the `N` key. Use them for the detail you removed from slides in step "Content rules".
