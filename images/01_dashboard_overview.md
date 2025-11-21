[← Back to README](../README.md) | [Page 2 →](02_patient_volume_trends.md)


![Overview](dashboard_screenshots/01_dashboard_overview.png)


## Purpose
Executive snapshot of operational, clinical, and financial KPIs for Massachusetts General Hospital encounters (2011–2022).

## Key Visuals
| Visual | What it shows |
|---|---|
| KPI cards | Total Encounters, Total Patients, Avg LOS (hrs), Total Revenue, Revenue/Encounter |
| Donut | 30-Day Readmission Rate |
| 100% Stacked Bar | Yearly Encounter Class Mix |
| Donut | Encounter Volume by Age Group |

## Slicers Used
- Timeline (DateTable[Date]), Year, Insurance Provider, Age Group

## Data Sources
- **Fact/View:** `vw_encounter_details`, `vw_readmissions`  
- **Dimensions:** `DateTable`, `payers`, `patients`

## Key DAX
```DAX
Total Encounters = DISTINCTCOUNT(vw_encounter_details[encounter_id])
Avg LOS (hrs) = AVERAGE('vw_encounter_details'[LOS_Hours])
Total Revenue = SUM('vw_encounter_details'[payer_coverage])
Revenue / Encounter = DIVIDE([Total Revenue], [Total Encounters], 0)
Readmission Rate % =
    VAR Readmits =
        SUM('vw_readmissions'[yes_readmit_30d])
    VAR TotalEncounters =
        COUNT('vw_readmissions'[encounter_id])
    RETURN
    DIVIDE(Readmits, TotalEncounters, 0)
```

## Insights

  - Stable LOS (7.25 hours) across the period.
  - 30-day Readmissions at 62.3% with higher rates in urgent/inpatient classes.
    **NOTE:** As this is synthetic dataset, this readmission rate is much higher than would be expected in real life (15% - 20%) 
  - Outpatient + Ambulatory dominate the encounter mix.

[← Back to README](../README.md) | [Page 2 →](02_patient_volume_trends.md)
