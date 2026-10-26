# Mentu-web

Notes for coding agents working on this repository. README.md has the deploy and domain steps.

- The site is a single static `index.html`, with no build step and no JavaScript. Keep it that way
  until a second page exists, then move to Astro (MIT).
- It is hosted on Vercel as the project `mentu-web`, at https://mentu-web-fawn.vercel.app.
  `mentu-web.vercel.app` is another person's site, so never link to it.
- There is no domain yet. Don't add canonical URLs, sitemaps or an email address that assume one.
  When the domain arrives, its DNS lives on Cloudflare with DNS-only records pointing at Vercel.
  Security headers go in `vercel.json`, not a Cloudflare `_headers` file.
- The Play listing doesn't exist yet. The install button says "Coming soon to Google Play" and
  links nowhere. Only promise what launches: free guidance, Android only.
- Follow the app's design rules from the Mentu repository (`AGENTS.md`, `ui/MentuTheme.kt`):
  - Body text is at least 20px and sized in `rem`.
  - Tap targets are at least 56px, and links are underlined.
  - Use the app's colours. Orange is for shapes only, never text.
  - Respect `prefers-reduced-motion`.
- Write in the app's plain voice: short sentences, "tap" not "click", and straight quotes.
