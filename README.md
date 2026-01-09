# Financial Fraud Detection Dashboard
Anomaly Detection in Credit Card Transactions | Tableau

## Problem Statement

Financial institutions face increasing challenges in identifying fraudulent credit card transactions due to high transaction volumes and evolving fraud techniques. 

The objective of this project is to design an interactive fraud detection system that can:
* Identify unauthorized or suspicious transactions
* Detect unusual spending patterns across demographics and categories
* Highlight geographic clusters of fraud
* Monitor time-based spikes in fraudulent activity
* Support real-time and data-driven fraud analysis


### Steps followed 

Step 1: Data Loading
* Opened Tableau Desktop
* Selected Text File from the Connect pane
* Loaded the credit card transactions dataset (cc_data.csv)
* Verified data types and field names in the Data Source view


Step 2: Data Understanding & Preparation
* Reviewed key fields such as:
    * Transaction Amount (Amt)
    * Transaction Date & Time (Trans Date Trans Time)
    * Gender
    * Category
    * Latitude (Lat) and Longitude (Long)
    * Fraud Indicator (Is Fraud)
* Ensured latitude and longitude fields were recognized correctly for geospatial analysis
* Confirmed no critical missing or invalid values affecting analysis

Step 3: Spending Distribution by Gender & Category
* Opened a new worksheet
* Dragged Amt to Columns
* Dragged Category and Gender to Rows
* Added Category to Color and Amt to Label
* Selected Box and Whisker Plot from Show Me
Purpose: Identify abnormal spending patterns and outliers that may indicate fraud.

Step 4: Geographic Distribution of Transactions
* Opened a new worksheet
* Dragged Long to Columns and Lat to Rows
* Converted both fields to Dimensions
* Dragged Amt to Color and Size
Purpose: Visualize transaction density and high-value transactions across locations.

Step 5: Fraud Location Mapping
* Opened a new worksheet
* Dragged Long to Columns and Lat to Rows
* Converted both to Dimensions
* Dragged Is Fraud to Color and Label
Purpose: Identify geographic fraud hotspots and regional fraud concentration.

Step 6: Time Series Analysis of Transactions
* Opened a new worksheet
* Dragged Trans Date Trans Time to Columns
* Changed date aggregation to Month
* Dragged Amt to Rows
* Changed the measure of Amt to Count
* Added Amt (Count) to Label
Purpose: Detect transaction volume trends and sudden spikes over time.


Step 7: Creation of Inflation-Adjusted Transaction Metric
* Navigated to Analysis → Create Calculated Field
* Created a calculated field named Inflation-Adjusted Transaction Amounts
* Applied the following formula:
[Amt] * (1 + 0.02) ^ (YEAR(TODAY()) - YEAR([Trans Date Trans Time]))

Step 8: Inflation-Adjusted Trend Visualization
* Opened a new worksheet
* Dragged Trans Date Trans Time to Columns
* Changed date level to Week Number
* Dragged Inflation-Adjusted Transaction Amounts to Rows
* Added Amt to Label
Purpose: Normalize transaction values across time to account for inflation.

Step 9: Dashboard Design & Layout
* Clicked on New Dashboard
* Set dashboard size for optimal screen visibility
* Added the following worksheets:
    * Spending Distribution (Box & Whisker Plot)
    * Geographic Transaction Map
    * Fraud Location Map
    * Monthly Time Series Chart
    * Inflation-Adjusted Transaction Trend

Step 10: Interactivity & Formatting
* Ensured consistent color themes across all visuals
* Applied legends and labels for clarity
* Enabled cross-filtering for interactive exploration
* Optimized tooltips to display transaction and fraud details

Step 11: Final Review & Publishing
* Reviewed dashboard for accuracy and usability
* Validated insights against fraud detection objectives
* Saved and exported the Tableau workbook
* Prepared the dashboard for sharing and presentation

# Key KPIs & Metrics

The dashboard tracks the following critical fraud detection metrics:

Transaction Metrics:
* Total Number of Transactions
* Total Transaction Amount
* Inflation-Adjusted Transaction Amount
* Average Transaction Value
* Monthly Transaction Count
Fraud Metrics:
* Total Fraudulent Transactions
* Fraud vs Non-Fraud Transaction Distribution
* Fraud Concentration by Location
* Fraud Frequency Over Time
Demographic & Category Metrics:
* Transaction Amount by Gender
* Spending Distribution by Category
* Outliers and Extreme Transaction Values
* Category-wise Fraud Exposure

# Key Insights
* Spending behavior varies significantly across categories and genders, with noticeable outliers indicating potential fraud
* Fraudulent transactions tend to cluster geographically rather than being evenly distributed
* Monthly transaction trends reveal sudden spikes that may indicate coordinated fraud attempts
* Inflation-adjusted analysis provides clearer long-term spending comparisons

# Conclusion
This project demonstrates how Tableau dashboards and anomaly detection techniques can be effectively used for real-time financial fraud monitoring. By integrating demographic, geographic, temporal, and inflation-adjusted insights, the dashboard provides a comprehensive view of transaction behavior and fraud risk.













