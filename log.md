# Memory Log

> Chronological record of all memory actions. Append-only.
> Format: `## [YYYY-MM-DD] action | subject`
> Actions: create, update, ingest, lesson, task, query, lint
> When this file exceeds 500 entries, rotate: rename to log-YYYY.md, start fresh.

## [2026-05-16] create | Memory vault initialized
- Domain: agent_memory
- Structure created: SCHEMA.md, index.md, log.md
- Directories: raw/, entities/, concepts/, comparisons/, queries/, tasks/, lessons/, _meta/
- Separate from trading wiki at `~/wiki`
- Initialized by James via Neddy

## [2026-05-16] create | Entity pages seeded
- [[james]] — User profile, preferences, devices, goals
- [[pi5-server]] — Hardware, network, services, model setup
- [[neddy-setup]] — This agent instance, Discord config, memory system
- Source: Session context from 2026-05-16

## [2026-05-16] create | Lesson pages seeded
- [[discord-gateway-lesson]] — Check processes with ps/pgrep, not hermes CLI
- [[video-research-lesson]] — Fetch transcripts before assuming content
- Source: Mistakes made during 2026-05-16 session, corrected by James

## [2026-05-16] create | Coding agent memory + new lesson
- Created [[coding-agent-memory]] — explains how Coder Agent uses persistent memory
- Created [[git-identity-lesson]] — git needs user.email/user.name before commits
- Patched `agent-role-coder` skill to include Karpathy wiki memory protocol
- Updated index.md
- Total pages: 10
- Source: Session-2026-05-16 — James wants coding agents to compound knowledge
