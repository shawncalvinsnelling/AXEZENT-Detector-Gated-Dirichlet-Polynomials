# Mathematical Proof Status

This page records what is established in the current repository and what must not be inferred.

## Status labels

- **PROVED:** a complete argument is written and its assumptions are explicit.
- **CONDITIONAL:** follows only when stated additional hypotheses or protocol requirements hold.
- **COMPUTATIONALLY CHECKED:** finite computation was run; this is not a universal theorem.
- **CANDIDATE:** a proposed statement or proof route still requires verification.
- **OPEN / NOT ESTABLISHED:** the required proof has not been supplied.

## Current proved statement

### Finite-grid witness lemma — PROVED

For a finite Dirichlet polynomial `P(t) = sum a_n n^(-it)`, define `L = sum |a_n| log(n)`. Then `|P'(t)| <= L` and `|P(t)-P(u)| <= L|t-u|`. If a finite grid covers a bounded interval with covering radius `h` satisfying `Lh <= epsilon`, then any exceedance `sup_I |P| >= tau` produces a grid witness of size at least `tau-epsilon`.

The proof is included in the README. The covering-radius condition matters: the word “mesh” should be defined carefully. A grid including both endpoints and with maximum adjacent spacing `delta` has covering radius at most `delta/2`.

## Not established by this lemma

This lemma does not prove:
- a uniform large-value or exceedance estimate as polynomial length or interval size grows;
- a multi-band resonance theorem without precise definitions and hypotheses;
- an all-scale cancellation estimate for arithmetic coefficients;
- the Riemann Hypothesis.

## Canonical manuscript audit required

Before adding further results as proved, compare the original manuscript and source files and record:
1. the exact theorem statement and all quantifiers;
2. every hypothesis on coefficients, bands, thresholds, and intervals;
3. the proof of each estimate and every constant;
4. which steps are unconditional and which depend on a protocol;
5. computational checks and their finite ranges;
6. the exact source version and its checksum.

Do not reconstruct missing theorem statements from summaries or label an unverified claim as proved.
