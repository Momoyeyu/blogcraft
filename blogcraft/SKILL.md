---
name: blogcraft
description: A gated pipeline for writing and reviewing technical blog posts. Align on an outline before drafting, keep the series' voice and notation, execute every code block on real environments, illustrate with hand-drawn theme-aware SVGs, and audit facts, consistency, symbols, and code before publishing. Triggers on writing a new post or series episode, outlining, reviewing, or illustrating an article — "write a post", "new episode", "写博客", "新篇", "EP.x", "审查文章", "补配图".
---

# blogcraft

Technical posts fail before the writing: the outline bakes in the wrong structure, code is never run, figures decorate instead of explaining, and notation drifts across a series. blogcraft exists to **gate each decision while it is still cheap to change** — and to keep the human in control of the two calls that matter: **the outline** and **the publish**.

Works with agents that load `SKILL.md`, the blog repository's own toolchain (build, check, dev server), and whatever Python/GPU environments the human names for code verification.

## Intake → Outline → Draft → Verify → Illustrate → Review → Ship

| Stage | Produces | Human decides |
|---|---|---|
| **Intake** | task card: mode, style references, paper sources, scope, authorization mode | everything on the card |
| **Outline** | heading tree with per-section code slots, merge proposals, topic additions | approve / revise each round |
| **Draft** | full prose + code, in the series' voice | — (style deviations only) |
| **Verify** | execution report: every code block, per environment | environment fallbacks |
| **Illustrate** | hand-drawn SVGs placed with narrative glue, theme-checked | figure list, style base, acceptance depth |
| **Review** | audit report + in-place fixes | audit dimensions, fix vs. list-first |
| **Ship** | green project checks, scoped diff | commit / publish (`draft: false`) |

## Stage gates are blocking

Every stage ends by **presenting a choice and stopping** — unless the human picked a looser authorization mode at Intake. At each boundary:

1. Emit the stage deliverable (outline tree, verification report, figure list, audit report).
2. Offer an explicit menu — e.g. "outline: approve / revise", "merge these pairs: which?", "ship: commit / publish / hold" — using the host agent's multiple-choice mechanism when one exists.
3. **Wait.** Do not start the next stage until the human answers.

Hard gates on top of that: nothing is drafted before the outline is approved; nothing is committed or published before the human sees the diff. The authorization mode chosen at Intake sets gate density — "stop at every stage", "outline + ship only" (default), or "autonomous until irreversible" — but the two hard gates always stand.

## Read only what is needed now

| Reference | Load when |
|---|---|
| [Intake](references/intake.md) | Starting any task; routes to the right entry point |
| [Outline](references/outline.md) | Planning or restructuring a post |
| [Draft](references/draft.md) | Writing prose and code |
| [Verify](references/verify.md) | A code block exists or changed |
| [Illustrate](references/illustrate.md) | Planning, drawing, or placing figures |
| [Review](references/review.md) | Auditing a post before publish |
| [Ship](references/ship.md) | Wrapping up; checks, diff, commit, publish |

Do not preload the directory. Follow the current stage only.

## Defaults

- Task modes: **new post** / **audit existing** / **add figures** / **restructure** — non-writing modes skip Draft.
- Answers already supplied are reused, not re-asked. Small choices (quote style, a single heading's wording) are decided by convention and flagged in the final report, never gated.
- Headings are short nouns: no parentheses, no colons; a too-long heading means too much content — split it. `结语` and `参考资料` are fixed names.
- Merge subsections only when two topics share one mechanism; never merge to thin out a table of contents.
- Code lives in a per-section `## 代码实现` next to its concept; a final catch-all section exists only if earlier sections left gaps.
- Every code block runs on the environments named at Intake. "It looks right" is not verification.
- Figures are hand-drawn SVGs matching the site's existing system — CSS variables, `prefers-color-scheme` dual themes, arrows meeting box boundaries. Verified in a running page, light and dark.
- References list: bare links, no parenthetical annotations.
- Project checks (`make check` or the repo's equivalent) are not optional. Commits and `draft` flips need explicit approval.
