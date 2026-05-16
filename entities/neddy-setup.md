---
title: Neddy (This Agent)
created: 2026-05-16
updated: 2026-05-16
type: entity
tags: [agent, config, workflow]
confidence: high
sources: [session-2026-05-16]
---

# Neddy (This Agent)

The agent instance configured by James. Name: Neddy.

## Identity
- Agent name: Neddy
- User name: James / Jay (never call user "Neddy")
- CLI agent (terminal output, no markdown formatting in replies)
- Persistent memory via `memory` tool + wiki/obsidian vaults

## Current Memory System
- **Short-term**: `memory` tool (user profile + environment facts) — injected every turn
- **Trading research**: `~/wiki` — trading/investing knowledge base, syncs to GitHub
- **Agent memory**: `~/memory` — this vault, for agent mistakes, tasks, preferences
  - Syncs to GitHub separately so James can browse on iPad
  - Coder Agent also reads/writes here (see [[coding-agent-memory]])

## Agent Roles
- **Main (Neddy)**: You are talking to me now. Coordinates all tasks.
- **Coder**: Spawns for coding tasks. Reads `~/memory` at session start, writes lessons back.
- **Trader**: Spawns for trading research. Reads `~/wiki` for market context.
- **Engineer**: Spawns for physical design/simulation tasks.

## Gateway Setup
- **Discord**: Bot `Neddy#0792`
  - Token stored in `config.yaml` (authoritative) — NOT `.env`
  - `.env` has `DISCORD_BOT_TOKEN` but it can drift; after token reset, `config.yaml` must be updated explicitly
  - Home channel: `#general` (ID: 1490138418661822617)
  - Allowed user: `498146615413178398`
  - Multiple channels: `#general/#neddy` for chat, `#investor-watchlist-research` for trading

## Model Configuration
- Provider: Ollama Cloud
- Main model: `kimi-k2.6:cloud`
- Fallback: `qwen3:cloud`

## Related
- [[james]] — the user
- [[agent-memory-system]] — how memory is organized
- [[discord-gateway-lesson]] — lessons about Discord checks
