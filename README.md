# 📊 Data Leverager — Power BI Report

A multi-year sales analytics report built in **Power BI** (version 2.8, created from Cloud — Power BI Service 2026.04). This report integrates sales transactions, product hierarchies, customer demographics, territory mapping, returns data, and a calendar dimension into a unified analytical model.

---

## 📁 File

| File | Description |
|------|-------------|
| `Data_Leverager_pbix.pbix` | Main Power BI Desktop report file (~1.8 MB) |

> **Requires:** Power BI Desktop (April 2026 / version 2.153.777.0 or later) or Power BI Service to open.

---

## 🗂️ Data Model

The report follows a **star schema** design with the following tables:

### Fact Tables

| Table | Description |
|-------|-------------|
| `Sales Data 2020` | Sales transactions for the year 2020 |
| `Sales Data 2021` | Sales transactions for the year 2021 |
| `Sales Data 2022` | Sales transactions for the year 2022 |
| `Returns Data` | Product return records |

### Dimension / Lookup Tables

| Table | Description |
|-------|-------------|
| `Customer Lookup` | Customer profiles and demographic attributes |
| `Product Lookup` | Individual product details |
| `Product Subcateg` | Product sub-category hierarchy |
| `Product Categori` | Top-level product category hierarchy |
| `Territory Lookup` | Geographic sales territory mapping |
| `Calendar Lookup` | Date dimension for time intelligence |

### Schema Diagram (Logical Layout)

```
Calendar Lookup ──────────────────────────────────────────┐
                                                           │
Territory Lookup ──────┐                                   │
                       │                                   │
Customer Lookup ───────┤                                   │
                       ▼                                   ▼
Product Lookup ──► Sales Data 2020 / 2021 / 2022 ◄── Returns Data
     │
     ▼
Product Subcateg ──► Product Categori
```

---

## 📄 Report Pages

| Page | Display Name |
|------|--------------|
| Page 1 | Page 1 *(canvas: 1280 × 720 px)* |

> Additional pages can be added as the report is extended.

---

## ⚙️ Technical Details

| Property | Value |
|----------|-------|
| Power BI Format Version | 1.28 |
| Data Model Version | 5 |
| Created From | Power BI Cloud (Service) |
| Release | 2026.04 |
| Query Engine Version | 2.153.777.0 |
| Theme | CY26SU04 (default Power BI theme) |
| Auto-detected Relationships | Enabled |
| Relationship Import | Enabled |
| Type Detection | Enabled |
| Enhanced Tooltips | Enabled |
| New Filter Pane | Enabled |

---

## 🚀 Getting Started

### Prerequisites

- [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (April 2026 release or later)
- Or access to [Power BI Service](https://app.powerbi.com)

### Opening the Report

1. Clone or download this repository.
2. Open **Power BI Desktop**.
3. Go to **File → Open report** and select `Data_Leverager_pbix.pbix`.
4. If prompted, refresh the data source credentials.

### Refreshing Data

The data model is embedded within the `.pbix` file. To connect to live/updated data sources:

1. Go to **Home → Transform data → Data source settings**.
2. Update the source connection strings to point to your data.
3. Click **Refresh** to reload.

---

## 📐 Data Model Design Notes

- Sales data is split across **three separate tables by year** (2020, 2021, 2022). For consolidated year-over-year analysis, these should be appended or unioned via Power Query.
- The **Calendar Lookup** table enables time intelligence functions (YTD, MoM, YoY comparisons).
- The **Product hierarchy** spans two levels: `Product Lookup → Product Subcateg → Product Categori`.
- **Returns Data** is modelled as a separate fact table, allowing return rate calculations alongside sales metrics.

*Generated from `Data_Leverager_pbix.pbix` — Power BI 2026.04*
