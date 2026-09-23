# DataBridge marketing site

One static page. No build step, no dependencies, no server-side anything —
`index.html` carries its own CSS and needs only the Google Fonts stylesheet it
links.

## Deploy

Copy this directory to any static host:

| Host | Command |
|---|---|
| Netlify | `netlify deploy --prod --dir=site` |
| Vercel | `vercel deploy --prod site` |
| Cloudflare Pages | `wrangler pages deploy site` |
| GitHub Pages | push `site/` to the `gh-pages` branch |
| nginx / IIS / Apache | copy the three files into the document root |

Preview locally with `python3 -m http.server -d site 8080`, then open
http://localhost:8080.

## Before it goes live

1. **The contact address.** `index.html` uses `hello@databridge.africa` in two
   `mailto:` links. Replace it with the real one.
2. **The canonical domain.** `index.html` (`rel="canonical"`, the Open Graph
   URLs), `robots.txt` and `sitemap.xml` all say `https://databridge.africa/`.
   Change all four if the domain differs.
3. **A share image.** Add a 1200x630 PNG as `og-image.png` and uncomment the
   `og:image` line in the head. Without it, a link shared in WhatsApp or
   LinkedIn shows text only.

## What the figures claim

The numbers in the "Measured, not estimated" section came from load testing
against generated core-banking data through the running application — 100M
rows out of Oracle, 61,163 rows/second, 41 jobs in 245 seconds, 2,385
automated tests. They are described on the page as measured in testing, which
is what they are. Do not let them be reworded into customer results.

No certification, customer or uptime claim appears anywhere on the page,
deliberately.
