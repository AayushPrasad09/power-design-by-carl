# Power Design — Claude Code plugin

A Claude Code plugin for slide decks **and** websites that don't look like AI made them.

**Brand DNA × codified design principles → polished, self-contained HTML.**
20 research-backed rules for slides, 20 for the web, and 72 ready-made brand systems
(Stripe, Apple, Linear, Spotify, Vercel, Notion, Tesla, Airbnb…).

---

## Install

In Claude Code, add this repository as a plugin marketplace, then install the plugin:

```
/plugin marketplace add AayushPrasad09/power-design-by-carl
/plugin install power-design@power-design
```

You can also pass a full git URL or a local folder path to `/plugin marketplace add`.

Restart Claude Code (or start a new session) after installing.

### Update / remove

```
/plugin marketplace update power-design
/plugin uninstall power-design@power-design
```

---

## Use

Just ask — the skill triggers on deck or website requests:

```
> make me a pitch deck in Stripe's style about our new product launch
> build me a landing page in linear.com's style for my new app
```

Or call it directly: `/power-design:power-design`.

The skill will:

1. Ask **deck or website?** (skipped when obvious).
2. Ask which brand — paste a URL, pick from the library, or use the neutral default.
3. Ask a short brief (deck: headline + 3–5 points + audience · site: type, goal, sections).
4. Generate a single self-contained `slides.html` or responsive `site.html`, checked against the matching 20 rules.
5. Open it in your browser and refine through conversation.

### Optional: live brand extraction

Extracting a brand from any URL uses [Firecrawl](https://firecrawl.dev) (free tier available).
Set up the Firecrawl MCP server with your own API key if you want this; the 72 built-in
brands work without it.

---

## Repository layout

```
.claude-plugin/
  marketplace.json                 # marketplace catalog (lists the plugin)
plugins/power-design/
  .claude-plugin/plugin.json       # plugin manifest
  skills/power-design/
    SKILL.md                       # the skill runbook
    principles/                    # 20 slide rules + 20 web rules (+ illustrations)
    lib/extract-brand.md           # Firecrawl brand-extraction recipe
    brands/<name>/brand-style.md   # 72 brand systems + _template.md
```

### Adding a brand

Copy `plugins/power-design/skills/power-design/brands/_template.md` to
`brands/<slug>/brand-style.md`, fill it in, bump `version` in both
`plugin.json` and `marketplace.json`, and push. Users get it with
`/plugin marketplace update power-design`.

---

## Credits & license

Packaged as a plugin by **Carl**. Original skill by **Jack Roberts** — [github.com/ItsssssJack/power-design](https://github.com/ItsssssJack/power-design)
· [power-design.vercel.app](https://power-design.vercel.app).
Brand library derived from [VoltAgent/awesome-design-md](https://github.com/VoltAgent/awesome-design-md).

MIT — see [LICENSE](LICENSE).
