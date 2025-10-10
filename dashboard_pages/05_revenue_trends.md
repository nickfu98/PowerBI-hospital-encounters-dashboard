[← Page 4](04_readmission_rates.md) | [Page 6 →](06_procedural_insights.md)

# Revenue Trends

![Revenue Trends](dashboard_screenshots/05_revenue_trends.png)

## Purpose
Assess financial performance by year, payer, and procedure.

## Key Visuals
| Visual | What it shows |
|---|---|
| Line: Total Revenue by Year | Revenue trend |
| Column: Avg Revenue/Encounter by Payer | Efficiency by payer |
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
Revenue / Encounter = DIVIDE([Total Revenue], [Total Encounters], 0)
```

## Insights
  - Medicare + Blue Cross Blue Shield dominate revenue; cardiology/radiology drive top procedure revenue.

[← Page 4](04_readmission_rates.md) | [Page 6 →](06_procedural_insights.md)
