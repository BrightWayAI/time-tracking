# Changelog

All notable changes to time-tracking are documented here.

Format follows [Keep a Changelog](https://keepachangelog.com/). Versions match `plugin.json`.

## [0.1.0] — Initial release

### Added
- Calendar-driven time tracking (`/track-time`) — pulls calendar events from a window (default yesterday or last week), classifies each as billable / non-billable per client (using attendee domain matching, title prefix, or project tag from setup), prompts for confirmation, appends to `~/Documents/Claude/time-log.csv`.
- Monthly invoice generation (`/generate-invoices`) — reads the time log, groups by client, applies each client's billing model (hourly / retainer / flat-fee project), drafts invoices using a user-editable template. Optionally hands off to `anthropic-skills:invoice` for final docx production. Marks rows as invoiced to prevent double-billing.
- `/setup-time` interview — captures clients with billing models, calendar tagging conventions, rounding rules (15 min / 30 min / actual), categories, invoice preferences (template, net terms, numbering, tax, delivery method, payment instructions). Optionally imports client list from `project-setup` if installed.
- Time log lives at `~/Documents/Claude/time-log.csv` as plain CSV — portable, hand-editable, backup-friendly.
- Schema documented in `references/time-log-schema.md` with privacy guidance.
- Companion plugin support: `project-setup` (engagement data), `claude-cortex` (memory of time-related observations), `core-ops` (pipeline-analyst for revenue-vs-time view).
