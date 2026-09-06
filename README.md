# Enterprise Operations Analytics | Power BI

Enterprise Operations Analytics is a Power BI case study built with Adventure Works training data. It shows how a reusable semantic model can turn sales, customer, workforce, and inventory data into a reporting experience that supports commercial and operational decisions.

## The business question

Revenue alone does not explain whether growth is healthy. A decision-maker needs to see revenue, cost, margin, product mix, regional performance, customer engagement, and workforce context in the same analytical environment.

This project answers that need through one report with four connected perspectives:

- **Commercial Sales:** revenue, COGS, gross margin, product mix, and regional performance.
- **Customer Analysis:** customer reach, order frequency, repeat customers, segmentation, and geography.
- **HR Analysis Dashboard:** employee count, tenure, job group, gender, and hiring trend.
- **Supply Chain & Inventory:** stock balance, units in, units out, inventory value, and category movement.

The public narrative focuses on the Commercial Sales and Customer Analysis pages because they provide the clearest decision story; the PBIX contains the complete four-page report.

## How the solution was built

The data was prepared in Power Query and organized as a star-schema-oriented model. Date, customer, product, and sales-territory dimensions filter the Internet Sales fact table, while product and date dimensions support inventory analysis. HR tables provide the workforce perspective. DAX measures then turn these model relationships into filter-aware KPIs rather than disconnected visual totals.

The report is designed to move from an executive question to an explanation: first identify where revenue and margin are moving, then isolate the product or region behind the result, and finally explore the customer context that can inform retention or commercial action.

## Measures that drive the analysis

| Measure | Why it matters |
|---|---|
| `Total Revenue` | Establishes the commercial baseline in the active filter context. |
| `Total COGS` | Shows the cost required to generate that revenue. |
| `Gross Profit Margin` | Separates profitable growth from volume without margin. |
| `YoY Revenue Growth %` | Places current revenue in a prior-year context. |
| `Total Customers` | Measures reach using distinct customers. |
| `Avg Orders per Customer` | Indicates purchase frequency and engagement. |
| `Returning Customers` | Highlights repeat-purchase behavior. |
| `Avg Spending` | Compares customer value across segments. |

The full measure catalog and process explanation are available in [`docs/measure-catalog.md`](docs/measure-catalog.md) and [`docs/data-model-and-process.md`](docs/data-model-and-process.md).

## Dashboard preview

The portfolio showcase highlights the two clearest decision views. The downloadable PBIX includes all four report pages.

### Commercial Sales

![Commercial Sales dashboard](assets/commercial-sales.png)

### Customer Analysis

![Customer Analysis dashboard](assets/customer-analysis-full.png)

## A validated business insight

In the current unfiltered Commercial Sales view, revenue is `$80.45M`, COGS is `$79.98M`, and gross profit margin is `0.58%`. Bikes generate `$66.30M`, or approximately `82.4%` of total revenue, while the displayed category margin is `-1.49%`.

The important conclusion is not simply that Bikes are the best-selling category. It is that the largest revenue stream is also the main profitability risk. A commercial manager would use this result to investigate pricing, discounting, product cost, and sales mix before treating revenue growth as healthy growth.

The Customer Analysis page provides the next layer of context. With `2013` selected, it shows `12.48K` customers, `1.17` average orders per customer, `$25M` total sales, and approximately `1K` returning customers. Since these values are rounded in the report, any derived customer percentage is described as approximate.

## Public-release quality controls

The public PBIX is a preserved, valid copy of the Adventure Works report package. Product-category totals reconcile to Total Revenue within `$1`, which is attributable to displayed rounding. The public narrative uses only the commercial and customer figures that were validated in the report view; customer and workforce detail should be interpreted within the selected filter context.

This repository contains Adventure Works training data only; the figures are portfolio examples and are not claims about a real company.

## Repository contents

- [`Enterprise Operations Analytics - Public Portfolio.pbix`](Enterprise%20Operations%20Analytics%20-%20Public%20Portfolio.pbix) — rebuilt portfolio report.
- [`docs/data-model-and-process.md`](docs/data-model-and-process.md) — model architecture and delivery narrative.
- [`docs/measure-catalog.md`](docs/measure-catalog.md) — selected DAX measure explanations.
- [`docs/business-insights.md`](docs/business-insights.md) — decision-oriented insight write-up.
- `assets/` — selected report screenshots.

## Tools

Power BI · Power Query · DAX · Star-schema modeling · KPI design · Business analysis

## Author

Omar Alyamani — Data Analyst / BI Analyst

