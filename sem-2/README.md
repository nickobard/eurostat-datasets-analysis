# Project 2: Regression Analysis with Multiple Regressors

This code performs a statistical analysis of life expectancy data in relation to per capita income and other factors for a set of countries. The main objectives are to explore the data, analyze the impact of numerical and categorical variables on life expectancy, and build a regression model to predict life expectancy based on these variables. Here is a summary of the key steps and findings:

Project is done in a team of three students. My parts of work are highlighted with ⭐.

### 1. Data Preparation and Exploration
- Dataset Overview:
  - The dataset contains observations on 29 countries, including 20 industrialized countries and 9 petroleum-exporting countries.
  - Variables include:
    - Country: Name of the country.
    - Life: Life expectancy in years.
    - Income: Per capita income in 1974 U.S. dollars.
    - Type: Categorical variable indicating "Industrialized" or "Petroleum" countries.
- Data Cleaning:
  - Excluded South Africa due to missing income data, resulting in a clean dataset for analysis.
- Feature Engineering:
  - Created a new categorical variable Government to represent the governance model of each country:
    - Categories: "Parliamentary or Constitutional Monarchy", "Republic", "Authoritarian/One-Party Regimes".
- Descriptive Statistics:
  - Calculated summary statistics for Life and Income.
  - Examined distributions and identified differences between country types.
### 2. Data Visualization
- Life Expectancy by Country:
  - Bar plot showing life expectancy, highlighting the significant difference between industrialized and petroleum-exporting countries.
- Income vs. Life Expectancy Scatter Plot:
  - Scatter plot with Income on the x-axis and Life on the y-axis.
  - Points colored by Type and shaped by Government.
  - Observations:
    - Petroleum countries tend to have lower income and life expectancy.
    - All petroleum countries are under "Authoritarian/One-Party Regimes".
- Density Plot of Life Expectancy:
  - Visual comparison of life expectancy distributions between country types, showing a clear distinction.
### 3. Analysis of Numerical Regressor (Income)
- Logarithmic Transformation:
  - Applied a log transformation to Income to linearize the relationship with Life.
- Linear Regression Model:
  - Model: $\text{Life} = \beta_0 + \beta_1 \log(\text{Income}) + \varepsilon$.
  - Findings:
    - Significant positive relationship between log-transformed income and life expectancy.
    - Interpretation: A 1% increase in income leads to an approximate 0.09-year increase in life expectancy.
- Residual Analysis:
  - Identified issues with residual distribution due to outliers.
  - Cook's distance indicated influential data points affecting the model.
### 4. Analysis of Categorical Regressor (Type)
- ANOVA Test:
  - Tested the difference in mean life expectancy between industrialized and petroleum countries.
  - Results indicated a significant difference.
- Linear Model with Type:
  - Model showed that Type alone explains a substantial portion of the variance in life expectancy $(R^2 \approx 0.83)$.
  - Interpretation: Petroleum countries have, on average, 21 years lower life expectancy than industrialized countries.
### ⭐ 5. Combined Analysis of Numerical and Categorical Regressors
- Interaction Model:
  - Explored a model with both Income and Type and their interaction.
  - Findings:
    - Slight improvement in model fit $(R^2 \approx 0.84)$.
    - Some regressors were not statistically significant.
- Multicollinearity Issue:
  - Identified strong multicollinearity between Type and Government.
  - Decided to exclude Government from the model due to redundancy.
### ⭐ 6. Model Refinement and Selection
- Model Comparison:
  - Compared models with different combinations of regressors.
  - Used adjusted $R^2$ and AIC for model evaluation.
  - Determined that log(Income) and Type were the most significant predictors.
- Final Model:
  - Selected the model: $\text{Life} = \beta_0 + \beta_1 \log(\text{Income}) + \beta_2 \times \text{Type}$.
  - Coefficients:
    - Intercept ($\beta_0$): Baseline life expectancy.
    - $\beta_1$: Effect of income on life expectancy.
    - $\beta_2$: Effect of country type on life expectancy.
- Interpretation:
  - A 1% increase in income results in an approximate 0.03-year increase in life expectancy.
  - Being a petroleum-exporting country reduces expected life expectancy by about 17 years.
### ⭐ 7. Model Diagnostics and Assumption Verification
- Normality of Residuals:
  - Performed tests (e.g., Shapiro-Wilk, Kolmogorov-Smirnov) to assess normality.
  - Detected deviations from normality due to outliers.
- Homoscedasticity:
  - Conducted Breusch-Pagan test to check for constant variance of residuals.
  - Results indicated heteroscedasticity.
- Impact on Conclusions:
  - Despite violations of some assumptions, the final model was considered acceptable based on adjusted R² and significance of predictors.
  - Alternative methods (e.g., robust regression) could be considered for further refinement.
### ⭐ 8. Interpretation and Conclusions
- Key Findings:
  - Income (log-transformed) and country type are significant predictors of life expectancy.
  - Petroleum-exporting countries have significantly lower life expectancy compared to industrialized countries, even after accounting for income.
- Implications:
  - Highlights the impact of economic factors and country characteristics on public health outcomes.
  - Suggests that governance and economic structure play a role in life expectancy beyond income levels.

***

Overall, the analysis provides insights into how life expectancy is influenced by economic indicators and country classification. By carefully selecting and evaluating models, the study identifies the most significant factors and addresses potential issues related to multicollinearity and model assumptions. The final model offers a practical interpretation of the relationship between income, country type, and life expectancy.
   