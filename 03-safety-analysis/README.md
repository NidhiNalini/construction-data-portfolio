# Alberta Construction Safety Outcomes Analysis

## Research Question
How does industry sector and geographic region affect safety outcomes
in Alberta construction projects between 2019 and 2023?


## What Is This?
This project is an end‑to‑end safety analytics workflow for Alberta construction projects, built to quantify how sector, geography, and season relate to safety performance. I designed it to behave like a real safety dashboard a civil engineer or HSE manager could use to compare risk profiles across sectors, zones, and project types. The focus is on turning raw project records into interpretable, rate‑based safety metrics.

## Dataset
The dataset is a synthetic but realistic collection of Alberta construction and industrial projects from 2019–2023, stored as a CSV and then loaded into a SQLite database. It contains 250 rows, each representing a project, with key columns including `sector`, `city`, `zone`, `contractor`, `project_value_cad`, `workers_on_site`, `safety_incidents`, `near_misses`, `lost_time_incidents`, `project_type`, and `season_started`. For analysis, I primarily used the safety and workforce fields plus sector, zone, project_type, and season.

## Methodology
I first cleaned the data in Python using Pandas: removing duplicates, handling missing values in safety fields, and imputing workforce and near‑miss counts using median values where appropriate. I then engineered rate‑based metrics such as `incident_rate` and `near_miss_rate` (per 100 workers) to normalise for site size, and built a simple relational schema in SQLite with separate `sectors`, `regions`, and `projects` tables. Using SQL queries and Seaborn/Matplotlib visualisations, I explored safety outcomes by sector, zone, project_type, and season, and interpreted the results through a civil engineering safety lens.

## Key Findings
1. **Oil & Gas projects exhibit the highest average incident rates per 100 workers**, which aligns with civil engineering experience that these sites involve complex pressurised systems, heavy lifting, and confined space work, all of which increase exposure to high‑energy hazards.
2. **Northern zone projects show higher and more variable incident rates than Central and Southern zones**, consistent with harsher environmental conditions (cold, ice, snow, reduced daylight) that make access, equipment operation, and housekeeping more challenging on remote sites.
3. **Larger sites tend to record more safety incidents in absolute terms**, but when normalised by workforce size, some smaller projects still show relatively high incident rates, suggesting that safety culture and supervision quality matter as much as scale.
4. **Winter projects generally have higher average incident rates than summer projects**, supporting the hypothesis that winter construction introduces additional risk factors such as slippery surfaces, cold‑related fatigue, and more complex temporary works.
5. **Near‑miss rates are elevated in Industrial and Oil & Gas sectors**, which is important from a safety‑engineering perspective because near misses are leading indicators; high near‑miss activity suggests underlying system weaknesses that can precede serious incidents if not addressed.

## Limitations
This analysis is based on a synthetic dataset, so while patterns are realistic, they do not represent actual company or provincial performance and cannot be used for real‑world benchmarking. The data is cross‑sectional at the project level and does not include detailed temporal trends (e.g., incidents over time), contractor safety culture metrics, or information on training, supervision, or subcontractor practices. Incident and near‑miss counts are treated as complete once cleaned, but in real projects reporting bias, under‑reporting, and differences in safety management systems by contractor or region would significantly affect the reliability of these metrics.

## Tools Used
Python · Pandas · SQLite · Matplotlib · Seaborn · Jupyter Notebook

## Background
Bachelor of Civil Engineering (Honours), Fiji National University.
Post-Baccalaureate in AI and Data Analytics, Red Deer Polytechnic.