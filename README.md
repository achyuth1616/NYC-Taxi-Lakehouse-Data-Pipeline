# NYC Taxi Lakehouse Data Pipeline Project

## Overview

This project implements an end-to-end Data Engineering pipeline using the Medallion Architecture (Bronze, Silver, and Gold layers) to process and analyze NYC Yellow Taxi trip data. The solution leverages Databricks, PySpark, Delta Lake, SQL, and Power BI to transform raw taxi trip records into business-ready analytical datasets and interactive dashboards.

The project processes over **10 million taxi trip records** and demonstrates data ingestion, cleansing, transformation, aggregation, and visualization workflows.

## Architecture

```text
NYC TLC Yellow Taxi Parquet Files
                │
                ▼
      Databricks Volume (Raw)
                │
                ▼
          Bronze Layer
      (Raw Delta Tables)
                │
                ▼
          Silver Layer
 (Data Cleaning & Feature Engineering)
                │
                ▼
           Gold Layer
 (Business Aggregations & KPIs)
                │
                ▼
      Power BI Dashboard
```

### Source

NYC Yellow Taxi Trip Records Dataset

https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page

### Files Used

- yellow_tripdata_2026-01.parquet
- yellow_tripdata_2026-02.parquet
- yellow_tripdata_2026-03.parquet

### Dataset Schema

| Column Name | Description |
|------------|-------------|
| VendorID | Taxi technology provider identifier |
| tpep_pickup_datetime | Pickup timestamp |
| tpep_dropoff_datetime | Dropoff timestamp |
| passenger_count | Number of passengers |
| trip_distance | Distance traveled (miles) |
| RatecodeID | Trip rate code |
| store_and_fwd_flag | Delayed transmission indicator |
| PULocationID | Pickup location ID |
| DOLocationID | Dropoff location ID |
| payment_type | Payment method |
| fare_amount | Base fare amount |
| extra | Additional charges |
| mta_tax | MTA tax |
| tip_amount | Tip amount |
| tolls_amount | Toll charges |
| improvement_surcharge | Improvement surcharge |
| total_amount | Total trip charge |
| congestion_surcharge | Congestion surcharge |
| Airport_fee | Airport pickup fee |
| cbd_congestion_fee | CBD congestion fee |

---

## Technology Stack

- Databricks
- Apache Spark (PySpark)
- Delta Lake
- SQL
- Power BI
- Git & GitHub

---

## Bronze Layer

### Objectives

- Load raw Parquet files into Databricks
- Preserve source data without modifications
- Store data in Delta format

### Operations Performed

- Raw data ingestion
- Schema validation
- Delta table creation

---

## Silver Layer

### Objectives

Improve data quality and prepare datasets for analytics.

### Data Quality Issues Identified

| Column | Null Records |
|----------|------------:|
| passenger_count | 3,057,123 |
| RatecodeID | 3,057,123 |
| store_and_fwd_flag | 3,057,123 |
| congestion_surcharge | 3,057,123 |
| Airport_fee | 3,057,123 |

### Data Cleaning

Removed records with:

- trip_distance <= 0
- fare_amount <= 0
- total_amount <= 0
- trip_duration_minutes <= 0

### Null Handling

- Filled passenger_count with 0
- Filled RatecodeID with 0
- Filled congestion_surcharge with 0
- Filled Airport_fee with 0
- Replaced store_and_fwd_flag nulls with "Unknown"

### Feature Engineering

Created derived columns:

- trip_date
- pickup_hour
- trip_duration_minutes
- day_of_week
- trip_month

---

## Gold Layer

Business-ready aggregated datasets created for reporting and analytics.

### Daily KPI

Contains:

- total_trips
- total_revenue
- avg_trip_distance
- avg_trip_duration

### Monthly KPI

Contains:

- month
- total_trips
- total_revenue
- avg_distance
- avg_duration

### Additional Gold Tables

- payment_analysis
- payment_revenue
- trips_by_hour
- duration_by_hour
- location_revenue
- top_pickup_locations
- top_dropoff_locations
- trips_by_day
- revenue_by_day

---

## Power BI Dashboard

### Daily Analytics Dashboard

#### KPI Cards

- Total Trips
- Total Revenue
- Average Trip Distance
- Average Trip Duration

#### Visualizations

- Daily Revenue Trend
- Trips by Hour
- Revenue by Payment Type
- Top Pickup Locations
- Top Dropoff Locations
- Location Revenue Analysis

### Monthly Analytics Dashboard

#### KPI Cards

- Monthly Revenue
- Monthly Trips
- Average Distance
- Average Duration

#### Visualizations

- Revenue by Month
- Trips by Month
- Revenue by Day of Week
- Trips by Day of Week

---

## Key Insights

- Processed over 10 million NYC taxi trip records.
- Built a Medallion Architecture using Databricks and Delta Lake.
- Improved data quality through cleansing, validation, and transformation.
- Generated business-ready Gold datasets for analytics and reporting.
- Developed interactive Power BI dashboards for operational and business insights.
- Implemented KPI aggregation for daily and monthly trend analysis.
  
---
```

NYC-Taxi-Lakehouse-Data-Pipeline/
│
├── README.md
├── architecture.png
├── datasets.md
│
├── notebooks/
│   ├── EDA/
│   ├── Bronze_Ingestion/
│   ├── Silver_Transformation/
│   ├── Gold_Aggregations/
│   └── SQL_Queries/
│
├── screenshots/
│   ├── raw_data_volume.png
│   ├── bronze_table.png
│   ├── silver_table.png
│   └── gold_tables.png
│
└── powerbi/
    ├── NYC_Taxi_Analytics_Dashboard.pbix
    ├── daily_analytics.png
    └── monthly_analytics.png
```




## Power BI Dashboard

The Power BI dashboard was built using the Gold Layer analytics generated in Databricks.

### Key Insights
- Total Trips
- Total Revenue
- Average Fare Amount
- Daily Trip Trends
- Monthly Analytics
- Peak Pickup Hours

### Dashboard File
`powerbi/NYC_Taxi_Analytics_Dashboard.pbix`

### Dashboard Screenshots

## Dashboard Preview

### Daily Analytics Dashboard
<img width="1161" height="652" alt="dashboard1" src="https://github.com/user-attachments/assets/3b5fba23-eb53-49a8-8373-8e6b565f0650" />


### Monthly Analytics Dashboard

<img width="1157" height="647" alt="monthly_analytics" src="https://github.com/user-attachments/assets/a89dcc9a-753f-406e-8759-c8a0c48733c4" />


---

## Author
Vadlakonda Achyuth Sai

**B.Tech Artificial Intelligence**  
**Anurag University**

Skills: Databricks • PySpark • SQL • Delta Lake • Power BI • Data Engineering
