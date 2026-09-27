# Ship

Read when wrapping up. Ship makes the result verifiable and keeps the repository clean — it does not publish on its own authority.

## Checks

- The project's own gate runs green — `make check`, `astro check`, whatever the repo defines. Not optional, not "probably fine".
- If figures or layout changed, the page was rendered and inspected in a real browser, both themes, console clean.
- `git status` + `git diff` show **only this task's files**. Unrelated history, scratch files, and other in-flight work stay untouched and unmixed — call them out in the report if they exist.

## The publish decision is the human's

Present the final menu and stop:

- `hold` — leave working tree as-is (default).
- `commit` — commit in the repo's message style; never commit unrelated changes along with it.
- `publish` — commit plus the post's publish step (e.g. `draft: false`); only on explicit word.

## Final report

- What changed, per file, in one line each.
- Verification evidence: test/env results, browser checks, figure list.
- Flagged judgment calls the human may want to revisit.
- Honest gaps: anything unchecked, unverifiable, or left as a follow-up.
