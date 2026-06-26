# Regional Sales Performance Dashboard

A Business Analyst portfolio project: from requirements gathering through SQL validation to an interactive Power BI dashboard, built on the public **Sample Superstore** dataset (Kaggle, ~10,000 order lines).

## Problem

The Sales organization had no self-serve way to monitor regional performance. Managers relied on manual spreadsheets and emails to Finance for monthly numbers, with no visibility into which regions, states, or product lines were underperforming — and no way to assess whether discounting was eroding profit margin.

## What I did

1. **Requirements** — Wrote a full BRD/FRD with business requirements, functional requirements, user stories (Agile format), and acceptance criteria. [`BRD_FRD_Sales_Dashboard.docx`](./BRD_FRD_Sales_Dashboard.docx)
2. **Data validation** — Queried the dataset directly in SQL to confirm KPIs *before* building any visuals, so the dashboard was built on verified numbers, not assumptions. [`sql_queries.sql`](./sql_queries.sql)
3. **Dashboard build** — Built an interactive Power BI dashboard: KPI cards, regional and sub-category breakdowns, a discount-vs-profit analysis, a monthly trend line, and four cross-filtering slicers.
4. **UAT** — Tested the finished dashboard against the original SQL output to confirm consistency. [`UAT_Test_Log.xlsx`](./UAT_Test_Log.xlsx)
5. **Case study** — Wrote up the findings and a recommendation in BA case-study format. [`Case_Study.docx`](./Case_Study.docx)

## Key findings

| Layer | Finding |
|---|---|
| **Region** | Central's profit margin (7.92%) was roughly half of West's (14.94%), despite generating revenue comparable to East. |
| **State** | The gap wasn't region-wide — Texas (−$25,729 profit) and Illinois (−$12,608 profit) were running outright losses, while the other 11 states in Central were solidly profitable. |
| **Category** | Within Texas and Illinois specifically, losses were concentrated in **Binders** and **Appliances** — sub-categories that were profitable (14.86% margin) everywhere else in the dataset. |
| **Root cause** | A dataset-wide discount-band analysis showed margin stayed positive up to ~20% discount (29.51% margin at 0% discount), then turned negative above 20% (−10.05%) and collapsed further above 30% (−48.16%). |

**Recommendation:** Review discount approval policy for orders above 20%, particularly for Binders and Appliances in the Central region.

## Dashboard preview

*(Add 2-3 screenshots of your finished Power BI dashboard here — drag image files into this repo and reference them like:)*

```markdown
![Dashboard overview](./screenshots/dashboard_overview.png)
![Discount vs profit](./screenshots/discount_vs_profit.png)
```

## Tools used

`SQL (SQLite)` · `Power BI` · `Excel` · Requirements documentation (BRD/FRD, user stories, UAT)

## Files in this repo

- `BRD_FRD_Sales_Dashboard.docx` — requirements documentation
- `sql_queries.sql` — all KPI/validation queries, tested
- `UAT_Test_Log.xlsx` — test cases and results
- `Case_Study.docx` — one-page findings summary
- `README.md` — this file
