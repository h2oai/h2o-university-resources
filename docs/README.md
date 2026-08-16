# H2O.ai Pre-Sales Enablement Skills Track

A self-contained learning site for the H2O.ai pre-sales enablement track:
118 curated videos across 6 modules, a certification quiz, and two reference
guides for use during live customer calls.

Content by **Rafael Coss**. Design by **Andreea Turcu**. H2O.ai University.

## What is here

| File | Page |
| --- | --- |
| `index.html` | The skills track — modules, video player, progress tracking, certification |
| `automation-landscape.html` | Reference guide 01 — automation & agentic AI vocabulary |
| `rag-battle-card.html` | Reference guide 02 — RAG → Graph RAG → Agentic RAG → MAG battle card |

Each file is self-contained: fonts, styles and scripts are inlined, so a page
needs no build step, no server and no dependencies. Two things still load from
the network — the YouTube video embeds and thumbnails, and the H2O.ai
University logo in the sticky header (served from the h2o.ai CDN). Everything
else renders offline.

## Publishing on GitHub Pages

1. Create a repository and push the contents of this folder to it.
2. Repository **Settings → Pages**.
3. Under **Source**, choose **Deploy from a branch**, pick `main` and `/ (root)`.
4. Save. The site appears at `https://<user>.github.io/<repo>/` within a minute or two.

`index.html` at the root becomes the landing page automatically, and the two
guides are linked from it — no configuration needed.

### Serving from a subfolder instead

If you'd rather keep the site under `/docs`, move these three files there and
pick `/docs` as the Pages folder in step 3. The links between pages are
relative, so they keep working.

## Embedding in Google Sites

Sites' **Embed code** box will not accept a file this size, so host it first
(GitHub Pages above), then embed the published URL:

```html
<iframe
  src="https://<user>.github.io/<repo>/"
  title="H2O.ai Pre-Sales Enablement Skills Track"
  width="100%"
  height="2400"
  style="border:0;"
  loading="lazy"
  allow="fullscreen; clipboard-write"
  allowfullscreen>
</iframe>
```

Google Sites embeds cannot auto-resize to their content, so the height is fixed.
`2400` is a sensible start with all modules collapsed.

**Test progress tracking on the live Sites page before you announce the track.**
Progress is stored in the learner's browser, and browsers partition or block
storage for cross-domain iframes — it may reset for learners even though it
works when the page is opened directly. If that happens, link out to the
published URL as a full page instead of embedding it.

## Notes for whoever maintains this

- **Progress** is kept in `localStorage` under `h2o-presales-track-v1`. It is
  per-browser and per-device; there is no backend and no login.
- **The quiz** is hosted on ClassMarker and opens in a popup window. It is
  currently marked as a draft on the page — 30 questions, 70% to pass, 30-minute
  limit, unlimited attempts.
- **Video descriptions** in the player need a YouTube Data API key, which each
  learner pastes once (stored locally). Without one, the page shows a short
  explainer instead. Nothing else depends on it.
- **Module 07** (presales methodology and execution) is intentionally shown as
  an "upcoming content" placeholder — those lessons are not recorded yet.

## Editing

These three files are compiled output — don't edit them directly. The sources
live one level up as `PreSalesTrack.dc.html`, `AutomationLandscape.dc.html` and
`RAGBattleCard.dc.html`, alongside the H2O.ai University design system in
`_ds/`. Edit those and recompile.
