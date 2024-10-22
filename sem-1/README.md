# Project 1: Crime Data Analysis

This code performs a comprehensive statistical analysis of crime data in Norway for the year 2021. The main objectives are data preparation, exploratory data analysis, and hypothesis testing using various statistical methods. Here's a summary of the key steps and processes

Project is done in a team of three students. My parts of work are highlighted with ⭐.

### 1. Country Selection
   - Parameter Calculation: Calculates a parameter M to select Norway as the country of interest for the analysis.
### 2. Imports Necessary Libraries
   - Loads essential R libraries for data manipulation and visualization:
     - cowplot, eurostat, ggplot2, gridExtra, repr, tibble, tidyr, vtable
### 3. Dataset Preparation
   - Data Download: Retrieves the crime dataset from Eurostat using get_eurostat().
   - Column Descriptions: Provides explanations for each column in the dataset.
   - Data Completeness Check: Verifies that there are no missing data for Norway in 2021.
   - Unit of Measure Explanation: Clarifies the different units of measure in the dataset.
   - Data Selection and Transformation:
     - Filters data for Norway's NUTS3 regions for the year 2021.
     - Selects relevant crime categories and renames them for clarity.
     - Adjusts the dataset to separate relative (rel) and absolute (abs) values.
     - Converts the iccs (crime categories) and geo (geographical regions) columns to factors.
### 4. Exploratory Data Analysis & Descriptive Statistics
   - Frequency Tables: Creates frequency tables to calculate probabilities and proportions of crimes by region and by type.
   - Data Visualization:
     - Generates bar plots to visualize the distribution of crime types across regions and vice versa.
     - Analyzes the plots to identify patterns, such as:
       - Theft being the most common crime across all regions.
       - Oslo having the highest relative amount of crimes in most categories.
### ⭐ 5. Contingency Table Analysis 
   -  Construction of Contingency Tables:
     - Builds contingency tables using both absolute and relative values.
     - Adjusts for overlapping crime categories by subtracting vehicle thefts from other thefts to avoid duplication.
   - Analysis with Margins:
     - Adds margins to display totals for each crime type and region.
     - Observes that Oslo has the highest crime probability and rate, while regions like Nordland have the lowest.
### ⭐ 6. Statistical Hypothesis Testing
   -  Pearson's Chi-Squared Test:
     - Attempts to test the independence between crime types and regions.
     - Notes that some expected frequencies are too low, violating test assumptions.
   - Test of Homogeneity:
     - Tests whether the distribution of crime types is consistent across regions.
     - Rejects the null hypothesis, indicating that distributions vary by region.
   - Fisher's Exact Test:
     - Applies this test due to low expected frequencies in the data.
   -    Concludes that crime types and regions are not independent.
###  7. Formulating and Testing Hypotheses
   - ⭐ Test 1: Total Criminality Comparison (2020 vs. 2021)
     - Objective: Determine if there's a significant difference in crime distribution between 2020 and 2021.
     - Methods Used:
       - Mann-Whitney U Test: Tests for differences in distributions; finds no significant difference.
       - Kolmogorov-Smirnov Two-Sample Test: Compares empirical distribution functions; also finds no significant difference.
     - Conclusion: Cannot reject the null hypothesis; crime distribution remained consistent between the two years.
   - Test 2: Crime Trend Analysis (2008 vs. 2019)
     - Objective: Examine changes in crime rates over time in the capital region.
     - Data Visualization:
       - Plots show a significant downward trend in crime rates using logarithmic scaling.
     - Statistical Testing:
       - Fisher's Exact Test: Tests independence between year and crime type.
       - Conclusion: Rejects the null hypothesis; significant decrease in crime rates over time.
   - Test 3: Country Comparison (Norway vs. Finland)
     - Objective: Compare crime rates between Norway and Finland in 2021.
     - Data Preparation:
       - Selects comparable crime categories and accounts for similar population sizes.
     - Statistical Testing:
       - Pearson's Chi-Squared Test: Tests for independence between country and crime type.
       - Conclusion: Rejects the null hypothesis; significant difference in crime rates between the two countries.
### 8. References
   - Cites sources and references used for data descriptions, methodologies, and guidelines, including Eurostat metadata and statistical guides.
   
***

Overall, the code demonstrates a systematic approach to analyzing crime data through:

- Data Preparation: Cleaning and transforming raw data for analysis.
- Exploratory Data Analysis: Using descriptive statistics and visualizations to understand data distributions and patterns.
- Hypothesis Testing: Applying appropriate statistical tests to investigate assumptions and draw conclusions.
- Data Interpretation: Providing practical insights based on statistical results and visual evidence.

The analysis effectively utilizes statistical techniques to explore crime patterns, test hypotheses about crime distributions, and compare crime rates across different years and countries.