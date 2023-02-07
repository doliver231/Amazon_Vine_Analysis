# Amazon_Vine_Analysis

## Overview

The purpose of this project is to analyze Amazon reviews written by members of the paid Amazon Vine program. The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. There are companies that pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review.

In this project, we had access to approximately 50 datasets. Each one contains reviews of a specific product, from clothing apparel to wireless products. After picking one of these datasets, we must use PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. We will then determine if there is any bias toward favorable reviews from Vine members in our chosen dataset. Of the 50 datasets, I chose to analyze reviews that were made by users in the "Videogames" category.

## Resources

* Dataset from Amazon S3: [US Reviews - Video Games](https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Video_Games_v1_00.tsv.gz), 
* SQL Schema: [Table Creation Schema](https://github.com/doliver231/Amazon_Vine_Analysis/blob/main/challenge_schema.sql)
* Deliverable 1: [Google Colab - ETL on Amazon Reviews](https://github.com/doliver231/Amazon_Vine_Analysis/blob/main/Amazon_Reviews_ETL.ipynb)
* Deliverable 2: [Google Colab - Vine Reviews Bias Analysis](https://github.com/doliver231/Amazon_Vine_Analysis/blob/main/Vine_Review_Analysis.ipynb)
* Software/Languages: PySpark, Python, SQL, PostgreSQL, PgAdmin, Amazon Web Services (AWS), Amazon S3 Data Storage, Google Colab

## Results

![Vine Reviews](https://github.com/doliver231/Amazon_Vine_Analysis/blob/main/Images/Vine_Reviews.png)

#### How many Vine reviews and non-Vine reviews were there?

* Vine members made up only 0.23% (94) of the reviews whereas the remaining 99.77% were Non-Vine members (40,471).

#### How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

* Vine members gave 48 out of 94 reviews a 5 star rating.
* Non-Vine members gave 15,663 out of 40,471 reviews a 5 star rating.

#### What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

* 51.1% of the reviews for Vine members were rated 5 stars.
* 38.7% of the reviews for Non-Vine members were rated 5 stars.

## Summary

Based on the results, Vine members did show bias when rating their products considering that the percent difference between the percentages of Vine user 5-star ratings vs. Non-Vine user 5-star ratings was about 27%. However, we have to take into account that Vine members only made up less than 1% of the total reviews. 99.77% of the total reviews are from Non-Vine users. For video game products, it seems like Vine users rarely took the oppportunity to give their reviews versus Non-Vine users. 

We also had filtered the total Vine user data to show those that have more than 20 reviews per user. In addition, we also filtered the data to show the reviews whose percentages of helpful reviews was greater than 50%. In order to possibly see another perspective is to include all of the data rather than adding those filters. Reviewing the data as is would give us more information and allow us to further support our assumption.