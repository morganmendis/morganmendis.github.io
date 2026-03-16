# CLAUDE.md

This file provides guidance to AI assistants (Claude and others) working in this repository.

## Project Overview

This is a personal portfolio/blog website for Morgan Mendis, hosted on GitHub Pages at `morganmendis.github.io`. It is a simple, static website with no build tools, frameworks, or dependencies.

## Repository Structure

```
morganmendis.github.io/
├── index.html      # Landing page with intro and quote
├── aboutme.html    # Personal biography and contact info
├── style.css       # All site styling
├── page.js         # Minimal JavaScript (currently unused)
├── bg_foto.jpeg    # Background image asset
└── CLAUDE.md       # This file
```

## Technology Stack

- **HTML5** — Semantic markup, no templating engine
- **CSS3** — Vanilla CSS with flexbox; no preprocessors (no Sass/Less)
- **JavaScript** — Vanilla JS only; the single `confirm()` call in `page.js` is currently commented out in the HTML
- **No package manager** — No `package.json`, `yarn.lock`, or `node_modules`
- **No build step** — Files are served directly as-is by GitHub Pages

## Development Workflow

### Local Development

Open HTML files directly in a browser — no dev server is required:

```bash
open index.html       # macOS
xdg-open index.html   # Linux
```

Or use any static file server (e.g., Python's built-in):

```bash
python3 -m http.server 8080
```

### Deployment

Pushing to the `master` branch automatically deploys to GitHub Pages. There is no CI/CD pipeline; deployment is manual and immediate on push.

### Branching

- `master` — production branch, maps directly to the live site
- Feature branches use the `claude/` prefix for AI-assisted work (e.g., `claude/add-claude-documentation-Xwou5`)

## Code Conventions

### HTML

- Use semantic HTML5 elements where appropriate
- Element IDs use `snake_case` (e.g., `about_img_1`, `index_1_img`)
- No CSS classes are used — styling is applied via element and ID selectors
- External images should be avoided; prefer locally committed assets

### CSS (`style.css`)

- Color scheme: white body text (`#FFFFFF`), red links/headings, green quotes (`#00FF00`)
- Background: fixed `bg_foto.jpeg` with a semi-transparent blue overlay (`#d0e4fe`)
- Content containers: `<div>` elements styled with `opacity: 0.6` for the background
- Font: `Cambria, Georgia, serif`
- No media queries currently; the site is not yet mobile-responsive

### JavaScript (`page.js`)

- Currently contains only a single `confirm()` dialog and is not loaded by any page
- Keep JavaScript minimal; prefer HTML/CSS solutions where possible

### File Naming

- HTML pages: lowercase, no separators (e.g., `aboutme.html`)
- Assets: lowercase with underscores (e.g., `bg_foto.jpeg`)
- Stylesheets/scripts: lowercase (e.g., `style.css`, `page.js`)

## Known Issues / Limitations

- **Broken external image**: `index.html` references an `imgur.com` image that no longer loads; prefer replacing with a locally committed image
- **No viewport meta tag**: The site lacks `<meta name="viewport">`, making it render poorly on mobile devices
- **No accessibility attributes**: Many images are missing `alt` text or have empty `alt` attributes

## Commit Style

Keep commit messages short and descriptive in the imperative mood, e.g.:

```
Add viewport meta tag for mobile responsiveness
Fix broken image link on landing page
Update bio in about page
```
