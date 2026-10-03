# Portfolio: AI, Cloud & Security

Single-file portfolio: one self-contained `index.html`, zero build step, zero dependencies
apart from Google Fonts.

## Live

| | |
|---|---|
| **Canonical** | https://portfolio-pramathramekar-gmailcoms-projects.vercel.app |
| Vercel project | `portfolio` (team: pramathramekar-gmailcoms-projects) |
| Source | https://github.com/Pramath-Ramekar/Pramath-Ramekar.github.io |
| Fallback | https://pramath-ramekar.github.io (GitHub Pages) |

## Deploy

```bash
vercel --prod --yes --name portfolio
```

`--name` is required: the CLI otherwise derives a name from the `D:\` folder path
and Vercel rejects it.

Pushes do **not** auto-deploy yet: the Vercel GitHub App is not authorized for this repo.
Connect it at vercel.com → portfolio → Settings → Git, or just run the command above
whenever you want to publish.

## Local preview

```bash
python -m http.server 8899
# open http://localhost:8899
```

## Structure

| Path | What |
|---|---|
| `index.html` | Everything: markup, CSS, JS |
| `vercel.json` | Security headers + cache rules (HSTS, X-Frame-Options, nosniff) |
| `assets/resume.pdf` | Downloadable CV |
| `404.html` | Redirect fallback |

## Features

- **⌘K / Ctrl+K command palette**: jump to any section, email, download CV, open profiles. `/` also opens it.
- Live IST clock in the masthead, computed from UTC so it's correct in every timezone.
- Type-in hero, scroll reveals, and stat counters: all disabled under `prefers-reduced-motion`.
- Expandable project cards, keyboard-navigable (`Enter`/`Space`, `aria-expanded`).
- Self-typing terminal footer.
- Responsive down to ~360px, skip-link + focus-visible states.

## Editing content

Everything user-facing is plain HTML in `index.html`. To change the palette commands,
edit the `CMDS` array in the `<script>` block near the bottom: targets must match element ids.

To re-brand: the palette lives in the `:root` block at the top of the `<style>`:
`--violet` (primary), `--violet-deep`, `--lav` (highlight), `--signal`/`--amber`/`--red` (severity).