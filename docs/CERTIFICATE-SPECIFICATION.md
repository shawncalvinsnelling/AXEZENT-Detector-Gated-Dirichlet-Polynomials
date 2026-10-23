# Finite-grid certificate specification

This specification is an implementation contract, not a claim that a C++ program has already produced a valid certificate.

## Mathematical input

For a finite Dirichlet polynomial
\[
P(t)=\sum_{n\in B}a_n n^{-it},
\qquad L=\sum_{n\in B}|a_n|\log n,
\]
choose a compact interval \(I=[T_0,T_1]\), a threshold \(\tau>0\), a tolerance \(0<\varepsilon<\tau\), and a finite grid \(G\subset I\) with verified covering radius \(h\). Require \(Lh\le\varepsilon\).

### Uniform grid with both endpoints

For \(M\ge1\), use
\[
g_j=T_0+j\Delta,\quad j=0,\ldots,M,\qquad
\Delta=(T_1-T_0)/M.
\]
This grid includes both endpoints and has covering radius at most \(h=\Delta/2\). It is sufficient to choose
\[
M\ge \frac{L(T_1-T_0)}{2\varepsilon}
\]
and then round \(M\) upward to a positive integer. If \(L=0\), the polynomial is constant. The implementation must still verify the generated grid and interval endpoints.

If a worker certifies at each grid point an enclosure \(|P(g_j)|\le U_j\), where the enclosure rigorously includes all evaluation error, then the whole interval is certified below threshold \(\tau\) if
\[
\max_j U_j+Lh<\tau.
\]
For the witness formulation, a true continuous exceedance \(\sup_I|P|\ge\tau\) forces at least one grid point to satisfy \(|P(g_j)|\ge\tau-\varepsilon\).

## Required fields in a certificate record

- schema_version
- polynomial_definition and exact index/coefficient encoding
- interval: exact representations of T0 and T1
- threshold_tau, tolerance_epsilon
- derivative_bound_L and the method used to prove it is an upper bound
- grid_rule, grid_count, and verified covering_radius_h
- evaluation_method, arithmetic type, precision, rounding mode
- rigorous per-point error/enclosure data or a reference to a checkable proof of it
- max_upper_bound, L_times_h, and the checked strict inequality
- source revision, compiler version, build flags, and SHA-256 digests of inputs, executable, and outputs

## Acceptance rules

1. Reject missing fields, NaNs, infinities, malformed coefficient records, and grid points outside the interval.
2. Recompute or independently verify L, the grid covering radius, and the final inequality.
3. Do not accept ordinary floating-point values as rigorous enclosures unless a validated error bound is provided.
4. A certificate covers only its declared polynomial and interval. It does not imply an estimate for larger intervals, longer polynomials, or N tending to infinity.
5. A certificate for a function of the form sum mu(n) exp(2 pi i n u/N)/sqrt(N) must state that function and its derivative bound explicitly; do not silently identify it with sum a_n n^(-it).

## Möbius Fourier-energy identity

The exact identity in paper/main.tex can be checked independently by expanding the finite square and grouping terms by the difference of indices. This check verifies a finite algebraic identity only. It does not certify asymptotic cancellation of the correlation sum.
