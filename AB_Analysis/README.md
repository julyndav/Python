## A/B Testing Analysis: Increasing E-Commerce Conversion & Revenue
This analysis evaluates an A/B test on an e-commerce platform to determine whether marketing and UX changes (Variant B) improve conversion rate and revenue relative to the control (Variant A).

<b>Result:</b> Variant B delivered a statistically significant increase in conversion rate which was consistent both before and after removing anomalous users making it the recommended rollout, despite no significant change in average order value.

<b>[View the full notebook](https://github.com/julyndav/Python/blob/main/AB_Analysis/Telecom%20Analysis_AB_Testing.ipynb)</b>

## Business Problem:
The marketing team proposed several initiatives to increase revenue, including new traffic channels, promotional campaigns, and website feature enhancements. Testing every idea requires time and resources, so hypotheses needed to be prioritized before committing to a full A/B test.

## Objectives:
<ul>
<li>Prioritize hypotheses using structured frameworks (ICE, RICE)</li>
<li>Evaluate a live A/B test's impact on conversion rate and revenue</li>
<li>Identify and control for data quality issues and statistical anomalies</li>
<li>Deliver a clear rollout recommendation backed by statistical testing</li>
</ul>
<br>
  
## Key Insights:
<ul>
<li>Conversion rate improved by 15.98% in Variant B on raw data, and remained significant at 18.06% after removing anomalous users</li>
<li>Results are statistically significant (p < 0.05)Results are statistically significant in both cases (raw: p = 0.0110; filtered: p = 0.0096)</li>
<li>No statistically significant difference in average order value, either before (p = 0.8622) or after (p = 0.6730) filtering</li>
<li>A small number of high-value orders inflated Group B's raw revenue advantage. Once the high-value orders were removed, Group B's average order size was actually 9.13% lower than Group A's, with no statistical significance</li>
<li>58 visitors were found assigned to both test groups — a data integrity issue that was corrected before any statistical testing, to preserve the validity of the A/B comparison</li>
<b><li>Final recommendation: Deploy Variant B</li></b>
</ul>
  
**Business Impact:**  
Increasing conversion rate; even without a corresponding increase in order value, can drive meaningful revenue growth on its own, making Variant B a high-impact, low-risk rollout.
<p>
<br>
</p>
  
## Data Description
<p></p>

### Hypotheses Dataset:
| Column | Description |
| --- | --- |
| Hypotheses | Brief descriptions of the hypotheses |
| Reach | User reach, on a scale of 1 to 10 |
| Impact |Impact on users, on a scale of 1 to 10 |
| Confidence | Confidence in the hypothesis, on a scale of 1 to 10 |
| Effort | Resources required to test a hypothesis, on a scale of 1 to 10. The higher the Effort value, the more resource-intensive the test |
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
<li>Identified 58 visitors assigned to both test groups; a data integrity issue that would have compromised the validity of the A/B comparison</li>
<li>Removed multi-group visitors' records to ensure each group reflects a clean, non-overlapping population before any statistical testing</li>
</ul>
<p></p>

### 2. Hypothesis Prioritization (ICE vs RICE)
<b>Frameworks used:</b>
<ul>
<li>ICE = (Impact × Confidence) / Effort</li>
<li>RICE = (Reach × Impact × Confidence) / Effort</li>
</ul>

![comparison](https://github.com/julyndav/Python/blob/main/AB_Analysis/images/comparison.png)
<b>Key Insights:</b>
<ul>
<li>Top-performing hypotheses by RICE: #7, #2, #0, #6, #8</li>
<li>Hypotheses focused on traffic growth and promotions ranked highest</li>
<li>Low-impact cosmetic changes (e.g., background color, category structure) consistently ranked lowest on both frameworks</li>
</ul>
<b>Takeaway:</b> Initiatives that increase traffic and user engagement offer the greatest revenue potential. Cosmetic UI changes were not worth the testing investment.
<br></br>


## A/B Test Analysis
<p></p>

### Conversion Rate (Primary Metric)
<ul>
<li>Raw data: p = 0.0110, relative gain +15.98% — statistically significant</li>
<li>Filtered data (anomalies removed): p = 0.0096, relative gain +18.06% — still statistically significant</li>
</ul>
<p></p>

### Average Order Value
<ul>
<li>Raw data: p = 0.8622, relative gain +27.83% — not statistically significant</li>
<li>Filtered data: p = 0.6730, relative gain −9.13% — not statistically significant</li>
</ul>
<p></p>

### Outlier Analysis
![OutliersPrice](https://github.com/julyndav/Python/blob/main/AB_Analysis/images/order_by_prices.png)
<ul>
<li>Identified extreme high-value orders (one ~$20K, one ~$2.5K)</li>
<li>9 users were flagged as anomalous based on order count (>2 orders) or order value (>$2,000)</li>
<li>Removing these users clarified the true conversion effect and eliminated artificial inflation of Group B's average order value</li>
</ul>
<b>Key Insight:</b>
A small number of anomalous transactions can significantly distort A/B test results. Group B's apparent order-value advantage disappeared entirely once these were excluded.
<br></br>

## Final Recommendation:
### Deploy Variant B
<ul>
<li>Conversion rate improvement is statistically significant and consistent, both before and after removing anomalies</li>
<li>Revenue gains are driven by increased conversions, not by larger order sizes</li>
<li>The lack of order-size improvement doesn't change the recommendation, since conversion rate — not order value — was the primary success metric</li>
</ul>
<p></p>

### Key Takeaways
<ul>
<li>Conversion rate is a more reliable success metric than revenue alone when a small number of large orders can skew results</li>
<li>Data integrity checks (like catching dual-group assignment) must happen before statistical testing, not after — otherwise results can't be trusted</li>
<li>Outliers can significantly distort experimental results if not identified and addressed</li>
<li>Structured prioritization frameworks (ICE/RICE) help focus testing effort on the highest-impact ideas</li>
<li>Statistical validation is essential before implementing any product or marketing change</li>
</ul>
<br>

## Tools & Skills Demonstrated
<b>Languages & Libraries:</b> Python, Pandas, NumPy, Matplotlib, SciPy

<b>Core Skills:</b>
<ul>
<li>Data cleaning, validation, and integrity checks</li>
<li>Exploratory data analysis (EDA)</li>
<li>Outlier detection and handling</li>
<li>Hypothesis prioritization (ICE/RICE)</li>
<li>Statistical hypothesis testing (Mann-Whitney U)</li>
<li>A/B testing methodology</li>
<li>Data visualization</li>
