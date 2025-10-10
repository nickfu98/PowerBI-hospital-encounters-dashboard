[← Page 2](02_patient_volume_trends.md) | [Page 4 →](04_readmission_rates.md)

# Length of Stay (LOS)

![Length of Stay](dashboard_screenshots/03_length_of_stay.png)

## Purpose
Measure operational efficiency via average LOS by time and demographic.

## Key Visuals
| Visual | What it shows |
|---|---|
| Line: Avg LOS by Year | Yearly efficiency trend |
| Column: Avg LOS by Month | Seasonality of LOS |
| Bar: Avg LOS by Age Group | Demographic differences |
| Bar: Top 10 Procedures by Avg LOS | Longest-stay procedures |

## Slicers Used
- Timeline, Year, Insurance Provider, Age Group

## Data Sources
- **Fact/View:** `vw_encounter_details`
- **Dimensions:** `DateTable`, `procedures`

## Key DAX
```DAX
Avg LOS (hrs) = AVERAGE('vw_encounter_details'[LOS_Hours])
```

## Insights
  - Longest LOS in <30 and 30–39 groups; spike in 2014 indicates episodic bottlenecks.

[← Page 2](02_patient_volume_trends.md) | [Page 4 →](04_readmission_rates.md)
