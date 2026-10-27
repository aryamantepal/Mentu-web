# Mentu-web

The public website for [Mentu](https://github.com/krizer18/Mentu), a voice-guided Android helper for
older adults. The plan for the site, its pages and its SEO is `website.md` in the Mentu repository.

Live at https://mentu-web-fawn.vercel.app until the domain is bought.

## What's here

One static page, `index.html`, with its CSS inline and no JavaScript or build step. Open it in a
browser to preview it. Move to Astro once the site needs a second page (privacy, delete account,
terms, help, guides).

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
