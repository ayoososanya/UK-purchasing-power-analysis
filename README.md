# UK Purchasing Power Analysis 2019–2024
### Did UK Workers Actually Get Poorer? A SQL Analysis of Wages vs Inflation

---

## Overview

Between 2019 and 2024, the UK experienced a global pandemic, an energy crisis, 
and the worst inflation in 40 years. This project investigates whether the average 
UK workers' wages kept pace with rising prices, or whether their purchasing 
power quietly eroded over this period.

Using publicly available ONS data, this analysis quantifies the gap between 
wage growth and inflation, month by month, identify the exact turning point 
when workers started falling behind, and tracks whether any recovery had 
occurred by the end of 2024.

This is the kind of analysis that personal finance companies — budgeting apps, 
lending platforms, salary benchmarking tools — need to understand the economic 
Reality, their users are living in.

---

## Tools & Technologies

- **Python** (pandas) — data loading and cleaning
- **SQL** (SQLite) — analysis and querying
- **DataLab** — notebook environment
- **Data Sources** — Office for National Statistics (ONS), Open Government 
  Licence v3.0

---

## Data Sources

| Dataset | Source | What It Measures |
|---|---|---|
| CPIH Inflation Index | ONS | Monthly price inflation (2015=100) |
| Real Average Weekly Earnings (X09) | ONS | Monthly real wages adjusted for CPI, in 2015 pounds |

Both datasets cover January 2019 to December 2024.

---

## The Five Questions

1. How much did inflation rise between 2019 and 2024, and which year was the worst?
2. Did wages keep pace with inflation year by year?
3. When exactly did the gap between wages and prices start opening up?
4. What was the single worst month for purchasing power?
5. Did purchasing power recover by 2024, and if so, by how much?

---

## Key Findings

**1. 2022 was the worst single year for inflation — but the squeeze started earlier**
Inflation rose 10 index points within 2022 alone, roughly double any other year 
in the dataset. However, the data shows wages began falling behind inflation as 
early as September 2021 — a full year before the cost of living crisis dominated 
headlines.

**2. Workers never kept up**
In every year except 2021, inflation outpaced wages. By 2024, the average 
inflation index stood at 124.85 — meaning prices were nearly 25% higher than 
in January 2019 — while purchasing power had only risen to 105.16. Workers 
were running to stand still and losing ground every year.

**3. 2024 was actually the worst year for purchasing power — not 2022**
This is the most counterintuitive finding. Despite inflation slowing down in In 
2023 and 2024, the accumulated gap between prices and wages meant that in November 
2024 was the single worst month in the entire dataset, with a purchasing power 
gap of -20.63 index points. Prices never fell — they just rose more slowly — 
while wages were still catching up from the 2022 shock. The average worker in 
late 2024 could buy roughly 20% less than they could have if their wages had 
kept pace with prices since January 2019.

**4. Recovery is underway but incomplete**
Wage momentum turned positive in 2023 (+0.17 average monthly growth) and 
accelerated in 2024 (+0.30). Workers are recovering, but the accumulated gap 
from 2022 remains so large that full recovery has not occurred by the end of 2024.

---

## Methodology

1. Loaded raw ONS CSV files into Python using pandas
2. Filtered CPIH data to Overall Index only (CP00), reducing 55,510 rows to 
   72 clean monthly records
3. Cleaned wages data — fixed inconsistent date formats, removed embedded 
   footnotes, selected relevant columns
4. Merged both datasets on the date column to create a single analytical table
5. Rebased both indexes to January 2019 = 100 for direct comparison
6. Loaded into SQLite and queried using SQL — including CTEs, window functions, 
   LAG, GROUP BY, and aggregate functions

---

## What This Means for Personal Finance

The sustained collapse in purchasing power from 2022 onwards has direct 
implications for fintech products and strategy:

- Demand for budgeting and expense tracking tools increased as discretionary 
  income shrank
- Credit risk profiles for average earners deteriorated significantly through 
  2022 and 2023
- Recovery in 2024 is promising but uneven — product strategies targeting 
  Financial recovery and savings rebuilding are well-timed

---

## About

Built by Ayoola Ososanya — Economics Graduate transitioning into Data Analytics.
Targeting research and data analyst roles in fintech and personal finance.

[LinkedIn](www.linkedin.com/in/ayoolaososanya) 
