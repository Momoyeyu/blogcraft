# Draft

Read when writing prose and code after outline approval. The target is indistinguishable-from-the-series writing, not merely correct content.

## Voice

Match the designated reference posts before writing a single section — read them for sentence rhythm, transition habits, and how much math vs. prose they carry. Series conventions that have held:

- **Blockquote questions as transitions** — `> **Router 会不会……？**` — a real question, then the answer.
- **Define every symbol before first use**; keep one symbol table coherent across the whole post and across episodes (a `d` that means embedding dim in §2 must not silently become head dim in §6).
- Interleave formula and code — explanation, formula, implementation, in that rhythm.
- Inline links at the point of mention; the reference list at the end stays bare links.
- Backlink earlier episodes; let the outro preview the next one if Intake confirmed it.
- Qualify contested claims with their conditions ("在一定条件下呈现远程衰减") rather than stating the folklore version.
- Paragraphs carry full thoughts — no orphan sentences, no fragment lists where prose belongs.

## Code

- Complete, runnable fragments sitting next to their concept under `## 代码实现`. Trim boilerplate the series already established (imports shared across episodes may be abbreviated once, with a note).
- Call out conventions and traps in prose — pairing conventions, `transpose(-1,-2)` vs `.T`, train/eval state — the things a reader copying the code would trip on.
- Keep cross-episode APIs identical (same helper names, same signatures). If this post genuinely needs a different shape, say why explicitly.
- Detailed over clever: the reader should be able to paste and run.

## Hand off

When the draft covers every approved outline node, run Verify. Do not illustrate yet — figure placement is its own stage with its own gate.
