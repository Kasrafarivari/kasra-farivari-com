# kasra-farivari.com

A personal site, separate in focus from kasrafarivari.org, built to be hosted on GitHub Pages.

## 1. Push to GitHub

1. Create a new repository (public), e.g. `kasra-farivari-com`.
2. Add these files to the repo root: `index.html`, `CNAME`, `robots.txt`, `sitemap.xml`.
3. Commit and push to the `main` branch.

Note: all CSS is inlined directly in `index.html` (no separate stylesheet) — this keeps the page to a single request for HTML/CSS, which helps mobile load time. The only external request is for Google Fonts (Newsreader + Inter); if you want to shave that off too, you can self-host the two font files instead, but for a page this size it's a minor gain.

## 2. Turn on GitHub Pages

1. In the repo, go to **Settings → Pages**.
2. Under "Build and deployment", set **Source** to "Deploy from a branch".
3. Set **Branch** to `main` and folder to `/ (root)`, then Save.
4. Under **Custom domain**, enter `kasra-farivari.com` and save (this writes the CNAME file again automatically — the one already in the repo does the same thing, so either is fine).
5. Check **Enforce HTTPS** once it becomes available (can take a few minutes to an hour after DNS is set up).

## 3. Point your domain's DNS at GitHub Pages

At your domain registrar (wherever kasra-farivari.com is registered), set:

**For the apex domain (kasra-farivari.com):**
Add four `A` records pointing to GitHub Pages' IPs:
```
185.199.108.153
185.199.109.153
185.199.110.153
185.199.111.153
```

**For www (www.kasra-farivari.com):**
Add a `CNAME` record:
```
www.kasra-farivari.com  →  <your-github-username>.github.io
```

DNS changes can take anywhere from a few minutes to 24 hours to propagate. You can check propagation with a tool like `dig kasra-farivari.com` or whatsmydns.net.

## 4. Get it indexed

This is the part that actually affects ranking — publishing the page alone won't do much on its own:

1. Add the site to [Google Search Console](https://search.google.com/search-console) (as a new property) and verify ownership (GSC gives you a DNS TXT record or HTML file option).
2. Submit `sitemap.xml` inside Search Console.
3. Use "Request indexing" on the homepage URL inside Search Console to nudge Google to crawl it sooner.
4. Do the same in [Bing Webmaster Tools](https://www.bing.com/webmasters) — Bing results also feed some other search surfaces.

## 5. Build a few real backlinks

Structured data and a sitemap help Google understand the page, but backlinks are what typically move ranking the most. A few low-effort, legitimate ones:

- Add the link to your LinkedIn profile's "Contact info" or featured section.
- Link to it from your GitHub profile README.
- Link to it from kasrafarivari.org (e.g. in the "Find me elsewhere" list) and vice versa.
- Add it anywhere else you're already listed online (Crunchbase, About.me, Product Hunt, Medium profile).

## Notes on content

- `index.html` currently has placeholder personal content (interests, "currently" section, bio paragraphs) written to sound like you but not written by you. Edit these to reflect your actual voice, current situation, and interests before publishing — the more genuine and specific it is, the better it works both as a page people actually read and as something Google treats as original.
- The `schema.org` Person markup in the `<head>` of `index.html` explicitly tells search engines this page is about you, with links to your other profiles (`sameAs`). Keep that block in sync if you add or change any of your social/profile links.
