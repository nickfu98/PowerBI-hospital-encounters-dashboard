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

The model follows a star schema, centered on vw_encounter_details linked to dimension tables for Payers, Procedures, Patients, and Date Table.

---

## Dashboard Pages
