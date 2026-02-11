# Fraud Detection ETL Pipeline (Databricks)

## Overview

Enterprise-grade ETL pipeline built using Databricks (Unity Catalog) following the Medallion Architecture: Bronze → Silver → Gold.

This project demonstrates data ingestion, normalization, risk modeling, and dashboard creation using Delta Lake.

---

## Architecture

RAW (Volume Storage)
    ↓
Bronze (Raw Delta Tables)
    ↓
Silver (Normalized Fact & Dimensions)
    ↓
Gold (Business Metrics & Dashboards)

---

## Data Source

Simulated financial transaction dataset (~500MB JSON files)

Includes:
- Transactions
- Fraud reports
- Customer data
- Country codes

---

## Bronze Layer

- Raw JSON ingested into Delta
- No transformations
- Added ingest_time for lineage

---

## Silver Layer

Normalized schema:

### Fact Table
- silver_fact_transactions

### Dimension Tables
- silver_dim_accounts
- silver_dim_country
- silver_dim_fraud_flags

---

## Gold Layer

Analytics-ready datasets:

- gold_risk_indicators
- gold_cross_border_activity
- gold_transaction_kpis
- gold_transactions_summary

---

## Risk Logic

- OVERDRAFT → unauthorized flag = 1
- HIGH_AMOUNT → amount >= 200000
- NORMAL → everything else

---

## Dashboard

Built in Databricks SQL:

- Risk distribution
- Cross-border flows
- KPI summary
- Transaction trends

---

## Key Learnings

- Unity Catalog path restrictions
- Delta schema evolution
- Join debugging
- Materialized view limitations
- Dashboard visualization constraints

---

## Tech Stack

- Databricks
- Delta Lake
- PySpark
- SQL
- Unity Catalog

---

## Future Improvements

- Incremental MERGE pipeline
- Watermark-based ingestion
- Streaming ingestion
- Real fraud scoring model

---

## Author

Shreyash Patel  
Transitioning from Software Development → Data Engineering  
