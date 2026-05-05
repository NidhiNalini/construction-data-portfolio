# Project 01 — Alberta Construction Projects EDA

## What Is This?
Exploratory Data Analysis of 210 Alberta construction and infrastructure
projects (2020–2023). Cleaned a real-world messy dataset and built
four visualisations to identify patterns in project value, delays, and safety.

## Dataset
- Source: alberta_projects.csv (synthetic, modelled on Alberta Open Data)
- Rows: 210 (189 after cleaning)
- Columns: project_id, city, sector, contractor, project_value_cad,
  start_date, end_date, status, workers_on_site, safety_incidents,
  delay_days, approved

## Data Issues Found & Fixed
- 0 duplicate rows removed (confirmed by audit)
- "approved" column had 6 inconsistent variations (Yes/yes/YES/y) — standardised
- project_value_cad stored as text — converted to float
- start_date and end_date stored as text — converted to datetime
- Missing values in workers_on_site filled with median (127.5)
- Missing values in safety_incidents filled with 0 (domain assumption: no report = no incident)
- 0 rows dropped due to missing project_value_cad

## Key Findings

**Project Value Distribution**
Project values are distributed relatively uniformly between $0M and $45M with
no significant right skew. This means the mean and median are close to each
other, and the dataset represents a balanced mix of small and large
infrastructure projects rather than being dominated by a few mega-projects.

**Average Project Value by Sector**
All five sectors (Residential, Infrastructure, Oil & Gas, Commercial, Industrial)
show comparable average project values in the $20M–$23M range. Residential
projects are marginally highest. This is notable because Oil & Gas projects might
be expected to dominate in Alberta — the data does not support that assumption
in this dataset.

**Workers on Site vs Safety Incidents**
No clear correlation was observed between the number of workers on site and
the number of recorded safety incidents. Incident counts appear broadly
independent of workforce size, suggesting that other factors — such as project
type, duration, or contractor safety culture — may be stronger drivers of
incident rates. As a civil engineer, this aligns with site experience: large,
well-managed sites can have better safety outcomes than smaller, less supervised
ones.

**Project Delay Distribution by Sector**
Industrial projects show the highest median delay (approximately 115 days) and
the greatest variability across the dataset. Commercial projects are the most
predictable, with the lowest median delay (approximately 80 days). All five
sectors share a similar maximum delay ceiling of approximately 175 days,
suggesting a common upper boundary on delay duration regardless of sector.

## Tools Used
Python · Pandas · Matplotlib · Seaborn · Jupyter Notebook

## Background
Bachelor of Civil Engineering (Honours), Fiji National University.
Post-Baccalaureate in AI and Data Analytics, Red Deer Polytechnic.
