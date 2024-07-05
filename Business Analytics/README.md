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

## Data Cleaning and Preparation:

![Data_cleaning](https://github.com/julyndav/Python/blob/main/Business%20Analytics/Images/data%20cleaning1.png)

<p></p>

![Data_cleaning2](https://github.com/julyndav/Python/blob/main/Business%20Analytics/Images/dc2.png)

Now that the data has been cleaned, data types are set and it was determined that there are no duplicates, analysis can start. 
<br></br>


## Product Analysis
Questions to answer:

1) How many people use it every day, week, and month?
2) How many sessions are there per day? (One user might have more than one session.)
3) What is the length of each session?
4) What's the user retention rate?

### 1) Visits daily, weekly monthly usage?
<ul>
<li>Visits table will be used for this part of the analysis</li>
<li>Columns created for year, month, week values to determine activity usage.</li>
<li>Averages will be used.</li> 
<li>Coding will be separated into DAU(daily average users), WAU(weekly average users) and MAU(monthly average users)</li>
</ul>
<br></br>

To determine users by month/year/week, the date value needs to be separated out into it's individual parts. This will be based off 
of 'Start Ts' (start date and time variable).
![Date_breakdown](https://github.com/julyndav/Python/blob/main/Business%20Analytics/Images/DAU1.png)
<p></p>
<br>

Now that the date has been broken down, let's use it to find our overall averages. 
![Overall_Averages](https://github.com/julyndav/Python/blob/main/Business%20Analytics/Images/averageusers_overall.png)
<p></p>
<br>

To see the actual user average per day, the 'groupby' function will be used. 
![DailyAU](https://github.com/julyndav/Python/blob/main/Business%20Analytics/Images/DAU_code.png)
<p></p>
<br>

![DAU_graph](https://github.com/julyndav/Python/blob/main/Business%20Analytics/Images/Daily%20Average%20Users.png)

The same code can be used to see the Average users per month and for the year with just a simple adjustment to the code.
Second portion of code creates a visualization of the "DAU'. Viewing the Jupyter Notebook will allow you to see the process for weekly and monthly
average users. 
<br></br>

### 2) Sessions per day?:
![Session_day](https://github.com/julyndav/Python/blob/main/Business%20Analytics/Images/sess%20per%20user.png)

<b>Insights: </b> Number of sessions and users are fairly close in size with number of sessions being slightly higher. This denotes that some users had more than one session. Numbers over 1.05 show that a few users have had more than one session. The brief overview of the number of daily sessions shows that 2018 was more established with almost double the user count. 2017 low numbers can be contributed to start up marketing efforts and the platform being new. Would like to know when the platform came online for a broader trend analysis.

<br></br>
### 3) Length of Session:
Session length was determined by using Python to calculat that time between 'Start Ts' and 'End Ts'. Duration time was returned in seconds.
<p></p>
On average, a user spends 1 minute/60 seconds on the app. This time should be enough to find the event of interest, but most likely it will take more time to buy tickets through the Yandex.Afisha application. 
Will need more research on whether people completely lose interest in what they have found, or go to other resources to buy a ticket there.
<br></br>

### 4) User Retention
Retention shows us how many users (in % out of registered) were active (had sessions) on a certain day/week/month after registration/first visit.
To show the customer retention, this is where cohort analysis will be used.  First is to create Cohort month which shows the first time the User has visited. 
This data will be used later in the coding process for Retention Rate and to create a heatmap as a visualization for this part of the analysis. 

Getting the separate date elements will allow us to get the difference to create the 'cohort index'. It will show us when the user was acquired, how long they have been active and retained.
Customers with an cohort index of 0(Conversion 0days), were acquired and active within the same month.





