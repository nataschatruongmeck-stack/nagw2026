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

Every page is a single self-contained HTML file — no build step, no webfonts, no CDN,
no network requests of any kind. Open any file directly in a browser and it works.

A shared navigation bar (`.nt-*` classes, hard-set values so it renders identically
regardless of each page's own token set) is inlined at the top of every page. When you
change it, change it in all four files.

## Publishing

Pages deploys from the `main` branch, root directory. Pushing to `main` publishes.
