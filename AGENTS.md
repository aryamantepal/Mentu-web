# Mentu-web

Notes for coding agents working on this repository. README.md has the deploy and domain steps.

- The site is plain static HTML and CSS at the repo root, with no build step and no framework.
  JavaScript is allowed where a page needs it, but prefer CSS. Pages are `.html` files, served
  without the extension by `vercel.json` (`cleanUrls`). Shared styles live in `styles.css`.
- It is hosted on Vercel as the project `mentu-web`, at https://mentu-web-fawn.vercel.app. Each
  push to `main` deploys to production, and each pull request gets a preview link.
  `mentu-web.vercel.app` is another person's site, so never link to it.
- There is no domain yet. Don't add canonical URLs, sitemaps or an email address that assume one.
  When the domain arrives, its DNS lives on Cloudflare with DNS-only records pointing at Vercel.
  Security headers go in `vercel.json`, not a Cloudflare `_headers` file.
- The Play listing doesn't exist yet. The hero shows a "Coming soon to Google Play" badge, styled
  so it doesn't look tappable. Swap it for a `.button` link when the listing exists. Only promise
  what launches: free guidance, Android only.
- Follow the app's design rules from the Mentu repository (`AGENTS.md`,
  `app/src/main/java/com/mentu/app/ui/MentuTheme.kt`):
  - Body text is at least 20px and sized in `rem`.
  - Tap targets are at least 56px, and links are underlined.
  - Use the app's colours. Orange is for shapes only, never text.
  - Respect `prefers-reduced-motion`.
- The layout follows https://www.khyaal.com/us, in Mentu's colours. New pages reuse it:
  - Colours are tokens on `:root` in `styles.css`. Use the tokens, not new hex values.
  - The top band is gold, with a very large, extra-bold, uppercase headline. Its size uses
    `clamp()` so it fits a 360px screen.
  - Nav links are small, uppercase and split by thin lines.
  - Cards have 20px corners and a thin warm border on cream. Buttons have 12px corners and
    uppercase text.
  - One dark brown band per page at most, with cream text. The footer is dark brown too.
  - "How it works" is a scroll tour built with CSS `animation-timeline`, with no JavaScript. It
    only runs in browsers that support it and for readers who allow motion. Everyone else sees
    the three step cards. Keep any new motion behind the same `@supports` and media check.
  - Never copy Khyaal's photos, logos, copy or numbers. Never invent users, ratings or reviews.
- Write in the app's plain voice: short sentences, "tap" not "click", and straight quotes.
