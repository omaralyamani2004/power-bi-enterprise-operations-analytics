# Curated Measure Catalog

The report contains more calculations than are useful to list in a portfolio. The following measures are the most relevant for explaining the business value of the dashboard.

## Commercial Sales

| Measure | Explanation | Decision use |
|---|---|---|
| `Total Revenue` | Aggregates sales revenue under the active date, product, and territory filters. | Tracks the size of the business and compares performance across categories and regions. |
| `Total COGS` | Aggregates cost of goods sold. | Highlights cost pressure and supports gross-profit analysis. |
| `Gross Profit Margin` | Calculates gross profit as a percentage of revenue. | Separates high-volume growth from profitable growth. |
| `YoY Revenue Growth %` | Compares revenue with the comparable prior-year period when the shared date dimension covers the full fact range. | Shows growth momentum in an executive view after date coverage is reconciled. |
| `Revenue by Ship Date` | Evaluates revenue using the shipping-date context through the inactive ship-date relationship. | Supports operational timing and fulfillment analysis after the shared date range is complete. |

## Customer Analysis

| Measure | Explanation | Decision use |
|---|---|---|
| `Total Customers` | Counts distinct customers in the selected context. | Measures customer-base reach by date, country, gender, income, or education. |
| `Avg Orders per Customer` | Divides order activity by the customer base. | Indicates purchase frequency and engagement. |
| `Returning Customers` | Identifies customers with repeat purchase behavior. | Supports retention and loyalty initiatives. |
| `Avg Spending` | Calculates average spend for the selected customer segment. | Compares customer value across marital status and other segments. |
| `Total Sales` | Reuses the sales KPI in customer and country context. | Connects customer behavior to commercial value. |

## HR and organizational analysis

| Measure | Explanation | Decision use |
|---|---|---|
| `Active Employee Count` | Counts active employee records according to the model definition. | Provides the workforce baseline. |
| `Average Tenure` | Calculates the average tenure metric used by the report. | Supports retention and workforce-experience analysis. |
| `Avg Hourly Rate` | Displays the average hourly-rate metric. | Provides a compensation benchmark by the selected context. |

## Measure design principles

- Measures remain filter-aware so slicers and cross-highlighting change the business context.
- Ratios use protected division logic so zero-denominator contexts do not create misleading errors.
- Distinct-count KPIs should use a consistent employee/customer key across cards, tables, and demographic breakdowns.
- A measure should be validated at total level and at one granular level before it is used in a public insight.

## Current validation note

The commercial KPI measures reconcile to the downloaded PBIX totals. Year-over-year and date-role measures remain subject to the shared date-table coverage issue documented in [`docs/data-model-and-process.md`](data-model-and-process.md); those measures should not support a public claim until the date table is extended through the latest fact date.
