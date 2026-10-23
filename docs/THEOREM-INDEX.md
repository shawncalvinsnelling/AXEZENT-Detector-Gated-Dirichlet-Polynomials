# Theorem and Dependency Index

This index records current statements and their evidence status.

## DG-001 — Derivative bound

For a finite Dirichlet polynomial `P(t) = sum a_n n^(-it)`, `|P'(t)| <= L`, where `L = sum |a_n| log(n)`. **Status: PROVED.**

## DG-002 — Lipschitz bound

`|P(t)-P(u)| <= L|t-u|`. This follows by integrating the derivative bound. **Status: PROVED.**

## DG-003 — Finite-grid witness

If a grid covers a compact interval with covering radius `h` and `Lh <= epsilon`, then a continuous exceedance of level `tau` implies a grid value at least `tau-epsilon`. **Status: PROVED.** The full argument is in the README.

## DG-004 — Multi-band exceedance estimate

The archived project record describes an unconditional multi-band exceedance bound. The exact theorem, hypotheses, constants, and proof must be checked against the canonical manuscript before this result is stated as proved here. **Status: SOURCE VERIFICATION REQUIRED.**

## DG-005 — Multi-band localization

The archived project record describes a protocol-conditional localization framework. The protocol and exact theorem need to be recovered. **Status: SOURCE VERIFICATION REQUIRED.**

## Scope boundary

No global Riemann Hypothesis result is established by the finite-grid witness lemma. Any broader implication requires a complete separate argument.

## Review procedure

Every additional result should include its exact statement, assumptions, proof location, evidence status, and dependencies. Finite computations must identify their checked ranges. Do not upgrade a claim's status without a checkable argument.
