# Illustrate

Read when planning, drawing, or placing figures. Figures are **load-bearing** — they go where prose cannot carry the concept, never as decoration.

## Where a figure earns its place

Structure comparisons (Pre-Norm vs. Post-Norm wiring), dataflows (Q/K pipelines), statistical regions (which dims a norm reduces over), curves (residual-stream std growth). A paragraph that already explains itself does not get a figure.

Propose the list as `{file, section, what it shows}` and let the human approve or hand over their own list — along with the style base and acceptance depth (both themes / light only / self-review).

## Style base

Default: the site's existing figure system — hand-authored SVG, draw.io-like academic composition, CSS variables only (no hardcoded colors), `prefers-color-scheme` light + dark, Helvetica-family labels with Times-italic math, arrows meeting element boundaries, aligned baselines. Reuse the variable names from existing figures (`--fg`, `--line`, `--accent`, …). A new style base needs one sample figure approved before the rest are drawn.

Subagents may draw in parallel; the orchestrating agent owns semantic correctness, placement, and the narrative glue — every figure is introduced by the sentence before it and picked up by the sentence after.

## Validate, don't trust geometry

1. XML parses; viewBox margins sane; arrow endpoints land on boundaries.
2. Serve the real page (dev server), confirm each `<img>` renders at its authored aspect ratio.
3. Screenshot **both themes**; check label legibility, clipping, overlapping text.
4. Console clean; then run the project's check suite.
