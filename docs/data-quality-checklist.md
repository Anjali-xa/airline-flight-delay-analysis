# Flight Data Quality & KPI Checklist

Use this checklist before publishing any analysis. Record the dataset source, download date, coverage period, licence, and filters in the project report.

## 1. Validate the source
- [ ] Confirm the official source and dataset version.
- [ ] Record the date range, geography, and included carriers/airports.
- [ ] Review licence and redistribution restrictions.
- [ ] Keep an untouched copy of the source data; do not commit restricted raw data.

## 2. Validate fields
- [ ] Confirm flight date and scheduled/actual times parse consistently.
- [ ] Check carrier and airport codes against the source documentation.
- [ ] Check that delay values use the documented unit (normally minutes).
- [ ] Distinguish cancelled, diverted, and completed flights.
- [ ] Check missing values and duplicate flight records.
- [ ] Investigate negative or implausible delay values rather than silently deleting them.

## 3. Define metrics consistently
Document the numerator, denominator, unit, and exclusion rules for every KPI.

| KPI | Suggested definition | Important note |
|---|---|---|
| Average arrival delay | Mean arrival delay among eligible completed flights | State how missing values are handled |
| On-time arrival rate | Eligible flights arriving within the chosen threshold / eligible completed flights | State the threshold |
| Cancellation rate | Cancelled flights / all scheduled flights | Include the reporting period |
| Average departure delay | Mean departure delay among eligible completed flights | Do not mix with arrival delay |
| Delay minutes | Sum of eligible delay minutes | Explain treatment of cancellations |

## 4. Analysis checks
- [ ] Compare airlines only over comparable periods and coverage.
- [ ] Segment airport results by month/season where useful.
- [ ] Check whether a small flight count is driving extreme averages.
- [ ] Show both counts and rates; avoid ranking tiny samples as definitive.
- [ ] Separate correlation and description from causal claims.

## 5. Reproducibility
- [ ] Keep cleaning steps in a notebook or script.
- [ ] Store SQL queries in the `sql/` directory.
- [ ] Include chart titles, units, date ranges, and source notes.
- [ ] Record limitations and any assumptions in the final report.
