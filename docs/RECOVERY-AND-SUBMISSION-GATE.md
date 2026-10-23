# Canonical Manuscript Recovery and Submission Gate

**Status:** WORKING PLAN — NOT A MATHEMATICAL RESULT
**Purpose:** Recover and audit the December 2025 multi-band Dirichlet-polynomial manuscript before preparing an AMS submission candidate.
**Owner:** Shawn Calvin Snelling · AXEZENT AI Research

## 1. Non-negotiable rule

Do not reconstruct missing theorem statements, numerical results, or proofs from a social-media summary or a plot. Preserve historical material as historical evidence, then independently restate and verify every mathematical claim. A polished PDF is not evidence of correctness or acceptance.

This document is a recovery plan. It does not assert that the archived multi-band theorem has been recovered, proved, independently reviewed, or accepted.

## 2. Historical evidence to recover

A public post dated 2025-12-15 described a project involving finite and multi-band Dirichlet polynomials; rare or large-value exceedance events; unconditional lemmas and detector-gated bounds; an entropy-coherence statistic written as κ_B(t) = 1 − H_B(t)/log Q; a claimed detector/gate protocol and replication material; calibration, failure envelopes, and replication protocols; and a graphic titled “Graphical Illustration: Unconditional Multi-Band Exceedance Bound — Mathematical Battle — Round 1.”

The post explicitly said the work was not a proof of the Riemann Hypothesis. These details are leads to locate the original source, not substitutes for formal definitions, hypotheses, data, or proofs.

### Recovery checklist

- [ ] Find the original .tex source and every included source file.
- [ ] Find the original PDF and compare its title, date, theorem numbering, and page count with the source.
- [ ] Recover every figure at original resolution and identify its generating script and data.
- [ ] Recover source archives, code, seeds, configurations, logs, and raw test results.
- [ ] Record provenance: original location, file hash, timestamp if available, and source revision.
- [ ] Preserve recovered originals unchanged; work only on copies.
- [ ] If an item cannot be recovered, mark it MISSING rather than inventing a replacement and calling it original.

## 3. Current repository baseline

The current paper/main.tex is version 0.2.0 dated 2026-10-23. It establishes:

- **DG-001 — PROVED:** derivative bound for a finite Dirichlet polynomial.
- **DG-002 — PROVED:** corresponding Lipschitz bound.
- **DG-003 — PROVED:** finite-grid witness lemma under its covering-radius and tolerance assumptions.
- **MF-001 — PROVED:** exact finite sinc-weighted correlation identity for the stated Möbius Fourier-energy expression.

The current manuscript does not establish a general multi-band exceedance estimate, validate detector performance, establish an asymptotic cancellation bound, justify an unproved limit exchange, or prove RH. Do not promote those claims without the missing arguments and evidence.

## 4. Required mathematical specification

Before evaluating the historical detector, create a definitions table that fixes every symbol and quantifier. Recover the exact polynomial(s), coefficients, index sets, band definitions, intervals, measure, thresholds, normalization, exceedance event, definitions of H_B(t), Q, κ_B(t), K(t), and D(t), the detector rule and tuning parameters, and the exact theorem statement with every assumption and dependency.

Define operationally what “rare,” “coherence,” “resonance,” and “multi-band” mean. Classify each result as unconditional, protocol-conditional, empirical, or conjectural. Do not assign a new meaning to a symbol merely because its historical definition is missing.

## 5. Separate theorem claims from experimental claims

Every claim needs a ledger row with: stable ID; exact formal statement and quantifiers; assumptions; proof location; dependencies; evidence status (PROVED, CONDITIONAL, COMPUTATIONALLY CHECKED, CANDIDATE, or OPEN); reproducible test command and parameters; limitations.

The historical example parameters N=128, T=1000, Q=64, gamma=2, seed “sparse-comb-bimodal,” adversary “rotating bimodal + tail noise,” and tau=0.35 are only a reproduction target. The reported FN%=3.2% must not be presented as validated until the exact implementation, labels, sample construction, denominator, and independent rerun are recovered. Report uncertainty and baseline comparisons where appropriate.

The proposed inequality

meas{K(t) ≥ 2, D(t) ≤ τ} ≤ 0.05 · meas{K(t) ≥ 2}

must be classified as a theorem, protocol acceptance criterion, or observed finite-run statistic. Do not conflate these categories.

## 6. Figure integrity

Label each figure as one of: PROOF FIGURE (illustration only, not the proof); COMPUTATIONAL FIGURE (script and data preserved); SCHEMATIC (conceptual, not evidence of a theorem); HISTORICAL UNVERIFIED (recovered from a post or screenshot without source data).

Never use a shaded region, trend line, or caption to imply a deterministic bound unless the exact bound is proved and the plotted quantities match the theorem. Define every axis, unit, threshold, and sample size.

## 7. Finite-grid certificate requirements

For P(t) = sum_{n in B} a_n n^(−it), the derivative bound |P′(t)| ≤ L, where L = sum |a_n| log(n), and grid covering radius h bridge grid samples to a continuous interval only when the conditions are checked. Numerical values need validated evaluation-error bounds; a floating-point scan alone is not a rigorous certificate.

Each certificate must specify the exact polynomial, interval, threshold, tolerance, grid rule, verified covering radius, derivative bound, arithmetic and error model, final inequality, source revision, and hashes. It certifies only that declared finite instance, not a uniform asymptotic result.

## 8. Validation and release gates

### Gate A — Source recovered
Original source, figures, and supporting artifacts inventoried. Unknowns explicitly marked.

### Gate B — Statements normalized
Every theorem and detector rule transcribed exactly and checked against the source.

### Gate C — Proof audit
Check every proof for missing hypotheses, invalid limit exchanges, unjustified uniformity, constants, edge cases, and dependency errors.

### Gate D — Independent reproduction
Run scripts from a clean environment; hash inputs and outputs; independently recompute empirical metrics and compare with stated baselines.

### Gate E — Manuscript build
Build the PDF from source with no missing references, undefined citations, unresolved cross-references, or unexplained generated files. Document a reproducible build command.

### Gate F — Submission review
Check journal scope, formatting, author declarations, references, data/code availability, and submission requirements against the chosen journal's current instructions. Call the paper a submission candidate, not “accepted” or “AMS-approved.”

Do not label the package 10/10 or submission-ready until these gates have evidence attached. A missing historical theorem is a blocker, not a formatting task.

## 9. Manuscript package target

- paper/main.tex — canonical manuscript source;
- paper/references.bib — bibliography;
- paper/figures/ — reproducible figures with source scripts and data;
- experiments/ — fixed configurations, scripts, environment specification, and raw results;
- tests/ — unit tests, regression tests, and independent identity checks;
- certificates/ — machine-readable finite-instance certificates and verifier;
- docs/PROOF-STATUS.md — current evidence ledger;
- docs/THEOREM-INDEX.md — theorem/dependency index;
- docs/REPRODUCIBILITY.md — clean-run instructions;
- docs/RECOVERY-AND-SUBMISSION-GATE.md — this recovery and acceptance plan.

## 10. Scope and integrity statement

This project concerns finite Dirichlet polynomials, detector design, exceedance events, and reproducible mathematical analysis. The finite-grid lemma and finite Möbius identity currently present are valid finite statements under their stated definitions. This plan claims no RH proof, universal exceedance theorem, detector accuracy guarantee, commercial performance, peer review, or journal acceptance.

The intended standard is exact statements, explicit assumptions, checkable proofs, independently reproducible computation, transparent limitations, and no upgrading of evidence status without evidence.