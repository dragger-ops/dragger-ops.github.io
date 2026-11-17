# Portfolio — Moses Ndereba Gichuru

Personal portfolio site. One static page, no build step, no dependencies to install.

**Live:** https://dragger-ops.github.io/

Also answers at https://dragger-ops.github.io/portfolio, which redirects to the root. The page itself exists in exactly one place, so there is nothing to keep in sync.

## Contents

```
index.html              the whole site — markup, styles and the copy-to-clipboard script
portfolio/index.html    redirect to the root, so the /portfolio link also works
.nojekyll               serve the files as-is; skip Jekyll processing
```

Fonts are the only external request (Google Fonts: Bricolage Grotesque, Inter, IBM Plex Mono). Everything else is inline, including the favicon.

## Run it locally

Open `index.html` in a browser. That is all it needs.

To serve it over HTTP instead (useful for checking the canonical URL and share previews):

```bash
python -m http.server 8000
# http://localhost:8000
```

## Deploying

GitHub Pages serves `index.html` from the default branch root. Push to the default branch and Pages republishes.

To enable Pages the first time: **Settings → Pages → Source: Deploy from a branch → `main` / `/ (root)`**.

## Design notes

- Light and dark themes, driven by `prefers-color-scheme` with a `[data-theme]` override. Every colour is a token on `:root`; no colour is defined only inside a media query.
- Layout is a sticky index rail beside one content column, collapsing to a single column below 920px. Work entries are full-width manifest rows rather than cards.
- Works down to roughly 360px wide with no horizontal scroll. Respects `prefers-reduced-motion`.

## Editing content

Each project is one `<article class="item">` block in the `#work` section:

- `.meta` — the domain and its status dot (`.dot` for live, `.dot.off` for anything else)
- `.kicker` — the category label above the title
- `.detail` — the bullet list; keep these concrete and specific
- `.tags` — the stack row

The four hero figures live in `.facts`. Keep them true; they are the first thing anyone checks.
