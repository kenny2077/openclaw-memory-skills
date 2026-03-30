---
name: durable_memory_writer
description: Capture durable user memory cleanly into MEMORY.md or daily memory notes.
user-invocable: true
---

# Durable Memory Writer

Use this skill when the user asks to remember something, shares a stable preference, describes an ongoing project, or gives a standing instruction that should improve future replies.

## Goal

Write memory that is compact, factual, and easy to retrieve later.

## What belongs in long-term memory (`MEMORY.md`)

Store only durable information such as:
- stable preferences and communication style
- recurring workflows and standing instructions
- ongoing projects with multi-session value
- important relationships or roles the assistant should remember
- durable constraints, goals, or decisions

Examples:
- "I prefer step-by-step explanations."
- "Use 3 solution tiers for coding problems."
- "I am building an OpenClaw memory skill pack."
- "Keep responses concise unless I ask for detail."

## What belongs in daily memory (`memory/YYYY-MM-DD.md`)

Store short-lived context such as:
- today's progress notes
- temporary blockers
- session-specific plans
- follow-up ideas that may matter for the next day or two

Examples:
- "Today the user installed OpenClaw in an Ubuntu VM."
- "They hit an API key issue and later fixed it."
- "They want to publish two skills to GitHub this week."

## Do not save

Do not save:
- secrets, tokens, passwords, API keys, or private credentials
- raw transcript dumps
- one-off jokes or filler
- speculative guesses about the user
- highly sensitive details unless the user clearly asks you to store them

## Writing rules

Before writing memory:
1. Check whether the fact already exists.
2. Update or merge instead of duplicating.
3. Rewrite into a short factual bullet.
4. Prefer sectioned structure over long paragraphs.

When writing to `MEMORY.md`, prefer sections like:
- `## Preferences`
- `## Active Projects`
- `## Recurring Workflows`
- `## Constraints`
- `## Important Context`

## Decision rule

Use `MEMORY.md` if the fact should still matter in a week or more.
Use `memory/YYYY-MM-DD.md` if it mainly helps with recent continuity.

## User-facing behavior

After writing memory:
- briefly say what was stored
- say whether it went to long-term memory or daily memory
- keep the confirmation short
