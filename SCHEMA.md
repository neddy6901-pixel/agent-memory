---
wiki_version: 1.0.0
domain: agent_memory
initialized: 2026-05-16
---

# Agent Memory Schema

## Domain
Neddy's persistent memory vault. Covers: user preferences, recurring tasks,
environment facts, agent mistakes & corrections, workflow patterns, and
conversations worth remembering across sessions.

This is NOT for trading research — that lives in `~/wiki`.

## Conventions
- File names: lowercase, hyphens, no spaces
- Every page starts with YAML frontmatter
- Use `[[wikilinks]]` to link between pages (minimum 2 outbound links per page)
- When updating a page, always bump the `updated` date
- Every new page must be added to `index.md`
- Every action must be appended to `log.md`
- Confidence levels: `high` = verified multiple times, `medium` = single source or inferred, `low` = guess or temporary
- Ticker symbols still get parens, but this vault is not trading-focused

## Frontmatter
```yaml
---
title: Page Title
created: YYYY-MM-DD
updated: YYYY-MM-DD
type: entity | concept | task | lesson | pipeline | note
tags: [from taxonomy below]
sources: [session-YYYY-MM-DD, raw/articles/source.md]
confidence: high | medium | low
contested: true
contradictions: [other-page-slug]
---
```

## Tag Taxonomy

### User
- preference, habit, schedule, location, device, goal

### Agent
- mistake, correction, improvement, workflow, tool, config

### Environment
- network, hardware, service, account, api

### Meta
- entity, concept, task, lesson, pipeline, note, recurring, one-off

## Page Thresholds
- **Create a page** when a fact/pattern appears in 2+ sessions OR is critical to get right
- **Add to existing page** when new info refines something already covered
- **DON'T create a page** for one-off trivia, transient state, or things easily re-discovered
- **Split a page** when it exceeds ~200 lines

## Entity Pages (people, devices, services)
One page per notable entity. Include:
- Overview / what/who it is
- Key facts and relationships
- Links to related pages
- Source references

## Task Pages (recurring workflows)
One page per recurring task pattern. Include:
- What triggers it (user request pattern)
- Step-by-step process
- Common pitfalls and how to avoid them
- Related tools/commands
- When it was last performed

## Lesson Pages (mistakes & corrections)
One page per category of mistake. Include:
- What I did wrong
- What the correction was
- Why it happened (root cause)
- How to avoid it next time
- Date of lesson

## Pipeline Pages (workflows)
Step-by-step workflows that span multiple tools. Include:
- Current setup and tools
- Process flow
- Known issues and workarounds
- Links to related tasks/lessons

## Update Policy
When new information conflicts with existing content:
1. Check dates — newer corrections generally supersede older ones
2. If genuinely contradictory (e.g. user changed preference), note both with dates
3. Mark contradiction in frontmatter
4. Flag for user review
