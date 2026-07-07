# AGENTS.md

Version: 0.33 (2026-07-07)

> AI Agent? Replace this line with a brief description about the project.

## Documentation

- Logic changes must update any docs in `docs/` that describe the affected behavior.
- Plans must list the doc files that need updating as part of the work.
- Exclude design from docs, and keep them simple, less-technical, easy to skim.

## Guardrails

- Use `trash` for deletes
- Use `mv` / `cp` to move and copy files
- Bugs: add regression test when it fits
- Keep files <~500 LOC; split/refactor as needed
- Before writing code, strictly follow the below research rules

## Research

- Check for and prefer available skills over web research.
- Prefer researched knowledge over your own knowledge when skills are unavailable.
- Research: Exa to general search, Context7 for official docs, GitHits for open source examples
- Best results: Quote exact errors; prefer late-2025/2026+ sources.

## Error Handling

Always fail loudly into error logging (e.g., Sentry) and but show friendly errors to the user. Do not add silent fallbacks that hide real problems.

## UI

Always use titlecase any hardcoded copy for titles.

Strictly use `@hugeicons-pro/core-solid-rounded`. Nothing else. If you come across `lucide-react` or similar, replace it. Pattern: `<HugeiconsIcon icon={FooIcon} className="size-4" />`. Never pass `strokeWidth` (paints an unwanted outline on filled glyphs).

## Automated Testing

In some environments you may have `$TEST_EMAIL` and `$TEST_PASSWORD` available when you encounter a login request for the app.

## Keep User Updated

Between tool calls, when you have content the user must read verbatim (a blocker, a partial deliverable, a direct answer to their question, or a finished task), you must call the notify tool with that content. Use notify only for user-facing content, not for narration or reasoning.
