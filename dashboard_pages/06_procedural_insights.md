[← Page 5](05_revenue_trends.md) | [Back to README →](../README.md)

# Procedural Insights

![Procedural Insights](../dashboard_screenshots/06_procedural_insights.png)

## Purpose
Summarize procedure mix, gender differences, and longest average stays.

## Key Visuals
| Visual | What it shows |
|---|---|
| KPI Cards | Total Procedures, Top 5 % of Total, Avg LOS |
| Clustered Bar | Gender distribution of Top 5 procedures |
| Bar | Top 5 procedures by Avg LOS |

## Slicers Used
- Timeline, Year, Insurance Provider, Age Group

## Data Sources
- **Fact/View:** `vw_encounter_details`
- **Dimensions:** `procedures`, `patients`, `DateTable`

## Key DAX
```DAX
Top 5 Procedures % =
VAR Top5 =
    CALCULATE([Total Encounters],
        KEEPFILTERS(
            TOPN(5, VALUES('procedures'[procedure_code]), [Total Encounters], DESC)
        )
    )
RETURN DIVIDE(Top5, [Total Encounters], 0)
```

## Insights
  - Top 5 procedures ≈ ~63% of volume; MRI/screenings are longest on average with mild gender variation.

[← Page 5](05_revenue_trends.md) | [Back to README →](../README.md)
