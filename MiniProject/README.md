# Mini Music Project ETL

## Table of Contents
1. [Overview](#overview)
2. [DDL scripts](#ddl-scripts)
3. [Design Diagram](#design-diagram)
4. [Discussion](#Discussion)
5. [ETL Pipeline](#ETLPipeline)
6. [Summary](#Summary)


## Overview
**Objective:** The Primary objective of this project is to develop a robust ETL pipeline for Sparkify, A music Streaming startup to facilitate the analysis of user activity and song play data. The project aims to migrate existing data warehouse to a data lake setup, leveraging Snowflake for enhances scalability and performance.


## DDL Scripts
```sql
-- Example DDL Script
create OR REPLACE TRANSIENT TABLE TECHCATALYST_DE.ZAYD.SONGS_DIM (
    song_id varchar(16777216),
    title    varchar(16777216),
    duration float
);

create OR REPLACE TRANSIENT TABLE TECHCATALYST_DE.ZAYD.USER_DIM (
    id varchar(16777216),
    firstname varchar (16777216),
    lastname varchar (16777216),
    gender varchar (10),
    level varchar (16777216)
);

create or replace TRANSIENT TABLE TECHCATALYST_DE.ZAYD.TIME_DIM (

    ts number(38,0),
    datetime timestamp,
    start_time varchar (16777216),
    dayofmonth number(38,0),
    weekofyear number(38,0)

);

create  or replace TRANSIENT TABLE TECHCATALYST_DE.ZAYD.ARTIST_DIM (

    artist_id varchar(16777216),
    artist_name varchar (16777216),
    artist_location varchar (16777216),
    artist_latitude float,
    artist_longitude float
);

create or replace TRANSIENT TABLE TECHCATALYST_DE.ZAYD.SONGPLAYS_FACT (
    id varchar(16777216),
    datetime_id varchar(16777216),
    level varchar(16777216),
    song_id varchar(16777216),
    artist_id varchar(16777216),
    sessionId varchar(16777216),
    location varchar(16777216),
    useragent varchar(16777216)
);

```

## Design Diagram
**Diagram Description**: The design below outlines the entire ETL process and data architecture for Sparkify.
![dataArchitechtureDiagram](image/miniprojectdd.jpg)


## ETL Pipeline
The ETL process for Sparkify extracts user activity and song data from JSON files in S3, transforms the data by cleaning and normalizing it,  and then reloading it into S3 with structured naming and categorization. Finally, the data is staged and loaded into Snowflake tables for detailed analysis and reporting.

