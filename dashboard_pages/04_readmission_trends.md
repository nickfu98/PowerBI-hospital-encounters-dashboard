[← Page 3](03_length_of_stay.md) | [Page 5 →](05_revenue_trends.md)

![Readmission Trends](dashboard_screenshots/04_readmission_trends.png)


## Purpose
Track 30-day readmission performance across insurance payer, encounter class, and age group.

## Key Visuals
| Visual | What it shows |
|---|---|
| Line: Readmission Rate by Year | Quality trend over time |
| Bar: Readmission Rate by Encounter Class | Where readmits concentrate |
| Bar: Readmission Rate by Insurance Provider | Payer differences |
| Column: Readmission Rate by Age Group | Demographic risk |

## Slicers Used
- Timeline, Year, Insurance Provider, Age Group

## Data Sources
- **View:** `vw_readmissions`
- **Dimensions:** `DateTable`, `payers`, `patients`

## Key DAX
```DAX
Readmission Rate % = 
  VAR Readmits =
      SUM('vw_readmissions'[yes_readmit_30d])
  VAR TotalEncounters =
      COUNT('vw_readmissions'[encounter_id])
  RETURN
  DIVIDE(Readmits, TotalEncounters, 0)
```

## Insights
  - Urgent care & inpatient classes show highest readmit rates; all encounter classes have 50%+ readmission rates except for Wellness (21.3%).
  - Elderly patients (70+) trend higher, while younger patients (<30-39) also readmit at higher rates than middle aged patients (40-69).

[← Page 3](03_length_of_stay.md) | [Page 5 →](05_revenue_trends.md)
