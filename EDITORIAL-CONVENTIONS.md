# Crispa Insights — Editorial Conventions

The standing rules for every article in the Valuation Fundamentals series. Apply all of
these every time, so the series stays consistent.

## Internal cross-linking (important)
Whenever an article mentions a concept that another article in the series covers, **link to
that article**. Readers may land on any post first, so each concept should point to its home
article. Link both directions as the series fills in (e.g. the 10x post links to the pillar;
the pillar and lens posts link to each other where relevant).

Article slug map (link targets):
- Pillar: `/how-much-is-my-company-worth/`
- `/saas-10x-revenue-myth/` — why 10x is a trophy, not a target
- `/revenue-growth-and-valuation/` — Lens 1
- `/gross-margin-and-valuation/` — Lens 2
- `/ebitda-margin-and-valuation/` — Lens 3
- `/rule-of-40-for-saas/` — Lens 4
- `/enterprise-value-vs-equity-value/`
- `/revenue-multiple-or-ebitda-multiple/`
- `/valuation-range-negotiation/`
- `/how-to-improve-your-valuation/`

## Sources
- A **Sources** block at the foot of every post, just before the "Talk to Crispa" box.
- Always list: the **SEG 2026 Annual SaaS Report**, linked to
  `https://softwareequity.com/research/annual-saas-report`, plus **Crispa valuation analysis**.
- Keep the inline "Source: SEG 2026 Annual SaaS Report" line under every chart too.

## Links
- All in-article links render **Crispa green** (`#2E7A5A`), underlined, darkening to `#225A44`
  on hover. Never default browser blue.

## Voice & numbers
- **Positive frame** throughout — empowering, never "you got this wrong."
- Currency in **DKK**. Write **"DKK"**, not "krone" (e.g. "each DKK of revenue", not "each krone"),
  a Danish-colleague preference. Use **"math"**, not "maths". **No em-dashes**.
- **One canonical data source per series, cited consistently.** For *this* series
  (Valuation Fundamentals), that source is the **SEG 2026 Annual SaaS Report**, so numbers
  never contradict across articles (e.g. median ~5.3x revenue / ~29.3x EBITDA). This is
  specific to this series — future series/articles may draw on different sources; the rule
  is one coherent source set per series, not SEG specifically.

## Structure (house style)
- Direct-answer box near the top, definition boxes, on-brand charts/tables, an FAQ with
  JSON-LD schema, then the Sources block, then the dark **Talk to Crispa** CTA
  (button → `https://crispa.ai/contact`) after the FAQ.
- Each article in its own folder with a clean URL; add it to the homepage grid + sitemap on launch.

---

# Format & design (the article template)

The visual and structural spec every article follows. Reuse these exact tokens so all posts
look like one series.

## Fonts
- **Tiempos** (serif) — headings, display numbers, blockquotes, definition terms. Weights 500
  and 600. Fallback: `Georgia, serif`.
- **DM Sans** (sans) — body text, UI, labels, captions. Weights 400 and 500.
- Fonts are embedded in each page (self-contained), so pages render the same anywhere.

## Colour tokens
| Role | Hex |
|---|---|
| Ink (near-black text, dark boxes) | `#0E1118` |
| Stone (page background) | `#F6F3EF` |
| Green — primary (links, buttons, accents) | `#2E7A5A` |
| Green — dark (hover, emphasis text) | `#225A44` |
| Green — mid (eyebrows, small accents) | `#3C8D69` |
| Mint (answer / try boxes background) | `#DCEFE3` |
| Slate (muted text, captions, standfirst) | `#58749F` |
| Secondary body text | `#37445c` |
| Sand (borders, rules) | `#E0D5C8` |
| Row tint (alt table rows) | `#FBF9F6` |

## Layout & type scale
- Article column: `max-width: 760px`, padding `60px 40px 80px`, centered on the stone bg.
- H1 — Tiempos 600, 46px. Standfirst — Tiempos italic, 23px, slate.
- H2 — Tiempos 500, 30px. H3 — Tiempos 500, 23px. Body — DM Sans, 18px, line-height 1.6.

## Components (in typical order)
1. **Eyebrow** — uppercase, letter-spaced, green (`Valuation Fundamentals · [topic]`).
2. **H1 + standfirst + meta** (`By Crispa · X min read · Updated [month year]`).
3. **Direct-answer box** — mint bg, 4px green left border, "The short answer:" lead. (Good for GEO.)
4. **Definition boxes** — green left border, small label + serif term, plain-English explainer.
5. **Charts** — SVG on a stone card, brand colours, with a **"Source:" line** underneath.
6. **Tables** — white bg, sand border, rounded. Feature tables get a dark header row, serif
   row labels, green values, alternating row tint.
7. **Blockquotes** — Tiempos italic, green left border, for the memorable line.
8. **Try box** — mint bg + green border, links to the valuation calculator on the pillar.
9. **FAQ** — question/answer list under a top rule, mirrored by **FAQPage JSON-LD** in the head.
10. **Sources** block (see above).
11. **Talk to Crispa CTA** — dark (ink) box, white headline, green button → `crispa.ai/contact`.
12. **Back-link** to the series hub.

## SEO / GEO + tracking (in <head>)
- Unique `<title>`, meta description, `<link rel=canonical>`, Open Graph + Twitter tags, robots.
- FAQ **JSON-LD** schema so AI search and Google can read the Q&As.
- **GTM** container `GTM-MP9C7Z5Z` in the head + its `<noscript>` in the body (same as the rest
  of the site), so every page is tracked with no per-page setup.
