![banner_image](https://github.com/julyndav/Python/blob/main/DOHMH%20Dog%20Bite%20Analysis/Images/PROJECT%20BANNER.png)


# An Exploratory Dive into Dog Bite Frequency.
Comprehensive exploratory analysis of dog bite incidents using NYC Open Data via Kaggle dataset and coding platform.

Processe and analyze 20K+ records spanning 2015 through 2021 from the New York City's Department of Health and Mental Hygiene. Focused on exploring and manipulating the data to uncover key trends and insights. Provided brief, data-driven insights throughout the analysis, highlighting significant patterns and anomalies. The customized visualizations were designed to effectively communicate findings and support public health initiatives.
<br></br>

## Table of Contents:
[Original Data Source - NYC Open Data](https://data.cityofnewyork.us/Health/DOHMH-Dog-Bite-Data/rsgh-akpg/about_data)<br>
[Kaggle Link to Dataset](https://www.kaggle.com/datasets/muhmiqbal/dog-bites-nyc)
<br></br>

### Skills Demostrated
<ul>
<li>Python</li>
<li>Pandas</li>
<li>Data cleaning </li>
<li>Creating Calculated Columns</li>
<li>Exploratory Analysis</li>
<li>Data Visualisation</li>
</ul>
<br></br>

## Challenge Project Rundown:
### Objectives:
Perform an exploratory analysis of dog bite data using Python to find any general metrics and trends then to visualize with using plotting libraries. <br>
#### Questions to ask:
<ul>
<li>What breed of dog is more prone to bite?</li>
<li>Which Boroughs have a high rate of incidences?</li>
<li>What is the gender breakdown? Which one is likely to bite?</li>
<li>Does Age play a factor?</li>
</ul>
<br>

## Description of Data
### Dog_Bite_Data Table:
| Variable | Purpose |
| --- | --- |
| UniqueID | Unique dog bite case identifier |
| DateofBite | Date bitten |
| Speices | Animal Type |
| Breed | Breed type |
| Age | Dog's age at time of bite. |
| Gender | Sex of Dog |
| Spay/Neuter | Surgical removal of dog's reproductive organs. |
| ZipCode | Dog bite Zipcode. |
<p></p>
<br>

# My Analysis Process:

### Reviewing the Data:
<ul>
<li>Analysis was done using Python via Jupyter Notebook platform.</li>
<li>Reviewed the available data card that gave an overview of the dataset.</li>
</ul>  
<p>
  
### Processing Data Overview:
<ul>
<li>Additional Panda libraries were added for visualizations.</li>
<li>Imported data into the Jupyter platform.</li>
<li>Explore data content and structure using '.head()','.info()', 'describe(). </li>
<li>Data Cleaning; missing/null values, correcting data types, handeling duplicates and standardizing formats.</li>
<li>Transform data, particularly date values.</li>
<li>Checking for discrepancies or anomalies.</li>
</ul>
<p></p>
 <br> 

# Analysis
<p></p>

### Data Cleaning
After running the '.info()' function, it gave a rundown of the dataset.<p>
<ul> <li> Null Values - 3 columns contained null values: 'Breed', 'Age' and 'ZipCode' contained null values.</li>
            1. 'Breed' null values - changed to 'Unknown'.<p>
            2. 'Age' null values - changed to (0) and all values kept.<p>
            3. 'ZipCode' null values - changed to (0) and all values kept.<p>
    <li> Duplicates - Almost half of the 'UniqueID's were duplicated. .</li>
    <li> Data Types - Data types set.</li>
            1. Outliers removed from 'Age'.<p>
            2. Date column formatted. Year and Month extracted from date into new columns.<p>
</ul>

### Key points that the unique values are showing us? 
<ul> <li> UniqueID - there are a total 10773 dogs in the study</li>
    <li> DateOfBite - 2331 dates that bites took place.</li>
    <li> Species - Only 1 species present in the data/study</li>
    <li> Breed - We have 1010 breeds of dogs!</li>
    <li> Gender - 3 types of genders are present.</li>
    <li> Boroughs - 6 Boroughs or neighboohds. </li>
    <li> BiteMonth - 12, giving data for a year.</li>  
    <li> BiteYear - Study contains 7 years worth of data.</li>
</ul
<br></br>

| Raw/Unprocessed Data     | Cleaned and Ready for Analysis      | 
| ----------------------------------- | ----------------------------------- | 
![raw](https://github.com/julyndav/Python/blob/main/DOHMH%20Dog%20Bite%20Analysis/Images/raw_data.png) | ![cleaned](https://github.com/julyndav/Python/blob/main/DOHMH%20Dog%20Bite%20Analysis/Images/cleaned_data.png) | 

<br></br>

## Breed Consolidation
Paring down over 1k dog breeds was the most time consuming part of the analysis but essential to ensure uniformity and consistency. With over 1000 different dog breeds, many of which might be variations or mixed breeds, it would be challenging to draw meaningful insights. By consolidating similar breeds the dataset will be more manageable. 

<ul>
<li>First to count the number of unique values in the 'Breed' column. The result was <b>1010 different breeds</b></li>
<li>The unique breed values were listed then revised.</li>
<li>Due to the size of the list, it was broken down into two sections.</li>
</ul>
<p></p>

![breed_consol](https://github.com/julyndav/Python/blob/main/DOHMH%20Dog%20Bite%20Analysis/Images/breed_manip.png)

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

