# gcp-lakehouse-data-engineering
End-to-end Lakehouse architecture on Google Cloud (Bronze / Silver / Gold) with BigQuery, Cloud Storage and Airflow.

# GCP Lakehouse – Data Engineering Architecture

This repository showcases a conceptual and practical approach to building a modern Lakehouse on Google Cloud Platform, following industry best practices for scalability, governance, and cost optimization.

## Architecture Overview

The solution is based on a layered Lakehouse architecture:

### Bronze Layer
- Raw data ingestion from multiple sources (APIs, transactional systems, files).
- Stored in Google Cloud Storage.
- Immutable, append-only data.
- Schema-on-read.

### Silver Layer
- Data cleansing, normalization, and enrichment.
- Implemented using:
  - Cloud Dataflow (Apache Beam) for scalable ETL
  - Dataproc (Spark) when advanced transformations are required
- Application of data quality validations and business rules.

### Gold Layer
- Curated datasets optimized for analytics and BI.
- Implemented in BigQuery.
- Optimized using:
  - Partitioning by time
  - Clustering by business keys
- Ready for consumption by BI tools and ML workloads.

## Orchestration
- Cloud Composer (Apache Airflow) for pipeline orchestration.
- Modular, idempotent DAGs.
- Separation of environments (dev / qa / prod).

## Data Governance
- Metadata management using Data Catalog / Dataplex.
- IAM-based access control.
- Clear ownership and dataset documentation.
- Support for lineage and auditability.

## Engineering Best Practices
- SQL standards and optimization for BigQuery.
- Python following PEP8 guidelines.
- Version control using Git.
- CI/CD-ready structure.
- Support for Slowly Changing Dimensions (SCD1 / SCD2).

## Objective
This repository demonstrates data engineering decision-making, architectural patterns, and best practices aligned with enterprise-scale analytics platforms on Google Cloud.
