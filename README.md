# Amazon_Vine_Analysis

## Project Overview
" Big Data " is a popular buzzword in the data industry today. But what does the term mean, and why is it important in the broader
context of data science. In this analysis, we dig into the industry definition of "big data". We explore big data ecosystem including Spark which improves the 
process for handling big data versus Hadoop. After diving into some of the technologies, used with big data, we perform ETL on a dataset 
from Amazon Web Service (AWS). Cloud service let us store large amounts of data at remote locations rather than locally, on top of many other services.
This allows for more scalability and performance. 

This analysis can be summarized in the following steps:
- Use PySpark to perform the ETL process to extract the dataset 
- Transform the data
- Connect to an AWS RDS instance
- Load the transformed data into pgAdmin
- Use PySpark to determine if there is any bias toward favorable reviews from Vine members in the dataset 
- Write a summary of the analysis


## Resources
Software: [PySpark](https://colab.research.google.com/notebooks/welcome.ipynb)

Cloud Service : [AWS](https://aws.amazon.com/)


## Results
Using the knowledge of the cloud ETL process, we create an AWS RDS database with tables in pgAdmin, pick a dataset from the Amazon Review datasets (Links to an external site.), and extract the dataset into a dataframe. We transform the dataframe into four separate dataframes that match the table schema in pgAdmin. Then, we upload the transformed data into the appropriate tables and run queries in pgAdmin to confirm that the data has been uploaded.

The tables are design as follows:

1- **The customers_table dataframe**: 





<img src="https://github.com/halmasieh/Amazon_Vine_Analysis/blob/main/customer_table.PNG" width="400" height="400"  />






2- **The products_table dataframe**:




<img src="https://github.com/halmasieh/Amazon_Vine_Analysis/blob/main/products_table.PNG" width="400" height="400"  />





3- **The review_id_table dataframe**:




<img src="https://github.com/halmasieh/Amazon_Vine_Analysis/blob/main/review_id_table.PNG" width="550" height="400"  />



4- **The vine_table dataframe**:




<img src="https://github.com/halmasieh/Amazon_Vine_Analysis/blob/main/vine_table.PNG" width="550" height="400"  />




To determine if there is any bias towards reviews that were written as part of the Vine program. We determine if having a paid Vine review makes a difference in the percentage of 5-star reviews. Therefore we address the following questions:

1- How many Vine reviews and non-Vine reviews were there?

As shown in the following dataframe




<img src="https://github.com/halmasieh/Amazon_Vine_Analysis/blob/main/vine-unvine.PNG" width="500" height="500"  />





- The number of Vine reviews means ("vine=Y") is 94.
- The number of non-Vine reviews means ("vine=N") is 40471

The total number of reviews is 40565.

2- How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?

As shown in the following dataframes




<img src="https://github.com/halmasieh/Amazon_Vine_Analysis/blob/main/5-star.PNG" width="500" height="500"  />






- The number of 5-star Vine reviews is 48  .
- The number of 5-star un-Vine reviews is 15663 .

3- What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?

We claculated the percentage of 5-star Vine reviews versus un-Vine reviews as follows:

- The percentage of 5-star Vine reviews is 51.06%
- The percentage of 5-star un-Vine reviews is 38.70%




## Summary
According to the observed percentages attributed to 5-star Vine reviews versus 5-star un-Vine reviews, it can be stated that
since the percentage of Vine reviews gave 5-star ratings is higher than un-Vine reviews, so, we could probably tell that the Vine
program has a positive bias. 

In addition, as shown in the following table, 




<img src="https://github.com/halmasieh/Amazon_Vine_Analysis/blob/main/marketplace.PNG" width="500" height="500"  />




we filtered the vine table based on the verified_purchase and marketplace columns. 
This analysis shows in which marketplace the purchased item has occured the most and with this information, 
the per capita consumption of the country can be predicted. 







