---
title: Video Research — Verify Before Assuming
created: 2026-05-16
updated: 2026-05-16
type: lesson
tags: [agent, mistake, correction, research, video]
confidence: high
sources: [session-2026-05-16]
---

# Video Research — Verify Before Assuming

**Lesson learned**: I watched a video and jumped to conclusions about what it showed.

## What I Did Wrong
- James asked about an Omi + Obsidian + Hermes video
- I found a video but didn't actually check its content first
- I started explaining what I thought it was about, without verifying
- James had to correct me: "I don't know what Omi is"
- I then had to actually fetch the transcript to understand it

## What the Correction Was
- James corrected me: he doesn't know what Omi is
- I fetched the transcript using youtube-transcript-api
- Only then did I understand: Omi is a **physical wearable device** ($89-150 pendant), not software
- The video showed hardware, not a software tool

## Why It Happened
- Made assumptions based on video title/thumbnail
- Didn't fetch content before summarizing
- Omi sounds like a software tool (like Omni), but it's actually hardware

## How to Avoid It Next Time
- **Always fetch the actual content** (transcript, article text) before summarizing
- If it's a video, use `youtube-transcript-api` or similar to get text
- Don't rely on titles/thumbnails for understanding
- When James asks "what is this about?" → fetch first, then explain

## Related
- [[james]] — user knowledge level (doesn't know every tech product)
- [[youtube-research-task]] — proper video research workflow
