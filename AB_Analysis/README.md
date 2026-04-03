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


#### 6 - 8. 95th and 99th percentiles 
Looking further into orders, the original 'orders' table was used for analysis as groups/revenue are not the focus for this section of the analysis. Let's get a visual on the scatter plot on orders by users.

As determined early in the analysis process, there are order spikes as shown in the table and scatterplot. 4 orders have higher than normal order sizes with 2 orders almost maxing out. 

<b>Orders by Users</b><p>
A brief section of code will provide the percentiles for the orders: <b> np.percentile(orders_by_users['orders'], [90, 95, 99]) </b>
<ul>
<li>90% of users have placed 1 or fewer orders.</li>
<li>95% of users have placed 2 or fewer orders.</li>
<li>99% of users have placed 4 or fewer orders.</li>
</ul>

<b>Order Prices</b>
<p></p>

| Orders by Users    | Order Prices    | 
| ----------------------------------- | ----------------------------------- | 
![rev_grp](https://github.com/julyndav/Python/blob/main/AB_Analysis/images/order_by_user.png) | ![avg_os](https://github.com/julyndav/Python/blob/main/AB_Analysis/images/order_by_prices.png) | 
<p></p>
<b>Order Prices Insight:</b> Now we can see what the previous spikes have created. Large order volumns in two instances giving us our anomalies. One order is $20K and another one is slightly above $2.5K. There are a few that are in range of $2K.<p>

Percentiles for revenue: <b>np.percentile(orders['revenue'], [90, 95, 99]).round()</b>

<ul>
<li>5% placed orders that cost more than 436 USD.</li>
<li>1% placed orders that cost more than 900 USD.</li>
<li>Orders outside of the 1% range can be considered anomalies.</li>
</ul>

### 9-12 Statistical Significance
<i>To view the actual coding process, see Jupyter notebook</i><p>
The steps to determine statistical significance is relatively the same:
<ul>
<li>Prepares order data for groups A and B.</li>
<li>Creates sample data for both groups, including users who did not place orders.</li>
<li>Performs the Mann-Whitney U test to compare the two groups.</li>
<li>Calculates the relative gain in conversion rate for groups.</li>
<li>Conducts hypothesis testing to determine if the difference is statistically significant.</li>
</ul>
<p></p>

#### 9. Difference in conversion between the groups using the Raw data.
The P-Value is: 0.0168<p>
Group B's relative gain is: 0.1381

**Insight:** The first value is P-value which is smaller than 0.05 so we can reject null hypothesis. After the relative gain is converted into a percentage, the relative conversion gain for Group B to Group A is 13.8%. The raw data analysis has shown that there is a difference between the two groups.<p>

 #### 10. Difference in average order size between the groups using the Raw data.  
*The P-Value is: 0.6915<p>*
*Group B's relative gain is: 0.2517<p>*
After 'Null and alternative Hypotheses testing':<p>
*pvalue: 0.6915<p>*
*Failed to reject null hypothesis: we can not make conclusions about the difference.*

**Insight:** The P-value is greater than .05. The p-value is considerably higher than 0.05, so failed to reject the null hypothesis, thus no conclusions can be made on differences in average order size.<p>

#### 11. Difference in conversion between the groups using Filtered data.
I got 22 anomalous users after filtering the data. Now to find out how their actions affected the test results. We'll calculate the statistical significance of the differences in conversion between the groups, using filtered data.
1. prepare samples of the number of orders per user for each test group.
2. Applying the statistical Mann-Whitney criterion to the resulting samples.
3. Null and alternative hypotheses testing<p>

*P-value:  0.0136<p>*
*Null hypothesis rejected: the difference is statistically significant<p>*
**Insight:** With the hypothese rejected, removing the differences still resulted in group difference.

#### 12. Difference in average order size between the groups using Filtered data.
*The P-Value is: 0.6347*
*Group B's relative gain is: -0.0979*<p>

After 'Null and alternative Hypotheses testing':<p>
*pvalue: 0.6347<p>*
*Failed to reject null hypothesis: we can not make conclusions about the difference.*<p>
P value has changed and also failed to reject hypothesis again, no conlusion from difference on this.

**Insight:** Now that the anomalies have been removed, we can see how much things have changed. Between the groups with raw data was 13.8% with the filtered data it is now 16.8% a difference of 3%; not a significant diference but still there.

On average order size with the raw data it was 25.2% and with the filtered data which removed the anomalies of the atypical orders sizes, Group B is in the negative. It just shows how much the atypical orders helped Group B out.

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
