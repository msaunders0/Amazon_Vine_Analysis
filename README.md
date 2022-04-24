# Amazon_Vine_Analysis

## Amazon Vine
For those who are unaware, Amazon Vine is a service where "trusted" reviewers from the Amazon platform are selectively invited to partake in reviewing products that have not yet garnered much attention. Sellers are given the opportunity to provide free products to selected reviewers in order to earn "honest and unbiased" reviews for said products. Does this sound like incentivization for a positive review? Possibly, but lets take a look at the numbers.

## The Data
For this analysis, a dataset of customer reviews, provided by Amazon, was used (https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Home_Entertainment_v1_00.tsv.gz). The particular dataset that was chosen revolves around reviews for products in the Home Entertainment category. The data was filtered, using Pyspark, and hosted in a database via AWS RDS. Of particular interest for this analysis was the total number of paid vs. unpaid reviews, the number of 5-star paid vs. unpaid reviews, and the percentage of 5-star paid vs. unpaid reviews, which is reflected in the selected filters.

![image](https://github.com/msaunders0/Amazon_Vine_Analysis/blob/main/Resources/dataset.png)

## The Purpose
The purpose of this analysis is to test whether bias plays a role in producing favorable reviews from Vine participants. The results will be somewhat limited, however, given that they will only reflect measured bias in the sampled dataset and not the entire Amazon review ecosystem in its' entirety.

## The Results
<ul>
  <li> How many Vine reviews and non-Vine reviews were there?</li>
  <ul>
    ![image](https://github.com/msaunders0/Amazon_Vine_Analysis/blob/main/Resources/total_paid.png)<br />
    ![image](https://github.com/msaunders0/Amazon_Vine_Analysis/blob/main/Resources/total_unpaid.png)<br />
    <li> The total number of Vine reviews was 261.</li>
    <li> The total number of non-Vine reviews was 24,040.</li>
  </ul>
  <li> How many Vine reviews were 5 stars? How many non-Vine reviews were 5 stars?</li>
  <ul>
    ![image](https://github.com/msaunders0/Amazon_Vine_Analysis/blob/main/Resources/fivestar_paid.png)
    ![image](https://github.com/msaunders0/Amazon_Vine_Analysis/blob/main/Resources/fivestar_unpaid.png)
    <li> Total number of 5 starred Vine reviews was 106.</li>
    <li> Total number of 5 starred non-Vine reviews was 10,899. </li>
  </ul>
  <li> What percentage of Vine reviews were 5 stars? What percentage of non-Vine reviews were 5 stars?</li>
  <ul>
    ![image](https://github.com/msaunders0/Amazon_Vine_Analysis/blob/main/Resources/percentage_paid.png)
    ![image](https://github.com/msaunders0/Amazon_Vine_Analysis/blob/main/Resources/percentage_unpaid.png)
    <li> Percentage of 5 starred Vine reviews was 40.6%.</li>
    <li> Percentage of 5 starred non-Vine reviews was 45.3%.</li>
  </ul>
  
## Summary
Based on the above results from the corresponding dataset, there does not seem to be any sort of statistical positivity bias for Vine participants whose reviews were included in this analysis. This assertion is largely based on the fact that 40.6% of Vine participants produced 5 starred reviews vs. 45.3% 5 starred reviews from non-Vine participants. It's reasonable to note that the sample size for Vine vs. non-Vine reviewers is significantly different. Because of this significant difference, and for the sake of remaining objective, it would be advisable to take these results with a grain of salt without expanding the analysis to include additional datasets from other categories. If one were to compare results across multiple categories and increase the sample size of reviews from Vine participants, a much more accurate idea of the existence or non-existence of positivity bias in Vine reviews would then be reflected.
