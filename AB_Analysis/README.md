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
<p></p>

### Outlier Analysis
<ul>
<li>Identified extreme high-value orders (>$20K and ~$2.5K)</li>
<li>1% of users contributed disproportionately to revenue</li>
<li>Removing outliers:</li>
  <ul>
  <li>Increased conversion clarity</li>
<li>Eliminated artificial inflation of AOV</li></ul>
</ul>
<b>Key Insight:</b>
A small number of anomalous transactions can significantly distort A/B test results.
<br></br>

## Conclusion for A/B Analysis:
### Deploy Variant B
<ul>
<li>Conversion rate improvements are statistically significant and consistent</li>
<li>Revenue gains are driven by increased conversions, not order size</li>
<li>Results remain valid even after removing anomalies</li>
</ul>
While large orders influenced revenue metrics, they did not alter the overall conclusion.
<p></p>

### Key Takeaways
<ul>
<li>Conversion rate is a more reliable success metric than revenue alone</li>
<li>Outliers can significantly distort experimental results</li>
<li>Structured prioritization frameworks improve decision-making</li>
<li>Statistical validation is critical before implementing changes</li>
</ul>
<br></br>

## Tools & Skills Demonstrated
<b>Languages & Libraries:</b>
<ul>
<li>Python</li>
<li>Pandas, NumPy</li>
<li>Matplotlib, Seaborn</li>
<li>SciPy</li>
</ul>
<p></p>

<b>Core Skills:</b>
<ul>
<li>Data cleaning & preprocessing</li>
<li>Exploratory data analysis (EDA)</li>
<li>Outlier detection & handling</li>
<li>Hypothesis prioritization (ICE/RICE)</li>
<li>Statistical hypothesis testing</li>
<li>A/B testing methodology</li>
<li>Data visualization</li>
