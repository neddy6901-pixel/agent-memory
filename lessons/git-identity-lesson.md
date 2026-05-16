---
title: Git Identity Required for Commits
created: 2026-05-16
updated: 2026-05-16
type: lesson
tags: [git, mistake, correction, config]
confidence: high
sources: [session-2026-05-16]
---

# Git Identity Required for Commits

**Lesson learned**: Git requires `user.email` and `user.name` to be set before any commit.

## What Went Wrong
- Created new git repo `~/memory` with `git init`
- Ran `git add -A` and `git commit -m "..."`
- Git rejected the commit with:
  ```
  Author identity unknown
  Please tell me who you are.
  Run:
    git config --global user.email "you@example.com"
    git config --global user.name "Your Name"
  ```

## What the Fix Was
- Set repo-local git identity (safer than global on multi-user systems):
  ```bash
  cd ~/memory
  git config user.email "james@local.pi"
  git config user.name "James"
  ```
- Then commit succeeded

## Why It Happened
- This was a fresh Pi setup — no global git identity had been configured
- `~/wiki` repo had already set its own local identity, so I never noticed
- Assumed git identity was already configured globally

## How to Avoid It Next Time
- **Before any `git commit` in a new repo**, verify identity:
  ```bash
  git config user.email 2>/dev/null || git config --global user.email 2>/dev/null || echo "NO EMAIL SET"
  git config user.name  2>/dev/null || git config --global user.name  2>/dev/null || echo "NO NAME SET"
  ```
- If missing, set repo-local identity first
- Or check if an existing repo nearby has identity set (`cd ~/wiki && git config user.email`)

## Related
- [[pi5-server]] — This Pi had no global git identity
- [[agent-memory-system]] — Part of memory vault setup
