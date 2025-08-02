# Housing Market Tracker - Real Estate Data Pipeline

## Project Overview

This project builds a modular, automated ETL pipeline to extract, transform, and load U.S. housing market data from Redfin dataset. The pipeline stores cleaned data in a local SQLite database and uploads Parquet files to AWS S3 for further analysis and visualization.

## Features

- Extracts Redfin Monthly Housing Market Data at https://www.redfin.com/news/data-center/ 
- Cleans and reshapes wide-formatted CSV data into a long format
- Calculates additional metrics such as monthly and year-over-year changes
- Stores data in SQLite and saves Parquet files locally and on S3
- Containerized with Docker for reproducibility
- (Future) Supports automated orchestration with Airflow
- (Future) Interactive dashboard for user-driven analysis

# Project Structure

real_estate_pipeline/
├── etl/
│ ├── extract.py # Data extraction logic
│ ├── transform.py # Data cleaning and transformation
│ └── load.py # Loading data to SQLite and S3
├── main.py
├── config/
│ └── settings.py # Configuration for paths and credentials
├── pipeline.py # Main script to run the full ETL process
├── requirements.txt # Python dependencies
├── Dockerfile # Docker container definition
├── README.md # Project documentation
└── .env # environment variables for AWS credentials



## Getting Started

### Prerequisites

- Python 3.10+
- AWS account with access to an S3 bucket
- Docker (for containerization)

### Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/real_estate_pipeline.git
   cd real_estate_pipeline

2. Add .env File
AWS_ACCESS_KEY_ID=your-access-key
AWS_SECRET_ACCESS_KEY=your-secret-key
AWS_DEFAULT_REGION=us-west-1
S3_BUCKET_NAME=your-s3-bucket-name

3. Build the Docker Image
docker build -t real-estate-pipeline .

4. Run the Container
docker run --env-file .env real-estate-pipeline

📦 Dependencies
Python 3.10 (via Docker)
boto3 AWS SDK for uploading to S3
pandas For data manipulation
Install manually with:
pip install -r requirements.txt

🧪 Future Enhancements
Build a Streamlit dashboard for visualization
Integrate with Airflow for scheduling
Add logging and unit tests
Include validation rules for incoming data

📜 License
This project is for educational and personal portfolio use.

🙋‍♀️ Author
Hang Tran
