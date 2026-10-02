# pramathramekar.github.io

Single-file portfolio — one self-contained `index.html`, zero build step, zero dependencies
apart from Google Fonts.

## Deploy to GitHub Pages

```bash
cd D:\Portfolio-web
git init
git add .
git commit -m "Portfolio: editorial-terminal single-file build"
git branch -M main
git remote add origin https://github.com/Pramath-Ramekar/Pramath-Ramekar.github.io.git
git push -u origin main
```

Then in the repo: **Settings → Pages → Source: Deploy from a branch → `main` / `root`**.

Live at `https://pramath-ramekar.github.io` shortly after.

## Local preview

```bash
python -m http.server 8899
# open http://localhost:8899
```

## Structure

| Path | What |
|---|---|
| `index.html` | Everything — markup, CSS, JS |
| `assets/resume.pdf` | Downloadable CV |

## Features

- **⌘K / Ctrl+K command palette** — jump to any section, email, download CV, open profiles. `/` also opens it.
- Live IST clock in the masthead, computed from UTC so it's correct in every timezone.
- Type-in hero, scroll reveals, and stat counters — all disabled under `prefers-reduced-motion`.
- Expandable project cards, keyboard-navigable (`Enter`/`Space`, `aria-expanded`).
- Self-typing terminal footer.
- Responsive down to ~360px, skip-link + focus-visible states.

## Editing content

Everything user-facing is plain HTML in `index.html`. To change the palette commands,
edit the `CMDS` array in the `<script>` block near the bottom — targets must match element ids.

To re-brand: the palette lives in the `:root` block at the top of the `<style>`:
`--violet` (primary), `--violet-deep`, `--lav` (highlight), `--signal`/`--amber`/`--red` (severity).