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

The objective is to load an initial dataset and create a dataframe contain vine and rating related fields , and perform a series of filter to determine percentage values for 5-star paid reviews versus 5-star unpaid reviews to determine if the a bias towards paid reviews.

The image below shows the initial data load count.

![Initial load counts](/Resources/Initial_load_count.png)

The image below shows the vine data frame created from a subset of the initial dataframe fields and counts , we can see from the image the fields required and the count matches the initial data load , therefore no data has been lost in the transformation.

![Initial load counts](/Resources/Vine_DF_with_count.png)

The image below shows the count of the data frame created after applying a filter to keep only entries with a total_votes count of greater than or equal to 20.

![Filter 1](/Resources/Filter_1_count.png)

The image below shows the count of the data frame created after applying a further filter to keep only entries with a where helpful_votes divided by total_votes is greater that 50%

![Filter 1](/Resources/Filter_2_count.png)

The image below shows the count of the dataframe created for reviews that are part of the vine program (paid reviews).

![Filter 1](/Resources/Filter_vine_Y_count.png)

The image below shows the count of the dataframe created for 5-star reviews that are part of the vine program (paid reviews).

![Filter 1](/Resources/Vine_paid_5_star.png)

The image below shows the count of the dataframe created for reviews that are not part of the vine program (unpaid reviews).

![Filter 1](/Resources/Filter_vine_N_count.png)

The image below shows the count of the dataframe created for 5-star reviews that are not part of the vine program (unpaid reviews).

![Filter 1](/Resources/Vine_unpaid_5_star.png)

The image below shows the percentage of 5-star review for vine reviewers.

![Filter 1](/Resources/Vine_paid_percentage.png)

The image below shows the percentage of 5-star review for vine reviewers.

![Filter 1](/Resources/Vine_unpaid_percentage.png)

## Deliverable 3 - Bias Conclusion and further analysis

### 5-Star rating bias

Using the above percentage values in the results section , we can determine that the is approximately 12% increase in 5-star paid reviews (51%) Vs unpaid reviews (39%). 

This would indicate that there is a positivae bias as part of the vine program.

### Further Analysis

It should be noted from the results section that there are many more non-vine reviews than vine reviews , this may affect that bias conclusion , therefore a further analysis that would be benificial to support the conclusion would to perform the analysis for each of the star ratings and see if the percentage comparisons provide similar percentage results.  
