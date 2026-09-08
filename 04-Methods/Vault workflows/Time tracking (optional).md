---
type: process
title: "Time tracking (optional)"
tags:
  - vault
  - workflow
---

# Time Tracking with ActivityWatch (Optional)

A passive time-tracking system using [ActivityWatch](https://activitywatch.net/), a free, open-source, local-first time tracker. This is entirely optional; the rest of the vault works without it.

## Why

See where time actually goes vs. plans. Calibrate how long things take. Especially useful if you find it hard to estimate time or lose track of where the day went.

## Key principle

**Passive tracking only.** You install ActivityWatch and it runs in the background, recording which application and window is in focus. No manual start/stop timers, no pomodoro, no active intervention. You review the data at the end of the day.

## Setup

1. **Install ActivityWatch:** Download from [activitywatch.net](https://activitywatch.net/). It runs as a tray application.
2. **Install the browser extension:** [ActivityWatch Web Watcher](https://docs.activitywatch.net/en/latest/getting-started.html) for Chrome/Firefox. This tracks which website is in the active tab.
3. **Let it run:** ActivityWatch starts collecting data immediately. Browse the web UI at `http://localhost:5600` to see your data.

## How it integrates with the vault

The integration is through a `## Time Log` section in daily notes. This can be:

- **Manual:** At the end of the day, open `localhost:5600`, review your activity, and write a brief time summary in your daily note
- **Automated:** Write or adapt a Python script to query the ActivityWatch API and append a summary to the daily note (see below)

### Suggested category taxonomy

| Category | What it covers |
|----------|---------------|
| Writing | Manuscripts, drafts, Word |
| Analysis | RStudio, VSCode, coding, HPC |
| Lab | Off-computer bench work (estimate from AFK gaps) |
| Meetings | In-person or video calls |
| Admin | Email, Slack, administrative tasks |
| Reading | Papers, journals, documentation |
| Career | Applications, CVs, cover letters |
| Leisure | Social media, video, news |
| Uncategorized | Everything else |

### Lab day integration

Lab time is off-computer and invisible to ActivityWatch. When you have a lab day:
- Your daily note's lab notebook entries (created via `/lab` or manually) provide timestamps
- Large AFK gaps during work hours suggest lab time
- Estimate and note it: `Lab: ~3h (media prep + plating)`

### Export script (optional)

If you want automated daily summaries, a Python script can:
1. Query the ActivityWatch REST API for today's events
2. Apply regex rules to categorize by application and window title
3. Append a `## Time Log` section to today's daily note with category totals and a condensed timeline

This is a build-it-yourself project. The core AW API endpoints:
- `http://localhost:5600/api/0/buckets/` — list available data buckets
- `http://localhost:5600/api/0/buckets/<bucket_id>/events` — get events
- `http://localhost:5600/api/0/query/` — run complex queries

## Privacy

All data stays local. ActivityWatch is open-source (MPL-2.0) with no telemetry. Only outbound call is a disableable GitHub update check. Your raw activity data never leaves your machine.

## Getting started

1. Install ActivityWatch and the browser extension
2. Let it run for a week without trying to act on the data
3. Browse the web UI to understand the data shape
4. Start writing brief time summaries in your daily notes
5. (Optional) Build or adapt an export script once you know what categories matter to you
