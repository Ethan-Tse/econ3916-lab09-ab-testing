# econ3916-lab09-ab-testing

# A/B Testing — Designing the Data-Generating Process

## Objective

I tested how the way data is generated (randomized experiment vs. observational comparison) changes what we can conclude about a treatment effect, using the LaLonde NSW job training data and the Cookie Cats A/B test.

## Methodology

- Loaded the LaLonde NSW job training experiment (445 people: 185 trainees and 260 controls) and computed the experimental ATE.
- Simulated an observational comparison group to show selection bias, then split the gap: Observational ATE = True ATE + Selection Bias.
- Ran a permutation test (9,999 shuffles) on the ATE.
- Computed a bootstrap BCa 95% confidence interval for the ATE.
- Ran a power analysis to find the power of this study and the sample size needed for three dollar effects.
- Applied the same tests to the Cookie Cats mobile game A/B test (90,189 players, gate at level 30 or 40, Day-1 retention).
- Wrote a sample-size function, `n_needed()`, checked it against the power analysis, and used it to size a rerun of Cookie Cats.

## Key Findings

**LaLonde NSW**
- Trainees earned $1,794.34 more than controls (permutation p = 0.0046, 95% CI $575.18 to $3,262.37).
- The simulated comparison group gave an ATE of $-14,784.45, so the observational estimate differs from the experimental one by the selection bias.

**Cookie Cats**
- The retention difference between the two gate placements was 0.59 pp (p = 0.0752).
- A rerun would need 111,924 players per group.
