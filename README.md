# NBA-Datalake
### Project Overview
This project automates the creation of a data lake for NBA analytics using AWS services. The setup_nba_data_lake.py script integrates Amazon S3, AWS Glue, and Amazon Athena and sets up the infrastructure needed to store and query NBA-related data.

### Features
* Creates an Amazon S3 bucket to store raw and processed data
* Uploads sample NBA data (JSON format) to the S3 bucket
* Creates an AWS Glue database and an external table for querying the data
* Configures Amazon Athena for querying data stored in the S3 bucket

### Technical Architecture
* Language: Python 3.x
* Cloud Provider: AWS (S3)
* External API: NBA API
* Dependencies:
    * boto3 (AWS SDK)
    * json
    * time
    * requests
    * load_dotenv
    * os

### Project Structure
```bash
nba-datalake/
├── src/
│   ├── setup_nba_data_lake.py
├── .gitignore
└── README.md
```

### Setup Instructions
#### Prerequisites
1. SportsData.io API Key:
   * Create a free account on SportsData.io.
   * Navigate to "Developers" > "API Resources" > "NBA".
   * Locate your API key under "Query String Parameters".
2. AWS Permissions: Ensure the user or role running the script has the required IAM permissions.
    * S3:
      * s3:CreateBucket
      * s3:PutObject
      * s3:DeleteBucket
      * s3:ListBucket
    * Glue:
      * glue:CreateDatabase
      * glue:CreateTable
      * glue:DeleteDatabase
      * glue:DeleteTable
    * Athena:
      * athena:StartQueryExecution
      * athena:GetQueryResults
#### Steps to Set Up the NBA Data Lake
1. Clone the repository: --bash git clone https://github.com/ahmedb24/weather-dashboard.git
2. Install dependencies: --bash pip install -r requirements.txt
3. Configure environment variables (.env): --bash NBA_ENDPOINT=your_nba_endpoint, SPORTS_DATA_API_KEY=your_sports_data_api_key, AWS_BUCKET_NAME=your_aws_bucket_name
4. Configure AWS credentials: --bash aws configure
5. Run the application: --bash python src/setup_nba_data_lake.py

### Future Enhancements
* Automate data ingestion with AWS Lambda
* Implement a data transformation layer with AWS Glue ETL
* Add advanced analytics and visualizations (AWS QuickSight)