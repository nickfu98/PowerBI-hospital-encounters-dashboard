# PowerBI Hospital Encounters Dashboard


## Project Overview
This Power BI dashboard analyzes 27,891 hospital encounters recorded between 2011 and 2022.
The goal was to uncover patterns in patient volume, length of stay, readmission rates, and revenue - enabling data-driven insights to improve hospital operations and patient outcomes.

This project was built from a the same synthetic hospital encounters dataset used in my SQL project. 
To keep the layout simple and readable, the dashboard is divided into six pages:

1. Dashboard Overview - executive summary of key hospital KPIs

2. Patient Volume Trends - yearly and monthly encounter trends

3. Length of Stay (LOS) - duration patterns by year, month, and age group

4. Readmission Rates - 30-day readmission trends by payer, class, and demographics

5. Revenue Trends - total and per-encounter revenue performance

6. Procedural Insights - procedure mix, gender distribution, and LOS by procedure

---

## Data Model
Source: SQL Server Management Studio (SSMS)
Tables: `encounters`, `patients`, `payers`, `procedures`

Date Table: Custom DAX table that auto-detects the first and last encounter dates (2011–2022) for slicer filtering.

The model follows a star schema, centered on `vw_encounter_details` linked to dimension tables for Payers, Procedures, Patients, and Date Table.

---

## Dashboard Pages
**1. Overview**
This page summarizes high-level KPIs across all encounters:
  - Total Encounters: 27,891
  - Total Patients: 974
  - Average LOS: 7.25 hours
  - Total Revenue: $31.1M
  - Revenue per Encounter: $1,115
  - 30-Day Readmission Rate: 62.35 %

Visuals:
  - KPI cards (Encounters, Patients, LOS, Revenue, etc.)
  - Donut chart for 30-day readmission rate
  - Stacked bar for yearly encounter class breakdown
  - Donut chart showing encounter volume by age group

Insight: The hospital maintained consistent patient throughput over the decade, with outpatient and ambulatory visits driving most of the encounter volume.

**2. Patient Volume Trends**
This page focuses on overall encounter activity and seasonal patterns.

Visuals:
  - Line chart: Total Encounters by Year
  - Column chart: Total Encounters by Month
  - Donut chart: Encounter Class Distribution
  - Bar chart: Top 10 Procedures by Encounter Volume

Insight: Encounter volume peaks in 2014 and 2020–2022, aligning with outpatient and urgent care growth.

**3. Length of Stay (LOS)**
Analyzes efficiency by measuring average stay duration across dimensions.

Visuals:
  - Line chart: Avg LOS (hours) by Year
  - Column chart: Avg LOS (hours) by Month
  - Bar chart: Avg LOS (hours) by Age Group
  - Bar chart: Top 10 Procedures by Avg LOS

Insight: Patients under 30 and 30–39 had the longest stays, averaging ~30–40 hours, while LOS spikes in early 2014 and late 2021 indicate episodic operational bottlenecks.

**4. Readmission (30-Day) Trends**
Tracks short-term readmissions as a quality measure across key categories.

Visuals:
  - Line chart: Readmission Rate by Year
  - Bar chart: Readmission Rate by Encounter Class
  - Bar chart: Readmission Rate by Insurance Provider
  - Bar chart: Readmission Rate by Age Group

Insight: Urgent Care and Inpatient classes show the highest readmission rates, particularly among patients aged 70+, suggesting opportunities to improve post-discharge follow-up.

**5. Revenue Trends**
Evaluates hospital financial performance and payer contributions.

Visuals:
  - Line chart: Total Revenue by Year
  - Column chart: Avg Revenue per Encounter by Payer
  - Column chart: Total Revenue by Payer
  - Bar chart: Top 10 Procedures by Total Revenue

Insight: Medicare and Blue Cross Blue Shield together account for nearly 70 % of total revenue, while cardiology and radiology procedures are the largest financial drivers.

**6. Procedural Insights**
Summarizes key procedural data, gender differences, and LOS trends.

Visuals:
  - KPI cards for:
    - Total Procedures (52)
    - Top 5 Procedures % of Total (62.7 %)
    - Average LOS (7.25 h)
  - Clustered Bar: Gender Distribution of Top 5 Procedures
  - Bar Chart: Top 5 Longest Procedures by Avg LOS

Insight: MRI and screening procedures account for over 60 % of total volume, with slight gender variation favoring female patients in preventive care services.

**Key Takeaways**
  - Hospital handled steady growth in encounters from 2011–2022.
  - Average LOS remained stable around 7.25 hours.
  - Readmissions remain elevated in inpatient and urgent care settings.
  - Revenue growth driven by public insurers and a handful of high-value procedures.
  - Procedural distribution dominated by radiology and screening services, consistent with modern outpatient trends.
