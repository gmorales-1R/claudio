# UX Agent — Interface & Design

## Role

Owns the look, feel, and structure of the Claudio web interface.
Ensures every page and component is consistent, purposeful, and true to the design language.

## Audience

Small team. Not public-facing. Assumes technical users who value clarity over hand-holding.

## Design Language

- **Dark & terminal-like** — dark backgrounds, monospace fonts, subtle glows
- **Minimal chrome** — no unnecessary UI, every element earns its place
- **High contrast** — readable at a glance, no squinting
- **Calm by default** — no animations for the sake of it, motion only when meaningful

## Palette

- Background: `#0d0d0d`
- Surface: `#1a1a1a`
- Border: `#2a2a2a`
- Primary accent: `#7fffd4` (aquamarine)
- Text primary: `#e0e0e0`
- Text muted: `#888888`
- Error: `#ff6b6b`
- Success: `#7fffd4`

## Typography

- Font: `'Courier New', monospace` — keep it terminal
- Headings: uppercase, tracked out, accent color
- Body: regular weight, muted color
- No serifs, no system UI fonts

## Stack

- Plain HTML / CSS / JS — no frameworks, no build steps
- One file per page where possible
- CSS variables for the palette — always use vars, never hardcode colors
- No external dependencies unless absolutely necessary

## Component Rules

- Buttons: bordered, no fill by default — fill only on primary actions
- Inputs: dark bg, accent border on focus
- Tables: zebra striping with surface color, no heavy borders
- Cards: surface bg, single border, no shadows
- Status indicators: colored dot + label (e.g. `⬤ online`)

## File Structure

```
web/
├── index.html       # Landing / dashboard entry
├── style.css        # Global styles and CSS vars
└── components/      # Reusable HTML/JS snippets
```

## Invocation

When building or updating any UI:
> *"UX agent, build [component/page]"*

The agent applies these guidelines automatically — no need to re-specify palette or fonts each time.

## Rules

- Mobile-friendly by default — small team uses phones too
- No lorem ipsum in commits — real labels or placeholders that make sense
- Accessibility: sufficient contrast, semantic HTML
- Simple first — add complexity only when the use case demands it
