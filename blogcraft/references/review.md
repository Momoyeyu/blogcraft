# Review

Read when auditing a post — standalone ("审查这篇文章") or as the penultimate stage of a new one.

## The four default dimensions

1. **Facts** — attributions, claimed results, what papers actually say. (Caught before: Sandwich-LN credited to the wrong model family.)
2. **Consistency** — formula ↔ code ↔ prose, and post ↔ series. Generic `Norm` in formulas must not become `LN` where the code says `RMSNorm`; helper signatures must match earlier episodes.
3. **Notation** — one symbol, one meaning, post-wide and series-wide; quantifiers and conditions stated (`α > 0`, "无 mask 时").
4. **Code completeness** — no undefined identifiers in fragments, no subtle tensor traps left in (`k.T`), verified state from the Verify report still holds.

The human may add dimensions (SEO, glossary, terminology table) or cut the list — confirm at the start of an explicit audit request; run all four by default.

## Fix vs. list

Default: fix in place and report a diff of what changed and why. Alternative on request: list findings first for human ruling — use this when a fix could change meaning (attribution disputes, contested claims).

## Rules

- Re-read the whole file; audits run on current state, not memory.
- Report honestly: list what was checked and found clean, not just the fixes.
- Flag remaining judgment calls ("可斟酌点") separately from defects — the human may prefer the existing phrasing.
