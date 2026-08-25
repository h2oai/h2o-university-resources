# H2O.ai Solution Engineering Enablement Skills Track

A self-contained learning site for the H2O.ai solution engineering enablement
track: 118 curated videos across 6 modules, a certification quiz, and two
reference guides for use during live customer calls.

H2O.ai University.

*Live site:** [h2oai.github.io/h2o-university-resources/pre-sales-enablement-track](https://h2oai.github.io/h2o-university-resources/pre-sales-enablement-track/)

## What is here

| File | Page | Content | Design |
| --- | --- | --- | --- |
| `index.html` | The skills track — modules, video player, progress tracking, certification | Andreea Turcu, approved by Andrew Braverman | Andreea Turcu |
| `automation-landscape.html` | Reference guide 01 — automation & agentic AI vocabulary | Rafael Coss | Andreea Turcu |
| `rag-battle-card.html` | Reference guide 02 — RAG → Graph RAG → Agentic RAG → MAG battle card | Rafael Coss | Andreea Turcu |

## Access control

Every page is **encrypted at rest**. What sits in this repository is AES-256-GCM
ciphertext with a PBKDF2-derived key (SHA-256, 200,000 iterations); the page
decrypts in the reader's browser once they enter the access passphrase, then
renders itself inside a frame. Nothing readable is exposed to GitHub, to search
engines, or to anyone who lands on the URL without the passphrase.

The passphrase is **shared internally by H2O.ai University and is deliberately
not recorded in this repository.** Ask Andreea Turcu or Andrew Braverman.

Practical notes:

- Unlocking requires a modern browser over HTTPS (the Web Crypto API is
  unavailable on plain `http://` and on `file://`).
- "Remember on this device for 30 days" stores the passphrase in the browser so
  the reader is let straight through on later visits, on that device only.
- All three pages use the same passphrase, so unlocking one unlocks the others
  on that device.

## The track

Six modules, roughly 7 hours of video, in recommended order. Every video is a
real H2O.ai University recording; nothing is a placeholder.

| Module | Focus | Time |
| --- | --- | --- |
| 01 | The H2O.ai Platform — what we sell and why it matters | ~40 min |
| 02 | H2O.ai Managed Cloud — where customers actually run the platform | ~22 min |
| 03 | Predictive AI — Driverless AI, TabH2O & ML infrastructure | ~95 min |
| 04 | Generative AI — h2oGPTe & LLM Studio | ~150 min |
| 05 | AI Agents — the next frontier | ~60 min |
| 06 | Specialized AI tools — Label Genie, Hydrogen Torch, H2O Wave | ~55 min |

The page also offers an **extended view**: the same videos regrouped as the
complete H2O.ai University courses they were drawn from, in recommended
chronological order, for anyone who wants the full course rather than the
curated path. Progress is shared between both views.

## The certification quiz

Hosted on ClassMarker, opened in a new tab from the page. 30 questions mapped
onto the six modules:

| Questions | Module | Covers |
| --- | --- | --- |
| 3 | 01 | AI lifecycle, the three paradigms of AI, data traceability |
| 3 | 02 | Managed Cloud scope, predictive + generative together, admin surface |
| 6 | 03 | TabH2O and tabular foundation models, Driverless AI, model drift |
| 9 | 04 | RAG, h2oGPTe collections, guardrails, hybrid retrieval, LoRA, LLM Studio |
| 5 | 05 | Chains vs. agents, routing, MCP, the Telco churn demo, MLOps fit |
| 4 | 06 | Label Genie, zero-shot labeling, Hydrogen Torch, H2O Wave |

- Pass mark **21/30 (70%)**, 30-minute limit, unlimited attempts.
- Question order and answer options are randomized on every attempt.
- The quiz is itself password-protected. That password is shown on the page and
  shared internally only — it is not recorded here.
- Certification is separate from the existing Partner certification.

## The two reference guides

Written for use mid-call rather than for study. Both are marked internal and
name competitors, so they are not for external distribution.

- **Guide 01 — automation vocabulary.** Twelve terms defined (RPA, AutoML,
  agency, agentic AI, framework vs. runtime vs. harness), seven eras of how the
  field arrived here, and where each H2O.ai product sits on the automation
  spectrum.
- **Guide 02 — RAG battle card.** Four generations of retrieval (RAG → Graph RAG
  → Agentic RAG → MAG), who leads each one, positioning against named
  competitors, a comparison matrix, discovery questions, and 17 objections with
  talk tracks and proof points — both the competitive objections and the
  commercial ones that actually stall deals. Has a **Print all sections** button
  that reveals every tab and objection for printing or PDF export.

Figures and benchmark claims on both guides are stamped **as of August 2026** —
re-check before quoting them to a customer.

## Publishing on GitHub Pages

This site is published from `docs/pre-sales-enablement-track/` in the
`h2oai/h2o-university-resources` repository.

1. Copy the three HTML files and this README into that folder, overwriting.
2. An empty `docs/.nojekyll` file must exist at the `docs` root — **do not
   delete it**, or GitHub Pages will not serve the folder correctly.
3. Repository **Settings → Pages** → **Deploy from a branch** → `main` and
   `/docs`.
4. The site appears at the live URL above within a minute or two.

`index.html` is the landing page. Because each page is separately gated, the
links between pages are **absolute URLs** pointing at the published site — if
the site ever moves to a different path or repository, the sources must be
recompiled so those links follow.

## Embedding in Google Sites

Sites' **Embed code** box will not accept a file this size, so host it first
(GitHub Pages above), then embed the published URL:

```html
<iframe
  src="https://h2oai.github.io/h2o-university-resources/pre-sales-enablement-track/"
  title="H2O.ai Solution Engineering Enablement Skills Track"
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

**Test progress tracking on the live Sites page before announcing the track.**
Progress is stored in the learner's browser, and browsers partition or block
storage for cross-domain iframes — it may reset for learners even though it
works when the page is opened directly. If that happens, link out to the
published URL as a full page instead of embedding it.

## Notes for whoever maintains this

- **Progress** is kept in `localStorage` under `h2o-presales-track-v1`. It is
  per-browser and per-device; there is no backend and no login. Completion state
  and the module a learner is on both survive a reload.
- **Video descriptions** in the player need a YouTube Data API key, which each
  learner pastes once (stored locally). Without one, the page shows a short
  explainer instead. Nothing else depends on it.
- **Module 07** (solution engineering methodology and execution) is intentionally
  shown as an "upcoming content" placeholder with a dashed border — those
  lessons are not recorded yet.
- **What loads from the network:** the YouTube video embeds and thumbnails, and
  the H2O.ai University logo in the sticky header (h2o.ai CDN). Everything else
  — fonts, styles, scripts, the certification badge — is inlined in the file.
- **Responsive** down to 360px, with 44px minimum tap targets, sticky module
  headers, and a video modal sized so the Mark Complete and Next controls are
  always reachable without scrolling.
- **Accessibility:** the term and objection accordions on the guides are real
  buttons with `aria-expanded`, so they are keyboard-reachable.

## Editing

These three HTML files are **compiled output — do not edit them directly.** The
sources live in the design project as `PreSalesTrack.dc.html`,
`AutomationLandscape.dc.html` and `RAGBattleCard.dc.html`, alongside the H2O.ai
University design system in `_ds/`. Editing means: change the source, recompile
to a self-contained page, re-encrypt with the passphrase, and re-upload.

## Credits

- **Track content and structure** — Andreea Turcu, approved by Andrew Braverman.
- **Reference guides 01 and 02** — Rafael Coss.
- **Design, build and site engineering** — Andreea Turcu.
- **Videos** — H2O.ai University.
