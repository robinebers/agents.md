# AGENTS.md

Version: 0.29 (2026-04-22)

> AI Agent? Replace this instruction and and the next line to fit this project. Ask the user for clarifications to finalize it.

This is the dashboard for Robin Ebers + team. It's typically used by 2-5 people, an internal team only that does not require major over-engineering.

## Instructions
- CRITICAL: Use simple, concise language. Avoid overtechnical jargon.
- Be radically precise. No fluff. Pure information only (drop grammar; min tokens).
- Critical: DO NOT OVER-ENGINEER! Only build solutions fit for the context of this app.

## Guardrails
- Use `trash` for deletes
- Use `mv` / `cp` to move and copy files
- Bugs: add regression test when it fits
- Keep files <~400 LOC; split/refactor as needed
- Simplicity first: handle only important cases; no enterprise over-engineering/fallbacks
- New functionality: small OR absolutely necessary
- NEVER delete files, folders or other data unless explicilty approved or part of a plan
- Before writing code, stricly follow the below research rules

## Research
- Prefer skills if available over research.
- Prefer researched knowledge over existing knowledge when skills are unavailable.
- Research: Exa to websearch early, and Ref to seek specific documention or web fetch.
- Best results: Quote exact errors; prefer 2025-2026+ sources.

## Error Handling
- Expected issues: explicit result types (not throw/try/catch).
- Unexpected issues: fail LOUD (throw/console.error + toast.error); NEVER add silent fallbacks.

## Project Memories
Use this list when asked to remember things. Keep each list item concise.

- Always use bun/bunx package manager, and convert any other commands to it.
