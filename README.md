# Data Science Job Market Analysis

**Dataset:** [ds_salaries.csv](https://www.kaggle.com/datasets/ruchi798/data-science-job-salaries) — 607 rows, Kaggle (2020–2022)  
**Tools:** DuckDB · Python · Pandas · Chart.js  
**Goal:** Explore salary trends, remote work patterns, and experience-level dynamics in the global data science job market.

---

## Project Structure

```
data-jobs-market-analysis/
├── data/
│   └── ds_salaries.csv          # Raw dataset (607 rows, 12 columns)
├── notebooks/
│   └── 01_sql_analysis.ipynb    # Full SQL analysis in DuckDB
├── dashboard/
│   └── dashboard.html           # Interactive HTML dashboard (Chart.js)
├── sql/
│   └── TOOL_CHOICE.md           # Why DuckDB over SQLite/PostgreSQL
└── README.md
```

---

## Dataset Columns

| Column | Description |
|---|---|
| `work_year` | Year the salary was paid (2020–2022) |
| `experience_level` | EN (Entry) / MI (Mid) / SE (Senior) / EX (Executive) |
| `employment_type` | FT / PT / CT / FL |
| `job_title` | Job title (50+ distinct titles) |
| `salary` | Raw salary in local currency |
| `salary_currency` | Currency of the salary |
| `salary_in_usd` | Salary normalized to USD |
| `employee_residence` | Employee's country |
| `remote_ratio` | 0 = on-site / 50 = hybrid / 100 = fully remote |
| `company_location` | Company's country |
| `company_size` | S / M / L |

---

## Analysis Plan

### Notebook: `01_sql_analysis.ipynb`

| # | Section |
|---|---|
| 1 | Dataset Overview |
| 2 | Salary by Experience Level |
| 3 | Top Paying Job Titles |
| 4 | Salary Growth Year-over-Year |
| 5 | Remote Work Patterns |
| 6 | Geographic Distribution |
| 7 | Company Size Impact |
| 8 | Salary Rankings with Window Functions |
| 9 | Multi-Dimensional Analysis with CTEs |

---

## Key Questions This Analysis Answers

1. How much does experience level impact salary in data science?
2. Which job titles pay the most — and which are overrated?
3. Is the data science job market becoming more remote over time?
4. Which countries offer the best data science salaries?
5. Do larger companies pay more than startups?
6. How fast are data science salaries growing year-over-year?

---

## Tool Choice: Why DuckDB

> Full benchmark and interview justification: [`sql/TOOL_CHOICE.md`](sql/TOOL_CHOICE.md)

DuckDB reads CSV directly, supports full analytical SQL (window functions, STDDEV, CTEs), runs 100% locally with no server setup, and is increasingly used in modern data stacks alongside dbt and Apache Arrow.

---

## Dashboard

Interactive standalone HTML dashboard — no server, no license required, opens in any browser.

5 visualizations:
- Salary by experience level (bar chart)
- Top 10 highest-paid job titles (horizontal bar chart)
- Salary growth year-over-year 2020–2022 (line chart)
- Remote work distribution and salary impact (bar + line chart)
- Geographic distribution — top 9 countries by average salary (bar chart)

> Full tool decision rationale: [`sql/TOOL_CHOICE.md`](sql/TOOL_CHOICE.md)
