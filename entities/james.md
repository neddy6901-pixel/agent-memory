---
title: James (User)
created: 2026-05-16
updated: 2026-05-16
type: entity
tags: [user, preference, habit, goal]
confidence: high
sources: [session-2026-05-16]
---

# James (User)

James (also goes by Jay) is the primary user of this agent instance.

## Identity
- Name: James / Jay
- Active trader/researcher (stocks, equities)
- Lives between two locations: home address and mom's address
- Uses iPad as primary browsing device

## Communication Preferences
- Wants multiple Discord channels for different topics:
  - `#general` / `#neddy` → normal chat
  - `#investor-watchlist-research` → trading research posts
  - Topic-specific channels (e.g. `#ufo`) created on demand
- James explicitly states which channel to use for research posts
- Uses terminal/CLI for direct agent interaction

## Trading & Research
- Building a daily social signal research pipeline
- Tracks stock tips from Twitter/X accounts (currently: @wliang, @nolimitgains)
- Uses personal X account for API access (read-only research pipeline)
- Active in market analysis, turnaround plays, growth companies
- Full trading research wiki lives separately at `~/wiki`

## Devices & Setup
- **Raspberry Pi 5** as home server (see [[pi5-server]])
  - Open WebUI at port 8080 (accessed from iPad browser)
  - Argon THRML fan on 4-pin JST header
  - Custom fan control: `pi5-fan-baseline` systemd service
- **iPad** → browses Open WebUI, Obsidian, and Discord
- Uses cloud-only models (no local Ollama)
  - Main: kimi-k2.6:cloud
  - Fallback: qwen3:cloud

## Goals
- Improve agent memory so it learns from mistakes
- Build compounding knowledge base (trading + agent memory)
- Uses Obsidian on iPad to browse wiki

## Related
- [[pi5-server]] — hardware details
- [[neddy-setup]] — this agent instance
- [[agent-memory-system]] — how memory works
