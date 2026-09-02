# ig-audit

An Instagram Reels audit and scriptwriting kit for Claude. It reads the **real**
numbers off your account — views, saves, shares, watch time — and turns them into an
audit, a content calendar, and Reel scripts written in your own voice.

Adapted from the free guide at [guia.fellipesales.com.br](https://guia.fellipesales.com.br)
by [@ofellipesales](https://instagram.com/ofellipesales). The prompts are his; this
plugin packages them as slash commands and adds the `reel-scriptwriter` skill that
`/ig-scripts` depends on.

## Install

```
/plugin install ig-audit@claude-watch
```

## Setup — connectors

The commands are useless without live data, so connect these first. All three are
account-level OAuth connectors: you add them yourself in Claude under **Settings →
Connectors**. Nothing here can install them for you.

| Connector | What it does | Needed by |
|---|---|---|
| **Windsor.ai** | Free bridge that pulls live Reel metrics (views, saves, shares, watch time) into Claude | `/ig-audit`, `/ig-scripts`, `/ig-calendar` |
| **Apify** | Pulls and transcribes public Reels from other creators | `/ig-niche` |
| **Metricool** | Schedules posts to Instagram, TikTok and LinkedIn | `/ig-schedule` |

**Windsor.ai** (~2 minutes, free, no code):

1. Create a free account at [windsor.ai](https://windsor.ai).
2. In Claude, open **Connectors**, search for **Windsor**, add it.
3. Authorize Windsor through Facebook and pick your Instagram profile. Your Instagram
   must be a **Business or Creator** account linked to a Facebook page — personal
   accounts expose no metrics API.
4. Set the connector to **Always allow**, or it will prompt for authorization in every
   conversation.

**Apify** is not in the public connector directory for every account. If you don't find
it under Connectors, add it as a custom MCP server from your Apify account settings.

**Metricool** is optional — only needed if you want Claude to schedule posts as well as
plan them.

## Commands

Run them in this order, **in one conversation** — each builds on the last.

| Command | What it does |
|---|---|
| `/ig-audit <@handle>` | Ranks your top 10 Reels by saves and shares, breaks down what's working and what isn't, emits a phone-readable PDF ending in a 3-line blind-spot verdict |
| `/ig-scripts` | Turns the audit into 3 ready-to-film scripts in your voice, with hook variants, on-screen text cues and captions |
| `/ig-calendar` | A realistic 7-day calendar at one post a day, leading with your strengths and fixing the blind spot |
| `/ig-hook <hook>` | Rewrites a flat hook 5 ways, then commits to one |
| `/ig-caption <reel> \| <keyword>` | 3 captions in your voice, opening with comment-bait |
| `/ig-niche <@a> <@b> <@c>` | Pulls and transcribes the outperforming Reels of creators in your niche, then picks the one format to recreate first |
| `/ig-schedule <caption>` | Finds your best slot this week and schedules the Reel — shows you what it will post before it goes live |

## Skill

`reel-scriptwriter` is loaded automatically when you ask for Reel scripts, hooks, or
captions — you don't have to invoke it. It carries the beat structure, the hook
formulas, the 30–55s word budget, and the rule that matters most: voice over polish.

## Notes

- Every number in an audit comes from the connector. If Windsor isn't connected, the
  commands stop rather than estimate — a made-up view count is worse than no audit.
- `/ig-schedule` posts to a real account. It confirms the slot and caption with you
  before committing.
