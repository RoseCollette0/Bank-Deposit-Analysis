# Term Deposit Subscription Prediction – Banking Marketing Analysis
## Overview
This project analyzes a real-world banking dataset to understand the factors that influence whether a customer subscribes to a term deposit following a marketing campaign. The goal is to uncover actionable insights using Excel to guide marketing strategies, improve targeting, and increase campaign efficiency.

## Objectives
- Predict the likelihood of a customer subscribing to a term deposit
- Identify the most influential factors affecting customer decisions (e.g., loan status, call duration, previous campaign outcomes)
- Determine the optimal number of contact attempts and the importance of call duration
- Reduce operational costs by minimizing outreach to low-potential customers

##  THE CAMPAIGN PERFORMANCE OVERVIEW DASHBOARD (Snipet)

[CAMPAIGN STRATEGY OPTIMIZATION DASHBOARD](![Campaign Perf  Dashboard](https://github.com/user-attachments/assets/19f0d439-66fc-48aa-8285-7e6a7c3c13e2)


## Tools and Techniques
- Microsoft Excel  
- Excel Pivot Tables  
- Data Cleaning and Preparation  
- Exploratory Data Analysis (EDA)  
- Dashboard Design and Visualization  

## Business Impact
- Improved marketing efficiency through targeted customer segmentation
- Reduced campaign costs by focusing on high-potential leads
- Increased subscription rates by identifying key conversion drivers
- Data-driven insights to support campaign planning and execution

## Dataset
The dataset contains 41,177 customer records and includes features such as:
- Demographic details (age, job, marital status, education)
- Financial information (balance, housing loan, personal loan, default status)
- Interaction history (number of contacts, duration of last contact, previous outcomes)
- Macroeconomic indicators (employment variation rate, euribor3m, consumer price index, consumer confidence index)
- Time-related features (month, day of the week)

## Project Status
- Data Cleaning and Preparation: Completed  
- Exploratory Data Analysis: Completed  
- Dashboard Development: Completed  
- Insights Summary: Included  

## Data Dictionary
AGE: The customer’s age.

JOB: The customer’s type of job.

MARITAL: The customer’s marital status.

EDUCATION: The customer’s level of education.

DEFAULT: Refers to whether a customer has previously failed to repay a loan or financial obligation.

HOUSING: Whether the customer has a housing loan.

LOAN: Whether the customer has a personal loan.

CONTACT: is the type of communication channel used to contact customers.

MONTH: The month in which the customer was last contacted.

DAY OF WEEK: The day of the week when the customer was last contacted.

DURATION: This represents the last contact duration in seconds.

CAMPAIGN: This represents the number of times the customer was contacted during the campaign.

PDAYS: is the number of days that have passed since a customer was last contacted during a previous marketing campaign.

PREVIOUS: The number of times the customer was contacted before the current campaign.

POUTCOME: Stands for the outcome of the previous marketing campaign. 

EMPLOYMENT VARIATION RATE: Represents the quarterly change in the employment rate.

CONSUMER PRICE INDEX (CPI): measures the average price level of consumer goods and services.

CONSUMER CONFIDENCE INDEX: CCI measures consumers' optimism or pessimism about the economy.

EURIBOR3M: is a 3-month Euro Interbank Offered Rate (Euribor). This is the interest rate at which European banks lend money to each other for a period of three months.

NR.EMPLOYED: stands for the number of employees in the economy, which is a macroeconomic indicator reflecting overall employment levels. 

Y: Refers to whether a customer accepted or rejected a bank's offer.


##  DATA CLEANING AND WRANGLING PROCESSES

### DATA CLEANING 

1. Dataset Loading and Null Value Check:
The dataset was loaded into Microsoft Excel, and a quick check for null values was done using the filter function. The =COUNTBLANK(range) formula was also used to double-check. No missing values were found in the dataset.
2. Text Normalization for Readability:
The `Find and Replace` function was used to convert the first letters of each word in the dataset columns into sentence case. This step was done to improve readability and ensure consistency in presentation across the dataset.

3. Spelling and Uniformity Correction:
The Find and Replace function was used to fix any spelling errors and make sure similar words were used consistently across the columns. This was done to maintain consistency in terminology throughout the dataset.

4. Whitespace Check:
The ‘Filter’ function was used to check the dataset, and it confirmed that there were no extra spaces. Therefore, no further trimming was needed.

5. Data Type Consistency:
   A thorough check was done to make sure the data types were consistent across the dataset. Numeric values were placed in the correct fields, and categorical data was assigned properly.

6. Outlier Detection:
   - The dataset was checked for outliers or unusual rows that could indicate data entry errors or anomalies using the ‘filter’ function. After reviewing the data, no significant outliers were detected.

7. Redundant or Duplicate Data:
The dataset was checked for duplicate records, and duplicate rows found, were deleted to maintain data integrity and prevent repetition.

8. Column Header Consistency:
In conclusion of the cleaning process, a final check was made on the column headers to ensure the names were consistent with the data given. Everything was aligned correctly, so there was no confusion when analyzing the data.


### DATA WRANGLING 

During the analysis process, several transformations and categorizations were applied to facilitate deeper insights and comparisons. Below are the key wrangling operations:

1.	Quarterly Column Creation from Months:
A new column labeled `Quarter` was derived from the `Month` column. 
This column was created by mapping each month to its respective quarter (Q1, Q2, Q3, or Q4), based on the month number:
•	Q1: January, February, March
•	Q2: April, May, June
•	Q3: July, August, September
•	Q4: October, November, December
  - This categorization allows for the grouping of data by quarters, facilitating time-based analyses.

2.	CPI Grading from CPI Column:
The `CPI` column was used to derive a new categorical column called `CPI_Grade`. 
Based on the CPI values, they were assigned to specific categories (e.g., 'Low', 'Medium', 'High'). 
This grading enabled a better understanding of inflation trends.

3.	CCI Grading from CCI Column:
  A new column called `CCI_Grade` was created by categorizing the CCI values into ranges and since the `CCI` values collected were all in negatives, they were graded in these ranges;
•	-20s: Values in the range of -20 to -29
•	-30s: Values in the range of -30 to -39
•	-40s: Values in the range of -40 to -49
•	-50s: Values in the range of -50 to -59
  - This grading system helped to classify customer confidence levels and study its relationship with deposits.

4.	Euribor3M Rating from Euribor3M Column:
The `Euribor3M` values were categorized into three levels based on their values. The ratings were:
•	Low: Euribor3M values < 1%
•	Medium: 1% ≤ Euribor3M < 2%
•	High: Euribor3M values ≥ 2%
No Euribor3m rates in the dataset was < or = 1, hence no low rates are recorded.
This transformation helped analyze the relationship between interest rates and subscription deposit volumes.

5.	Responses from the Y Column:
The `Y` column, which originally contained 'yes' or 'no' responses, was split into two separate columns:
•	Yes Column: Counted the number of 'yes' responses.
•	No Column: Counted the number of 'no' responses.
This transformation allowed for a clearer analysis of the distribution of 'yes' and 'no' responses across the dataset.

Conclusion:
After completing the cleaning and wrangling steps, the dataset is now ready for detailed analysis. The data is structured, standardized, and enriched with additional variables that will allow for in-depth insights into trends and patterns. 

##  INSIGHT & RECOMMENDATION – TERM DEPOSIT SUBSCRIPTION ANALYSIS

This project analyzes a real-world banking dataset to uncover actionable insights into the factors that influence a customer's decision to subscribe to a term deposit following a marketing campaign. The goal is to help the bank improve targeting, optimize marketing strategies, and increase campaign efficiency using Excel.

### INSIGHT 
The analysis reveals that subscription behavior is shaped by customer demographics, financial history, engagement patterns, and macroeconomic sentiment. High subscription rates are found among:

•	Older adults (ages 61–82)
•	Students and retirees
•	Customers without housing or personal loans
•	Non-defaulters and previously successful contacts
•	Those contacted 1–3 times with 2–5 minute calls
Additionally, external economic indicators play a role:

•	During periods of low Consumer Confidence Index (CCI), when consumers are more pessimistic about the economy, subscription rates increase, suggesting people lean toward secure saving options like term deposits.
•	Moderate EURIBOR 3M rates, indicating economic stability, also correlate with higher subscription volumes. This implies that people feel more confident locking in savings when interest rates are steady rather than volatile.
•	For the Consumer Price Index (CPI), the data shows that higher subscription rates occur when CPI is low, indicating that during low inflation periods, customers are more willing and financially able to commit to long-term savings. As inflation rises (higher CPI), subscriptions tend to decline, likely due to increased financial strain on consumers.

### RECOMMENDATION
The bank should;

1.	Focus campaigns on high-performing customer segments with favorable financial profiles and previous positive engagement.
2.	Optimize contact strategies to 1–3 call attempts and 2–5 minutes duration per call.
3.	Prioritize and intensify marketing efforts during periods of low CCI, moderate EURIBOR 3M rates, and low CPI, when consumers are more open to saving.
4.	Reduce outreach to customers with high risk (e.g., defaulters) or low engagement history to minimize operational costs.
5.	Consider using financial education programs and incentive-based campaigns to improve outreach to low-performing but potentially convertible segments (e.g., younger customers, blue-collar workers).

In summary, by targeting the right customers, at the right time and under the right economic conditions, the bank can significantly improve campaign effectiveness, optimize spending, and drive stronger long-term subscription outcomes.



##  Insight & Recommendation Summary – Term Deposit Subscription Analysis

| **Factor Analyzed**                          | **Key Insight**                                                                                      | **Recommendation**                                                                                      |
|---------------------------------------------|-------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------|
| **Contact Attempts per Campaign**           | 80.67% of successful subscriptions occur within 1–3 calls; returns drop significantly after 6 calls. | Limit contact attempts to 1–3; set a cutoff around 6 to reduce costs and avoid customer fatigue.         |
| **Age**                                     | Customers aged 61–82 have the highest subscription rate (43–49%).                                     | Prioritize targeting older adults; explore tailored strategies for younger age groups (17–27).          |
| **Job**                                     | Students (31%) and retirees (25%) convert best; blue-collar and service workers have the lowest rates. | Focus on high-performing occupations; offer tailored incentives to low-performing job segments.         |
| **Marital Status**                          | Singles (14.01%) subscribe more than married or divorced individuals.                                 | Design marketing strategies that appeal to singles; test family-oriented offers for married/divorced.   |
| **Education**                               | University-educated and unknown education groups show highest subscription rates.                     | Prioritize degree holders; improve accessibility for lower-educated groups via simplified communication. |
| **Previous Campaign Outcome**               | Customers with past positive responses have a 65.11% success rate.                                    | Re-target previously successful contacts; deprioritize those with past negative responses.              |
| **Call Duration**                           | 2–5 minute calls (120–300 seconds) yield highest engagement.                                          | Encourage optimal call lengths with personalized offers to maintain engagement.                         |
| **Default History**                         | Non-defaulters are far more likely to subscribe (4196 Yes vs. 3 for confirmed defaulters).            | Focus on customers without defaults; use risk-based strategies for others.                              |
| **Day of Contact**                          | Thursday, Tuesday, and Wednesday have the highest conversion rates.                                   | Prioritize outreach on high-performing days; rethink Monday strategy.                                   |
| **Housing Loan Status**                     | Customers without housing loans are more likely to subscribe.                                         | Target non-loan holders; offer installment plans to customers with housing loans.                       |
| **Personal Loan Status**                    | Subscription rate is higher among those without personal loans.                                       | Focus on non-borrowers; offer specific financial plans to personal loan holders.                        |
| **Consumer Confidence Index (CCI)**         | Subscriptions increase during periods of low confidence.                                               | Launch campaigns during economic pessimism; offer premium deals when confidence is high.                |
| **Consumer Price Index (CPI)**              | Subscriptions increase when CPI is low (i.e., low inflation periods).                                 | Emphasize term deposit benefits during low inflation periods; adjust messaging during high CPI.         |
| **EURIBOR 3M**                              | Subscriptions peak at moderate EURIBOR levels, suggesting trust in stable economies.                  | Promote term deposits during economic stability; reassure customers during volatile rate changes.       |
