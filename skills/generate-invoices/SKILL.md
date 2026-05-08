---
name: generate-invoices
description: Generate monthly invoices from the time log. Reads ~/Documents/Claude/time-log.csv, groups by client, applies each client's billing model, drafts invoices, optionally hands off to the invoice skill for final document production. Auto-fires on "/generate-invoices", "generate invoices for [month]", "bill clients", "monthly invoicing", "send out invoices", "create my invoices", or any phrase about producing client bills from logged time. Run on the 1st of the month.
---

See `commands/generate-invoices.md` for the full workflow.

## When this skill fires

- User runs `/generate-invoices` directly
- User says: "generate invoices", "bill clients", "monthly invoicing", "create my invoices", "send out invoices for [month]"
- A scheduled task triggers this (common pattern: 1st of month at 9am)

## Pre-flight

Confirm `references/user-context.md` exists with at least one client + billing model. If missing, route to `/setup-time` first.

Also confirm `~/Documents/Claude/time-log.csv` exists with rows for the target month. If empty, recommend `/track-time` first.

## What this skill is NOT for

- Sending invoices. The plugin drafts; the user sends.
- Payment tracking. Once invoiced, payment status is tracked elsewhere.
- Tax calculation. Surfaces taxable amounts; doesn't compute jurisdictional tax.
