[← Back to README](../README.md) | [Page 2 →](02_patient_volume_trends.md)

# Dashboard Overview (2011–2022)

![Overview](../dashboard_screenshots/01_dashboard_overview.png)

## Purpose
Executive snapshot of operational, clinical, and financial KPIs for Massachusetts General Hospital encounters (2011–2022).

## Key Visuals
| Visual | What it shows |
|---|---|
| KPI cards | Total Encounters, Total Patients, Avg LOS (hrs), Total Revenue, Revenue/Encounter |
| Donut | 30-Day Readmission Rate |
| 100% Stacked Bar | Encounter Class mix by Year |
| Donut | Encounter Volume by Age Group |

## Slicers Used
- Timeline (DateTable[Date]), Year, Insurance Provider, Age Group

## Data Sources
- **Fact/View:** `vw_encounter_details`, `vw_readmissions`  
- **Dimensions:** `DateTable`, `payers`, `patients`

## Key DAX
```DAX
Total Encounters = COUNTROWS('vw_encounter_details')
Avg LOS (hrs)   = AVERAGE('vw_encounter_details'[LOS_Hours])
Total Revenue   = SUM('vw_encounter_details'[payer_coverage])
Revenue / Encounter = DIVIDE([Total Revenue], [Total Encounters], 0)
Readmission Rate % = DIVIDE(SUM('vw_readmissions'[yes_readmit_30d]), COUNTROWS('vw_readmissions'), 0)
```DAX
Total Encounters = COUNTROWS('vw_encounter_details')
Avg LOS (hrs)   = AVERAGE('vw_encounter_details'[LOS_Hours])
Total Revenue   = SUM('vw_encounter_details'[payer_coverage])
Revenue / Encounter = DIVIDE([Total Revenue], [Total Encounters], 0)
Readmission Rate % = DIVIDE(SUM('vw_readmissions'[yes_readmit_30d]), COUNTROWS('vw_readmissions'), 0)
```

## Insights

  - Stable LOS (~7.25 hours) across the period.
  - Readmissions ~62% with higher rates in urgent/inpatient classes.
  - Outpatient + Ambulatory dominate encounter mix.

[← Back to README](../README.md) | [Page 2 →](02_patient_volume_trends.md)
