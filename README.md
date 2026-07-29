# nagw2026

NAGW Presentation Docs — three single-file tools for design systems, published with GitHub Pages.

**Live:** https://nataschatruongmeck-stack.github.io/nagw2026/

| Page | What it does |
| --- | --- |
| [`index.html`](index.html) | Landing page and index of the three tools |
| [`contrast-matrix.html`](contrast-matrix.html) | WCAG 2.1 contrast matrix — every ordered pair in a palette, judged against AA and AAA |
| [`token-foundry.html`](token-foundry.html) | Design token builder with the contrast check built into the editor, exports JSON |
| [`figma-first-workflow-guide.html`](figma-first-workflow-guide.html) | Guide to the Figma → Claude Design → Claude Code route, and the checkpoints along it |

## How it's built

Every page is a single HTML file with its CSS and JS inlined — no build step and no
third-party requests. The only external assets are two self-hosted fonts in `fonts/`.

**Colour** — all four pages use the palette defined in the workflow guide: navy `#0E1826`,
paper `#E8ECF1`, stamp blue `#134E8B`, plus semantic pass/hold/fail. The other two pages
keep their own CSS; the shared block just re-points their `:root` tokens at these values,
so nothing in the original stylesheets had to be rewritten.

**Type** — Caprasimo for the nameplate, Fraunces for headlines, system stacks for body and
data. Fraunces is variable; the axes are set once in `--nt-vf` (`SOFT 100, WONK 1, opsz 20`)
— the low `opsz` is deliberate, it keeps the letterforms sturdy instead of thin at display
sizes. Both faces are SIL OFL, licences in `fonts/`.

**The shared block** (`.nt-*` classes, hard-set values so the bar renders identically
regardless of each page's own tokens) is inlined at the top of every page. When you change
it, change it in all four files.

Every colour pair was checked against WCAG 2.1 AA before use — which seemed like the
minimum for a site that ships a contrast checker.

## Publishing

Pages deploys from the `main` branch, root directory. Pushing to `main` publishes.
