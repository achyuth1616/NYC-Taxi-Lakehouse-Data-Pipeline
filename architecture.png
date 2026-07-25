┌─────────────────────────────┐
│ NYC Taxi Dataset (Parquet)  │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│     Databricks Volume       │
│      Raw Data Storage       │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│       Unity Catalog         │
│  Data Governance Layer      │
└──────────────┬──────────────┘
               │
               ▼
┌─────────────────────────────┐
│     Bronze Delta Table      │
│       Raw Data Layer        │
└──────────────┬──────────────┘
               │
        PySpark ETL
               ▼
┌─────────────────────────────┐
│     Silver Delta Table      │
│  Cleaned & Validated Data   │
└──────────────┬──────────────┘
               │
   PySpark Aggregations & KPI
               ▼
┌─────────────────────────────┐
│      Gold Delta Table       │
│   Business-Ready Metrics    │
└──────────────┬──────────────┘
               │
      ┌────────┴────────┐
      ▼                 ▼
┌─────────────┐  ┌─────────────┐
│ Databricks  │  │  Power BI   │
│ SQL Queries │  │ Dashboards  │
└─────────────┘  └─────────────┘
