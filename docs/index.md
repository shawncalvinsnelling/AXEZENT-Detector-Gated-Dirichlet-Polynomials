# Detector-Gated Dirichlet Polynomial Research

<div align="center">

## ∿ ┃ ⊙ ┃ ∿

**AXEZENT AI Research**

Finite polynomials. Explicit thresholds. Checkable witnesses.

</div>

## Start here

1. Read the [project overview](../README.md).
2. Review the [proof-status ledger](PROOF-STATUS.md) before relying on any claim.
3. Consult the [theorem index](THEOREM-INDEX.md) for the current statement inventory.
4. Follow the [reproducibility notes](REPRODUCIBILITY.md) before treating a numerical scan as a certificate.

## Central idea

For a finite Dirichlet polynomial
`P(t) = sum a_n n^(-it)`,
the derivative bound
`|P'(t)| <= sum |a_n| log(n) = L`
implies a Lipschitz estimate. If a finite grid covers an interval with radius `h` and `Lh <= epsilon`, any continuous exceedance of threshold `tau` has a grid witness at least `tau-epsilon`.

This is a finite-interval statement. It does not, on its own, provide a uniform estimate as the polynomial or interval grows.

## Standards used here

- State every hypothesis and quantifier.
- Identify which claims are unconditional and which depend on a protocol.
- Keep computations tied to their finite tested ranges.
- Keep unresolved implications visibly unresolved.
- Preserve the source version for every theorem added from the archived manuscript.

## Current repository boundary

The elementary finite-grid witness lemma is written out and proved in the README. The original multi-band theorem statements still need to be reconciled with the canonical manuscript before they are added as proved results.
