[← Page 3](03_length_of_stay.md) | [Page 5 →](05_revenue_trends.md)

# Readmission (30-Day) Trends

![Readmission Trends](dashboard_screenshots/04_readmission_rates.png)

## Purpose
Track 30-day readmission performance across payer, class, and age.

## Key Visuals
| Visual | What it shows |
|---|---|
| Line: Readmission Rate by Year | Quality trend over time |
| Bar: By Encounter Class | Where readmits concentrate |
| Bar: By Insurance Provider | Payer differences |
| Column: By Age Group | Demographic risk |

## Slicers Used
- Timeline, Year, Insurance Provider, Age Group

## Data Sources
- **View:** `vw_readmissions`
- **Dimensions:** `DateTable`, `payers`, `patients`

## Key DAX
```DAX
Readmission Rate % =
DIVIDE(SUM('vw_readmissions'[yes_readmit_30d]), COUNTROWS('vw_readmissions'), 0)
```

## Insights
  - Urgent care & inpatient classes show highest readmit rates; elderly cohorts (70+) trend higher.

[← Page 3](03_length_of_stay.md) | [Page 5 →](05_revenue_trends.md)
