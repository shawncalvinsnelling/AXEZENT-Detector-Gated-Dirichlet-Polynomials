# Reproducibility Notes

## Purpose

Computational experiments can help detect algebra mistakes, check finite examples, and compare implementations. They do not replace proof of a statement quantified over all sizes or all admissible inputs.

## Required record for every computation

Record:
1. the mathematical statement being tested;
2. exact parameter values and ranges;
3. source code and version;
4. software/runtime versions;
5. numerical precision and rounding policy;
6. expected and actual output;
7. known limitations and possible failure modes.

## Grid verification

For the finite-grid witness lemma, record the polynomial coefficients, index set, interval endpoints, threshold `tau`, tolerance `epsilon`, value of `L`, and grid covering radius `h`. Check `Lh <= epsilon` before using grid values to rule out an exceedance at level `tau`.

A numerical scan without a rigorous derivative bound and covering-radius check is evidence about sampled points only; it is not a certificate for the whole interval.

## Exact arithmetic and floating point

Use exact arithmetic when quantities are rational or algebraic and the tools support it. Otherwise document precision, error bounds, and how numerical uncertainty affects each conclusion.

## Scope discipline

A finite verification supports only the cases actually checked. Never describe a bounded search as proof for all parameters unless a separate mathematical argument closes the remaining cases.
