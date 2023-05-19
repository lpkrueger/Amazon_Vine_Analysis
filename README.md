# Amazon_Vine_Analysis
Module 17, Big Data - UNCCH Data Analytics Bootcamp, Spring 2023

## Project Overview

### Purpose
In this exercise, I assisted Jennifer in analyzing Amazon reviews that were written by members of the paid Amazon Vine program, which allows manufacturers and publishers to receive reviews for their products, and looked for bias between paid and upaid reviews. 

## Method
PySpark was used to perform the ETL process to extract one dataset from a group of over 50 datasets, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Then, PySpark was employed to determine if there is any bias toward favorable reviews from Vine members in the dataset. 

From the Module 17 Challenge:
```
    Deliverable 1: Perform ETL on Amazon Product Reviews
    Deliverable 2: Determine Bias of Vine Reviews
    Deliverable 3: A Written Report on the Analysis (README.md)
```

for this study, a dataset of US reviews of pet products was employed from the following source: https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Pet_Products_v1_00.tsv.gz

- Link to schema file for creating tables using PostGres pgAdmin
    - [challenge_schema](challenge_schema.sql)

- Links to notebook files for analysis using PySpark in Google Colab
    - [Amazon_Reviews_ETL](Amazon_Reviews_ETL.ipynb)
    - [Vine_Review_Analysis](Vine_Review_Analysis.ipynb)

## Results
- Of the 38,010 total reviews in this sample: 
    -  There were 170 5-star Vine (paid) reviews in this sample
    - There were 37,840 5-star non-Vine (unpaid) reviews in this sample

- Only 0.5% of 5-star reviews were from Vine (paid) members, while 99.5% were from non-Vine (unpaid) members. This indicates that the paid membership does not introduce any measureable bias toward Vine members. 

Vine Table
    ![vine_table](/vine_table.png)

## Summary 

Based on this analysis, there is an insignificant quantitiy of high-scoring paid reviews compared to unpaid reviews, so there is no measureable bias toward having the paid program in this particular case, without further investigation. 

To better learn whether there is bias toward the paid Vine program for receiving 5-star reviews, it would be important to determine the average score of both paid and upaid reviews, then compare those averages. If the average review score for the paid program is higher than the unpaid average review score, then there could be more evidence of bias. 

