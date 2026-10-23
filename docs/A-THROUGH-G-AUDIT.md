# A–G Research Audit and Completion Record

**Status:** IN PROGRESS — original-source recovery and independent verification remain open.

## A — Source recovery and provenance

The current repository contains a manuscript dated 2026-10-23. A historical public post dated 2025-12-15 describes multi-band Dirichlet polynomials, rare exceedances, detector-gated claims, calibration, replication, and a stated non-RH scope. A comment attributed to Hen Tza describes a chart and a deterministic bound on total exceedance duration. The original full manuscript, legible figure equations, figure source/data, and dated original artifacts have not yet been independently recovered. Preserve any recovered original unchanged and record its provenance and checksum.

Historical notes report N=128, T=1000, Q=64, gamma=2, threshold tau=0.35, a sparse-comb-bimodal seed, rotating-bimodal plus tail-noise conditions, and FN%=3.2%. These are historical reports, not independently reproduced findings.

## B — Claim-by-claim mathematical audit

Status labels: **PROVED** means a complete argument follows from stated assumptions; **FINITE-CHECKED** means exhaustive computation on a specified finite domain; **EMPIRICAL** means a measured result under a documented protocol; **CANDIDATE** means an incomplete conjecture; **BLOCKED** means required source, definitions, or proof are missing.

| Claim | Status | Reason / next action |
|---|---|---|
| Derivative and Lipschitz bounds | PROVED | Finite differentiation and triangle inequality. |
| Finite-grid witness lemma | PROVED | Compactness, covering radius, reverse triangle inequality. |
| Numerical grid certificate | CONDITIONAL | Requires a rigorous numerical evaluation-error bound. |
| Exceedance-duration energy inequality | PROVED | Integrate the pointwise indicator inequality. |
| Exact finite-interval energy identity | PROVED | Expand finite sum and integrate termwise. |
| Multi-band union bound | PROVED | Finite subadditivity of measure. |
| Entropy coherence range [0,1] | PROVED | Shannon entropy bounds for Q categories, Q≥2. |
| Universal small exceedance fraction | BLOCKED | Needs an energy estimate relative to tau squared times interval length. |
| Detector-gate inequality with factor 0.05 | BLOCKED / historical claim | Definitions and proof or reproducible experiment missing. |
| 3.2% false-negative rate | HISTORICAL / UNVERIFIED | No independent rerun yet. |
| gamma=2 more robust than gamma=1 | CANDIDATE | Define robustness and test with controls and uncertainty. |
| Entropy beats circular variance on antipodal bimodality | CANDIDATE | Specify distributions, estimators, labels, baselines, loss, uncertainty. |
| Implication for the Riemann Hypothesis | NOT ESTABLISHED | No implication chain is proved here. |

## C — Theory and proof obligations

Let B be a finite set of positive integers and P(t)=sum a_n exp(-it log n). Then P'(t)=-i sum a_n(log n)exp(-it log n), so |P'(t)|≤L=sum |a_n|log n. Thus |P(t)-P(u)|≤L|t-u|. If a finite grid G covers I with radius h and Lh≤epsilon, then sup_I |P|≥tau implies max_G |P|≥tau-epsilon. This is a finite-interval certificate, not an asymptotic theorem.

For E_tau={t in I: |P(t)|≥tau}, pointwise tau² 1_E≤|P|², hence meas(E_tau)≤tau^(-2) integral_I |P|². The inequality alone does not guarantee rarity: to show relative duration at most rho, one must prove integral_I |P|²≤rho tau² |I|.

Expanding the finite product gives integral_I |P(t)|²dt = sum_{m,n} a_m conjugate(a_n) integral_I exp(-it(log m-log n))dt. The diagonal integral is |I|; for m≠n the absolute value of the oscillatory integral is at most 2/|log(m/n)|. This identity is exact, but its triangle-inequality estimate may be too crude to establish a useful uniform bound.

For finitely many bands, meas(union E_j)≤sum meas(E_j), without an independence assumption. For a probability vector p over Q≥2 categories, H(p)=-sum p_j log p_j and kappa=1-H(p)/log Q lie in [0,1]. This bounded statistic is not, by itself, a validated detector.

## D — Reproducibility protocol

Preserve the exact source commit, runtime and dependency versions, operating system, precision, parameters, seeds, data-generation procedure, calibration/test partition, ground-truth rules, baseline detectors, raw machine-readable outputs, summary-generation command, and clean-environment rerun log. Define TP, FP, FN and each denominator. For the reported 3.2% FN rate, state the number of positive cases and whether FN%=FN/(TP+FN); explain label construction and whether threshold tuning used evaluation data. Do not call this result verified until rerun independently.

## E — Adversarial and falsification suite

Test constant and single-frequency polynomials; near-threshold peaks between grid points; cancellation and unequal coefficients; overlapping bands; thresholds near zero and the maximum amplitude; entropy at uniform, point-mass, zero-containing, and near-uniform limits; antipodal bimodal distributions; rotation and tail-noise contamination; detector blind spots; ablation of the bimodality guard; gamma=1 versus gamma=2; sensitivity to seed, sample size, threshold and calibration split; and negative controls without genuine coherence. Use explicit ground-truth labels and baseline methods. Narrow a universal claim if a counterexample defeats it.

## F — Manuscript and release package

The candidate paper should contain abstract, scope, definitions, assumptions, complete proofs, conditional propositions, protocol, reproducible results only, limitations, references, and a proof-status table. Standard mathematical terminology should replace unexplained proprietary vocabulary while retaining explicitly defined AXEZENT components. Required artifacts include the canonical paper, reconstructed candidate, verified-core notes, reproducibility protocol, proof-status ledger, theorem index, certificate specification, experiment source/results, source figures/data, citation metadata, and version history. Do not claim AMS acceptance, endorsement, peer review, or an RH proof without documentary evidence.

## G — Release integrity and repository security

Keep work on research/reconstruct-2025-ams-manuscript and PR #1 until reviewed. Do not merge or publish a release automatically. Inspect changed paths, diffs, commit history, and test results. Enable and verify branch protection or a ruleset, required review and status checks, secret scanning and push protection where supported. Review collaborators, tokens, OAuth/GitHub Apps, and Actions permissions. Never commit credentials, private correspondence, or confidential design details. Record release commit SHA, artifact hashes, test commands, and unresolved items.

## Completion gate

A–G is complete only when source recovery is documented, every claim has an evidence status, experiments can be rerun, adversarial tests are reported, the candidate manuscript builds, and repository settings are verified. Until then this audit remains IN PROGRESS.
