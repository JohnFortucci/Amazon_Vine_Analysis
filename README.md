# Amazon Vine Analysis

## Introduction

Using the Amazin datasets we be analyzing Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. Companies like SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

We will be selecting one of the datasets available and perform the following :- 

1) Load the data into an AWS RDS and query the data loaded using Postgres.
2) Use Pyspark to determine if there is any bias for favorable reviews from Vine members.
3) Write a written summary of the findings

## Deliverable 1 - Load the data into an AWS RDS and query the data loaded.

### Overview

An AWS RDS is created , connect to the instance using pgADmin. Using create 4 tables and transform the Amazon review selected and insert the data in the appropriate table , query the tables to ensure data has been loaded.

### Results

The following tables are created via pgAdmin

![pgAdmin Tables](/Resources/Tables.png)

Excecuting the script : Amazon_Reviews_ETL.ipynb to load the data into the appropriate tables.

The image below shows the initial dataframe created when the Amazon review data is loaded.

![Initial DF](/Resources/initial_df.PNG)

The image below shows that 4 data frames created from the initial data load , these dataframes are written to the respective database tables.

![Split data frames](/Resources/Split_data_frames.PNG)

The image below shows the respective counts for each of the tables.

![Table counts](/Resources/SQL_Counts.PNG)

The image below shows 5 entries for each of the tables.

![Table counts](/Resources/Queries.PNG)

## Deliverable 2 - Determine if there is any bias for favorable reviews from Vine members.

### Overview

Using PySpark determine if there is any bias towards reviews that were written as part of the Vine program from the dataset selected.

### Results


