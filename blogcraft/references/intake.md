# Intake

Read when a task starts. Intake pins down everything that varies between runs, so later stages never have to guess — and routes the task to the right entry point.

## Determine the task mode

| Mode | Route |
|---|---|
| **New post** | Full pipeline: Outline → … → Ship |
| **Audit existing** | Review → Ship |
| **Add figures** | Illustrate → Review → Ship |
| **Restructure / local edit** | Outline (scoped) → Draft → Ship |

If the request is ambiguous ("看看这篇文章"), read the target file first, then propose the most likely mode rather than silently choosing one.

## Build the task card

Ask once, up front — never mid-pipeline:

- **Style references** — which published posts set the voice. Default: the most recent episodes in the same series. If none exist, ask for one.
- **Paper / reference sources** — the human supplies a list, or the agent proposes arXiv links for approval, or a mix. Never silently invent a bibliography.
- **Scope limits** — domain boundary and hotness bar (e.g. "LLM mainstream methods only, no niche variants"). Niche topics are proposed explicitly, labeled as such, never smuggled in.
- **Verification environments** — the machines that must run the code (e.g. `ssh mac-studio` for MPS, `ssh laptop` for CUDA). Record actual names; test reachability before Draft.
- **Series position** — episode number, `draft` status, whether the intro links back and the outro previews forward.
- **Authorization mode** — gate density: `stop at every stage` / `outline + ship only` (default) / `autonomous until irreversible`.

## Rules

- Answers already in the prompt are reused, not re-asked.
- Small choices (quote style, one heading's wording) follow convention and are flagged in the final report — never gated.
- Irreversible or high-cost moves (deleting content, restructuring merged sections, changing verification environments, committing, publishing) always ask, regardless of mode.
- Output the card as a short summary table, confirm it, then enter the routed stage.
