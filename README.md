# Argus paper fleet: open report

Every weekday around the US open, reports which paper buys and sells are going in for each fleet account. Read-only.

**Type:** Claude scheduled task · **Area:** Investing research (paper money)

## What it does

- Runs the engine's health check, lists the queued paper orders, and verifies the hash chains.
- Spots when the fleet is behind (the daily update didn't run) and says the next update will catch up and mark those decisions LATE.

## Guardrails

- No brokerage calls at all, no file changes, never deletes.
- Always says it is paper money and not a recommendation.

## When it triggers

> Every weekday around the US market open - report which paper buys and sells are going in at today's open for each fleet account. Read-only; no data fetch; never places orders.

## What's in this repo

- `SKILL.md`: the skill itself, the file Claude or Codex reads.
- Not included: Argus 2.0 itself is private and not published.
- Written to be generic: where the skill relies on the user's own files, it names them by role, not by content.

## Install

This is a Claude scheduled-task prompt. Create a scheduled task in the Claude desktop app and paste the body of `SKILL.md` as its prompt, or save it as `~/.claude/scheduled-tasks/argus-paper-fleet-open/SKILL.md`. It expects the project files it names to exist.
