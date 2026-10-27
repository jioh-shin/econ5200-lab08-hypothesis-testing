# Diagnosing Underpowered Studies and P-Hacking

## Objective
I examined how low statistical power, multiple testing, and p-hacking can affect the reliability of statistical results.

## Methodology
- Calculated the statistical power of a pilot study and estimated the sample size needed to reach 80% power.
- Applied the Benjamini-Hochberg correction to test whether subgroup results remained significant after adjusting for multiple comparisons.
- Simulated repeated hypothesis tests under true null hypotheses to measure the probability of false positives.
- Wrote my own Benjamini-Hochberg function and compared its results with statsmodels.
- Compared four statistical tests on heavy-tailed earnings data to examine how the choice of test statistic affects results.

## Key Findings
- The pilot study had only 10.9% power with 15 people per group. Reaching 80% power required 222 people per group, producing a p-value of 0.0012.
- After applying the Benjamini-Hochberg correction, none of the 20 subgroup results remained significant.
- In 1,000 simulations of 20 true-null tests, 65.8% produced at least one p-value below 0.05, compared with the theoretical probability of 64.2%.
- My Benjamini-Hochberg function matched statsmodels and correctly identified 2 subgroups when two real effects were introduced.
- The four tests on heavy-tailed earnings data produced different results depending on the statistic being tested, rather than whether the test was parametric or permutation-based.

Overall, I found that small sample sizes, multiple testing, and the choice of test statistic can substantially affect statistical conclusions.
