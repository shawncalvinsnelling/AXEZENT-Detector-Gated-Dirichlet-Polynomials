# A–Z AXEZENT Research Completion Audit

**Status: IN PROGRESS.** This is the full 26-workstream plan. Completing a checklist means documenting the evidence, not assuming a positive result. Preserve the original research artifacts unchanged and distinguish historical claims from newly verified results.

## A — Archive and provenance
Recover the December 2025 manuscript, dated versions, source files, figures and metadata. Hash recovered files and preserve originals. Current reconstruction is not claimed to be verbatim recovery.

## B — Bibliography and prior art
Verify every citation against primary publications. Identify related analytic number theory, exponential sums, large values, entropy statistics and detector-evaluation work. Do not claim novelty until the literature review supports it.

## C — Definitions and conventions
Define the finite index sets, coefficients, frequency bands, interval, measure, thresholds, event sets, detector outputs, entropy bins, all parameters and all quantifiers. Check notation for collisions and ambiguous uses.

## D — Derivations and proofs
Review every line of every theorem. Check assumptions, edge cases, equality cases, convergence requirements and dependency links. Only mark PROVED where a complete argument is available.

## E — Exceedance and rarity claims
Separate the valid energy-duration inequality from any stronger rarity statement. A relative-duration bound rho requires an estimate of the form integral_I |P|^2 <= rho tau^2 |I|. Prove the actual advertised constants rather than inferring them from the general inequality.

## F — Finite-grid certification
Check grid coverage, mesh radius, derivative bounds and threshold margins. For numerical certificates, include a rigorous bound on floating-point or interval-arithmetic error.

## G — Gate definition and logic
Define K(t), D(t), each event and the conditional denominator. Determine whether the factor 0.05 is a theorem under assumptions or an empirical estimate. Never blur these interpretations.

## H — Harmonic and energy analysis
Verify exact finite-interval correlation integrals and diagonal/off-diagonal terms. Assess whether the available estimates are strong enough for the intended conclusion; a correct but weak bound may not establish rarity.

## I — Independent implementation review
Inspect source code, algorithm definitions, input validation, precision, random number generation, determinism and dependency pinning. Compare implementation behavior against the mathematical specification.

## J — Jitter, mesh and numerical sensitivity
Vary grid placement, resolution, precision and near-threshold cases. Include tests where a peak lies between grid points. Document any numerical uncertainty.

## K — Known edge cases
Test constant and single-frequency polynomials, zero coefficients, cancellation, highly unequal coefficients, empty or degenerate bands where allowed, thresholds near zero and thresholds above the attainable maximum.

## L — Limits and asymptotics
Identify every limit, exchange of limit and sum/integral, uniformity claim and dependence on interval length or band size. Do not infer an asymptotic theorem from a finite calculation.

## M — Multi-band composition
Verify the union-bound statement, overlapping events, dependence between bands, normalization and scaling. State explicitly when independence is unnecessary and where a sharper result would need additional hypotheses.

## N — Null models and negative controls
Construct cases with no intended coherence signal, randomized phases, shuffled labels and other appropriate controls. Measure false alarms as well as missed detections.

## O — Out-of-sample protocol
Separate calibration, validation and final test data. Avoid threshold tuning on the evaluation set. Preserve held-out results and document any exploratory iterations.

## P — Performance metrics
Define TP, FP, TN, FN, precision, recall, false-positive rate, false-negative rate and their denominators. Report sample counts and uncertainty intervals, not percentages alone.

## Q — Quality of entropy coherence
Prove the normalization range for probability vectors. Test sensitivity to binning, sample size, zero cells, smoothing, normalization and distribution shift. A bounded statistic is not automatically a good detector.

## R — Robustness and adversarial testing
Test antipodal bimodality, rotating modes, tail noise, outliers, overlapping bands, adversarial phase choices and the proposed bimodality guard. Compare gamma=1 and gamma=2 under predeclared metrics and controls.

## S — Seeds and statistical reproducibility
Recover the reported seed/configuration, define the generator, publish raw outputs and rerun from a clean environment. For the historical 3.2% false-negative report, recover positive-case counts and truth-label rules before repeating the claim.

## T — Tests and automation
Add unit tests for definitions and boundary cases, regression tests for historical fixtures when recovered, deterministic experiment commands and a clean CI run. Report test counts and failures truthfully.

## U — User-facing documentation
Explain what the framework does and does not establish, how to run experiments, what files are authoritative, how to reproduce tables and figures, and how to report defects. Avoid unsupported superlatives.

## V — Visuals and figure integrity
Recover original chart source/data where possible. Regenerate figures from scripts. Include axes, units, parameters, sample sizes, uncertainty, captions and source hashes. Do not redraw an unreadable screenshot and represent it as original evidence.

## W — Writing and submission readiness
Use standard mathematical terminology, theorem/proof environments, a scope statement, limitations, verified references and a claim-status table. Build the LaTeX source. Submission readiness does not imply acceptance or endorsement by the AMS.

## X — eXternal independent review
Request independent review only with the owner's explicit approval. Prepare a concise reproducibility package and specific questions. Record reviewer comments accurately and do not describe informal feedback as peer review or endorsement.

## Y — Yield, use cases and commercial claims
Identify plausible use cases and benchmark requirements, but separate a research hypothesis from a demonstrated product capability. Do not promise predictable communications behavior or performance gains until validated in the relevant system. Keep private or sensitive design details out of public commits unless expressly approved.

## Z — Zero-trust release and repository security
Keep changes on the draft branch until reviewed. Inspect diff, branch and commit history, collaborators, tokens, GitHub Apps, Actions permissions and third-party actions. Verify branch protection/rulesets, required reviews/checks and secret scanning/push protection in GitHub settings. Documentation alone does not enable settings. Record commit SHA, artifact hashes, tests and remaining blockers. Never merge, publish a release, or contact anyone externally without explicit approval.

## Historical claims currently awaiting verification
A historical post is reported to mention N=128, T=1000, Q=64, gamma=2, tau=0.35, a sparse-comb-bimodal seed, rotating-bimodal plus tail-noise adversarial conditions, and FN%=3.2%. These are historical reports only until the original implementation, label definitions, sample counts and output artifacts are recovered and independently rerun. The reported detector-gate inequality with factor 0.05 is not established by the currently proved finite core.

## Current proved core
For a finite Dirichlet polynomial P(t)=sum_{n in B} a_n exp(-it log n), differentiation gives |P'(t)| <= sum |a_n| log n. This yields a Lipschitz bound and a finite-grid witness lemma. For E_tau={t in I: |P(t)|>=tau}, tau^2 1_{E_tau}<=|P|^2 gives meas(E_tau)<=tau^{-2} integral_I |P|^2. Expanding the finite sum gives the exact finite-interval energy identity, and finite subadditivity gives a multi-band union bound. For a probability vector p on Q>=2 categories, kappa=1-H(p)/log Q lies in [0,1]. These statements do not alone prove universal rare exceedances, the 0.05 gate claim, the 3.2% error rate, or anything about the Riemann Hypothesis.

## Completion rule
A–Z is complete only when each section has artifacts or a documented reason it remains blocked; mathematical claims have proof/evidence labels; experiment outputs are reproducible; manuscript builds pass; the original-source comparison is documented; and the repository's actual protection settings have been checked. Unresolved items must remain visible rather than being silently marked complete.
