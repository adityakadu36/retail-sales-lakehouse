# retail-sales-lakehouse

A retail sales lakehouse built on Databricks using the Brazilian E-Commerce Public Dataset by Olist.

## Overview

This project implements a medallion architecture lakehouse on Databricks using the Olist retail dataset. Raw CSV files are stored in the `retail_data` Volume under the Bronze schema and processed through three layers — Bronze, Silver, and Gold.

## Architecture: Bronze → Silver → Gold

- **Bronze** — ingests raw files into Delta tables with explicit schemas and lineage metadata columns
- **Silver** — cleans, deduplicates, and transforms the data, resolving joins and data quality issues
- **Gold** — builds aggregated tables for reporting and downstream consumption

## Dataset — Olist Brazilian E-Commerce

Source: https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce

The dataset is not included in this repository. Download it from the link above and upload the CSV files to the Bronze Volume.

## Tech Stack

- Databricks
- PySpark
- Spark SQL
- Delta Lake
- Unity Catalog

## Setup

Before running any pipeline notebook for the first time, run `notebooks/setup/00_create_catalog_schemas.ipynb` once to create the catalog and Bronze/Silver/Gold schemas.

## Project Status

- Bronze — complete ✓
- Silver — in progress ((customers + orders + order_items complete))
- Gold — planned

## Repo Structure
```
retail-sales-lakehouse/
├── README.md
├── .gitignore
└── notebooks/
    └── bronze/
        └── Bronze__Ingestion.ipynb
​```
