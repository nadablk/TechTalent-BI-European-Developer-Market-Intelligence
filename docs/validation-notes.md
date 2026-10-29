# Validation notes before portfolio publication

The supplied ZIP contains a Power BI `.pbix` file and a French PDF report. It does not contain the raw annual survey CSVs or the Python ETL scripts described in the report. The checks below are therefore a review of the report's stated claims and packaged assets, not a rerun of the analysis.

## Items to reconcile

1. **AI adoption figures:** The report's global overview states an overall AI-use rate of 16%, while the AI section describes rates of approximately 50% in 2023 and 80% in 2025. Confirm whether these figures use different definitions, filters, denominators, or time periods. If they do, label them clearly; otherwise correct the discrepancy.
2. **Respondent counts:** The report refers to 248,000 total respondents across all years and approximately 60,000 European respondents after filtering, but also presents some dashboard KPIs as if the total were the Europe-only population. Confirm the report-level region filter and all card measures.
3. **Salary outliers and units:** Verify the source salary columns, whether values are annual or monthly, currency conversion rules, and the handling of extreme and missing values. Document exclusions and the resulting sample sizes.
4. **Year-to-year comparability:** Stack Overflow survey questions and response options may change by year. Confirm the mapping of each source year's columns and ensure percentages use consistent denominators.
5. **Experience buckets:** The report's descriptions of experience ranges overlap in places (for example, 0–1 and 0–2 years). Confirm the intended mutually exclusive bucket definitions.
6. **AI and salary association:** Higher observed salaries among AI-tool users do not establish that AI usage causes higher salaries. State this as an association only, and consider controls for country, experience, role, and year.
7. **Forecasting:** The report states that predictive analysis is still in progress. Do not present 2026–2027 projections as validated forecasts until the model, holdout strategy, uncertainty intervals, and baseline comparisons are documented.
8. **Geographic definition:** The report describes Europe using a selected set of countries. Publish the exact country list and explain whether “Europe” means a geographic region, the EU, or a chosen market subset.

## Recommended QA checklist

- [ ] Recompute all headline KPIs from the same documented filter context.
- [ ] Check distinct respondent counts and possible repeated respondents across survey years.
- [ ] Check nulls, duplicate records, conflicting labels, and salary outliers.
- [ ] Validate relationships and filter direction in the Power BI model.
- [ ] Reconcile each DAX measure against a small independent calculation.
- [ ] Record exact dataset versions, download dates, source URLs, and licenses.
- [ ] Add the ETL scripts and environment details if they are available and permitted for publication.
- [ ] Label results as survey-based estimates, with sample size and limitations.

## Publication guidance

Treat the figures and recommendations in the accompanying report as claims to verify, not independently confirmed facts. Avoid using them as the sole basis for real-world hiring or compensation decisions.
