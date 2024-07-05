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


# Product Analysis
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

![Session_length](https://github.com/julyndav/Python/blob/main/Business%20Analytics/Images/length%20of%20sess.png)

<i> From unusally large spike of 0's, it seems to correlate with visitors that have 0 conversion days.</i>
<br></br>

### 4) User Retention
Retention shows us how many users (in % out of registered) were active (had sessions) on a certain day/week/month after registration/first visit.
To show the customer retention, this is where cohort analysis will be used. First is to create Cohort month which shows the first time the User has visited. 
This data will be used later in the coding process for Retention Rate and to create a heatmap as a visualization for this part of the analysis. 

<b>Retention Analysis Steps:</b>
1) Imported <b>datetime as dt</b> to work with dates.
2) Applied a function to just have the year and month with the day defaulted to 1 (the first of the month).
3) Created 'cohort month' based on first month of user's visit.
4) Created a column index for month cohort.

Getting the separate date elements will allow the creation of the index. It will show us when the user was acquired, how long they have been active and retained.

![Retention_Code](https://github.com/julyndav/Python/blob/main/Business%20Analytics/Images/retention%20code.png)
<i>Customers with an cohort index of 0(Conversion 0d), were acquired and active within the same month</i>
<p></p>

5) Now to create the pivot table that is key in getting the heatmap visual for retention. Cohort months will act as the 'rows' with the cohort index as the column labels and values based on Uid (user id) totals.
6) The Uid totals are converted into a percentage, the results are displayed as a pivot table

![Retent_pt](https://github.com/julyndav/Python/blob/main/Business%20Analytics/Images/retention%20table.png)
<p></p>

7) To display the heatmap; custom colors were selected and values formatted to show percentages appropriatley.

   ![heatmap](https://github.com/julyndav/Python/blob/main/Business%20Analytics/Images/retention%20heatmap.png)
   <p></p>

### Insights: 
The average retention rate from all cohorts decreased slowly over time. One of the few months to retain a somewhat steady user percentage was June. July, August and September faired better the the rest of the months as they were able to have a slightly higher average for most of the month. Towards the end of 2018 the rate had a declining trend.

### Reccomendation:
May 2018 had no registerable data. The data for May 2018 needs more attention to see what is going on and why the data collection period wasn't for the entire month.

### Product Analysis Conclusion:
Yandex.Afisha sees an average of 900 users daily with each users having around 1 session. The time spent on the site for that session is about 10 minutes. There was a significant spike in users around November 24th/Thanksgiving times which could be attributed to the holiday season. The 24th/25th of November is also one of the biggest shopping days of the year as a precursor to Christmas. Tickets may have been purchased as gifts but more user information would be need to to determine that. The spike in Users also coincides with an increase is session lenght to almost 18 minutes. The site my have slowed due to server traffice.
One area of concern is the plunge in both users and session lenght that occured around March 31st. With such a sharp decrease in both users and session length; a few things may have occured. It could be a site crash, site maintenance or voluntary/involuntary site take down but again, more information would be need to make a solid conclusion.

<br></br>
# Sales
In this section of the analysis, the 'visits' table that was customized for cohort analysis will be merged with the orders tables creating a new df (data frame) .

### Sales Objective:
1) How are customer purchasing items?
2) How many orders do they make during a given period of time?
3) What is the average purchase size?
4) How much money do they bring? (LTV)

### 1) Preferred way to purchase?:
Once the tables were merged, the 'groupby' function was used on the 'Device' variable, the the 'revenue' was summed. The total revenue value was formatted to show
millions.  To find the number of users per each device, the same method was used to determine the total users. 

![Dev_users](https://github.com/julyndav/Python/blob/main/Business%20Analytics/Images/purchase%20how.png)
<p></p>



