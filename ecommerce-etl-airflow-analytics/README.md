# E-Commerce ETL Pipeline with Python, SQL, Airflow and AI for sentiment analysis

## 1. Overview

This project is an end-to-end ETL pipeline for a e-commerce platform.

**Goals:**

- Ingest raw CSV data about customers, products, orders, order items and reviews
- Load raw data into staging tables
- Transform data into a star-schema warehouse using SQL
- Orchestrate the pipeline with Apache Airflow
- Enrich product reviews with basic sentiment analysis

Focus is on **Python + SQL + Airflow**.  
AI is used for enrichment step.

---

## 2. Architecture

Layers:

1. **Raw layer** – CSVs in `data/raw/`
2. **Staging layer** – `stg_*` tables (1:1 with raw files)
3. **Warehouse layer** – dimensions (`dim_*`) and facts (`fact_*`)
4. **Analytics layer** – SQL models (e.g., product review summary)

High-level flow:

Raw CSV → Staging → Dimensions/Facts → Analytics Views

(See `diagrams/architecture.png` – add later.)

---

## 3. Data Model

**Source entities:**

- `customers` – customer profile info
- `products` – product catalog
- `orders` – one row per order
- `order_items` – line items per order
- `reviews` – text reviews and ratings

**Warehouse (star-schema):**

- Dimensions:
  - `dim_customer`
  - `dim_product`
  - `dim_date`
- Facts:
  - `fact_orders`
  - `fact_order_items`
- Enriched:
  - `reviews_enriched` (sentiment tags)

(See `diagrams/erd.png` – add later.)

---

## 4. Tech Stack

- **Language:** Python 3
- **Orchestration:** Apache Airflow
- **Database:** PostgreSQL
- **Storage:** Local CSV files
- **AI:** Simple sentiment analysis using a pre-trained model (e.g., TextBlob or HuggingFace)

---

## 5. Repository Structure

```text
ecommerce-etl-airflow-analytics/
├── dags/                     # Airflow DAGs
├── sql/                      # DDL + models + DQ checks
├── data/                     # Raw and sample data
├── src/                      # Python ETL + utils + AI enrichment
├── notebooks/                # Optional exploration
├── diagrams/                 # Architecture and ERD diagrams
└── README.md
