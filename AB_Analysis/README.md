## A/B Testing Analysis: Increasing E-Commerce Conversion & Revenue
This project evaluates an A/B test conducted on an e-commerce platform to determine whether product and marketing changes improve conversion rates and overall revenue.

Using hypothesis prioritization frameworks (ICE and RICE) alongside statistical testing, the analysis identifies high-impact business initiatives and determines whether the experimental variant should be implemented.

<b>Result:</b>
Variant B delivered a statistically significant increase in conversion rate, making it the recommended rollout despite no significant change in average order value.
<br></br>


## Business Problem:
The marketing team proposed several initiatives to increase revenue, including:
<ul>
<li>Promotional campaigns</li>
<li>New traffic acquisition channels</li>
<li>Website feature enhancements</li>
</ul>
However, testing all ideas requires time and resources.
<p></p>
<b>Objectives:</b>
<ul>
<li>Prioritize hypotheses using structured frameworks</li>
<li>Evaluate performance through A/B testing</li>
<li>Measure impact on conversion and revenue</li>
<li>Identify and control for data anomalies</li>
</ul>
<br>
  
## Key Insights:
<ul>
<li>Conversion rate increased by 13.8%–16.8% in Variant B</li>
<li>Results are statistically significant (p < 0.05)</li>
<li>No statistically significant difference in average order value</li>
<li>A small number of high-value orders significantly skewed revenue metrics</li>
<li>Final recommendation: Deploy Variant B</li>
</ul>
<br>

## Description of the data
<p></p>

### Hypotheses Dataset:
| Column | Description |
| --- | --- |
| Hypotheses | Brief descriptions of the hypotheses |
| Reach | User reach, on a scale of one to ten |
| Impact |Impact on users, on a scale of one to ten |
| Confidence | Confidence in the hypothesis, on a scale of one to ten |
| Effort | Resources required to test a hypothesis, on a scale of one to ten. The higher the Effort value, the more resource-intensive the test |
<p>

### Orders Dataset:
| Column | Description |
| --- | --- |
| transactionId | Order identifier |
| visitorId | Identifier of the user who placed the order |
| date | Date of order |
| revenue | Revenue from the order |
| group | Experiment group (A or B) | 
<p>

### Visits Dataset: 
| Column | Description |
| --- | --- |
| date | Visit date |
| group | Experiment group |
| visits | Number of visits |
<br>

## Approach
### 1. Data Cleaning
<ul>
<li>Parsed and standardized date formats</li>
<li>Identified and removed duplicate users</li>
<li>Detected users assigned to both test groups (data integrity issue)</li>
<li>Excluded invalid users to preserve experiment validity</li>
</ul>
<p></p>

### 2. Hypothesis Prioritization (ICE vs RICE)
<b>Frameworks used:</b>
<ul>
<li>ICE = (Impact × Confidence) / Effort</li>
<li>RICE = (Reach × Impact × Confidence) / Effort</li>
</ul>
<b>Key Insights:</b>
<ul>
<li>Top-performing hypotheses: #7, #0, #2, #6, #8</li>
<li>Hypotheses focused on traffic growth and promotions ranked highest</li>
<li>Low-impact UI changes consistently ranked lowest</li>
</ul>
<b>Takeaway:</b> Initiatives that increase traffic and user engagement provide the greatest revenue potential
<br></br>


## A/B Test Analysis
<p></p>

### Key Metrics Evaluated:
<ul>
<li>Conversion rate</li>
<li>Average order value (AOV)</li>
<li>Revenue trends</li>
<li>User behavior patterns</li>
</ul>
<p></p>

### Conversion Rate (Primary Metric)
<ul>
<li>Statistically significant improvement in Variant B</li>
<li>P-value: 0.0168 (raw data)</li>
<li>P-value: 0.0136 (filtered data)</li>
</ul>
Strong evidence that Variant B improves user conversion
<br></br>

# Analysis Overview:
### Prioritizing the Hypothesis:
Here's a look at the hypotheses: 
 ![hypotheses](https://github.com/julyndav/Python/blob/main/AB_Analysis/images/hypotheses.png)
<p></p>
Now to take the scores for the hypotheses and see which ones have the potential of giving the highest return on revenue.
<p></p>

 #### ICE: 
 <ul>
   <li>ICE = (Impact* Confidence)/Effort</li>
   <li>Once ICE was calculated, the hyptheses were sorted based on ICE score.</li>
 </ul>
<b>Insight:</b>
8, 0, 7 6 and 2 where the top hypotheses with 8 being number one with 16.2. Launch a promotion that gives users discounts on their birthdays<b>(16.2)</b> and adding two new channels for attracting traffic<b>(13.3)</b> are the top picks<p></p>

#### RICE:
<ul>
   <li>RICE = (Impact*Reach*Confidence)/Effort</li>
   <li>Once ICE was calculated, the hyptheses were sorted based on RICE score.</li>
 </ul>
<b>Insight:</b>
7, 2 , 0, 6, 8 were the top hypotheses with 0 and 6 having the same RICE score. 8 fell from 1st with ICE to the bottom of the top 5. 6 didn't change position, 7 and 0 are the only two that remained in the top 3.<p></p>

![ice_rice](https://github.com/julyndav/Python/blob/main/AB_Analysis/images/comparison.png)

### Conclusion for Prioritizing Hypotheses:
From both of the ICE and RICE plots, we get a better visual of how the two represent the hypotheses presented. We can see that numbers 3, 4 and 5 can be dropped; they performed poorly on both spectrums. Changing the category structure(#3), background color(#4) and adding a customer review page(#5) would have no significant effects customer base or revenue. These seem to be 'cosmetic' changes.

The 5 Hypotheses that should be focused on are numbers 7, 0, 2, 6 and 8. From those 5, the top three would be 7, 8 and 0. Hypothesis 7 maintained good standing in both ICE and RICE categories. Subscription forms are an excellent way to retain current visitors and give new visitors more insights into what the company is doing and has to offer.

Promotional discounts(#8) and adding channels to bring in more traffic(#0) both garner focus in increasing customer base and revenue. Even though (#8) performed poorly in terms of RICE; it did so well in the ICE category that it brought it in line with the second best hypothesis(#0). Reaching more visitors and giving discounts have been proven industry actioons in increasing customer base and revenue potential.
<br></br>

## A/B Test Analysis

| Cummulative Revenue by Group     | Cumulative Average Order Size by Group      | 
| ----------------------------------- | ----------------------------------- | 
![rev_grp](https://github.com/julyndav/Python/blob/main/AB_Analysis/images/c_rev_grp.png) | ![avg_os](https://github.com/julyndav/Python/blob/main/AB_Analysis/images/c_order_group.png) | 

<p></p>
<b>Cummulative Insights:</b> Once again Group B has exceeded Group A results and at the same time frame of 2019-8-17 which is where Group B spiked. After B's spike, it is slowing trending downward. Group A, once it had reached it's peak at 2019-8-13, it seems to level off and stay constent.<p>
  
When reviewing the relative difference in order size between the groups, there are 2 points where the difference between the groups spikes. There must be some abnormally large orders placed. This will be looked into further in the analysis process.
<p></p>

### Tools and Skills Demonstrated:
<ul>
<li>Python</li>   
<li>Pandas / NumPy</li>
<li>Data cleaning</li>
<li>Exploratory data analysis</li>
<li>Outlier detection</li>
<li>Hypothesis testing</li>
<li>A/B testing methodology</li>
<li>Data visualization</li>
</ul>
<b>Libraries used:</b>
<ul>
<li>Pandas</li>
<li>NumPy</li>
<li>Matplotlib</li>
<li>Seaborn</li>
<li>SciPy</li>
<br>



# Conclusion for A/B Analysis:
Although our general conclusions from the test didn't change, using the raw vs filtered data examples demonstrates clearly how anomalies can affect A/B test results. All it takes is 2-5 huge orders to skew the comparsion between the groups.
Between the raw and filtered, Group B showed gains on Group A except were the order size was concerend. Removing the abnormally large orders, which caused the massive spike in the plot for 'Average Order size' for Group B, negated Group B's gain that it had on Group A in that category.

Based on the overall results, I would suggest ending the test and going with Group B. Despite Group B's anomalies, they still garned the large orders from a few visitors which boosted the Groups revenue. It's obvious that the tested hypotheses of numbers 7, 0 and 8 really resonated with Group B
