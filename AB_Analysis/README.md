## A/B Testing Project overview:
Together with the marketing department, a list has been compiled of hypotheses that may help boost revenue. 
My goal is to prioritize these hypotheses, launch an A/B test, and analyze the results. The analsys will incorporate cummalitive averages, exploring outliers and looking at conversion rates.
<br></br>

## Table of Contents:
[Jupyter Notebook](https://github.com/julyndav/A_B-Testing/blob/main/A_B%20Testing.ipynb)
<p></p>

### Skills Demostrated:
<ul>
<li>Extract and Loading Data</li>   
<li>Python (for data cleaning, data manipulation and exploratory analysis)</li>
<li>Data Manipulation (Pandas and NumPy for handling and transforming data)</li>
<li>Statistical Knowledge(apply statistical tests and understand their results)</li>
</ul>
<br>

## Required Project Libraries:
| Library |Purpose |
| --- | --- |
| Pandas | Main library for working with data |
| Numpy | Used for numerical operations on large quantities of data |
| Seaborn | Python visualization library based on matplotlib |
| Matplotlib | Python visualization library |
| SciPy | For statistical operations |


## Description of the data
<p></p>

### Hypotheses table:
| Variable | Purpose |
| --- | --- |
| Hypotheses | Brief descriptions of the hypotheses |
| Reach | User reach, on a scale of one to ten |
| Impact |impact on users, on a scale of one to ten |
| Confidence | confidence in the hypothesis, on a scale of one to ten |
| Effort | the resources required to test a hypothesis, on a scale of one to ten. The higher the Effort value, the more resource-intensive the test |
<p>

### Orders table:
| Variable | Purpose |
| --- | --- |
| transactionId | order identifier |
| visitorId | identifier of the user who placed the order |
| date | of the order |
| revenue | from the order |
| group | the A/B test group that the user belongs to | 
<p>

### Visits table: 
| Variable | Purpose |
| --- | --- |
| date | date |
| group | A/B test group |
| visits | the number of visits on the date specified in the A/B test group specified |

<br></br>


## Analysis Steps:
| Step |Description |
| --- | --- |
| 1 | Create project description |
| 2 | Import libraries |
| 3 | Upload and analyize data |
| 4 | Data cleaning and preparation |
| 5 | Prioritize hypothese |
| 6 | Determining how prioritzation changes between the two models |
| 7 | Apply A/B Testing to the models |
| 8 | Determine the best hypothese |
| 9 | Project Conclusion(s) |

<br></br>
## Hypotheses Gathered by Marketing Department:
<ul>
<li>Add two new channels for attracting traffic. This will bring 30% more users</li>
<li>Launch your own delivery service. This will shorten delivery time</li>
<li>Add product recommendation blocks to the store's site. This will increase conversion and average purchase size</li>
<li>Change the category structure. This will increase conversion since users will find the products they want more quickly</li>
<li>Change the background color on the main page. This will increase user engagement</li>
<li>Add a customer review page. This will increase the number of orders
<li>Show banners with current offers and sales on the main page. This will boost conversion
<li>Add a subscription form to all the main pages. This will help you compile a mailing list
<li>Launch a promotion that gives users discounts on their birthdays
</li>
</ul>

<br></br>
# Analysis Overview:

## Data Cleaning and Preparation:
<OL>
<li> After initial review of Hypotheses table, there was no data cleaning or processing needed for the hypotheses dataframe.</li>
<li>Orders table:</li>
<UL>
<li>Code was adjusted in importing datasets by the use of 'parse' for the date.</li>
<li>Duplicates where checked in the 'visitorID' column. Duplicates were dropped.</li>   
</UL>
<li>Visits table:
  <ul>
    <li>After first inital running of visits df, group and date columns were object data types.</li>
    <li>Code was adjusted in importing datasets by the use of 'parse' and dtype.</li>
  </ul>
</OL>
<p></p>

### Group Check
There might be mistakes in the original datasets; for example, some of the visitors might have gotten into both group A and group B. Now to check the visior df. Going off of first visits, we'll see if any visitors are in both groups.<p>
<ul>
  <li>Review 'orders' table.</li>
  <li>Find the first group each user has visited 'first_group'.</li>
  <li>Merge first visit group with 'orders' df to see if visitor has been to another group.</li>


![user_groups](https://github.com/julyndav/Python/blob/main/AB_Analysis/images/AB%20Groups.png)<p>
<li> We can see from the third transaction, that the visitor has been in two groups. This is what we wanted to detect.</li>
<li>Using '.value_counts' function, the number of occurrences for each user was listed. </li>
</ul>

#### Let's finalize the groups!
![user_grp_complete](https://github.com/julyndav/Python/blob/main/AB_Analysis/images/AB%20Groups_2.png)

<i> 937 rows x 5 columns</i>

<li>Group B: 510 visitors.</li>
<li>Group A: 427 visitors.</li>
<br>

## Prioritizing the Hypothesis:
The file hypotheses_us.csv contains nine hypothesis on boosting an online store's revenue with Reach, Impact, Confidence, and Effort (aka RICE) specified for each.

RICE has four components:
<ul>
<li>Reach — how many users will be affected by the update you want to introduce</li>
<li>Impact — how strongly this update will affect the users, their experience, and their satisfaction with the product</li>
<li>Confidence — how sure you are that your product will affect them in this way</li>
<li>Effort — how much will it cost to test the hypothesis</li>
</ul>
<p></p>

#### The task is to:
<ul>
<li>Apply the ICE framework to prioritize hypothesis. Sort them in descending order of priority.</li>
<li>Apply the RICE framework to prioritize hypothesis. Sort them in descending order of priority.</li>
<li>Show how the prioritization of hypothesis changes when you use RICE instead of ICE. Provide an explanation for the changes.</li>
</ul>
<p></p>

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

Now to compare the results of both the ICE and RICE analysis:

![comp_icerice](https://github.com/julyndav/Python/blob/main/AB_Analysis/images/ice_rice.png)

### Conclusion for Prioritizing Hypotheses:
From both of the ICE and RICE plots, we get a better visual of how the two represent the hypotheses presented. We can see that numbers 3, 4 and 5 can be dropped; they performed poorly on both spectrums. Changing the category structure(#3), background color(#4) and adding a customer review page(#5) would have no significant effects customer base or revenue. These seem to be 'cosmetic' changes.

The 5 Hypotheses that should be focused on are numbers 7, 0, 2, 6 and 8. From those 5, the top three would be 7, 8 and 0. Hypothesis 7 maintained good standing in both ICE and RICE categories. Subscription forms are an excellent way to retain current visitors and give new visitors more insights into what the company is doing and has to offer.

Promotional discounts(#8) and adding channels to bring in more traffic(#0) both garner focus in increasing customer base and revenue. Even though (#8) performed poorly in terms of RICE; it did so well in the ICE category that it brought it in line with the second best hypothesis(#0). Reaching more visitors and giving discounts have been proven industry actioons in increasing customer base and revenue potential.
<br></br>

## A/B Test Analysis
#### Steps for the A/B analysis:
1. Graph cumulative revenue by group.  
2. Graph cumulative average order size by group.
3. Graph the relative difference in cumulative average order size for group B compared with group A. 
4. Calculate each group's conversion rate as the ratio of orders to the number of visits for each day. Plot the daily conversion rates of the two groups and describe the difference. 
5. Plot a scatter chart of the number of orders per user. 
6. Calculate the 95th and 99th percentiles for the number of orders per user. Define the point at which a data point becomes an anomaly.
7. Plot a scatter chart of order prices. 
8. Calculate the 95th and 99th percentiles of order prices. Define the point at which a data point becomes an anomaly.
9. Find the statistical significance of the difference in conversion between the groups using the raw data. 
10. Find the statistical significance of the difference in average order size between the groups using the raw data. 
11. Find the statistical significance of the difference in conversion between the groups using the filtered data. 
12. Find the statistical significance of the difference in average order size between the groups using the filtered data. 
<p></p>

#### Cumulative revenue by group. 
<ul>
  <li>Using the table/dataframe that was created from filtering users in multiple groups.</li>
  <li>An array is built ('datesGroups') with unique paried date-group values.</li>
  <li>The newly created 'datesGroup' table is used in conjunction with the 'visits' df to create a table that will bring together the 'Group', 'date', and how many visits per group.</li>
  <li>The 'orders' table is also grouped together on 'date, and 'group'. From that grouping, totals are aggregated for the number of 'transactionIDs', 'visitorIDs' and total revenue for each date.</li>
  
  <p></p>

   ![visit_grps](https://github.com/julyndav/Python/blob/main/AB_Analysis/images/visit_group.png)
   ![visit_grps](https://github.com/julyndav/Python/blob/main/AB_Analysis/images/orders_group.png)
   
   <i> 'visits' table followed by the 'orders' table giving a glimpse at the daily revenues.</i><p>
   <li>The two tables are combined on the date/group values. The resulting df is named 'cumulativeData'</li>
   <li>Once the tables are combined, 'Revenue by Group' can be plotted with each group being separated.</li>
</ul>
<p></p>

#### 2.Cumulative average order size by group
<i> No new data frames need to be created. The 'cumulativeData' df will be used to determine the average order size per group.</i>

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

#### 9. Difference in conversion between the groups using the raw data.
The P-Value is: 0.0168<p>
Group B's relative gain is: 0.1381

Insight: The first value is P-value which is smaller than 0.05 so we can reject null hypothesis. After the relative gain is converted into a percentage, the relative conversion gain for Group B to Group A is 13.8%. The raw data analysis has shown that there is a difference between the two groups.

   
