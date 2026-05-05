# Project 02 — Alberta Construction Projects SQL Pipeline

## What Is This?
Engineered a normalised 3-table SQLite database from a single flat CSV containing 189 Alberta construction projects. Designed the schema, derived dimension tables programmatically using Python and Pandas, loaded all tables via an automated pipeline, and queried the database using SQL JOINs and aggregations to extract business insights.

## Dataset
- Source: alberta_projects.csv (synthetic, modelled on Alberta Open Data)
- Rows: 210 (189 after cleaning)
- Columns: project_id, city, sector, contractor, project_value_cad,
  start_date, end_date, status, workers_on_site, safety_incidents,
  delay_days, approved
- Tables derived : 3

## Schema Design
- regions table
    Columns: region_id (PK), city, province
- contractors table
    Columns: contractor_id (PK), contractor_name
- projects table:
    Columns: project_id (PK), region_id(FK), contractor_id(FK), sector,project_value_cad, start_date, end_date, status, workers_on_site, safety_incidents, delay_days, approved
## Key Findings
- Residential sector had the highest average project value at $23M followed closely by Infrastructure at $22M
- Industrial projects recorded the highest total safety incidents (269) across all sectors
- Infrastructure sector had the highest average delay at 94.6 days
- Edmonton recorded the highest average project delay at 114 days
across 24 projects.
- Blackfalds recorded the lowest average delay at 74 days — the most predictable city for project delivery
- The highest value project was AB-2022-0098 (Commercial, $44.9M) delivered by Bird Construction in Calgary

## Tools Used
Python · Pandas · sqlite3 · Jupyter Notebook

## Background
Bachelor of Civil Engineering (Honours), Fiji National University.
Post-Baccalaureate in AI and Data Analytics, Red Deer Polytechnic.
