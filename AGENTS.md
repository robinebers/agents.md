# AGENTS.md

Version: 0.30 (2026-05-27)

> AI Agent? Replace this instruction and and the next line to fit this project. Ask the user for clarifications to finalize it.

## CRITICAL RULES

- Use simple, concise language. Avoid super jargon.
- Be radically precise. No fluff. Pure information only (drop grammar; min tokens).
- The platform is still in development and, as such, think 5 to 10 users. Do not over-engineer.

## Documentation

- Functional logic and Convex changes MUST update any docs in `docs/` that describe the affected behavior.
- Plans MUST list the doc files that need updating as part of the work.
- Exclude design from docs, and keep them SIMPLE.

## Guardrails

- Use `trash` for deletes
- Use `mv` / `cp` to move and copy files
- Bugs: add regression test when it fits
- Keep files <~500 LOC; split/refactor as needed
- NEVER delete files, folders or other data unless explicitly approved or part of a plan
- Before writing code, strictly follow the below research rules

## Research

- Check for and prefer available skills over web research.
- Prefer researched knowledge over your own knowledge when skills are unavailable.
- Research: Exa to websearch, Ref for official docs, GitHits for open source examples
- Best results: Quote exact errors; prefer late-2025/2026+ sources.

## Error Handling

- Expected issues: explicit result types (not throw/try/catch).
- ALWAYS FAIL LOUDLY INTO SENTRY (but show friendly errors to the user); NEVER add silent fallbacks.

## UI

- Titlecase any hardcoded copy for titles.

## Icons

- Strictly use `@hugeicons-pro/core-solid-rounded`. Nothing else.
- If you come across `lucide-react` or similar, replace it.
- Pattern: `<HugeiconsIcon icon={FooIcon} className="size-4" />`. Never pass `strokeWidth` (paints an unwanted outline on filled glyphs).

## Automated Testing

The cloud environments have `$TEST_EMAIL` and `$TEST_PASSWORD`. Sometimes the login redirect might say that the login failed. This is an unknown bug. In these cases, just go back to localhost:3000 and you should be logged in.
