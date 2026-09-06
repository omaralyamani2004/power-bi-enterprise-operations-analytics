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

## Publication blockers

### Customer detail table

The Top Customers table displayed the same `$24,637,273.29` Total Revenue for multiple customer rows. That is not a credible customer-level distribution when the table is grouped by customer. The likely causes are an incorrect measure filter context, an `ALL`/`REMOVEFILTERS` expression, or an inactive/missing relationship between the customer dimension and sales fact.

**Required fix:** validate the customer key relationship and rewrite the table measure so each customer row preserves customer filter context. Reconcile the top-customer sum back to the total after the fix.

### HR headcount

The HR page showed `290` on the employee KPI while the gender breakdown showed `237` male and `97` female, totaling `334`. This means the cards and demographic visual are not using the same counting definition or filter context.

**Required fix:** use one canonical employee key and a consistent distinct-count measure for the KPI and every demographic breakdown; then reconcile the categories to the total.

## Portfolio decision

Only Commercial Sales and the validated headline/segment visuals from Customer Analysis are included in the public showcase. The customer detail table and HR page remain documented as QA findings, not as final business claims.
