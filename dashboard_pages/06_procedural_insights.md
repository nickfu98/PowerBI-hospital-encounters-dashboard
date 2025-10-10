[← Page 5](05_revenue_trends.md) | [Back to README →](../README.md)


![Procedural Insights](dashboard_screenshots/06_procedural_insights.png)


## Purpose
Summarize procedure mix, gender differences, and longest average stays.

## Key Visuals
| Visual | What it shows |
|---|---|
| KPI Cards | Total Procedures, Top 5 Procedures % of Total, Avg LOS |
| Clustered Bar | Gender distribution of Top 5 procedures |
| Bar | Top 5 procedures by Avg LOS |

## Slicers Used
- Timeline, Year, Insurance Provider, Age Group

## Data Sources
- **Fact/View:** `vw_encounter_details`
- **Dimensions:** `procedures`, `patients`, `DateTable`

## Key DAX
```DAX
Top 5 Procedures % of Total = 
    VAR Top5Total =
        SUMX(
            TOPN(
                5,
                VALUES(procedures[DESCRIPTION]),
                [Total Encounters],
                DESC
            ),
            [Total Encounters]
        )
    VAR AllTotal =
        CALCULATE(
            [Total Encounters],
            KEEPFILTERS(VALUES('DateTable'[Year])),
            KEEPFILTERS(VALUES(Payers[payer_name])),
            REMOVEFILTERS(Procedures)
        )
    RETURN
    DIVIDE(Top5Total, AllTotal, 0)
```

## Insights
  - Top 5 procedures = 62.7% of total volume
  - Depression screenings and health/social care account for the majority of all procedures with minor differences between genders.
  - Breast related screenings/care take the longest on avearge.

[← Page 5](05_revenue_trends.md) | [Back to README →](../README.md)
