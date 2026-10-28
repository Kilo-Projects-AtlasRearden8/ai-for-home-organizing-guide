# STATUS

## What was built

A beginner manual and static HTML site on using AI to organize the home, published by Asdale Dynamics, LLC.

**Project files**

- `LICENSE` — MIT License, copyright line exactly `Copyright (c) 2026 Asdale Dynamics, LLC`
- `README.md` — project overview, credits Asdale Dynamics, LLC, links to the manuals
- `.markdownlint.yaml` — lint config (MD013 line-length disabled; prose/URLs left unwrapped)
- `docs/` — beginner manuals in Markdown
  - `privacy.md` — privacy-first rule: never scan or upload sensitive IDs
  - `intro.md` — getting started with AI, prompting, starter routine
  - `digital-filing.md` — folders, file naming, email/paper mail
  - `photo-routines.md` — weekly photo cleanup, AI photo captions, home inventory photos, backups
  - `household-inventories.md` — what to inventory, room-by-room with AI, spreadsheet template, storage, insurance
  - `family-schedules.md` — one calendar, routines, Sunday reset, low-energy days, chore rotation
  - `printable-labels.md` — what to label, AI-written label text, print options
- `site/` — same manuals as a static HTML website
  - `index.html` — home page with privacy callout and full navigation
  - one HTML page per doc (`privacy`, `intro`, `digital-filing`, `photo-routines`, `household-inventories`, `family-schedules`, `printable-labels`)
  - `style.css` — shared warm, print-friendly styles
  - `printable-labels.html` — printable label sheet (12 sticker labels per page, ~2" x 1") plus write-on bin templates, with `@media print` styles

**Credit & privacy**

- Asdale Dynamics, LLC credited in `README.md`, every HTML footer, and every doc's closing line.
- Hub site referenced: dylanasdale.github.io (behind *The Massive AI Manual*).
- Privacy-first throughout: golden rule (no sensitive IDs with AI) appears on the privacy page, home page, and as a callout on filing/photos/inventories/schedules/labels pages.
- No secrets, API keys, or personal data in any file. No `.github/workflows` files. No remote repos created. Nothing pushed.

## How to run it

- **Read the manuals:** open any file in `docs/` in a Markdown viewer or text editor. Start with `docs/privacy.md`.
- **View the website:** open `site/index.html` in any browser. No build step, no server required — it is plain static HTML + CSS.
- **Print labels:** open `site/printable-labels.html`, press `Ctrl+P` (or `Cmd+P`), and print on sticker paper or regular paper. In the print dialog, turn off headers/footers and set margins to None/Minimum so labels print at full size.
- **Host anywhere:** the `site/` folder is deployable to any static host (GitHub Pages, etc.) as-is. Not done here per instructions (no remote, no publish).

## Verification results

- `npx htmlhint "site/*.html"` — 8 files scanned, no errors.
- `npx markdownlint "docs/*.md"` — no errors (config in `.markdownlint.yaml`).
- All internal links between site pages verified present by inspection; every nav target file exists.
- Print styles confirmed via `@media print` (header/nav/footer hidden on print).
- No test runner or build script exists in this project (static site + Markdown manuals); verification is lint + manual inspection.
- No secrets/API keys/personal data present (grep-confirmed absent).

## Known gaps

- No automated test suite or CI (intentionally none — no `.github/workflows`). Verification is manual/lint only.
- HTML not run through a formal validator (W3C) — htmlhint used instead; pages are simple, well-formed HTML5.
- The external hub link (dylanasdale.github.io) and MIT license link (opensource.org) were not fetched/live-checked.
- Printable label physical sizing (~2" x 1") depends on printer and paper; print a test page first.
- Local AI app recommendations (LM Studio, Ollama) are mentioned but not bundled or tested in this repo.
- Medical disclaimer included; no medical advice given or intended.
- Single commit only; no release tagging.
