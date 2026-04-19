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

## tortellini.html — same pattern as pasta.html
- Nav sections: Calculator | Filling | Shaping | Broth | Serving
- Same `.pg-hero`, `.pg-chrome-bar`, `.calc-wrap`, `.cards`, `.steps`, `.storage-grid` components as pasta.html
- Tortellini link is live in index.html (no longer "coming soon")

### Calculator config (sourced from Pasta_Tortellini_Matrix.xlsx → Config sheet)
- Primo: 19 tortellini/serving, 240 ml broth | Antipasto: 9 tortellini/serving, 120 ml broth
- Base batch: 400 g loin (pre-cooked weight), 300 g prosciutto, 300 g mortadella, 450 g parmigiano, 165 g eggs → 316 tortellini at 5 g each
- Pork loin card label: "pre-cooked weight" (not raw)

### Recipe decisions (David's method, not official)
- Shaping: 2¾-inch (7 cm) round cutter, NOT the official 6 cm square
- Filling per tortellino: 4 g at assembly (official is 5 g; base batch yield uses 5 g)
- Pasta thickness: level 7 (thinnest setting on David's machine)
- Always made ahead and frozen — never served fresh at a dinner party
- Two-pot serving method: cook in secondary broth, serve in clarified homemade broth
- Broth: clarified with egg whites (raft method); freeze ahead, chamber vacuum sealer preferred

### CSS gotcha — `.steps li` grid layout
- `.steps` uses `display: grid; grid-template-columns: 24px 1fr` with `::before` as counter
- If a `<strong>` tag is the first direct child of `<li>`, the following text node auto-places into the 24 px counter column and stacks word-by-word
- Fix: wrap ALL content inside each `<li>` in a `<div>` so it's one grid item: `<li><div>...</div></li>`
