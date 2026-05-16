---
title: Discord Gateway Checks
created: 2026-05-16
updated: 2026-05-16
type: lesson
tags: [agent, mistake, correction, discord, tool]
confidence: high
sources: [session-2026-05-16]
---

# Discord Gateway Checks

**Lesson learned**: I made a mistake checking Discord gateway status. Here's the correction.

## What I Did Wrong
- Used `hermes gateway status` — this returned empty output (command didn't work as expected)
- Didn't actually verify if the gateway process was running
- User had to tell me they sent a message to `#general` and I didn't reply

## What the Correction Was
- James corrected me: check running processes instead
- `ps aux | grep -i discord` or `pgrep -f discord` to find the gateway process
- `hermes gateway` CLI commands may not be the right tool

## Why It Happened
- Assumed `hermes` CLI had a `gateway status` subcommand
- Didn't verify the command actually returned meaningful data
- Process checks are more reliable than status wrappers

## How to Avoid It Next Time
- When checking if a service is running, **always use `ps aux | grep <service>` or `pgrep -f <pattern>` first**
- If `hermes` CLI commands exist, verify they produce output before relying on them
- For Discord specifically:
  1. `ps aux | grep -i discord` → check process exists
  2. `pgrep -f discord` → get PID
  3. `process(action="list")` → Hermes process manager
  4. Only then try `hermes` subcommands if needed

## Related
- [[neddy-setup]] — gateway config
- [[james]] — user communication preferences
