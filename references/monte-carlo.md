# Monte Carlo Forecasting

Use Monte Carlo simulation to estimate delivery completion when historical squad data is available.

## Acceptable data

- Completed item cycle times
- Sprint or weekly throughput
- Feature-level delivery durations
- Squad velocity or throughput history

## Method

1. Identify work type and size class.
2. Select comparable historical records.
3. Define remaining work items or estimated work item count.
4. Randomly sample historical throughput or cycle time.
5. Run 5,000 to 10,000 simulations where possible.
6. Report P50, P75, P85, and P95.

## Interpretation

| Percentile | Meaning |
|---|---|
| P50 | Median forecast |
| P75 | Planning forecast |
| P85 | Safer delivery commitment |
| P95 | Conservative forecast |

## Minimum data thresholds

| Data volume | Forecast quality |
|---|---|
| 10-20 comparable completed items | Rough forecast |
| 30+ comparable items | Stronger forecast |
| 6-10 sprints or weeks of throughput | Squad-level forecasting |

## Output requirements

Forecast output must include:

- Method
- Dataset used
- Number of simulations
- Confidence quality
- P50, P75, P85, P95 durations and dates where possible
- Recommended delivery commitment
- Caveats

## Data handling

- Treat historical data as primary evidence
- Identify and exclude outliers where appropriate
- Segment by squad, size, work type, and dependency profile
- Avoid averaging unrelated work
- Do not overstate precision

When data is missing or below minimum thresholds, label the forecast as provisional and recommend the data needed to improve confidence.

## Target date comparison

If the user provides a target date, compare the forecast distribution against it and explain delivery probability where possible. Never present a forecast as a commitment.
