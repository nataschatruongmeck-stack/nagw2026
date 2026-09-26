# nagw2026

Companion site for *The Skeptic's Guide to AI-Assisted Web Design*, presented by Natascha Truong at NAGW 2026. Published with GitHub Pages.

**Live:** https://nataschatruongmeck-stack.github.io/nagw2026/

| Page | What it does |
| --- | --- |
| [`index.html`](index.html) | Home page, with links to each page and a list of resources |
| [`design-tokens.html`](design-tokens.html) | What a design token is, what a token file looks like, and how to use it |
| [`contrast-matrix.html`](contrast-matrix.html) | WCAG 2.1 contrast matrix — every ordered pair in a palette, judged against AA and AAA |
| [`token-foundry.html`](token-foundry.html) | Design token builder with the contrast check built into the editor, exports JSON |
| [`figma-first-workflow-guide.html`](figma-first-workflow-guide.html) | Steps to go from Figma to final code, with four workflow options and human checks at each step |

## How it's built

Every page is a single HTML file with its CSS and JS inlined — no build step. The only
external assets are two self-hosted fonts in `fonts/`. The one third-party request is
opt-in: choosing a Google Font to preview in Token Foundry loads it from
fonts.googleapis.com.

**Color** — all six pages use the palette defined in the workflow guide: navy `#0E1826`,
paper `#E8ECF1`, stamp blue `#134E8B`, plus semantic pass/hold/fail. The two tools
keep their own CSS; the shared block just re-points their `:root` tokens at these values,
so nothing in the original stylesheets had to be rewritten.

**Type** — Caprasimo for the nameplate, Fraunces for headlines, system stacks for body and
data. Fraunces is variable; the axes are set once in `--nt-vf` (`SOFT 100, WONK 1, opsz 20`)
— the low `opsz` is deliberate, it keeps the letterforms sturdy instead of thin at display
sizes. Both faces are SIL OFL, licenses in `fonts/`.

**The shared block** (`.nt-*` classes, hard-set values so the bar renders identically
regardless of each page's own tokens) is inlined at the top of every page. When you change
it, change it in all six files.

Every color pair was checked against WCAG 2.1 AA before use — which seemed like the
minimum for a site that ships a contrast checker.

## Publishing

Pages deploys from the `main` branch, root directory. Pushing to `main` publishes.

## Disclaimer

This is a personal project. The views here are my own and do not represent my
employer. Claude and Figma are named because they are the tools I
demonstrate, not as an endorsement or a recommendation to adopt them. Use AI tools at your
own risk and follow your organization's policies. AI-generated code must be reviewed,
validated, and security-tested before it goes to production.

## License

© 2026 Natascha Truong. All rights reserved. The code and content in this repository may not
be copied, modified, or reused without permission. See [`LICENSE`](LICENSE).

The two fonts in `fonts/` are separate works under the SIL Open Font License; their licenses
are included alongside them.
