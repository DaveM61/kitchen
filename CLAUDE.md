# kitchen.daveandmike.net — Repo Context

See ~/Documents/Git/CLAUDE.md for the full dave&mike visual system.

## Structure
- `index.html` — kitchen landing page (inline styles)
- `pasta.html` — Fresh Egg Pasta recipe page (different header technique — see below)
- `assets/kitchen_header.png` — header photo for index.html

## index.html
- 3-column `.link-groups` grid on desktop, collapses to 1 column on mobile (≤600px)
- Sections: Recipes · Tools · Menu Archive
- Uses `.link-group-label` (9px/500, letter-spacing 0.22em, uppercase, var(--muted))

## pasta.html — different header pattern
- Uses `.pg-hero` with `::before` pseudo-element gradient instead of mask-image
- Gradient direction: cream left → transparent right (horizontal)
- Gradient values: `#F0EDE7 0%, #F0EDE7 25%, rgba(240,237,231,0.6) 42%, transparent 58%`
- Title is inside `.pg-hero-inner` with `.pg-hero-title` class
- Has a sticky `.chrome-bar` below the hero for navigation
