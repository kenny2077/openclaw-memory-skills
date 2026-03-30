---
name: import_external_memory
description: Convert pasted memory or summaries from other assistants into clean OpenClaw memory.
user-invocable: true
---

# Import External Memory

Use this skill when the user pastes or uploads memory-like content from another assistant, notes app, export, or profile summary and wants it absorbed into OpenClaw memory.

## Goal

Turn noisy external memory into clean OpenClaw-native memory.

## Accepted inputs

This skill can process:
- ChatGPT memory summaries
- Claude conversation summaries
- Gemini notes
- exported profile text
- manually written preference/project lists

## Extraction rules

Extract only durable, reusable information such as:
- identity and role context
- stable preferences
- long-term goals
- active projects
- recurring workflows
- durable constraints

Ignore:
- casual filler
- long transcript sections
- repeated points
- speculative or uncertain claims
- stale temporary details unless the user says they still matter

## Output routing

- Put durable facts into `MEMORY.md`.
- Put recent, session-only, or "currently working on" notes into `memory/YYYY-MM-DD.md`.

## Normalization rules

When importing:
1. Deduplicate aggressively.
2. Rewrite vague statements into short factual bullets.
3. Merge related facts under clear headings.
4. Keep the imported memory shorter and cleaner than the source text.
5. Never copy large raw blocks unless the user explicitly asks for archival storage.

## Recommended long-term headings

Use headings such as:
- `## Preferences`
- `## Active Projects`
- `## Goals`
- `## Constraints`
- `## Important Context`

## Safety rules

Do not import secrets or credentials.
Do not turn guesses into facts.
If the source contains contradictory durable facts, ask one short clarification question before writing.

## User-facing behavior

When finished:
- give a short import summary
- say what went to `MEMORY.md`
- say what went to daily memory, if anything
- keep the response concise
