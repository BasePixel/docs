# BasePixel Documentation

Public documentation for BasePixel, deployed via [Mintlify](https://mintlify.com).

Live at: [docs.basepixel.io](https://docs.basepixel.io)

## Stack

- **Mintlify** for hosting and rendering
- **MDX** for content (markdown + React components)
- All content is in this repository

## Local development

Install Mintlify CLI:

```bash
npm i -g mint
```

Run locally from this directory:

```bash
mint dev
```

Opens at `http://localhost:3000` with hot reload.

## Project structure

```
basepixel-docs/
├── docs.json                 # Mintlify config (navigation, theme, branding)
├── favicon.ico
├── logo/
│   ├── basepixel-lockup-light.svg   # White text for dark mode
│   └── basepixel-lockup-dark.svg    # Black text for light mode
├── images/
│   └── banner-hero.png
├── introduction/
│   ├── what-is-basepixel.mdx
│   ├── how-it-works.mdx
│   └── why-ai.mdx
├── play/
│   ├── mint.mdx
│   ├── action-mode.mdx
│   ├── battle.mdx
│   └── redeem.mdx
├── ai/
│   ├── overview.mdx
│   ├── how-ai-fights.mdx
│   └── v1-roadmap.mdx
└── resources/
    ├── faq.mdx
    ├── contracts.mdx
    └── links.mdx
```

## Deploying

### First-time setup

1. Push this directory to a GitHub repo (e.g. `basepixel/docs`)
2. Sign up at [mintlify.com](https://mintlify.com)
3. Connect your GitHub account
4. Import the repo
5. Mintlify auto-detects `docs.json` and deploys

### Custom domain

Set up `docs.basepixel.io`:

1. In Mintlify dashboard → Domain settings
2. Add `docs.basepixel.io`
3. Add DNS CNAME: `docs` → `cname.mintlify.app`
4. Wait for SSL provisioning (~5 min)

### Updates

Push to `main` branch → Mintlify auto-deploys in ~30 seconds.

## Editing content

All content is in `.mdx` files. MDX = Markdown + React components.

### Available components

- `<Card>`, `<CardGroup>` — feature highlights
- `<Steps>`, `<Step>` — numbered workflows
- `<Note>`, `<Tip>`, `<Warning>` — callouts
- `<Accordion>`, `<AccordionGroup>` — collapsible sections
- `<Tab>`, `<Tabs>` — tabbed content
- `<CodeGroup>` — multi-language code blocks

Full reference: [mintlify.com/docs/components](https://mintlify.com/docs/components)

### Style guide

- **Lead with the answer.** Don't bury key info under intros.
- **Short paragraphs.** Aim for 3-5 sentences max.
- **Tables for comparisons.** Lists for steps. Cards for choices.
- **One H2 per section.** Don't nest H3s deeply.
- **Action verbs.** "Mint a pixel" not "Pixel minting."
- **Skim-friendly.** Most readers won't read every word.

## Content updates needed before launch

- [ ] Replace placeholder Diamond + facet addresses in `resources/contracts.mdx`
- [ ] Replace placeholder Twitter / Discord / GitHub URLs in `docs.json` and `resources/links.mdx`
- [ ] Add real audit reports to contracts page (or remove the section if no audit shipped)
- [ ] Add screenshots of the actual UI to play guides
- [ ] Sync `PIXEL_ABI` snippet in `resources/contracts.mdx` against the published artifact

## Changelog

Track major doc updates here:

- **2026-05-04** — Sync to current contract surface: dropped Genesis tier (not implemented), updated 16-color palette → uint24 RGB, corrected facet list (6 facets, not 10), `mint(tokenId, faction, color)` signature, real event names (`PixelAttacked` etc.).
- **2026-05-03** — Initial MVP documentation.
