# Detector-Gated Bounds for Multi-Band Dirichlet Polynomials

**Shawn Calvin Snelling · AXEZENT AI Research**

Research on finite Dirichlet polynomials, detector-gated exceedance estimates, finite-grid witnesses, and reproducible mathematical verification.

## Mathematical setting

A finite Dirichlet polynomial is

`P(t) = sum_{n in B} a_n n^(-it)`,

where `B` is a finite set and the coefficients are complex numbers. Its derivative satisfies

`|P'(t)| <= L`, where `L = sum_{n in B} |a_n| log(n)`.

Therefore `|P(t)-P(u)| <= L|t-u|` for all real `t,u`.

## Finite-grid witness lemma

Let `I=[T0,T1]`, let `tau > 0`, and choose `0 < epsilon < tau`. Suppose a finite grid `G` covers `I` with covering radius at most `h`, and `Lh <= epsilon`. Then

`sup_{t in I} |P(t)| >= tau` implies `max_{g in G} |P(g)| >= tau-epsilon`.

**Proof.** Since `P` is continuous and `I` is compact, choose a point `t*` attaining the maximum. Select `g` in the grid with `|t*-g| <= h`. The reverse triangle inequality gives `|P(g)| >= |P(t*)| - |P(t*)-P(g)| >= tau - Lh >= tau-epsilon`. Thus the claim follows.

## Research scope

This lemma provides a finite-grid witness under an explicit derivative bound. It does not by itself establish a global large-value estimate, an all-scale cancellation bound, or the Riemann Hypothesis.

The archived full manuscript's exact theorem statements, hypotheses, constants, and proofs must be checked against the canonical source before additional results are presented as proved. This repository distinguishes proved statements, conditional claims, finite computations, candidates, and open obligations.

## Repository map

- `docs/PROOF-STATUS.md` — proof labels and limitations
- `docs/THEOREM-INDEX.md` — theorem statements and dependencies
- `docs/REPRODUCIBILITY.md` — standards for computational checks
- `assets/axezent-symbol.svg` — project symbol
- `CITATION.cff` — citation metadata

## Citation

Snelling, Shawn Calvin. *Detector-Gated Bounds for Multi-Band Dirichlet Polynomials*. AXEZENT AI Research, research manuscript, December 2025. Canonical manuscript version to be verified against the archived source.
