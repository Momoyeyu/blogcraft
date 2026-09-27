# Verify

Read whenever a code block exists or changed. **Every block runs for real** — reading code and finding it plausible is not verification.

## Environments

Run on the machines named at Intake (e.g. `ssh mac-studio` for MPS, `ssh laptop` for CUDA). Probe reachability early; if an environment is unavailable — missing torch, driver mismatch, host down — stop and offer fallbacks (`local CPU only` / `smoke only` / `defer`), don't silently downgrade coverage.

## Coverage

- **Diff against ground truth** where one exists: `allclose` against `nn.*` equivalents, including eval-mode and running-stat paths, not just the forward happy path.
- **Assert the claimed property**, not just that code runs — e.g. RoPE's inner product depending only on `m−n`, permutation equivariance of attention, std growth tracking √n.
- **Exercise edge cases**: masks, dtype (bf16/fp32), empty tails, >2D tensors.
- Typical traps, worth a targeted assert each: interleaved vs. half-split pairing, `k.T` reversing all axes on >2D tensors, train/eval divergence, unpadded batch statistics leaking through padding tokens.

## Report

Emit a verification table — block, claim tested, environment, result — and fix failures in the draft, then re-run. The report is a stage deliverable shown at the next gate; "15/15 on MPS + CUDA" with a list beats a paragraph of reassurance.
