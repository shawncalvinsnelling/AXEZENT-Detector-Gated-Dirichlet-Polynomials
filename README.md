# Detector-Gated Bounds for Multi-Band Dirichlet Polynomials

<div align="center">

<img src="assets/axezent-symbol.svg" alt="AXEZENT mathematical gate symbol" width="120" />

**Shawn Calvin Snelling · AXEZENT AI Research**

*Finite Dirichlet polynomials · exceedance estimates · grid witnesses · reproducible mathematics*

[Project symbol](assets/axezent-symbol.svg) · [Documentation](docs/index.md) · [Proof status](docs/PROOF-STATUS.md) · [Theorem index](docs/THEOREM-INDEX.md) · [Reproducibility](docs/REPRODUCIBILITY.md)

</div>

---

## Overview

This repository organizes research on detector-gated estimates for finite Dirichlet polynomials and methods for identifying large-value events across bounded intervals and multiple bands.

The goal is to make the mathematics inspectable: state assumptions explicitly, separate unconditional statements from protocol-dependent procedures, preserve proof dependencies, and make computational checks reproducible.

## Mathematical setting

A finite Dirichlet polynomial has the form

`P(t) = sum_{n in B} a_n n^(-it)`,

where `B` is a finite set of positive integers and `a_n` are complex coefficients. Its derivative satisfies

`|P'(t)| <= L`, where `L = sum_{n in B} |a_n| log(n)`.

Therefore `|P(t)-P(u)| <= L|t-u|` for all real `t,u`.

## Finite-grid witness lemma

Let `I=[T0,T1]`, let `tau > 0`, and choose `0 < epsilon < tau`. Suppose a finite grid `G` covers `I` with covering radius at most `h`, and `Lh <= epsilon`. Then

`sup_{t in I} |P(t)| >= tau` implies `max_{g in G} |P(g)| >= tau-epsilon`.

**Proof.** Since `P` is continuous and `I` is compact, choose a point `t*` attaining the maximum. Select `g` in the grid with `|t*-g| <= h`. The reverse triangle inequality gives `|P(g)| >= |P(t*)| - |P(t*)-P(g)| >= tau - Lh >= tau-epsilon`. Thus the claim follows.

## Research organization

- **Mathematical statements:** definitions, hypotheses, and exact theorem formulations.
- **Proof status:** proved lemmas are distinguished from conditional claims, computational observations, and open obligations.
- **Reproducibility:** numerical checks must document parameters, precision, code, and outputs.
- **Research connections:** any application to a broader conjecture requires its own explicit implication chain.

## Status and scope

The finite-grid witness lemma above is an elementary consequence of the derivative bound and is proved here. It does not, by itself, establish a global bound for Dirichlet polynomials or settle any broader conjecture.

The archived full manuscript and its original theorem statements must be checked against the source version before additional results are represented as part of the canonical paper. No theorem, numerical result, or external review status is inferred merely from a project title or draft correspondence.

## Repository map

| Path | Purpose |
|---|---|
| `docs/index.md` | Research documentation landing page |
| `docs/PROOF-STATUS.md` | Evidence labels and current mathematical boundaries |
| `docs/THEOREM-INDEX.md` | Index of statements and dependencies |
| `docs/REPRODUCIBILITY.md` | Standards for computational checks |
| `assets/axezent-symbol.svg` | Project symbol |
| `CITATION.cff` | Citation metadata |
| `CONTRIBUTING.md` | Standards for corrections and new results |

## Corrections

Corrections should identify the exact statement, the assumptions used, and the proof or counterexample supporting the change. Do not upgrade a claim's status without a checkable argument.

## Citation

Snelling, Shawn Calvin. *Detector-Gated Bounds for Multi-Band Dirichlet Polynomials*. AXEZENT AI Research, research manuscript, December 2025. Canonical manuscript version to be verified against the archived source.

---

<div align="center">

**AXEZENT AI Research** · Exact statements. Explicit assumptions. Reproducible checks.

</div>
