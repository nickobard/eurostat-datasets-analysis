# Project 3: Gross Domestic Product (GDP) Analysis

This code performs a comprehensive statistical analysis of the Gross Domestic Product (GDP) per capita of European countries for the year 2013. The main objectives are to explore factors influencing GDP per capita, select relevant regressors, build regression models, and validate model assumptions. Below is a summary of the key steps and findings:

Project is done in a team of three students. My parts of work are highlighted with ⭐.


### 1. Data Preparation
   - Dataset Selection: Retrieves GDP per capita data for European countries in 2013 from the Eurostat database using the get_eurostat function.
   - Data Cleaning:
     - Filters out aggregate regions (e.g., EU aggregates) to focus on individual countries.
     - Renames columns for clarity and converts country codes to country names using the countrycode package.
   - Initial Checks: Confirms there are no missing values in the dataset.
### 2. GDP Analysis
   - Descriptive Statistics:
     - Calculates statistical measures such as mean, median, and skewness for GDP per capita.
     - Observes a strong deviation of the mean from the median, indicating a skewed distribution.
   - Data Visualization:
     - Creates a histogram of GDP per capita to visualize its distribution.
     - Identifies potential clusters and notes the presence of outliers with exceptionally high GDP per capita.
### 3. Regressor Selection
   - Additional Data Sources:
     - Imports supplementary data from the Human Development Report, including:
       - Life Expectancy at Birth (LE)
       - Mean Years of Schooling (MYS)
       - Expected Years of Schooling (EYS)
       - Gross National Income Per Capita (GNIpc)
   - Data Transformation:
     - Calculates the Education Index (EI) based on MYS and EYS.
     - Computes Net Factor Income from Abroad per capita (NFIApc) by adjusting GNIpc and GDPpc, converting currencies as needed.
   - Binary Factor:
     - Introduces a binary variable BB_entry to indicate whether a country is part of the "Blue Banana" economic region.
### 4. Data Visualization
   - Scatter Plots:
     - GDP per capita vs. Life Expectancy: Shows a positive relationship and identifies clusters.
     - GDP per capita vs. Education Index: Displays a trend where higher education levels correlate with higher GDP per capita.
     - GDP per capita vs. NFIApc: Highlights outliers and general trends.
   - Bar Charts:
     - Ranks countries by GDP per capita, illustrating disparities among countries and the influence of Blue Banana affiliation.
### 5. Dependencies Among Regressors
   - Correlation Analysis:
     - Uses Spearman's rank correlation due to non-normality of data.
     - Finds significant negative correlations between:
       - Life Expectancy and NFIApc
       - Education Index and NFIApc (after removing outliers)
   - Statistical Tests:
     - T-tests and Wilcoxon Tests: Compare groups based on BB_entry to assess the impact of Blue Banana affiliation.
     - Findings:
       - Blue Banana affiliation significantly affects GDP per capita and other variables.
### ⭐ 6. Linear Modeling
   - Initial Linear Model:
     - Constructs a linear regression model with all regressors: GDPpc ~ LE + EI + NFIApc + BB_entry.
     - Interpretation:
       - Positive Influences: Life Expectancy, Education Index, and Blue Banana affiliation.
       - Negative Influence: Net Factor Income from Abroad per capita.
   - Model Fit:
     - Adjusted R-squared of approximately 0.98, indicating a very good fit.
### ⭐ 7. Model Refinement
   - Polynomial Transformations:
     - Applies polynomial functions to LE and NFIApc to capture non-linear relationships.
     - Evaluates models with polynomial terms, interactions, and combinations thereof.
   - Model Comparison:
     - Considers adjusted R-squared values and model complexity.
     - Identifies that adding polynomial terms slightly improves or maintains model performance without overfitting.
### ⭐ 8. Outlier Analysis
   - Identification of Outliers:
     - Uses Cook's Distance to detect influential data points.
     - Key Outliers: Luxembourg, Liechtenstein, and Norway.
   - Data Adjustment:
     - Removes identified outliers to improve model robustness.
     - Observes a slight decrease in model performance but gains in generalizability.
### ⭐ 9. Multicollinearity Check
   - Variance Inflation Factor (VIF):
     - Calculates VIF scores to assess multicollinearity among regressors.
     - Result:
       - All VIF values are below 4, indicating no significant multicollinearity.
### ⭐ 10. Model Assumption Tests
- Linearity:
  - Validates linearity through residual plots and prior transformations.
- Homoscedasticity:
  - Conducts the Breusch-Pagan test to confirm constant variance of residuals.
  - Result: No evidence of heteroscedasticity.
- Normality of Residuals:
  - Performs the Shapiro-Wilk test on residuals.
  - Result: Residuals are approximately normally distributed.
- Autocorrelation:
  - Assumes no autocorrelation due to cross-sectional data (single year).
### ⭐ 11. Final Model Selection
- Model Optimization:
  - Utilizes the Akaike Information Criterion (AIC) for model selection.
  - Employs a stepwise selection process to identify the best-fitting model.
- Final Model Specification:
  - Formula: GDPpc ~ NFIApc + BB_entry + EI + I(LE^2)
  - Interpretation:
    - NFIApc: Negative effect on GDP per capita.
    - BB_entry: Positive effect, indicating higher GDP per capita for Blue Banana countries.
    - Education Index (EI): Significant positive influence.
    - Squared Life Expectancy (LE^2): Captures non-linear effects on GDP per capita.
- Model Performance:
  - Adjusted R-squared of approximately 0.93, indicating strong explanatory power.
- Assumption Verification:
  - Confirms that all statistical assumptions are satisfied in the final model.
### ⭐ 12. Conclusion
- Key Findings:
  - Life Expectancy, Education Index, and Blue Banana affiliation are significant positive predictors of GDP per capita.
  - Net Factor Income from Abroad per capita negatively impacts GDP per capita.
- Implications:
  - Highlights the importance of human development indicators in economic performance.
  - Emphasizes the economic advantages associated with the Blue Banana region.
- Model Utility:
  - Provides a robust model for understanding factors affecting GDP per capita among European countries.
  - Can serve as a foundation for further economic and policy analysis.

***
Overall, this code systematically analyzes the factors influencing GDP per capita in European countries by:
- Data Integration: Combining data from Eurostat and the Human Development Report.
- Exploratory Data Analysis: Using statistical measures and visualizations to understand data distributions and relationships.
- Statistical Testing: Applying appropriate tests to assess dependencies and validate assumptions.
- Model Building: Creating and refining regression models to explain the variability in GDP per capita.
- Assumption Checking: Ensuring the final model meets all necessary statistical assumptions for validity.
- The analysis effectively demonstrates the interplay between economic indicators and human development factors, offering valuable insights into the determinants of GDP per capita across European nations.