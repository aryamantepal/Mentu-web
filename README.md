# Mentu-web

The public website for [Mentu](https://github.com/krizer18/Mentu), a voice-guided Android helper for
older adults. The plan for the site, its pages and its SEO is `website.md` in the Mentu repository.

Live at https://mentu-web-fawn.vercel.app until the domain is bought.

## What's here

Plain static HTML and CSS, with no build step and no framework. Open any `.html` file in a browser
to preview it.

- `index.html` is the home page. Its home-only CSS is inline.
- `privacy.html`, `terms.html` and `delete-account.html` are the legal pages. Play and the app link
  to them at `/privacy`, `/terms` and `/delete-account`, so keep those URLs stable.
- `styles.css` holds the styles every page shares: colour tokens, header, footer, cards and buttons.
- `vercel.json` turns on `cleanUrls`, so Vercel serves `privacy.html` at `/privacy`. This only works
  on Vercel. Locally, open the `.html` file, because the footer links point at the clean URLs.

Marked "To be confirmed" notes on the legal pages are gaps: TypeSafe's data terms, launch countries,
the support email (needs the domain) and a lawyer's review.

## Deploying

The site is on Vercel as the project `mentu-web` (team `aryamantepals-projects`, Hobby plan),
connected to this GitHub repository. Each push to `main` deploys to production, and each pull
request gets a preview link. Previews have Vercel Authentication on, so open them signed in to
Vercel, or fetch them with `vercel curl`.

To deploy by hand from this folder, run `vercel deploy --prod`. It deploys whatever is checked
out, so run it from `main`, or production gets ahead of `main` and the next push undoes it.

`mentu-web.vercel.app` belongs to someone else's project, so Vercel gave this one
`mentu-web-fawn.vercel.app`.

## Adding the domain later

1. Buy the domain (GitHub Student Pack or Cloudflare Registrar) and keep its DNS on Cloudflare.
2. In Vercel → mentu-web → Settings → Domains, add the apex (`example.com`) and `www.example.com`,
   and set `www` to redirect to the apex.
3. In Cloudflare DNS, add the records Vercel shows. Today they are `A @ → 76.76.21.21` and
   `CNAME www → cname.vercel-dns.com`. Set both to **DNS only** (grey cloud). If Cloudflare proxies
   them, Vercel can't renew its HTTPS certificate and requests can loop between the two.
4. Add `<link rel="canonical" href="https://example.com/">` to the page so search engines index
   the domain, not the `vercel.app` address.
5. Use the domain for the support email (`help@example.com`) and in the Play listing.
