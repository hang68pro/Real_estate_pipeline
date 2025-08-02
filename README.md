# Real_estate_pipeline
Real Estate Data Pipeline: End-to-end ETL pipeline extracting, transforming, and loading housing market data from Redfin into SQLite and AWS S3 using Python and pandas.
# 🏡 Real Estate Data Pipeline

This project builds a complete data pipeline that extracts housing market data from Redfin, cleans and transforms the dataset, stores it in SQLite, and optionally uploads a versioned Parquet file to AWS S3. The pipeline is modular, using Python scripts organized by ETL phase.

## 🔧 Tech Stack
- Python 3.10
- Pandas
- SQLAlchemy (SQLite)
- Parquet (via `pandas`)
- AWS S3 (via Boto3)
- Docker (optional)
- Redfin Housing Market CSVs

## 📁 Pipeline Structure
```bash
real_estate_pipeline/
├── data/                  # Raw CSVs from Redfin
├── etl/
│   ├── extract.py         # Reads CSV
│   ├── transform.py       # Cleans & reshapes data
│   └── load.py            # Saves to SQLite & Parquet
├── config/
│   └── settings.py        # AWS / DB paths
├── output/                # Versioned Parquet outputs
├── pipeline.py            # Runs full pipeline
├── requirements.txt
├── .env                   # AWS credentials (excluded from Git)
└── README.md

📦 Example Output
output/2025-08/redfin_data.parquet

real_estate.db with a redfin_data table

🚀 Future Add-ons
Dockerized container for deployment

Airflow DAG for automation

Visualizations of market trends
