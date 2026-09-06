# Data Model and Delivery Process

## Model approach

The report is organized around a star-schema-oriented semantic model. Fact tables hold measurable events, while dimensions provide the filters and grouping used by the report.

```text
DimDate ───────────────┐
DimCustomer ───────────┤
DimProduct ────────────┼──> FactInternetSales ──> Commercial Sales / Customer Analysis
DimSalesTerritory ─────┘

DimDate ───────────────┐
DimProduct ────────────┼──> FactProductInventory ──> Supply Chain & Inventory

Human Resources dimensions/facts ─────────────> HR Analysis Dashboard
```

The naming convention separates dimensions (`Dim...`) from facts (`Fact...`) and keeps measures in a dedicated measure layer where applicable.

## End-to-end process

1. **Scope the business questions** — revenue, profitability, customer behavior, workforce profile, and inventory movement.
2. **Prepare the data in Power Query** — apply data types, standardize fields, shape model-ready tables, and remove unnecessary columns.
3. **Build the semantic model** — connect date and descriptive dimensions to the relevant fact tables and establish a consistent filter path.
4. **Create DAX measures** — define revenue, cost, margin, growth, customer-frequency, retention, and workforce KPIs.
5. **Design role-based pages** — executive commercial view first, then customer and organizational analysis views.
6. **Add analytical interaction** — slicers for date, geography, product, customer attributes, and department; cross-filtering connects visuals to decisions.
7. **Validate the numbers** — reconcile headline cards with category totals, test a filtered slice, and inspect row-level context in tables.
8. **Publish only after QA** — public screenshots should use training data and exclude any visual whose measure context is not reconciled.

## QA decisions for this portfolio version

- **Commercial Sales:** selected for the public showcase because the headline KPIs, category totals, and regional story form a clear executive narrative.
- **Customer Analysis:** selected for the public showcase; the public PBIX uses a row-context-preserving sales aggregation for customer-level detail. Customer-level findings should still be interpreted within the selected date and segment filters.
- **HR Analysis:** not published as a finished insight because the total employee KPI and gender breakdown currently do not reconcile.
- **Supply Chain & Inventory:** not included in the first public release because it needs stronger narrative framing and validation.

