# Tool Decision Log

## Context
Portfolio project: SQL analysis of data science job salaries (607 rows, CSV source).
Goal: demonstrate advanced SQL skills (window functions, CTEs, aggregations) and data visualization for a data analyst portfolio.

## SQL Engine — DuckDB

| Criteria | SQLite | **DuckDB** ✅ | PostgreSQL | BigQuery |
|---|---|---|---|---|
| Setup | Built-in Python | `pip install duckdb` | Local server required | Google account |
| Window functions | Partial | Full | Full | Full |
| CTEs | Yes | Yes | Yes | Yes |
| STDDEV / VARIANCE | No | Yes | Yes | Yes |
| Read CSV directly | No | Yes | No | Yes |
| Analytical speed | Slow | Very fast | Fast | Very fast |
| 100% local & free | Yes | Yes | Yes | No |
| Market relevance 2024+ | Low | High (growing fast) | High | High |

**Decision: DuckDB**

- Reads CSV directly — no database setup required
- Full analytical SQL out of the box (window functions, CTEs, STDDEV)
- Embedded, no server, works 100% locally
- Growing rapidly in modern data stacks alongside dbt and Apache Arrow

> *"I chose DuckDB because it supports full analytical SQL while running entirely in-process without a server — appropriate for a local analysis on 607 rows, and increasingly relevant in modern data engineering stacks."*

---

## Visualization — Standalone HTML (Chart.js + Tufte principles)

| Criteria | Power BI | Tableau | **HTML/Chart.js** ✅ | Matplotlib |
|---|---|---|---|---|
| Works on Mac | Desktop: No | Yes | Yes | Yes |
| GitHub embeddable | No (.pbix) | No | **Yes** | Static image only |
| License required | Yes | Yes | No | No |
| Interactive | Yes | Yes | Yes | No |
| Setup | High | High | None | pip install |

**Decision: Standalone HTML dashboard**

- Single `.html` file — opens in any browser, no license, no server
- Fully embeddable and viewable directly on GitHub Pages
- Interactive charts via Chart.js
- Power BI and Tableau remain relevant tools for client engagements where a license is provided
