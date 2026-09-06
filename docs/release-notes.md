# Public Portfolio Release Notes

## Rebuilt from

`Enterprise Operations Analytics.pbix`

The source file was preserved. The public portfolio file is a derived copy intended for the Adventure Works training-data showcase.

## Corrections applied

### Customer Analysis detail table

The Top Customers table previously used the `Commercial Sales.Total Revenue` measure and returned the same total for multiple customer rows. The public copy replaces that projection with a direct sum of `FactInternetSales.SalesAmount`, preserving the customer row context through the existing dimension-to-fact relationship.

### HR headcount consistency

The public copy aligns the employee KPI, gender breakdown, marital-status breakdown, job-group breakdown, and employee trend to the existing `HUMAN RESOURCES & ORGANIZATIONAL.Active Employee Count` measure. This removes the previous mix of row-count and measure definitions that produced non-reconciling headcounts.

### Naming quality

The page title typo `HR ANALYSIS DASHBORARD` was corrected to `HR ANALYSIS DASHBOARD` in the public copy.

## Release gate

The public release includes the rebuilt `.pbix`, the two strongest screenshots, the measure catalog, the model/process explanation, the insight write-up, and the QA validation log. Insights use only values that can be reconciled from the visible report totals or are explicitly labelled as approximate.

