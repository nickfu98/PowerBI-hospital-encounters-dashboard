[← Page 4](04_readmission_rates.md) | [Page 6 →](06_procedural_insights.md)


![Revenue Trends](dashboard_screenshots/05_revenue_trends.png)


## Purpose
Assess financial performance by year, insurance provider, and procedure.

## Key Visuals
| Visual | What it shows |
|---|---|
| Line: Total Revenue by Year | Revenue trend |
| Column: Average Revenue/Encounter by Payer | Efficiency by payer |
| Column: Total Revenue by Payer | Payer contribution |
| Bar: Top 10 Procedures by Revenue | High-value services |

## Slicers Used
- Timeline, Year, Insurance Provider, Age Group

## Data Sources
- **Fact/View:** `vw_encounter_details`
- **Dimensions:** `DateTable`, `payers`, `procedures`

## Key DAX
```DAX
Total Revenue = SUM('vw_encounter_details'[payer_coverage])
Average Revenue / Encounter = DIVIDE([Total Revenue], [Total Encounters], 0)
```

## Insights
  - Medicare + Blue Cross Blue Shield dominate average revenue per encounter whereas Medicare + Medicaid dominate total revenue.
  - Cardiology and depression/mental health care drives top procedure revenue.
  - Yearly revenue is consistently $2M+ with a spike to $3.5M in 2014.
  - **NOTE:**

[← Page 4](04_readmission_rates.md) | [Page 6 →](06_procedural_insights.md)
