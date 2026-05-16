---
title: Coding Agent Memory System
created: 2026-05-16
updated: 2026-05-16
type: concept
tags: [agent, workflow, coding, memory]
confidence: high
sources: [session-2026-05-16]
---

# Coding Agent Memory System

The Coder Agent (spawns for coding tasks) now has persistent memory via the `~/memory` vault.

## How it works
1. **Session start** → Coder Agent reads `~/memory/SCHEMA.md`, `index.md`, and `lessons/` related to the task
2. **During task** → If a tool fails in a new way, a library has a gotcha, or James corrects the code, the agent writes a lesson
3. **After task** → Lesson gets committed to git, pushed to GitHub, appears on James's iPad
4. **Next time** → Agent doesn't repeat the same mistake because it reads its own lessons

## What gets logged
- **Lessons** (`lessons/`) — Mistakes, corrections, gotchas (e.g. "Discord token is in config.yaml not .env")
- **Tasks** (`tasks/`) — Recurring coding patterns (e.g. "How to set up a new Discord bot command")
- **Entities** (`entities/`) — Tools, APIs, services the agent interacts with

## Conventions for coding lessons
- Filename: `{language}-{topic}-lesson.md` (e.g. `python-async-lesson.md`)
- Frontmatter: `type: lesson`, `tags` from SCHEMA taxonomy
- Body: What went wrong, what the fix was, why it happened, how to avoid it
- Minimum 2 `[[wikilinks]]` to other pages

## Related
- [[neddy-setup]] — Main agent setup
- [[james]] — User preferences
- [[agent-memory-system]] — Overall memory architecture
