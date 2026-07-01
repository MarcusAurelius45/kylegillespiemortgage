# SETUP.md — Getting kylegillespiemortgage.com live (plain English)

Total hands-on time: ~30–45 minutes, once. Steps 1–4 can be done by you, by Claude Code
(tell it: "follow SETUP.md in this folder"), or by any VA/freelancer.

## What this folder is

A complete, ready-to-publish website. No build step, no database, no code to write.
- `index.html` — the canonical "who is Kyle Gillespie" page
- `guides/` — the article library (grows over time)
- `llms.txt`, `AGENTS.md`, `robots.txt`, `sitemap.xml` — the AI-readability layer
- `CLAUDE.md` — instructions the automation follows
- `.github/workflows/draft-article.yml` — the automated article-drafting engine

## Step 1 — Put the files on GitHub (~10 min)

1. Create a free account at github.com (if you don't have one).
2. Create a new repository named `kylegillespiemortgage` (private is fine).
3. Upload everything in this folder to the repository.
   - Easiest: on the repo page, "Add file" → "Upload files" → drag the folder contents in.
   - Or tell Claude Code: "create a GitHub repo from this folder and push it."

## Step 2 — Host it free on Cloudflare Pages (~10 min)

1. Create a free account at cloudflare.com.
2. Go to "Workers & Pages" → "Create" → "Pages" → "Connect to Git".
3. Pick the `kylegillespiemortgage` repo.
4. Build settings: framework preset "None", build command EMPTY, output directory "/".
5. Click Deploy. In ~1 minute you'll have a live preview URL like
   kylegillespiemortgage.pages.dev — check that the site loads.

(Netlify works identically if you prefer it.)

## Step 3 — Point your GoDaddy domain at it (~10 min)

1. In Cloudflare Pages: your project → "Custom domains" → "Set up a custom domain" →
   enter kylegillespiemortgage.com. Cloudflare shows you the DNS records it needs.
2. In GoDaddy: My Products → kylegillespiemortgage.com → DNS → add/edit the records
   exactly as Cloudflare showed (usually one CNAME).
3. Wait for it to verify (minutes to a few hours). Also add the "www" version when prompted.

Done — https://kylegillespiemortgage.com is live.

## Step 4 — Tell the search engines it exists (~10 min, big payoff)

ChatGPT's browsing leans on Bing's index, so Bing matters more than people think.

1. **Bing Webmaster Tools** (bing.com/webmasters): add the site, verify via DNS
   (GoDaddy record), submit https://kylegillespiemortgage.com/sitemap.xml.
2. **Google Search Console** (search.google.com/search-console): same — add property,
   verify via DNS, submit the sitemap.
3. Optional: enable IndexNow in Bing Webmaster Tools so new pages get picked up fast.

## Step 5 — Turn on the article engine (~5 min)

1. Get an API key from console.anthropic.com (this pays for the automated drafting;
   a couple of articles a month costs on the order of a few dollars).
2. In GitHub: repo → Settings → Secrets and variables → Actions → "New repository secret"
   → Name: ANTHROPIC_API_KEY → paste the key.
3. That's it. On the 1st and 15th of each month (or whenever you press "Run workflow"
   in the Actions tab), Claude drafts the next backlog article as a PULL REQUEST —
   a pending draft, never auto-published.

## The ongoing routine (your only recurring job)

1. A pull request appears titled "DRAFT for compliance review: …".
2. Send the draft to OriginPoint compliance (copy the article text or share the PR link).
3. When approved, click "Merge" on the PR. The site updates itself within a minute.
4. If compliance wants edits, comment "@claude <the requested change>" on the PR and it
   will revise, or edit the file directly.

## Before going live — one manual check

Open index.html and the guide and verify the bracketed facts are right: the $1B+ figure,
titles, phone, address, award claims. Fix anything off (or tell Claude Code to). Then
route the whole site through OriginPoint compliance once for launch sign-off.
