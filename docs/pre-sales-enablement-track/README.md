# H2O.ai Pre-Sales Enablement Skills Track

A self-contained learning site for the H2O.ai pre-sales enablement track:
118 curated videos across 6 modules, a certification quiz, and two reference
guides for use during live customer calls. H2O.ai University.

## What is here

| File | Page | Content | Design |
| --- | --- | --- | --- |
| `index.html` | The skills track — modules, video player, progress tracking, certification | Andreea Turcu, approved by Andrew Braverman | Andreea Turcu |
| `automation-landscape.html` | Reference guide 01 — automation & agentic AI vocabulary | Rafael Coss | Andreea Turcu |
| `rag-battle-card.html` | Reference guide 02 — RAG → Graph RAG → Agentic RAG → MAG battle card | Rafael Coss | Andreea Turcu |

Each page is a single self-contained file — fonts, styles, images and scripts
are inlined, so there is no build step, no server and no dependencies. Only the
YouTube embeds and thumbnails load from the network.

## Access

All three pages are AES-256 encrypted. The file served by GitHub Pages is
ciphertext; the passphrase decrypts it in the browser. Unlocking one page
unlocks the others for that session, and there is a 30-day "remember this
device" option.

The passphrase is shared internally by H2O.ai University — it is deliberately
not recorded in this repository.

## Published at

https://h2oai.github.io/h2o-university-resources/pre-sales-enablement-track/

Served from `docs/pre-sales-enablement-track/` on `main`
(Settings → Pages → Deploy from a branch → `main` / `/docs`). The empty
`docs/.nojekyll` file must stay — without it Pages runs Jekyll and skips files.

## Embedding in Google Sites

Insert → Embed → **By URL** with the address above is the cleanest option.
For an inline embed use:

```html
<iframe
  src="https://h2oai.github.io/h2o-university-resources/pre-sales-enablement-track/"
  title="H2O.ai Pre-Sales Enablement Skills Track"
  width="100%"
  height="2400"
  style="border:0;"
  loading="lazy"
  allow="fullscreen; clipboard-write"
  allowfullscreen>
</iframe>
