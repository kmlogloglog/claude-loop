# Claude Loop

**Operational memory and safety for [Claude Code](https://www.anthropic.com/claude-code).**

Claude Loop adds persistent memory, file-level rollback, automatic test feedback, loop detection, context-pressure awareness, and before/after screenshot comparison to every Claude Code session — running entirely on your machine.

🌐 **Live site:** [claudeloop.surge.sh](https://claudeloop.surge.sh/)
👤 **Built &amp; maintained by:** [Karim Meleka](https://karimmeleka.com) · [@kmlogloglog](https://github.com/kmlogloglog)

---

This repository contains the source for the Claude Loop marketing site — a fast, dependency-free static page that explains what Claude Loop does and ships a small library of **copy-ready agent "loops"** you can paste straight into Claude Code.

## What's a loop?

A normal prompt fires once and hopes for the best. A *loop* turns that single shot into a cycle — try something, check the result, decide the next move, and stop the moment the goal is genuinely met. The site includes a tabbed, copyable set of example loops:

| Loop | For |
| --- | --- |
| **Speed Sweep** | Measured, page-by-page performance wins |
| **Flake Killer** | Quieting intermittent CI failures |
| **Docs Drift Fixer** | Keeping docs in sync with code |
| **Coverage Climber** | Raising test coverage that reflects real behavior |
| **Error Triage** | Knocking down the loudest production errors, safely |
| **Diff Polisher** | One careful pass before a change ships |

## Tech

- Single self-contained `index.html` — no build step, no framework, no dependencies.
- Source Serif 4 / Inter / JetBrains Mono via Google Fonts.
- Full SEO: semantic HTML, Open Graph + Twitter cards, JSON-LD (`WebSite`, `SoftwareApplication`, `Person`, `FAQPage`), `sitemap.xml`, `robots.txt`, and a generated `og-image.png`.
- Progressive-enhancement scroll reveal (content stays fully visible if JS is off).

## Run locally

```bash
python3 -m http.server 8080
# then open http://localhost:8080
```

## Deploy

Published to [Surge](https://surge.sh):

```bash
surge . claudeloop.surge.sh
```

### Regenerate the social image

`og-image.png` is rasterized from `og-image.svg` (1200×630):

```bash
npx sharp-cli -i og-image.svg -o og-image.png resize 1200 630
```

## Credits

The loop concept and the "ways to work with loops" framing build on the open-source
[Loopy / Loop Library](https://github.com/Forward-Future/loopy) project by Forward Future (MIT).
All copy here is original; only the underlying ideas are shared.

## License

[MIT](LICENSE) © Karim Meleka
