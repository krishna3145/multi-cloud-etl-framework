# multi-cloud-etl-framework

Production-grade multi-cloud ETL framework supporting AWS S3, Azure ADLS Gen2, and Google Cloud Storage with unified connector pattern, format conversion, and audit trail.

## Architecture

```
Source (AWS / Azure / GCP)
        ↓
  CloudConnector (abstract)
  ├── AWSConnector    → S3 via boto3
  ├── AzureConnector  → ADLS Gen2 via azure-storage
  └── GCPConnector    → GCS via google-cloud-storage
        ↓
  MultiCloudETL Engine
  ├── Format conversion: Parquet ↔ Avro ↔ ORC ↔ CSV
  ├── Audit columns injection
  ├── Partition writing
  └── Compression handling
        ↓
  Target (AWS / Azure / GCP)
```

## Supported Combinations

| Source | Target | Use Case |
|--------|--------|----------|
| AWS S3 | Azure ADLS | McKesson clinical → Databricks analytics |
| Azure ADLS | GCP BigQuery | Cross-cloud ML training |
| GCP GCS | AWS S3 | Backup and disaster recovery |

## Tech Stack

`AWS S3` `Azure ADLS Gen2` `GCP Cloud Storage` `Apache Spark` `Parquet` `Avro` `ORC` `Python` `Terraform`
