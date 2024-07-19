## Table of Contents:
[Jupyter Notebook](https://github.com/julyndav/A_B-Testing/blob/main/A_B%20Testing.ipynb)

## Required Project Libraries:
| Library |Purpose |
| --- | --- |
| Pandas | Main library for working with data |
| Numpy | Used for numerical operations on large quantities of data |
| Seaborn | Python visualization library based on matplotlib |
| Matplotlib | Python visualization library |

<br></br>

## A_B-Testing Project overview:
From a supplied dataset, work with provided hypotheses from a marketing department using the concepts of Reach, Impact, Confidence and Effort to determine
which hypothese will be most likely to boost an online store's projected revenue. 
<br></br>

## Analysis Steps:
| Step |Description |
| --- | --- |
| 1 | Create project description |
| 2 | Import libraries |
| 3 | Upload and analyize data |
| 4 | Data cleaning and preparation |
| 5 | Prioritize hypothese using two framework models |
| 6 | Determining how prioritzation changes between the two models |
| 7 | Apply A/B Testing to the models |
| 8 | Determine the best hypothese |
| 9 | Project Conclusion(s) |

<br></br>
## Brief Analysis Overview:
The analsys will incorporate cummalitive averages, exploring outliers and looking at conversion rates. 
Hypothese that will be tested are:<br><li>
Add two new channels for attracting traffic. This will bring 30% more users<li>
Launch your own delivery service. This will shorten delivery time<li>
Add product recommendation blocks to the store's site. This will increase conversion and average purchase size<li>
Change the category structure. This will increase conversion since users will find the products they want more quickly<li>
Change the background color on the main page. This will increase user engagement<li>
Add a customer review page. This will increase the number of orders<li>
Show banners with current offers and sales on the main page. This will boost conversion<li>
Add a subscription form to all the main pages. This will help you compile a mailing list<li>
Launch a promotion that gives users discounts on their birthdays

We'll use frameworks to as a comparison for the hypotheses to determine the best ones. This framework involves:<br><li>
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


## Project Conclusion:
Conclusion for A/B Analysis:
Although our general conclusions from the test didn't change, using the raw vs filtered data examples demonstrates clearly how anomalies can affect A/B test results. All it takes is 2-5 huge orders to skew the comparsion between the groups.
Between the raw and filtered, Group B showed gains on Group A except were the order size was concerend. Removing the abnormally large orders, which caused the massive spike in the plot for 'Average Order size' for Group B, negated Group B's gain that it had on Group A in that category.

Based on the overall results, I would suggest ending the test and going with Group B. Despite Group B's anomalies, they still garned the large orders from a few visitors which boosted the Groups revenue. It's obvious that the tested hypotheses of numbers 7, 0 and 8 really resonated with Group B
