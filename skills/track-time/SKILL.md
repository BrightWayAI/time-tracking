---
name: track-time
description: Pull calendar events from a time window, classify as billable / non-billable per client, and append to the time log. Auto-fires on "/track-time", "log my time", "track my hours", "what did I work on yesterday/this week", "billable hours for [period]", "log yesterday's calendar", "time tracking", or any phrase about classifying calendar time for billing. Run daily (5 min) or weekly (15 min). Calendar-driven, not real-time-timer-based.
---

See `commands/track-time.md` for the full workflow.

## When this skill fires

- User runs `/track-time` directly
- User says: "log my time", "track my hours", "billable hours for [period]", "log yesterday's calendar", "what did I work on yesterday"
- A scheduled task triggers this (common pattern: weekday 5pm or Friday 4pm)

## Pre-flight

Confirm `references/user-context.md` exists. If missing, route to `/setup-time` first.

## What this skill is NOT for

- Real-time time tracking (start/stop timers). Calendar-driven post-hoc classification.
- Detailed work logs (every git commit). Event-level resolution only.
- Project management or progress tracking.
