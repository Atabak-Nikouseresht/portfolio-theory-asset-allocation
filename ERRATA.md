# Errata and evidence limits

This is a documentation-only review of the archived collaborative report by **Atabak Nikouseresht and Alessandro Bonfiglio**. It preserves the report rather than silently correcting its tables. Findings below were checked against the current PDF, including rendered tables on pages 31, 34, and 36; no original analysis was rerun.

**Reviewed artifact:** `Portfolio_Theory_Exam-7_260908_112421.pdf`, 60 pages, SHA-256 `0794ae857c98d2aa9e8ba417629297692843c51b90e921bd545f113cb8d0c943`.

**Page convention:** all locations below specify PDF page / printed page; the two numbers coincide in this copy. Values retain their table's units: percentage returns/volatility in Tables 5–6 and 24–26, decimal returns/standard deviations in the all-model tables, and decimal portfolio weights in weight tables.

## Review outcome

| Question checked independently | Outcome |
| --- | --- |
| Do negative unconstrained weights contradict the long-only exercise? | No: Q7–Q8 and Q9–Q10 are explicitly separate. A narrower label/prose inconsistency exists within Q16–Q17. |
| Do differing GMV results have a documented sample/settings explanation? | No such explanation is supplied; material NYSE statistics and monthly weights remain internally inconsistent. |
| Is a supposedly excluded security shown with nonzero weight? | Yes: Quantum Computing in daily Nasdaq GMV, prose versus Table 25 and corroborating Table 31. |
| Is hybrid out-of-sample superiority established? | No independently established out-of-sample superiority: the report asserts an expectation but provides no separately identified OOS comparison. |

## 1. Constraint context: separate exercises, but a beta-section label inconsistency

### Distinct exercises — not an error

- **Q7–Q8, PDF p. 9 / printed p. 9:** weights sum to one, with no nonnegativity constraint; short selling is explicitly allowed. Figures 5–6 and prose on pp. 9–11 describe unconstrained long/short allocations.
- **Q9–Q10, PDF pp. 11–13 / printed pp. 11–13:** a separate optimization imposes `w_i >= 0` and full investment. Figures 7–8 describe this long-only exercise.
- **Q11–Q12, PDF p. 13 / printed p. 13, Tables 3–4:** daily/monthly unconstrained and long-only statistics are labeled separately.
- **Q18–Q19, PDF pp. 21–23 / printed pp. 21–23, Tables 11–14:** SML tables explicitly concern long-only portfolios. Their differing portfolio betas are not, by themselves, contradictions with an unconstrained exercise.

**Clarification:** do not describe short positions in Q7–Q8 as violations of Q9–Q10. Nor should different results for different constraints or frequencies automatically be labeled numerical errors.

### Actual inconsistency within Q16–Q17

The introduction on **PDF p. 18 / printed p. 18** says the portfolio beta exercise concerns optimized long-only MV portfolios. However:

- **Table 9, p. 18:** NYSE portfolio betas are `0.5930` daily and `−0.2174` monthly. The accompanying explanation on **p. 19** explicitly invokes the unconstrained daily allocation (about 81% Eli Lilly), a negative McCormick weight, and unconstrained monthly short positions.
- **Table 10 and prose, PDF p. 20 / printed p. 20:** Nasdaq portfolio betas are `−0.0189` daily and `3.6393` monthly. The monthly explanation explicitly invokes Q8's extreme unconstrained weights above 1,000%.
- For comparison, the separately labeled long-only SML portfolio betas are NYSE `0.4799` daily / `0.0828` monthly (Tables 11–12, pp. 21–22) and Nasdaq `−0.0066` daily / `0.0239` monthly (Tables 13–14, pp. 22–23).

**Assessment:** the beta section's opening label and its explanatory context conflict. The prose points to an unconstrained context, but without the original weights/return series and calculation code, the portfolio beta entries cannot be independently authenticated or relabeled as a numerical correction.

**Impact — methodological interpretation issue:** the constraint label affects which portfolio the beta explanation describes. The numerical betas are not corrected or relabeled without original calculation evidence.

## 2. GMV statistics and settings: unresolved internal inconsistencies

### Context checked before comparing

Q13–Q14 describes **long-only** frontiers for the selected securities (**PDF pp. 14–16 / printed pp. 14–16**). Q22–Q23 again imposes full investment and nonnegative weights (**pp. 29–30**). Q24 combines a GMV component with the other models (**pp. 32–36**). The report's overall stated sample is 1,305 daily / 60 monthly observations (**p. 3**), and the selected universes contain ten securities per market (**p. 6**).

These are distinct presentation sections, but the report does not identify a different sample window, missing-value treatment, selected universe, covariance estimator, or optimizer configuration that reconciles the following GMV differences. This does not prove identical computational inputs were actually used; it means a changed-input explanation is not documented. Daily versus monthly results and NYSE versus Nasdaq results must remain separate.

### NYSE monthly GMV performance

| Report location (PDF / printed page) | Mean / expected return | Std / volatility | Variance | Sharpe |
| --- | --- | --- | --- | --- |
| Table 6, p. 16 / p. 16, long-only frontier GMV | 0.856% | 3.331% | 0.001109 | 0.207 |
| Table 24, p. 31 / p. 31, standalone GMV statistics | 0.850% | 3.358% | 0.001128 | 0.207 |
| Table 30, p. 34 / p. 34, all-model GMV column (decimal units) | 0.008557 | 0.033305 | 0.001109 | 0.206880 |

Table 30 is consistent with the rounded Table 6 values, but Table 24 differs in mean, volatility, and variance. The volatility and variance differences cannot be explained simply by Table 30 using decimal rather than percentage units. **Unresolved internal inconsistency; no version is chosen as correct.**

### NYSE daily GMV distribution shape

| Statistic | Table 24, PDF p. 31 / printed p. 31 | Table 29 GMV column, PDF p. 34 / printed p. 34 |
| --- | --- | --- |
| Skewness | 0.484 | −0.142259 |
| Excess kurtosis | 4.878 | 2.354323 |

The daily mean, standard deviation, variance, and rounded Sharpe broadly agree between these tables, but the shape statistics do not. The report supplies no estimator/sample explanation for the sign change in skewness or the excess-kurtosis discrepancy. **Unresolved internal inconsistency, not ordinary display rounding.**

### NYSE monthly GMV component weights

**Table 23, PDF p. 30 / printed p. 30** and **Table 28's GMV column, PDF p. 34 / printed p. 34** present different monthly weights for the same named GMV component. Examples in decimal weight units:

| Security | Table 23 monthly GMV | Table 28 monthly GMV |
| --- | --- | --- |
| Kroger | 0.2137 | 0.2527 |
| McCormick & Co | 0.1519 | 0.1194 |
| Eli Lilly | 0.1470 | 0.1193 |

These are not just an additional number of printed decimal places. No changed optimization inputs are documented, so the component weights and their relationship to the differing statistics remain unresolved. The review does not recompute a GMV portfolio or infer which table was used in the actual analysis.

### Nasdaq qualification

**Table 5, PDF p. 15 / printed p. 15** and **Table 26, PDF p. 32 / printed p. 32** agree in displayed daily GMV return, volatility, variance, and Sharpe, and in displayed monthly volatility, variance, and Sharpe. Their monthly mean is `0.206%` versus `0.205%`; **Table 34's GMV mean, p. 36**, is `0.002058` in decimal units. This small display discrepancy is recorded, but a rounding/truncation or precision convention is not supplied, so it is not treated as proof of a materially different Nasdaq run. The NYSE discrepancies above are the substantive unreconciled cases.

**Impact — potentially material to a stated conclusion:** unreconciled GMV statistics and weights limit comparisons involving the GMV component; no replacement numbers or explanation are certified.

## 3. Excluded security versus nonzero daily GMV weight

**PDF p. 31 / printed p. 31**, Q22–Q23 Nasdaq discussion, says Quantum Computing is excluded in the daily dataset but receives a monthly weight. On the same page, **Table 25** gives Quantum Computing a **daily GMV weight of `0.0017`** and monthly weight of `0.0225`. **Table 31, PDF p. 35 / printed p. 35**, repeats daily GMV `0.0017`.

Moreover, every daily security weight displayed in Table 25 is nonzero, contrary to the preceding statement that some daily Nasdaq securities receive no allocation. A small displayed positive weight is not zero. No exclusion tolerance or post-optimization threshold is documented. This is a **prose/table inconsistency**, not a new determination of the true optimized holdings. The zero monthly Oramed and Gilead weights are a separate, consistently documented context.

**Impact — local interpretation issue:** the described daily holdings conflict with the displayed positive weight. The true exclusion policy remains unverifiable without original optimizer settings.

## 4. Hybrid out-of-sample superiority: not established

**Q24, PDF p. 33 / printed p. 33** defines the hybrid as equal-weighted MV, BL, Pure Bayesian, and GMV component weights, normalized for full investment. **PDF p. 37 / printed p. 37**, immediately before Section 14, expresses certainty that the hybrid is likely to have an out-of-sample advantage.

The report does not present separately identified training/test date boundaries, a holdout or walk-forward evaluation, or an OOS performance table for that claim. Reading the report's later theoretical sections does not supply such a test; they address long-run-risk asset-pricing derivations, not a hybrid allocation backtest. The missing code/data also prevent independent reproduction.

The available comparison tables report the following frequency-specific Sharpe values; they are **not labeled OOS results**:

| Market / frequency | Location: PDF / printed page | Hybrid | MV | Pure Bayesian |
| --- | --- | --- | --- | --- |
| NYSE daily | Table 29, p. 34 / p. 34 | 0.066924 | 0.078604 | 0.078604 |
| NYSE monthly | Table 30, p. 34 / p. 34 | 0.338434 | 0.397687 | 0.397674 |
| Nasdaq daily | Table 33, p. 36 / p. 36 | 0.045671 | 0.058346 | 0.058346 |
| Nasdaq monthly | Table 34, p. 36 / p. 36 | 0.162303 | 0.271027 | 0.271021 |

**Interpretation:** hybrid OOS superiority is a conjecture, with **no independently established OOS superiority** in the available evidence. Lower reported Sharpe than MV/Pure Bayesian does not prove future inferiority either. No new backtest or recalculation was performed, and no undocumented split is presumed.

**Impact — potentially material to a stated conclusion:** future superiority must remain a conjecture, not an empirical finding; displayed historical comparisons are not prospective validation.

## 5. Additional directly observed presentation/generalization issues

- **Hybrid volatility, PDF p. 36 / printed p. 36:** prose claims it is below MV for every market/frequency. **Table 34 on the same page** reports Nasdaq monthly Std `0.052789` for Hybrid versus `0.052655` for MV, contradicting the universal statement. The other three displayed comparisons do not rescue that universal claim.
- **GMV Sharpe, same page:** prose says GMV has the lowest Sharpe across all four specifications. **Table 30, PDF p. 34 / printed p. 34**, gives NYSE monthly GMV `0.206880` versus BL `0.163411`; **Table 29** gives daily GMV `0.035789` versus BL `0.035651`. The universal claim is not supported by the tables.
- **Figure 21, PDF p. 34 / printed p. 34:** the caption identifies NYSE daily hybrid weights, but the rendered plot title identifies Nasdaq daily weights and its security labels include ABVC Biopharma, Astrotech, and Gilead Sciences. This is a chart/caption mismatch; no chart replacement is attempted.

## Attribution, provenance, and scope

The cover (**PDF p. 1 / printed p. 1**) identifies both authors. Public default-branch commit history was inspected through the GitHub commits/contributors API and compared with local Git history at base `5afc01ea47635b80e463e4621d5265b0bc5bdbfe`. It records an initial README, PDF upload (`9161083722a51a54cf2f7267793da975ea6c7685`), and later README/privacy maintenance attributed to Atabak Nikouseresht. No inspected record separates original analytical or writing contributions. **Individual academic contributions remain unseparated**; repository ownership and upload authorship are not a division-of-labor record.

This is an archival/report-only project with no supplied original code or data. This review changes documentation only, does not edit the PDF or rewrite history, and is not a complete validation of every equation, citation, statistic, or economic explanation in the report. No external method reference is needed to establish these internal source conflicts. Resolving numerical discrepancies requires the original calculation materials and documented sample/estimator/constraint settings, not an editorial choice of the more plausible number.
