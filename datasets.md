# Datasets

## Overview

This directory contains the datasets used in the **NYC Taxi Lakehouse Data Pipeline Project**. These datasets serve as the primary data source for ingestion, transformation, and analytics workflows.

## Dataset Source

**Dataset Name:** NYC Yellow Taxi Trip Records

**Provider:** New York City Taxi & Limousine Commission (TLC)

**Official Source:** https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page

## Dataset Description

The NYC Yellow Taxi Trip Records dataset contains detailed information about taxi trips in New York City, including trip timestamps, passenger counts, trip distances, fare details, payment information, and pickup/drop-off location identifiers.

The dataset is widely used for data engineering, big data processing, analytics, and machine learning applications.

## File Format

* Format: Parquet
* Data Type: Structured Transportation Data
* Frequency: Monthly Releases

## Dataset Schema

| Column Name           | Description                       |
| --------------------- | --------------------------------- |
| VendorID              | Taxi service provider identifier  |
| tpep_pickup_datetime  | Pickup date and time              |
| tpep_dropoff_datetime | Drop-off date and time            |
| passenger_count       | Number of passengers              |
| trip_distance         | Distance traveled during the trip |
| RatecodeID            | Rate code applied to the trip     |
| store_and_fwd_flag    | Trip record storage indicator     |
| PULocationID          | Pickup location identifier        |
| DOLocationID          | Drop-off location identifier      |
| payment_type          | Payment method used               |
| fare_amount           | Base fare amount                  |
| extra                 | Additional charges                |
| mta_tax               | MTA tax amount                    |
| tip_amount            | Passenger tip amount              |
| tolls_amount          | Toll charges                      |
| improvement_surcharge | Improvement surcharge             |
| total_amount          | Total trip cost                   |
| congestion_surcharge  | Congestion surcharge              |
| Airport_fee           | Airport-related fee               |

## Data Usage

This dataset is utilized for:

* Data Ingestion and Storage
* Data Cleaning and Validation
* Exploratory Data Analysis (EDA)
* Business Intelligence and Reporting
* Data Engineering Pipeline Development
* Performance and Trend Analysis

## Note

Large dataset files are not included in this repository due to GitHub storage limitations. The data can be downloaded directly from the official NYC TLC website using the source link provided above.

