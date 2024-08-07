# TechCatalyst Group 2 Capstone Project

## Team Members
- Samee Malik
- Zayd Ghaffar
- Sriya Patturi

## Repository Description
This repository contains all the work completed during the TechCatalyst training course. It showcases our approach to utilizing big data analytics for enhancing taxi fleet management in New York City, utilizing AWS, Snowflake, Databricks, and ThoughtSpot.

### Data Sources
- NYC Yellow Taxi Data
- NYC Green Taxi Data
- NYC Weather Data
- NYC Taxi Zone Lookup Data

## Problem Statement
Taxi companies in NYC struggle with fleet management due to unpredictable traffic and varying passenger demands, leading to revenue losses and decreased customer satisfaction.

## Solution Overview
We developed a data-driven approach using AWS technologies, Snowflake, and Databricks to analyze taxi data, identify peak traffic and high-demand areas, and predict trip durations. This enhances fleet management and improves customer service. We use Snowflake for data storage and staging, and ThoughtSpot for real-time data visualizations, which supports strategic decision-making and operational optimizations.

### Technologies Used
- **Databricks**: Used for data manipulation and running Spark jobs.
- **AWS S3**: Used for data storage and management.
- **AWS Athena**: Used for querying data directly from files in S3.
- **AWS Glue**: Employed for data cataloging and ETL processes.
- **Amazon SageMaker**: Utilized for creating and deploying machine learning models.
- **Snowflake**: Used for data warehousing, allowing scalable analysis.

### Snowflake Workflow
- **Data Staging:** Utilized external stages to direct Snowflake to data locations in S3.
- **Table Creation:** Created necessary columns for queries and views.
- **Data Loading:** Used the `COPY INTO` command to load data into Snowflake tables from S3, followed by basic querying to verify data integrity.
- **View Creation:** Developed different views for analysis and loaded them into ThoughtSpot.

### Data Transformations
- Joined Yellow and Green taxi datasets, ensuring correct data types and schema validation.
- Renamed columns for clarity and loaded Taxi Zone Lookup data, casting data types to match schema requirements.
- Performed feature engineering to add columns like day, hour, month, year, trip duration, airport binary, season, AM/PM, weekday/weekend, and pickup time block.
- Filtered out implausible records, specifically those with erroneous trip durations.
- Segregated data by year (2024) for focused analysis.
- Integrated historical weather data from Excel into a PySpark dataframe, ensuring data type consistency.
- Validated data to prevent data loss during final dataset transformations.

### Machine Learning with SageMaker
- Utilized SageMaker to build models predicting taxi trip durations.
- Iterated through five models, with successive improvements:
  1. Initial model with uncleaned data.
  2. Model with cleaned data.
  3. Outlier-filtered model (3 standard deviations).
  4. Model incorporating weather data.
  5. Simplified model focusing on the most influential features based on feature importance.

## Visualizations and Models
This folder contains code and screenshots of the data pipelines and machine learning models through various phases of development. Each phase highlights different aspects of the data and the effects of different transformations and cleaning processes.

