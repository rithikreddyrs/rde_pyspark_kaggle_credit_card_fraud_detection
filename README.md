# rde_pyspark_kaggle_credit_card_fraud_detection

## Report on Credit Card Fraud Detection Data Processing
### 1. Objective
The project focuses on processing and analyzing credit card transaction data to prepare it for fraud detection analysis.

### 2. Approach
#### Environment Setup:
Initialized a Spark session to handle large-scale data processing.
Imported necessary libraries for file handling, data manipulation, and analysis.

#### Data Ingestion:
Downloaded a credit card fraud dataset 'mlg-ulb/creditcardfraud' using the Kaggle API.
Extracted the dataset and loaded multiple copies into a single PySpark DataFrame.

#### Data Preparation:
Removed duplicate rows from the dataset.
Checked for missing values in all columns.
Renamed columns for consistency by converting to lowercase and replacing spaces with underscores.

#### Exploratory Data Analysis (EDA):
Computed dataset dimensions (number of rows and columns).
Displayed schema and descriptive statistics.
Calculated key statistics like mean, median, and mode for specific columns

#### Feature Engineering:
Normalized the "Amount" column using Z-score normalization and created additional features such as a logarithmic transformation of "Amount".
Stored the cleaned and processed dataset in Parquet format for efficient querying and storage.

#### SQL Queries:
Created a temporary view to run SQL queries for additional analysis:
Average normalized amount for fraudulent transactions.
Maximum normalized amount for non-fraudulent transactions.
Average logarithmic transaction amounts grouped by class.

### 3. Methodology
Data Ingestion: Centralized ingestion and consolidation of CSV files into a PySpark DataFrame.

Feature Engineering: Enhanced the dataset with additional features to improve downstream analytics or modeling.

Storage and Querying: Leveraged Spark SQL for summarizing data and saved processed data in an optimized format.

### Findings
Dataset Overview:
The dataset don't have any missing values or corrupt values, number of rows in the dataset after deduplication is: 283726, columns: 31

Statistical Insights:
Mean value of Class: 0.001667101358352777
Median of Amount: 22.0
Mode of Time: 3767.0

Calculated mean and standard deviation of the "Amount" column.
Performed normalization and transformation to improve data usability.

### Conclusion
The task effectively preprocesses a credit card transaction dataset for fraud detection. It handles the challenges of data cleaning, transformation, and storage while providing insights through SQL queries and statistical calculations. The output dataset is now ready for further analytical tasks or machine learning model development.