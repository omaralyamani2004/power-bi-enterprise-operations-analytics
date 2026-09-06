# QA Validation and Publication Gate

This document records the checks used before presenting the dashboard as a portfolio project.

## Checks that passed

### Commercial Sales reconciliation

| Check | Result | Interpretation |
|---|---:|---|
| Total Revenue | `$80,450,597` | Executive KPI in the current unfiltered view. |
| Product-category total | `$80,450,598` | Difference of `$1`, explained by displayed category rounding. |
| Total COGS | `$79.98M` | Consistent with the reported revenue and low margin. |
| Gross Profit Margin | `0.58%` | Approximately `(Revenue - COGS) / Revenue` using the displayed values. |
| Bikes revenue share | `82.4%` | `$66.30M / $80.45M`; calculated from displayed values. |

The category totals and the executive KPI tell the same commercial story: Bikes dominate revenue, but the displayed margin is negative. This is a useful, evidence-based portfolio insight.

### Customer KPI snapshot

With the report's `2013` date selection and other slicers at `All`, the visible cards show:

- `12.48K` Total Customers
- `1.17` Avg Orders per Customer
- `$25M` Total Sales
- approximately `1K` Returning Customers

The values are rounded in the report, so any derived percentage should be described as approximate.

## Findings corrected in the public copy

### Customer detail table

The Top Customers table displayed the same `$24,637,273.29` Total Revenue for multiple customer rows. That is not a credible customer-level distribution when the table is grouped by customer. The likely causes are an incorrect measure filter context, an `ALL`/`REMOVEFILTERS` expression, or an inactive/missing relationship between the customer dimension and sales fact.

**Correction applied:** the public copy replaces the measure projection with `SUM(FactInternetSales[SalesAmount])` so each customer row preserves customer filter context. The report should still be refreshed in Power BI Desktop before using row-level values as business claims.

### HR headcount

The HR page showed `290` on the employee KPI while the gender breakdown showed `237` male and `97` female, totaling `334`. This means the cards and demographic visual are not using the same counting definition or filter context.

**Correction applied:** the public copy aligns the KPI and demographic visuals to the canonical `Active Employee Count` measure. The report should still be refreshed in Power BI Desktop before using the HR page as a decision source.

## Portfolio decision

The public showcase uses Commercial Sales for the primary numeric insight. The rebuilt PBIX also contains the corrected Customer Analysis and HR definitions, while the original source findings remain documented for transparency.
