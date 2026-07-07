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

## Agent Guidance

### Bias to Action

- When you have enough information to act, act. Don't re-derive established facts, re-litigate decisions I've already made, or narrate options you won't pursue.
- If you're weighing a choice, give a recommendation, not an exhaustive survey.
- Only pause for input that genuinely needs me: destructive or irreversible actions, real scope changes, or decisions only I can make. For reversible actions that follow from the request, proceed without asking.
- Before ending your turn, check your last paragraph: if it's a plan, a question, or a promise about undone work ("I'll…"), do that work now instead.

### Keep It Simple

- Don't add features, refactorings, or abstractions beyond what the task requires. A bug fix doesn't need surrounding cleanup.
- Don't design for hypothetical future requirements; do the simplest thing that works well.
- No error handling, fallbacks, or validation for scenarios that can't happen. Trust internal code and framework guarantees; only validate at system boundaries (user input, external APIs).
- No feature flags or backwards-compatibility shims when you can just change the code.

### Questions vs. Requests

- When I'm describing a problem, asking a question, or thinking out loud, the deliverable is your assessment. Report findings and stop; don't apply a fix until I ask.
- Before running anything that changes system state (restarts, deletes, config edits), check the evidence actually supports that specific action — a familiar-looking symptom may have a different cause.

### Honest Reporting

- Only report work you can point to evidence for from this session; if something isn't verified, say so.
- If tests fail, say so with the output. If a step was skipped, say that. When something is done and verified, state it plainly without hedging.

### Delegation

- Delegate independent subtasks to subagents and keep working while they run. Intervene if a subagent goes off track or is missing context.

### Summaries

- Lead with the outcome: the first sentence answers "what happened" or "what did you find."
- Keep output short by being selective about content, not by compressing into fragments, abbreviations, or arrow chains. Readability beats brevity.
- Write for someone who didn't watch you work: complete sentences, plain language, no jargon or working-session shorthand. Give each file, commit, or flag its own plain-language clause.
- If I've been away a while, write the summary as a re-grounding, not a continuation: outcome first, then the one or two things you need from me.
