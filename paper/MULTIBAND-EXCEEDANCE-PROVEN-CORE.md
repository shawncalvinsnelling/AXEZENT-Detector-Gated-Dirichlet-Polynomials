# Multi-Band Exceedance: Proven Core and Conditional Extensions

**Status:** Research note; finite lemmas below are proved. No claim is made that this recovers the missing December 2025 manuscript verbatim.

## Abstract

We record two rigorous tools for finite Dirichlet polynomials: (i) a finite-grid witness principle from a derivative bound, and (ii) a deterministic upper bound for the measure (duration) of threshold exceedance obtained from the integral of squared magnitude. We also specify a normalized entropy-coherence statistic and state the assumptions needed for its range bound. These facts form a reproducible baseline for a multi-band detector framework. They do not imply that exceedance is universally rare: that conclusion requires an energy bound small relative to the threshold and interval, plus the exact model-specific hypotheses.

## 1. Definitions

Let I = [T0,T1] be a compact interval of length |I| = T1−T0. Let

P(t) = Σ_{n∈B} a_n n^(−it),

where B is a finite subset of positive integers and a_n are complex numbers. For τ>0 define the exceedance set

E_τ(P;I) = {t∈I : |P(t)| ≥ τ}.

Write meas(E) for Lebesgue measure. All statements below concern the specified finite polynomial and interval unless additional uniform hypotheses are stated.

## 2. Lemma A — derivative and grid witness

Set L = Σ_{n∈B} |a_n| log n. Then |P′(t)|≤L and |P(t)−P(u)|≤L|t−u|.

**Proof.** Termwise differentiation is valid for the finite sum and gives P′(t)=−iΣ a_n(log n)n^(−it). Since |n^(−it)|=1, the triangle inequality gives |P′(t)|≤L. Integrating the derivative along the segment from u to t proves the Lipschitz bound.

Suppose G⊂I is a finite grid with covering radius h, meaning each t∈I is within distance h of some g∈G. If Lh≤ε, where 0<ε<τ, then

sup_{t∈I}|P(t)| ≥ τ  ⇒  max_{g∈G}|P(g)| ≥ τ−ε.

**Proof.** Compactness and continuity give t* attaining the maximum. Choose g∈G with |t*−g|≤h. Then |P(g)|≥|P(t*)|−|P(t*)−P(g)|≥τ−Lh≥τ−ε. ∎

**Use.** This lemma converts a continuous exceedance into a finite-grid witness. It does not bound how much total time the polynomial exceeds the threshold.

## 3. Lemma B — deterministic exceedance-duration bound

**Theorem (energy bound for exceedance duration).** For any measurable complex-valued function P on I with finite integral of |P|² and any τ>0,

meas(E_τ(P;I)) ≤ (1/τ²) ∫_I |P(t)|² dt.

**Proof.** On E_τ, |P(t)|²≥τ². Therefore τ²·1_{E_τ}(t)≤|P(t)|² for every t∈I. Integrating gives τ² meas(E_τ)≤∫_I |P(t)|²dt. Divide by τ². ∎

This is a deterministic inequality, not a probabilistic claim. It yields a useful “rare exceedance” conclusion only when the available energy estimate makes the right-hand side small compared with |I|. In particular, the bound may be trivial if the energy is large; no universal rarity is implied.

### 3.1 Exact finite-polynomial energy formula

For the finite Dirichlet polynomial above, termwise expansion and integration give

∫_{T0}^{T1}|P(t)|²dt = Σ_{m,n∈B} a_m conjugate(a_n) J_{m,n},

where J_{m,n}=T1−T0 if m=n, and otherwise

J_{m,n} = [exp(−i(T1)(log m−log n)) − exp(−i(T0)(log m−log n))] / [−i(log m−log n)].

Equivalently, the off-diagonal integral has absolute value at most 2/|log(m/n)|. Thus a valid, sometimes crude, explicit upper bound is

∫_I |P(t)|²dt ≤ |I| Σ_{n∈B}|a_n|² + Σ_{m,n∈B, m≠n} 2|a_m||a_n|/|log(m/n)|.

Combining this with the theorem gives a fully deterministic finite-instance upper bound for exceedance duration. Better bounds require cancellation or structural information about the coefficients; they must be proved separately.

**Proof of the formula.** Expand |P(t)|² as the finite double sum Σ a_m conjugate(a_n) exp(−it(log m−log n)) and integrate each term. The diagonal integral is |I|; the off-diagonal antiderivative gives the displayed expression. Taking absolute values of the off-diagonal integrals yields the stated inequality. ∎

## 4. Multi-band corollary

Let P_1,…,P_r be measurable functions on the same interval I, with thresholds τ_j>0 and exceedance sets E_j={t∈I:|P_j(t)|≥τ_j}. By the union bound for measure and Lemma B,

meas(⋃_{j=1}^r E_j) ≤ Σ_{j=1}^r meas(E_j) ≤ Σ_{j=1}^r τ_j^(−2) ∫_I |P_j(t)|²dt.

**Proof.** Subadditivity of Lebesgue measure gives meas(⋃E_j)≤Σmeas(E_j). Apply Lemma B separately to each P_j and sum. ∎

This is an unconditional finite-family inequality. It does not establish that the right-hand side is small, that bands are independent, or that detector-gated events satisfy a sharper percentage bound. Those conclusions require additional assumptions or data.

## 5. Entropy-coherence statistic

Let p=(p_1,…,p_Q) be a probability vector, with Q≥2 and p_j≥0, Σp_j=1. Define Shannon entropy H(p)=−Σ_{j:p_j>0} p_j log p_j and normalized entropy coherence

κ(p)=1−H(p)/log Q.

**Lemma.** 0≤κ(p)≤1.

**Proof.** Shannon entropy satisfies 0≤H(p)≤log Q for a probability vector on Q outcomes. Dividing by log Q>0 and subtracting from 1 yields the result. Equality κ=1 occurs for a point mass; equality κ=0 occurs for the uniform distribution. ∎

This range lemma alone does not show that κ detects resonance, predicts exceedance, or improves on another statistic. To substantiate such claims, specify how p(t) is constructed from the signal, how zero/empty bins are handled, how thresholds are chosen, and what ground-truth label defines a successful detection.

## 6. Detector performance is an empirical claim unless proved

A claimed false-negative rate must be tied to a fixed test population, precise positive/negative labels, sample-generation procedure, detector version, threshold, denominator, and reproducible random seeds. Report the numerator and denominator as well as the percentage. Compare with at least a simple baseline and an appropriate alternative detector. If tests are synthetic, say so; do not generalize to real communication systems without validation on representative data.

Any previously reported example configuration (N=128, T=1000, Q=64, γ=2, seed “sparse-comb-bimodal”, τ=0.35, or FN%=3.2%) is a reproduction target only until the exact implementation and underlying run are recovered and independently rerun.

## 7. What is and is not proved

- **PROVED:** derivative/Lipschitz bound and finite-grid witness lemma.
- **PROVED:** energy/measure inequality for threshold exceedance.
- **PROVED:** exact finite-polynomial integral formula and its triangle-inequality upper bound.
- **PROVED:** finite-family multi-band union bound.
- **PROVED:** normalized Shannon entropy coherence lies in [0,1] under the probability-vector definition.
- **NOT PROVED HERE:** that exceedance is always rare; that a specific detector has a given false-negative rate; that coherence is a causal mechanism; that the historical December 2025 theorem is recovered; any asymptotic theorem uniform in polynomial length or interval; any implication proving the Riemann Hypothesis.

## 8. Research path to a stronger theorem

To obtain a genuinely sharper multi-band result, the next task is to prove a model-specific estimate for the sum of energies or correlations that is substantially smaller than the trivial bound. The proof must state dependence on interval length, band locations, coefficients, thresholds, and any normalization. If the intended theorem is a deterministic duration limit, the exact set whose measure is bounded and the exact constant must be stated. If the bound is conditional on a detector gate, include the gate's hypotheses and prove the implication.

Do not infer the missing limit theorem from a plot or a comment. Recover the historical statement if possible; otherwise label any newly derived statement as new work and document the difference.

## 9. Scope statement

This note establishes elementary but useful finite-instance bounds. It is a sound foundation for reproducible detector research, not a proof of the Riemann Hypothesis and not, without further estimates, a universal theorem that extreme events cannot persist. A professional submission should include this scope statement or an equivalent one.