## A_B-Testing Project overview:
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

















## Project Conclusion:
Conclusion for A/B Analysis:
Although our general conclusions from the test didn't change, using the raw vs filtered data examples demonstrates clearly how anomalies can affect A/B test results. All it takes is 2-5 huge orders to skew the comparsion between the groups.
Between the raw and filtered, Group B showed gains on Group A except were the order size was concerend. Removing the abnormally large orders, which caused the massive spike in the plot for 'Average Order size' for Group B, negated Group B's gain that it had on Group A in that category.

Based on the overall results, I would suggest ending the test and going with Group B. Despite Group B's anomalies, they still garned the large orders from a few visitors which boosted the Groups revenue. It's obvious that the tested hypotheses of numbers 7, 0 and 8 really resonated with Group B






Frameworks will be used as a comparison for the hypotheses to determine the best ones. This framework involves:<br><li>
Reach — how many users will be affected by the update you want to
introduce<li>
Impact — how strongly this update will affect the users, their experience, and
their satisfaction with the product<li>
Confidence — how sure you are that your product will affect them in this way<li>
Effort — how much will it cost to test the hypothesis

This will rate our hypotheses on a scale of 1-10. Below is what our comparison looks like using the applied framework and separating things into two groups.
![ICE_RICE](https://github.com/julyndav/A_B-Testing/blob/main/images/comparison.png)

After the comparison, will be better equiped to make a decision based on the test results. The possible decisions are:<br>
<ol>
  <li> Stop the test, consider one of the groups the leader. </li>
  <li>Stop the test, conclude that there is no difference between the groups. </li>
  <li>Continue the test. </ol>
<p></p>

Analysis was closed out with determining comparison rates between the two groups and finding the statistical significance of the difference in conversion between the groups using the raw data. Conclusions and insights were including in the closing of the analysis also. 

Here's a snippet of how the comparison rates faired:
![Comparisongrouprates](https://github.com/julyndav/A_B-Testing/blob/main/images/comprison%20groups.png)


