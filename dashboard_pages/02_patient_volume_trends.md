## 02 — Patient Volume Trends
**File:** `dashboard_pages/02_patient_volume_trends.md`
```markdown
[← Page 1](01_dashboard_overview.md) | [Page 3 →](03_length_of_stay.md)

# Patient Volume Trends

![Patient Volume Trends](../dashboard_screenshots/02_patient_volume_trends.png)

## Purpose
Understand encounter volume across years/months and service types.

## Key Visuals
| Visual | What it shows |
|---|---|
| Line: Encounters by Year | Annual volume trend |
| Column: Encounters by Month | Seasonality |
| Donut: Encounter Class | Mix of ambulatory/outpatient/etc. |
| Bar: Top 10 Procedures by Volume | Highest-volume procedures |

## Slicers Used
- Timeline, Year, Insurance Provider, Age Group

## Data Sources
- **Fact/View:** `vw_encounter_details`
- **Dimensions:** `DateTable`, `procedures`

## Key DAX
```DAX
Total Encounters = COUNTROWS('vw_encounter_details')
