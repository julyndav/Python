# An Exploratory Dive into Dog Bite Frequency.
Comprehensive data analysis of dog bite incidents using NYC Open Data and Kaggle datasets.

Extracted, processed, and analyzed 10K+ records spanning 2015 through 2021 from the New York City's Department of Health and Mental Hygiene. Focused on exploring and manipulating the data to uncover key trends and insights. Provided brief, data-driven insights throughout the analysis, highlighting significant patterns and anomalies without developing a dashboard. The customized visualizations were designed to effectively communicate findings and support public health initiatives.h 2021 and consists of 10K+ records. The focus of this analysis to explore and manipulate the data and design customized visuals. 
<br></br>

## Table of Contents:
[PowerBI Dashboard Overview](https://github.com/julyndav/PowerBI/tree/main/NYC_Dog_Bite_Analysis)<br>
[Original Data Source - NYC Open Data](https://data.cityofnewyork.us/Health/DOHMH-Dog-Bite-Data/rsgh-akpg/about_data)<br>
[Kaggle Link to Dataset](https://www.kaggle.com/datasets/muhmiqbal/dog-bites-nyc)
<br></br>

## About this project:

### Challenge Project Rundown
#### Objective:
As a BI Developer for National Rail, a company that provides business services to passenger trains operatored in England, Scotland, and Wales, 
create an exploratory dashboard that will: 
<ul>
<li>Identify the most popular train routes</li>
<li>Determine peak travel times</li>
<li>Analyze revenue from different ticket types & ticket classes</li>
<li>Diagnose on-time performance and contributing factors</li>
</ul>
<br>


# My Analysis Process:

### Reviewing the Data:
<ul>
<li>Reviewed the provided data consisting of two CSV tables: one with working data and another with variable information.</li>
<li>Loaded the working data into Power BI for initial data cleaning, formatting, and manipulation which was minimal.</li>
</ul>  
<p>
  
### Processing Data:
<ul>
<li>Formatted currency and date columns.</li>
<li>Reviewed each column’s variables, consolidating the 'Reason for Delay' column to unify various delay reasons.</li>
<li>Ensured data consistency and accuracy through cleaning and validation processes.</li>
</ul>
<p></p>
  
### Dashboard Concept:
<ul>
<li>Outlined key metrics and potential visuals, dividing the dashboard into four main sections based on the initial requirements.</li>
<li>Designed the overall aesthetic and layout to ensure a user-friendly interface. The background and icons were designed and exported from PowerPoint.</li>
</ul>
<p></p>

### Skills Demostrated
<ul>
<li>Data extraction and loading</li>
<li>Data cleaning (using Power Query)</li>
<li>Calculated Columns</li>
<li>Data Analysis Expression (DAX) Functions</li>
<li>Dashboard design</li>
<li>Data Visualisation</li>
</ul>
<br></br>

# Dashboard
## Overview Page:
<ul>
<li>Displays general ticket information: quantity, purchase methods, monthly ticket totals, and average price.</li>
<li>Highlights the number of stations covered, with a focus on the top 3 departure and arrival stations, their on-time performance, and revenue.</li>
<li>KPIs and visuals to provide a summary of other key metrics.</li>
</ul>
<p></p>

![MainDB](https://github.com/julyndav/PowerBI/blob/main/UK_National_Rail/Images/UKRail%20Img1.png)

### Overview Insights: 
<b>Online Sales:</b>
With 59% of purchases done online, there is a clear trend towards digital transactions. Contactless and debit card usage could be from in station purchases. 

<b>Utilization of Discount Railcard:</b>
Despite the discount railcard availability, 66% of passengers do not use it. Identifying reasons for low adoption (e.g., awareness, perceived value, eligibility) and implementing targeted marketing or adjustments could boost usage, increasing ticket sales and revenue.

<b>Efficiency Based on Punctuality:</b>
Focusing on maintaining or improving punctuality for the top arrival stations (average 82% on-time) and departure stations (average 89% on-time) can boost customer satisfaction, repeat business, and operational efficiency. Addressing factors for underperforming stations can optimize operations and reduce associated costs.

<br></br>

## Route Overview:
<ul>
<li>Showcases ticket classes, highlights reasons for delay and refunds totals per ticket class.</li>
<li>Features an interactive route map and a general timeline to visualize passenger patterns over a 24-hour period.</li>
<li>There are separate dashboards for Arrival and Departure information. These are accessed via the buttons on the main route page.</li>
<li>If one chooses, there is a Passenger dashboard which displays passenger trip information.</li>  
</ul>
<p></p>

![RouteOv](https://github.com/julyndav/PowerBI/blob/main/UK_National_Rail/Images/Route_Overview.png)
<br></br>


## Departures:
<ul>
<li>Visualizations exclude canceled trips to provide a clearer picture of actual departures.</li>
<li>Identifies peak travel times: 6-8am and 4-6pm, influenced by working class commuters and possibly students.</li>
<li>Breaks down ticketing by station.</li>
<li>Customized tooltip to display additional information.</li>
</ul>
<p></p>

![RouteOv](https://github.com/julyndav/PowerBI/blob/main/UK_National_Rail/Images/Departures.png)
### Departure Station Insights: 
<b>Departure Stations:</b>
The distance between Edinburgh and the nearest departure station in Leeds represents a substantial area for possibly increasing the number of stations along this route and has significant profit potential. By enhancing accessibility and service coverage in this corridor, it can effectively capture untapped market demand and optimize revenue generation.
<br></br>

<figure>
  <img src="https://github.com/julyndav/PowerBI/blob/main/UK_National_Rail/Images/Dept_TT.png" alt="Departure Timetable">
  <figcaption>Departure Tooltip showing top metrics per selected station.  Values shown are default.</figcaption>
</figure>
<br></br>

### Arrivals:
<ul>
<li>Similar layout to Departures but focuses on average delay times and performance issues.</li>
<li>Examines trip delays, on-time percentages, and cancellations.</li>
<li>Analyzes station-specific delays to highlight where performance improvements can be made.</li>
<li>Only arrivals had data on delays.</li>
</ul>
<p></p>

![RouteOv](https://github.com/julyndav/PowerBI/blob/main/UK_National_Rail/Images/Arrivals.png)
### Arrival Station Insights:

<b>Arrival Stations:</b>
Same with Departures, there are substantial areas that are vacant. This significantly increases commuter time by bus or other means to get to/from a station. 
Costs involved in laying new rail is substantial so thorough research would need to be conducted in those areas to see if rail expansion is even viable.

<b>Delay Factors:</b>
Delays in railway operations can be categorized into two primary factors: weather-related delays, which are unpredictable despite forecasts, and operational delays typically caused by technical malfunctions or staffing issues. Understanding these delays requires a deeper analysis to determine their root causes, severity levels, and the condition of existing equipment. This data-driven approach will enable targeted improvements to optimize efficiency, and enhance customer satisfaction by minimizing disruptions.
<br></br>

### Overall Route Recommendations:
<b>Station Expansion Strategy:</b>
Conduct feasibility studies to identify optimal locations for new departure and arrival stations between Edinburgh and Leeds. Studies to include but not limited to, resident surveys, land surveys, and market demand research. Focus on areas with significant population density but lacking sufficient station access. This will capture untapped market demand. Evaluate development costs against potential revenue increases to ensure budget and long-term strategic objectives.
<br></br>
<br></br>

## Peak Travel Times:
<ul>
<li>Uses DAX calculations to assist in identifing peak travel hours and group them into categories.</li>
<li>Includes a heatmap to visualize passenger patterns and trends over different hours of the day.</li>
<li>Addressed issues with time variable sorting by creating a separate table for 'DayOfWeek' and DAX to ensure correct hour of the day order.</li>
</ul>
<p></p>

![RouteOv](https://github.com/julyndav/PowerBI/blob/main/UK_National_Rail/Images/Time_Perf.png)
<p></p>

### Travel Time Insights:
<b>Peak Travel Times:</b>
Standard work should have the highest commuter numbers as people are either on their way to or from work. These hours are from 9am-5pm. Next are the 'Non-Work' hours from 6pm-12am. This time frame is peak for those doing errands after work, going to events or something similar.

<b>Time Between Stations:</b>
It's to be expected that the Edinbburgh Station has the highest average travel time. Not only is Edinburgh the northern most station but there is a sizeable distance between it and the nearest station. 

<b>Passenger Volumne:</b>
The heatmap clearly displays the peek travel times for those that commute to and from either work or school. 
<br></br>
### Travel Time Recommendations:
<b>Passenger Volumn:</b>
Ensure that trains have sufficient capacity during peak hours to handle the high passenger volume. This may involve larger trains or adding additional cars to existing services. Put in place measures to manage passenger flow at major stations during peak hours, such as additional staffing, clear signage, and crowd control measures to help with boarding and exiting. These recommendations will help reduce congestion, minimize travel times, and ensure a more comfortable and efficient journey for all commuters. 
<br></br>
<br></br>

## Revenue:
<ul>
<li>Summarizes monthly revenue amounts.</li> 
<li>Incorporated custom tooltip that breaks down the months into days of the week for that month.</li>
<li>Highlights the difference between gross and net revenue amounts.</li>
<li>Provides a detailed revenue breakdown by ticket type and class to identify key revenue drivers.</li>
</ul>
<p></p>

![RouteOv](https://github.com/julyndav/PowerBI/blob/main/UK_National_Rail/Images/Revenue_DB.png)
<br></br>

### Revenue Insights:
<b>Refunds:</b>
Approximately 4% of trip transactions resulted in a refund. Weather related delays resulted in the lowest refund rate at 9.69% but accounted for the majority of delays. Technical and staffing issues attributed to the highest refund rates with Technical issues accounting for over 50% of refunds. 

<b>Revenue</b>
December is shown but the month only contained a weeks worth of data from 2023 which had 34 tickets sold for that time frame. For January, the highest grossing day of the week was Wednesday at $39K. February highest grossing day was Friday at $25k. March's highest grossing surprisingly was Sunday at $29k and April's highest grossing day was Tuesday at $30k.

From the 'Revenue Breakdown', We can see that passengers prefer to:
1) Purchase tickets online
2) Purchase Standard Class tickets
3) Not use the discount railcard
4) Purchase tickets in advance.
<p></p>

### Revenue Recommendations:
<b> Improve Technical and Staffing Reliability:</b>
Implement a rigorous maintenance schedule to minimize technical issues. Conduct regular training sessions and improve the staffing process to ensure that adequate staff is available, especially during peak times. Invest in better monitoring and early detection systems to quickly address technical problems before they impact service.

<b> Refund/Delays:</b>
Enhance the communication system to inform passengers promptly about weather-related delays and offer alternative options to reduce the impact.
Consider offering flexible rescheduling options rather than refunds to retain revenue.

<b> Ticket Recommendations:</b>
1) Improve the user experience on the online ticketing platform to make it more intuitive and faster.
2) Provide a seamless mobile experience to cater to on-the-go customers.
3) Offer exclusive online discounts or loyalty points to encourage more online purchases.
4) Offer early bird discounts for passengers who book tickets well in advance.
5) Provide additional benefits for advance purchasers, such as seat selection or free Wi-Fi.
6) Railcard: Reevaluate the discount railcard program to understand why it is underutilized. Simplify the process of acquiring and using the discount railcard.
   Promote the benefits of the discount railcard through targeted marketing campaigns.
<br></br>
<br></br>


## Passenger Dashboard Overview.
![Passengers](https://github.com/julyndav/PowerBI/blob/main/UK_National_Rail/Images/Passenger_DB.png)

