# Yandex Afisha Business Analysis

## Project overview:

Yandex Afisha; an app and website that helps users find out about events like movie showings, exhibitions, gigs, concerts and buy tickets. The data has been collected from 2017 through 2018. The analysis will explore various customer, date and revenue attributes. Our objective is to incorporate data visualization techniques and business analysis tools to uncover patterns, correlations, and unique characteristics within the data sets.

This project will focus on using Cohort Analysis and Data Visualizations to explore the analytical side of business. This will incorporate data cleaning, data manipulation, exploratory analysis, user retention, sales analysis, customer life time values and visualizations. Customer metrics were plotted and the finding interpreted along with providing insights and conclustions to back up reccomendations to marketing, sales and excutives on which marketing sources are worth futher investment and which ones should be scrapped. 

By doing so, we can identify key factors to help the marketing department from Yandex make effective investments in marketing, have an overview of the effectiveness of current marketing efforts, get a visualization of return rates and other customer metrics.
<br></br>

## Table of Contents:
[Jupyter Notebook](https://github.com/julyndav/Business_Analytics/blob/main/BA_Yandex-Afisha.ipynb)<br>
[Data Visualizations](https://github.com/julyndav/Business_Analytics/tree/main/cohort_images)
<br></br>


### Skills Demostrated:
<ul>
<li>Python (for data cleaning, data manipulation and exploratory analysis)</li>
<li>Panda Libraries (for data visualizations)</li>
<li>Dashboard Design (PowerBI and Powerpoint)</li>
<li>Extract and Loading Data</li>
</ul>
<br></br>

## Required Project Libraries:
| Library |Purpose |
| --- | --- |
| Pandas | Main library for working with data |
| Numpy | Used for numerical operations on large quantities of data |
| Seaborn | Python visualization library based on matplotlib |
| Matplotlib | Python visualization library |
<br>

## Description of the data
<p></p>

### Visits table:
| Variable | Purpose |
| --- | --- |
| Uid | User's unique identifier |
| Device | User's device |
| Start Ts |Session start date and time |
| End Ts | session end date and time |
| Source Id | Identifier of the ad source the user came from |
<p></p>

### Orders table:
| Variable | Purpose |
| --- | --- |
| Uid | Unique identifier of the user making an order |
| Buy Ts | Order date and time |
| Revenue | Revenue from the order |
<p></p>

### Costs table: 
<i>Data on marketing expenses</i>
| Variable | Purpose |
| --- | --- |
| Source_id | Ad source identifier |
| dt | Date |
| costs | Expenses for ad source |
<p></p>
<br></br>

## Analysis Steps:
| Step |Description |
| --- | --- |
| 1 | Create project description |
| 2 | Import/installing libraries |
| 3 | Upload and analyize data |
| 4 | Data cleaning and preparation |
| 5 | Customer segmentation and analysis |
| 6 | Determining Customer Retention Rate |
| 7 | Sales Analysis (conversion rate, purchase size, LTV |
| 8 | Marketing Analysis (marketing costs, CAC, ROMI) |
| 9 | Conclusion and Reccomendations |

<br></br>

# Analysis Overview:

### Data Cleaning and Preparation:





From using cohort analysis, here a few snapshots.  <p>
![Orders over time](https://github.com/julyndav/Business_Analytics/blob/main/cohort_images/order%20over%20time.png)
<p>
<p></p>
To see how customer purchases have played out over time, lets take a peek at the LTV (Life Time Value) of the customer base:

![Life Time Value](https://github.com/julyndav/Business_Analytics/blob/main/cohort_images/LTV.png)

To end the project, a through conclusion was given with reccommendations. This was expanded on in the above Tableau Dashboard. 
<br></br>

## Brief Project Conclusion:
#### <i>Full conclusion within the project notebook</i>
*Overall Impression(s):Users get to the website and atleast make one purchase pretty much immediately. The ads are bringing in relevant users that want the product, but most users do not make multiple orders/visits and orders are small. Usally movie goers stay up to date on the latest and upcoming movies; it makes sense that their purchases would continue. Are customers not happy after their intial purchase?

