# Crispa Insights

The Crispa Insights site: data-backed valuation guides for founders. Plain HTML,
hosted on Netlify at **insights.crispa.ai**, deployed automatically from GitHub.

## Structure

```
/                                   → the hub homepage (index.html, lists all articles)
/how-much-is-my-company-worth/      → the pillar article (its own folder = clean URL)
sitemap.xml                         → list of all pages (update when you add an article)
robots.txt                          → tells search engines where the sitemap is
netlify.toml                        → Netlify config (no build step)
```

Each article lives in its own folder as `index.html`, which gives a clean URL like
`insights.crispa.ai/rule-of-40/`. Every page already includes the Crispa GTM Web
container (`GTM-MP9C7Z5Z`), so GA4, Snitcher, the LinkedIn pixel and HubSpot all
track automatically.

## First-time setup (do once)

### 1. Put this folder on GitHub
1. Create a free account at github.com if you don't have one.
2. Create a new **private** repository called `crispa-insights`.
3. Upload the contents of this folder (drag the files into GitHub's "upload files"
   page, or use GitHub Desktop). Commit.

### 2. Connect GitHub to Netlify
1. In Netlify: **Add new site → Import an existing project → GitHub**.
2. Pick the `crispa-insights` repo.
3. Build command: leave blank. Publish directory: `.` (a dot). Click **Deploy**.
4. From now on, every change you push to GitHub deploys automatically.

### 3. Point the subdomain insights.crispa.ai at Netlify
1. In Netlify: **Domain management → Add a domain →** `insights.crispa.ai`.
2. Netlify shows a **CNAME** record. In your domain provider (where crispa.ai is
   managed), add that CNAME for the `insights` host.
3. Wait for it to verify (minutes to an hour). Netlify adds HTTPS automatically.

## Adding a new article (every time after setup)

1. Make a new folder named with the article's URL slug, e.g. `rule-of-40/`.
2. Put the article's `index.html` inside it. (Easiest: copy an existing article
   folder and replace the content, so the GTM tag and styling carry over.)
3. Add a card for it in the hub: open the root `index.html`, copy an existing
   `<a class="card">…</a>` block, paste it inside the `<div class="grid">`, and
   edit its link, title and text. (Or just ask Crispa's assistant to add it.)
4. Add its URL to `sitemap.xml`.
5. Commit and push to GitHub. It's live in under a minute.

That's the whole loop: **write → drop in a folder → push.** No Framer rebuild.
