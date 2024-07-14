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

# Analysis Process:

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
<OL>
<li> Null Values - 3 columns contained null values: 'Breed', 'Age' and 'ZipCode' contained null values.</li>
<ul>
  <li>'Breed' null values - changed to 'Unknown'.</li>
  <li>'Age' null values - changed to (0) and all values kept.</li>
  <li>'ZipCode' null values - changed to (0) and all values kept</li>
</ul>  
<li>Duplicates - Almost half of the 'UniqueID's were duplicated.</li>
  <ul>
    <li>Looking into the 'UniqueID' column, it was discovered that the duplicated ID's were for separate records. With the column losing it's integrity, it was dropped from the dataset and analysis.</li>
  </ul>
<li>Data Types - Data types set.</li>
<UL>
<li>Outliers removed from 'Age'.</li>
<li> Date column formatted. Year and Month extracted from date into new columns.</li>   
</UL>
</OL>
<p></p>

| Raw/Unprocessed Data     | Cleaned and Ready for Analysis      | 
| ----------------------------------- | ----------------------------------- | 
![raw](https://github.com/julyndav/Python/blob/main/DOHMH%20Dog%20Bite%20Analysis/Images/raw_data.png) | ![cleaned](https://github.com/julyndav/Python/blob/main/DOHMH%20Dog%20Bite%20Analysis/Images/cleaned_data.png) | 

<p></p>

### Let's get a glimpse of column values.
![Unique_Values](https://github.com/julyndav/Python/blob/main/DOHMH%20Dog%20Bite%20Analysis/Images/unique_data.png)<p>


### Key points that the unique values are showing us? 
<ul> <li> DateOfBite - 2331 dates that bites took place.</li>
    <li> Species - Only 1 species present in the data/study</li>
    <li> Breed - There are 1652 breeds of dogs!</li>
    <li> Gender - 3 types of genders are present.</li>
    <li> Boroughs - 6 Boroughs or neighboohds. </li>
    <li> BiteMonth - 12, giving data for an entire year.</li>  
    <li> BiteYear - Study contains 7 years worth of data.</li>
</ul
<br></br>

## Breed Consolidation
Paring down over 1.6k dog breeds was the most time consuming part of the analysis but essential to ensure uniformity and consistency. Many of the breeds listed are variations of a main breed, it would be challenging to draw meaningful insights with so many breeds. By consolidating similar breeds the dataset will be more manageable. 

<ul>
<li>First to count the number of unique values in the 'Breed' column. The result was <b>1652 different breeds</b></li>
<li>The unique breed values were listed then revised.</li>
<li>Due to the size of the list, this section of code is extensive.</li>
<li>A goat and an alpaca were part of the data so they were removed.</li>  
</ul>
<p></p>

![breed_consol](https://github.com/julyndav/Python/blob/main/DOHMH%20Dog%20Bite%20Analysis/Images/breed_manip.png) <p></p>

The breeds were condensed down to 296 breeds.
<br></br>


# Exploratory Analysis & Visualizations

## Steps:
| Step |Description |
| --- | --- |
| 1 | Determine & load custom color pallete |
| 2 | Column details - Breakdown each column by it's values |
| 3 | Gender distribution |
| 4 | Spay/Neuter Percentage? |
| 5 | Age Analysis |
| 6 | Boroughs |
| 7 | Top 10|
| 8 | Month, Year Breakdown |
| 9 | Conclusion and Reccomendations |
<p></p>


### Column Details:
Viewing the unique values of each column for this analysis is possible because the data set is small, making it manageable. Understanding these values can help identify data patterns, anomalies, or other potential data quality issues. It also aids in selecting analysis techniques to better understand the data's structure. This approach may not be feasible with a large data set due to its size and complexity.<p>

#### Column Details: Values 
<i>** Note that the 'UniqueID' column was dropped due to duplication issues. Breed is not listed here due to amount of values.</i>
<ul><li> Species - Dog (even though goat and alpaca were present they were listed under 'Dog' for species).</li>
    <li> Gender - (M)ale, (F)emale, (U)nknown.</li>
    <li> Spay/Neuter - (Y)es, (N)o </li>
    <li> Boroughs - Bronx, Queen, Manhattan, Brooklyn, Staten Island, Other.</li> 
    <li> Months - All 12 months present.</li>
    <li> Years - 2015 through 2021.</li>
</ul
<br></br>

#### Gender Distribution
For this section the analysis will look into:
1. How many dog per gender/what is the percentage of each?
2. Spay/Neutered percentage overall and per gender?

The code for the total number and percentage was a bit extensize has it placed the separte visualizations side by side along with incorporating bar labels and an external legend.

![Gender_dist](https://github.com/julyndav/Python/blob/main/DOHMH%20Dog%20Bite%20Analysis/Images/gender_dist.png)<p></p>

The genders were also separated out in terms of Spay/Neuter percentages.<p>
![gendr_snprcnt](https://github.com/julyndav/Python/blob/main/DOHMH%20Dog%20Bite%20Analysis/Images/gendr_spnt.png)



**Gender Insights:**
<ul>
  <li>Female dogs make up about 15% of the data. </li>
  <li>With almost 50% with gender unknown, it points to the dog running away after the bite incident</li>
  <li>Total number of dogs: 22658</li>
  <li>Number of dogs that have been Spayed/Neutered: 5875</li>
  <li>Number of dogs NOT Spayed/Neautered:16783</li>
</ul>
The percentages of "fixed" (spayed/neutered) was also visualized.  26% were yes while 74% of the dog have not been fixed.
A small percentage (0.6%) of dogs with an unknown gender were recorded as being spayed or neutered. This discrepancy raises questions about the accuracy of the data. How to have the spay/neuter status recorded without knowing the gender of the dog?
<br></br>

#### Age Analysis
Earlier in the data cleaning phase, the 'Age' column was reviewed after correcting the vaules and setting the data type. There were some outliers (ages over 20yrs) that were filtered out leaving the ages from 0-20. <p>
Out of curiosity, dogs that had reached 20yrs of age were singled out. This was done with a short section of python code.<p>
![olddogs](https://github.com/julyndav/Python/blob/main/DOHMH%20Dog%20Bite%20Analysis/Images/old_dogs.png)


