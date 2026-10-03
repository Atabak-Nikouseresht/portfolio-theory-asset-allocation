# Portfolio Theory — Asset Allocation and Risk Analysis

**Research question:** How do diversification-based security selection, return frequency, and portfolio-construction assumptions change the reported risk–return characteristics of NYSE and Nasdaq allocations?

A **collaborative academic project by Atabak Nikouseresht and Alessandro Bonfiglio**, submitted as a Portfolio Theory take-home examination at the University of Bologna. This is an **archival, report-only repository**, not an executable research package or a deployable allocation tool.

**Methods covered:** descriptive return statistics, covariance/correlation-based selection, unconstrained and long-only mean–variance optimization, efficient frontiers, global minimum variance (GMV), beta/CAPM Security Market Line analysis, Black–Litterman, and a hybrid combining long-only MV, Black–Litterman, Pure Bayesian, and GMV weights.

> **Read the [errata and evidence limits](ERRATA.md) before interpreting results.** The report contains unresolved GMV discrepancies and portfolio-label/prose inconsistencies. Hybrid out-of-sample superiority is a conjecture, not an independently established result. The original code and input data are not included; no calculations have been reproduced here.

## Report and reading guide

- **[Portfolio Theory report](Portfolio_Theory_Exam-7_260908_112421.pdf)** — 60 pages; cover dated 25 May 2026, academic year 2025–2026, Group 8.
- **[ERRATA.md](ERRATA.md)** — source-page/table evidence, distinctions between separate exercises and actual inconsistencies, and limits on performance claims.

PDF page numbers and printed page numbers coincide throughout this copy. References below identify both by the same number.

| Research component | Report location: PDF / printed pages |
| --- | --- |
| Return distributions, covariance/correlation, security selection and price behavior | 3–8, Q1–Q6 |
| Unconstrained MV, then a separate long-only MV exercise | 8–14, Q7–Q12; Tables 3–4 |
| Long-only efficient frontiers and GMV comparisons | 14–16, Q13–Q14; Tables 5–6 |
| Market-index comparisons, beta estimation and CAPM/SML comparisons | 17–23, Q15–Q19; Tables 7–14 |
| Black–Litterman with an equal-weight prior and specified investor views | 24–29, Q20–Q21; Tables 15–22 |
| Long-only GMV and equal-weight combination of four allocation models | 29–37, Q22–Q24; Tables 23–34 |
| Separate theoretical discussion of long-run risks, recursive preferences, and term structures | 37–58; references on 59–60 |

The report states **1,305 daily observations, 60 monthly observations, 131 NYSE securities, and 80 Nasdaq securities** (PDF / printed p. 3). These are report-stated counts, not independently validated data counts. Q4–Q5 selects ten securities per market by low average absolute correlation, subject to a filter excluding securities with more than 5% missing daily observations (p. 6).

## What the reported comparisons establish — and do not establish

- **Constraints are exercise-specific.** Q7–Q8 allows short selling under full investment; Q9–Q10 adds nonnegative weights. Negative weights in the former are not violations of the latter. The beta section nevertheless mixes a long-only introduction with unconstrained explanatory prose; see [errata item 1](ERRATA.md#1-constraint-context-separate-exercises-but-a-beta-section-label-inconsistency).
- **GMV results cannot be treated as one reconciled set.** NYSE GMV statistics and monthly weights differ across sections without a documented change in sample or settings. The errata records both versions without selecting a corrected result.
- **Hybrid comparisons are descriptive report evidence.** The displayed hybrid Sharpe ratios are below the MV/Pure Bayesian values in each of the four market/frequency comparisons (Tables 29–30 and 33–34). The report does not present a separately identified out-of-sample evaluation establishing hybrid superiority.
- **Daily and monthly figures are frequency-specific.** Per-period Sharpe ratios are not presented here as directly comparable annualized performance measures. Reported allocations, benchmark comparisons, and CAPM differences are not prospective return guarantees or independently verified investment performance.

## Available artifacts and reproducibility

| File | Role |
| --- | --- |
| `Portfolio_Theory_Exam-7_260908_112421.pdf` | Archived collaborative examination report; unchanged by this documentation review |
| `README.md` | Research question, methods, attribution, and evidence boundaries |
| `ERRATA.md` | Documentation-only review of identified inconsistencies and unsupported generalizations |

No original analysis scripts, notebooks, spreadsheets, input price/return data, dependency environment, or independently reproducible run outputs are supplied. Consequently the repository alone cannot reproduce the reported selection, optimized weights, or statistics. This review adds no code, data, empirical recalculation, or new backtest. The analytical derivations in the later part of the report have not received a complete equation-by-equation validation in this review.

## Academic context and attribution

- **Course / institution:** Portfolio Theory, University of Bologna
- **Project:** collaborative take-home examination, 2025–2026
- **Authors:** Atabak Nikouseresht and Alessandro Bonfiglio (report cover, PDF / printed p. 1)
- **Individual contributions:** unseparated; no verified division of analytical or writing responsibilities was found. Public commit history documents report upload and repository documentation/privacy maintenance, not the original division of academic labor. Account ownership is not evidence of sole authorship.

Author contact details on the cover are redacted in the existing public copy; legitimate author attribution is retained. This documentation revision does not modify the PDF or rewrite repository history. The report is supporting academic portfolio evidence, not production engineering evidence or investment advice.
