# Amazon Review Analysis
______________

### Technologies used

* Spark 3.1.1
* AWS RDS
* Google Colab
* PostgreSQL

__________


## Overview & Purpose

Here we show a small exercise in harnessing Spark and AWS's RDS services; we pull cloud-hosted review data from Amazon's servers and run it through Spark and its Postgres driver to connect it to a AWS-hosted database. In this case, the dataset includes reviews from products solder under the "Kitchen" category.

We then run it through a basic ETL process to ensure the data fits the database's schema, and also run a basic, separate analysis in parallel surrounding Amazon's paid review program, Vine.

## Results

| Feature                  | n (%)        |
|--------------------------|--------------|
| Total reviews            | 99,046       |
| Paid reviews             | 1,207 (1)   |
| Unpaid reviews           | 97,839 (99) |
| Paid five star reviews   | 509 (42)    |
| Unpaid five star reviews | 45,858 (47) |

## Summary

The analysis above shows that Amazon's paid reviews as part of the Vine program make up a very small subset of the overall reviews for this category (1%). However, the proportions of five star reviews for both paid and unpaid groups are quite similar (42% vs 47%), suggesting that there isn't a positivity bias with paid reviews. 

Further statistical testing would need to be done to conclude whether this difference is indeed statistically significant, however. To validate the hypothesis that there is a positivity bias with paid reviews for this category, I would use a **two proportion z-test**. 

We could also expand our analysis to look at the distribution of ratings, stratified by paid versus unpaid, and report descriptive statistics on our findings. Furthermore, we could also use an NLP pipeline to perform a **sentiment analysis** to see whether positive sentiment reviews correlated with a five star rating.



