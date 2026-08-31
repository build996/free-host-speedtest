# Free Host Speed Test

A deliberately tiny static page, deployed **identically** to every free hosting platform we review, so their global access speed can be compared on equal terms.

Live: **https://build996.github.io/free-host-speedtest/**

## Why it exists

"Which free host is fastest?" is usually answered with vendor marketing or a synthetic score from a machine sitting next to the server. Neither tells you what a visitor experiences.

This page removes every variable except the host. Same HTML, same near-zero payload, no images, no frameworks, no build step — so any difference in load time is the platform's edge network and cold-start behaviour, not the site.

The page stamps its own load time in the browser, which makes it obvious when a response was served from cache versus generated fresh.

## How to use it

1. Deploy this repo to whichever free hosts you want to compare — Cloudflare Pages, GitHub Pages, Netlify, Vercel, Render, Deno Deploy, Hugging Face Spaces all take it as-is.
2. Run each resulting URL through a multi-location latency tool (we use 17ce and itdog for China-inclusive coverage, since most Western tools miss the region where free-CDN performance varies most).
3. Compare TTFB and full load, and note **cold starts** separately — several free PaaS tiers sleep after idling, so the first request after a quiet period is the number that actually matters to a visitor.

The page is `noindex` on purpose: it exists to be measured, not to rank.

## Related

Part of a small set of measured, regularly re-checked references:

| Repo | Covers |
|---|---|
| **[actually-free-hosting](https://github.com/build996/actually-free-hosting)** | Which free hosting tiers still exist — does it sleep, does it expire |
| **[free-ai-api-benchmark](https://github.com/build996/free-ai-api-benchmark)** | The same approach applied to free AI APIs: speed, quotas, agent tasks, run weekly |
| **[awesome-free-ai-apis](https://github.com/build996/awesome-free-ai-apis)** | Real free-tier limits for AI APIs, with the catches |

Write-ups at **[toolfreebie.com](https://toolfreebie.com)** — see [free hosting compared](https://toolfreebie.com/best-free-hosting-2026/).

MIT.
