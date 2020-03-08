# Big-Data-Analytics-on-Amazon-Customer-Reviews

Performed analysis using Hadoop MapReduce, chaining, secondary sorting, joins, binning, summarization and filtration patterns. 
Also made use of Apache Pig to perform some analysis along with Mahout for recommendations. 

## Abstract:
Analysis of amazon is very crucial part when it comes to find an efficient way of getting insights on customer reviews about different products. Hence, this project is mainly aimed to analyze big data and produce an informative result about the customer reviews for the product Camera present on Amazon using Hadoop architecture, Mahout and Pig

## Dataset:
### Dataset Link: 
https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Camera_v1_00.tsv.gz

### Accessing the data:
Data is present in the Amazon S3 bucket. It can be accessed as mentioned in below link –
 https://s3.amazonaws.com/amazon-reviews-pds/readme.html

### About the data:
DATA FORMAT -
Tab ('\t') separated text file, without quote or escape characters. This dataset is 1GB in size.
First line in the file is header; 1 line corresponds to 1 record.

DATA COLUMNS:
marketplace            - 2 letter country code of the marketplace where the review was written.
customer_id            - Random identifier that can be used to aggregate reviews written by a single author.
review_id                 - The unique ID of the review.
product_id               - The unique Product ID the review pertains to. In the multilingual dataset the reviews for the same product in different countries can be grouped by the same product_id.
product_parent       - Random identifier that can be used to aggregate reviews for the same product.
product_title            - Title of the product.
product_category    - Broad product category that can be used to group reviews 
                                      (also used to group the dataset into coherent parts).
star_rating                - The 1-5 star rating of the review.
helpful_votes           - Number of helpful votes.
total_votes               - Number of total votes the review received.
vine                            - Review was written as part of the Vine program.
verified_purchase   - The review is on a verified purchase.
review_headline      - The title of the review.
review_body            - The review text.
review_date             - The date the review was written.

## Data Analysis:
1.	Find the total number of products present in the dataset
2.	Find the average product rating reviews for each product
3.	Find the topN reviewed products sorted by count
4.	Find total product rating for all those products which are present in the topN reviewed products
5.	Find all the users who has reviewed each product
6.	Find all the records partitioned by the date in which the product was reviewed
7.	Find all the product information for each unique star rating of the product by dividing it  into different categories/bins
8.	Recommend the products to the user based on the star rating
9.	Find the count of the reviews grouped by date for each product
10.	Find the count of products for each product star rating

## Techniques/Technologies Used:
1.	Hadoop MapReduce
2.	Summarization Pattern – Numerical Summarization, Inverted Index
3.	Joins – Reduce Side Inner Join
4.	Partitioning
5.	Secondary Sorting
6.	MapReduce Chaining
7.	Filtering Pattern – TopN filtering pattern
8.	Binning Pattern
9.	Mahout Recommendation
10.	 Apache Pig

## Additional Notes:
1.	Dataset was taken from Amazon S3 bucket on cloud using AWS-CLI
2.	Implemented logging using log4j in almost all analysis
3.	Implemented MultipleInputs in Reduce Side Join Pattern
4.	Implemented MultipleOutputs in Binning pattern
5.	Used a Custom Partitioner
6.	Used to Combiner in TopN filtering pattern
7.	Implemented a WritableComparator class while performing secondary sorting
8.	Used MapReduce Chaining to chain various job in analysis
9.	Ran pig script in local mode and used the grunt shell
