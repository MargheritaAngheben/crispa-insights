# Crispa Insights

The Crispa Insights site: data-backed valuation guides for founders. Plain HTML,
hosted on Netlify at **insights.crispa.ai**, deployed automatically from GitHub.

> The **writing and formatting rules** for the articles themselves (voice, DKK not
> krone, the Sources block, the colon rule, the Pleo figures, etc.) live in
> **`EDITORIAL-CONVENTIONS.md`** in the repo root. This README is about how the repo
> and publishing work.

## How publishing works: two branches

The difference between the two branches is the whole game:

- **`main` = LIVE.** Anything on `main` is published to insights.crispa.ai within a
  minute (Netlify auto-deploys it). Only finished, approved articles belong here.
- **`draft_articles` = work in progress.** New articles and anything under review live
  here. Netlify does **not** publish this branch, so nothing on it is public. This is
  where articles go first and where colleagues review them.

**Golden rule:** new and in-progress articles go to **`draft_articles`**. An article
only moves to **`main`** when it's ready to go live.

## Status: what's live vs. in draft

| Article | Slug | Branch | Status |
|---|---|---|---|
| Pillar — How much is my company worth? | `how-much-is-my-company-worth` | `main` | ✅ Live |
| Why your SaaS isn't worth 10x | `saas-10x-revenue-myth` | `draft_articles` | Draft |
| Lens 1 — Revenue growth | `revenue-growth-and-valuation` | `draft_articles` | Draft |
| Lens 2 — Gross margin | `gross-margin-and-valuation` | `draft_articles` | Draft |
| Lens 3 — EBITDA margin | `ebitda-margin-and-valuation` | `draft_articles` | Draft |
| Lens 4 — Rule of 40 | `rule-of-40-for-saas` | — | Planned |
| Enterprise value vs equity value | `enterprise-value-vs-equity-value` | — | Planned |
| Revenue multiple or EBITDA multiple | `revenue-multiple-or-ebitda-multiple` | — | Planned |
| Valuation range / negotiation | `valuation-range-negotiation` | — | Planned |
| How to improve your valuation | `how-to-improve-your-valuation` | — | Planned |

> Update this table whenever an article moves from draft to live, or a new one is started.

## Structure

```
/                                    → hub homepage (index.html, lists published articles)
/how-much-is-my-company-worth/       → an article (its own folder = clean URL)
sitemap.xml                          → list of published pages (update when publishing)
robots.txt                           → points search engines to the sitemap
netlify.toml                         → Netlify config (no build step)
EDITORIAL-CONVENTIONS.md (repo root) → the writing/format rules for articles
```

Each article lives in its own folder as `index.html`, which gives a clean URL like
`insights.crispa.ai/rule-of-40-for-saas/`. Every page already includes the Crispa GTM
Web container (`GTM-MP9C7Z5Z`), so GA4, Snitcher, the LinkedIn pixel and HubSpot track
automatically. **Don't commit `.DS_Store`** (a hidden Mac system file, it's just clutter).

## Adding a new article (always to the draft branch first)

In **GitHub Desktop**:

1. Switch **Current Branch** to **`draft_articles`** (top of the window), then click
   **Fetch origin → Pull** so you have everyone's latest work.
2. In Finder, inside `crispa-insights-site`, make a folder named with the article's URL
   slug (e.g. `rule-of-40-for-saas`). Put the article inside it, named exactly
   **`index.html`**. (Easiest: copy an existing article folder and swap the content, so
   the GTM tag and styling carry over.)
3. Back in GitHub Desktop, tick the new folder under **Changes** (leave `.DS_Store`
   unticked), write a short summary, click **Commit to draft_articles**, then **Push origin**.
4. It's now on GitHub for review but **not public**. Reviewers open the repo on
   github.com, switch the branch dropdown to **`draft_articles`**, and read it there.

On github.com you can also do it with **Add file → Upload files**, just switch the branch
to `draft_articles` first.

## Publishing an article (move it to main → it goes live)

When an article is approved and it's its launch day:

1. The simplest, safest path: switch **Current Branch** to **`main`** in GitHub Desktop,
   then **ask Crispa's assistant to publish that one article.** It will copy the article
   folder onto `main`, add its card to the hub homepage, and add its URL to `sitemap.xml`,
   the fiddly bits. You then **Commit** and **Push origin** on `main`, and Netlify deploys
   it within a minute.
2. Manual alternative, if *every* draft is ready at once: on `main`, use the menu
   **Branch → Merge into current branch → `draft_articles`**, then add the homepage cards
   and sitemap entries, Commit and Push. (Don't use this if only one of several drafts is
   ready, it would publish them all.)
3. After publishing, update the **Status** table above (move the row to `main` / ✅ Live).

## First-time setup (already done, kept for reference)

The site is already on GitHub, connected to Netlify, and live at insights.crispa.ai. These
were the one-time steps:

1. **GitHub:** a private repo `crispa-insights` holding this folder.
2. **Netlify:** Add new site → Import from GitHub → pick the repo. No build command;
   publish directory `.` (base directory `crispa-insights-site`). Auto-deploys the `main`
   branch on every push.
3. **Subdomain:** in Netlify, Domain management → add `insights.crispa.ai`; add the CNAME
   Netlify shows at the domain provider for the `insights` host. HTTPS is automatic.
