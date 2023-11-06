# Preliminary_Forecast_Presentation
Revision of Forecast

- ![#f03c15](https://placehold.co/15x15/f03c15/f03c15.png) `Seth`
- ![#c5f015](https://placehold.co/15x15/c5f015/c5f015.png) `Heena`
- ![#1589F0](https://placehold.co/15x15/1589F0/1589F0.png) `Ayesha`




  
# Data Collection - GDP and CPI - Exogeneous Variables 
1. **For GDP:**
 - Consumer spending (Seth)
 - Business investments (Seth)
 - Government expenditure (Seth)
 - Real GDP - log (Seth)
 - Net exports (Heena)
 - Corporate Pricing (Seth)
 - Labor Market participation (Heena)
 - Mortgage rate (Ayesha)
 - Unemployment (Ayesha)
 
2. **For Inflation:** 
- Consumer price index (Seth)
- Yield curve/ Open market operations (Ayesha)
- Interest rates (Heena)
- Money supply  (Ayesha)
- Expectations (Seth)
- Gas prices due to the geopolitical events (Heena)
- Consumer spending (Seth)

# CPI Core - ![#f03c15](https://placehold.co/15x15/f03c15/f03c15.png) `Seth`

> - subset = subset(cpi, select= c("REF_DATE", "VALUE", "Alternative.measures"))
> - library(dplyr)
> - subset = subset%>% filter(Alternative.measures == "Measure of core inflation based on a factor model, CPI-common (year-over-year percent change)")
> - subset = subset(cpi, select= c("REF_DATE", "VALUE"))
> - subset = subset(cpi, select= c("REF_DATE", "VALUE", "Alternative.measures"))
> - library(dplyr)
> - library(quantmod)
> - subset$REF_DATE <- as.yearmon(subset$REF_DATE)
> - View(subset)
> - subset = subset%>% filter(Alternative.measures == "Measure of core inflation based on a factor model, CPI-common (year-over-year percent change)")
> - subset = subset(subset, select= c("REF_DATE", "VALUE"))
> - View(subset)

__Export Data to a xlsx file__

> - install.packages("openxlsx")
> - library(openxlsx)
> - file_path <- "/Users/kumbalas-INS/Documents/cpi_core.xlsx"
> - write.xlsx(subset, file_path, sheetName = "cpi_core1", rowNames = FALSE)
> - cat("Data exported to:", file_path, "\n")


__Data exported to: /Users/kumbalas-INS/Documents/cpi_core.xlsx__

![image](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/assets/147195203/34588c2a-7a6c-4365-a39d-a48027695b75) **Find the excel file here:** [cpi_core.xlsx](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/files/13245727/cpi_core.xlsx)

# Gas Prices dataset - 218 observations - ![#c5f015](https://placehold.co/15x15/c5f015/c5f015.png) `Heena`
`Not data available during 2000 - 2001`
> - gasp = read.csv("C:/Users/kumbalas-INS/Downloads/gas_prices.csv")
> - colnames(gasp)
> - subset = subset(gasp, select= c("REF_DATE", "VALUE", "GEO"))
> - library(dplyr)
> - subset = subset%>% filter(GEO == "CANADA")
> - subset = subset(subset, select= c("REF_DATE", "VALUE"))
> - library(quantmod)
> - subset$REF_DATE <- as.yearmon(subset$REF_DATE)

__Export Data to a xlsx file__

> - library(openxlsx)
> - file_path <- "/Users/kumbalas-INS/Documents/g.xlsx"
> - write.xlsx(subset, file_path, sheetName = "gasprices1", rowNames = FALSE)
> - cat("Data exported to:", file_path, "\n")


__Data exported to: /Users/kumbalas-INS/Documents/g.xlsx__

![image](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/assets/147195203/34588c2a-7a6c-4365-a39d-a48027695b75) **Find the excel file here:** [g.xlsx](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/files/13245822/g.xlsx)

# Unemployment Rate and Participation Rate - ![#c5f015](https://placehold.co/15x15/c5f015/c5f015.png) `Heena` + ![#1589F0](https://placehold.co/15x15/1589F0/1589F0.png) `Ayesha`
> - data = read.csv("C:/Users/kumbalas-INS/Downloads/data.csv")
> - colnames(data)
> - unique(data$Statistics)
> - unique(data$GEO)
> - unique(data$REF_DATE)
> - unique(data$Labour.force.characteristics)
> - subset = subset(data, select= c("REF_DATE", "VALUE", "Labour.force.characteristics"))
> - library(dplyr)
> - subset = subset%>% filter(Labour.force.characteristics == "Unemployment rate")
> - View(subset)
> - subset2 = subset(data, select= c("REF_DATE", "VALUE", "Labour.force.characteristics"))
> - subset2 = subset2%>% filter(Labour.force.characteristics == "Participation rate")
> - library(quantmod)
> - unemployment_rate = subset
> - View(unemployment_rate)
> - participation_rate = subset2
> - unemployment_rate = subset(data, select= c("REF_DATE", "VALUE"))
> - participation_rate = subset(data, select= c("REF_DATE", "VALUE"))
> - View(unemployment_rate)
> - View(participation_rate)
> - library(quantmod)
> - participation_rate$REF_DATE <- as.yearmon(participation_rate$REF_DATE)
> - View(participation_rate)
> - View(subset)
> - unemployment_rate1 = subset
> - participation_rate1 = subset2
> - rm(subset)
> - rm(subset2)
> - participation_rate = subset(participation_rate1, select= c("REF_DATE", "VALUE"))
> - unemployment_rate = subset(unemployment_rate1, select= c("REF_DATE", "VALUE"))
> - rm(unemployment_rate1)
> - rm(participation_rate1)
> - library(quantmod)
> - unemployment_rate$REF_DATE <- as.yearmon(unemployment_rate$REF_DATE)
> - participation_rate$REF_DATE <- as.yearmon(participation_rate$REF_DATE)
> - View(participation_rate)
> - View(unemployment_rate)


__Export Data to a xlsx file__


> - library(openxlsx)
> - file_path <- "/Users/kumbalas-INS/Documents/participation_rate.xlsx"
> - write.xlsx(participation_rate, file_path, sheetName = "participation_rate", rowNames = FALSE)
> - cat("Data exported to:", file_path, "\n")


__Data exported to: /Users/kumbalas-INS/Documents/participation_rate.xlsx__

 
![image](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/assets/147195203/34588c2a-7a6c-4365-a39d-a48027695b75) **Find the excel file here:** [participation_rate.xlsx](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/files/13246407/participation_rate.xlsx)


__Export Data to a xlsx file__


> - library(openxlsx)
> - file_path <- "/Users/kumbalas-INS/Documents/unemployment_rate.xlsx"
> - write.xlsx(unemployment_rate, file_path, sheetName = "unemployment_rate", rowNames = FALSE)
> - cat("Data exported to:", file_path, "\n")


__Data exported to: /Users/kumbalas-INS/Documents/unemployment_rate.xlsx__


![image](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/assets/147195203/34588c2a-7a6c-4365-a39d-a48027695b75) **Find the excel file here:** [unemployment_rate.xlsx](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/files/13246416/unemployment_rate.xlsx)

# Interest Rate - Monthly - - ![#c5f015](https://placehold.co/15x15/c5f015/c5f015.png) `Heena`
> - data = read.csv("C:/Users/kumbalas-INS/Documents/bank_rate_monthly.csv")
> - colnames(data)
> - library(quantmod)
> - data$Date <- as.yearmon(data$Date)
> - View(data)


__Export Data to a xlsx file__


> - library(openxlsx)
> - file_path <- "/Users/kumbalas-INS/Documents/bankratem.xlsx"
> - write.xlsx(data, file_path, sheetName = "Bankrts_m", rowNames = FALSE)
> - cat("Data exported to:", file_path, "\n")


__Data exported to: /Users/kumbalas-INS/Documents/bankratem.xlsx__

  
![image](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/assets/147195203/34588c2a-7a6c-4365-a39d-a48027695b75) **Find the excel file here:**[bankratem.xlsx](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/files/13246595/bankratem.xlsx)

# Monetary Aggregates - Money Supply - ![#1589F0](https://placehold.co/15x15/1589F0/1589F0.png) `Ayesha`
> - data = read.csv("C:/Users/kumbalas-INS/Documents/monetaryag.csv")
> - View(data)
> - data <- na.omit(data)
> - colnames(data)
[1] "date"         "M1...gross."  "M1....gross." "M2....gross."
> - library(quantmod)
> - data$date <- as.yearmon(data$date) **⬅ this is not the foremat that should be used**
> - View(data)


![image](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/assets/147195203/34588c2a-7a6c-4365-a39d-a48027695b75) **Find the .csv file here (not modified in r):**[monetaryag.csv](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/files/13246699/monetaryag.csv)

# Plots

![BoC_Chart](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/assets/147195203/d07a9f59-8980-463f-b6ee-92ef253d43fc)

__Figure 1: Household income refers to total income from all sources before taxes and deductions. Note: This chart presents median values.__ 

![BoC_Chart (1)](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/assets/147195203/54aa1592-7a84-4560-9f54-28750c4862ca)


__Figure 2: This chart presents median values.__


![BoC_Chart (2)](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/assets/147195203/88a3b75c-a4c3-4224-83d5-c8eb1a4c1dbe)


__Figure 3: Note: This chart presents a measure of median uncertainty based on the interquartile range of respondents’ forecasting outcomes for different time frames.__

# Mortagage Rates 

![image](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/assets/147195203/6187b771-a5b1-4e10-a8a5-a99c5fbb7b5e)**Find the excel file here:**[mrate.xlsx](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/files/13260692/mrate.xlsx)


# Steps to Forecast

Forecasting economic indicators like GDP and inflation using a Vector Autoregression (VAR) model is a multi-step process, and it involves not only technical proficiency in using statistical software but also a deep understanding of econometric theory. The steps below outline the process you would typically follow to perform such a forecast using the R programming language, along with the type of R code you would use for each step. Note that the specific code may vary based on the structure of your data and the specific requirements of your analysis.

Steps and R Code for VAR Model Forecasting
1. Prepare the Data
First, you need to read in all the datasets and combine them into a single data frame where each column represents one of the variables, and each row represents a time period (month).


# Load necessary libraries
library(vars)
library(readr)

# Read in your datasets
consumer_spending <- read_csv("path/to/consumer_spending.csv")
business_investments <- read_csv("path/to/business_investments.csv")
# ... continue for all datasets

# Combine into one data frame (assuming they all have the same number of rows)
data_combined <- data.frame(consumer_spending, business_investments, ...)
2. Test for Stationarity
VAR models require all data to be stationary. You will likely need to difference or transform your data to achieve stationarity.

r
Copy code
# Test for stationarity
library(tseries)
adf.test(data_combined$variable_name)

# Difference the data if necessary
data_combined_diff <- diff(data_combined)
3. Determine the Lag Order
You'll need to identify the optimal number of lags for the VAR model.


# Select the lag order
lag_selection <- VARselect(data_combined_diff, lag.max = 15, type = "both")
optimal_lag <- lag_selection$selection$AIC(n)
4. Create the VAR Model
Create the VAR model using the chosen lag order.


# Fit the VAR model
var_model <- VAR(data_combined_diff, p = optimal_lag, type = "both")
5. Check for Serial Correlation
Ensure that the residuals of your VAR model do not exhibit serial correlation.


# Diagnose the model
serial.test(var_model)
6. Forecasting
Forecast the future values using the VAR model.


# Forecast future values
forecast_length <- 45 # months
var_forecast <- predict(var_model, n.ahead = forecast_length)
7. Transform the Forecasts Back (If You Differenced the Data)
If you differenced the data to achieve stationarity, you need to reverse this process on your forecasts to make them interpretable.


# Convert forecasts back to original scale if the data was differenced

8. Evaluate the Forecasts
You may want to evaluate the forecasts by comparing them to some benchmark or through out-of-sample testing if you have withheld some data for validation.


Copy code
# Code for evaluating the forecasts
# This will depend on the method of evaluation you choose
Conclusion
The above steps are a generic outline, and the actual implementation will depend on the specifics of your datasets and the assumptions you are comfortable making. It's also worth noting that the vars package in R is one of many tools you can use for this type of analysis. It is important to understand the theory behind VAR models and the implications of the decisions made at each step, such as how to handle non-stationarity and the choice of lag length.

Before running any code, ensure that your datasets are formatted correctly, with consistent time periods and no missing values. Additionally, it's important to have a solid understanding of the underlying economic theory guiding the selection of variables to include in the model, as well as the expected relationships between them.

Remember, econometric modeling is as much an art as a science, requiring careful judgment and iterative refinement to produce reliable forecasts.





# What are the underlying economic theory guiding the selection of variables to include in the model?

The selection of variables in an econometric model like a Vector Autoregression (VAR) is guided by both economic theory and empirical considerations. Here are some of the theoretical and practical factors to consider:

Economic Theory
Theoretical Relevance: Variables should be chosen based on their theoretical importance to the economic indicators being forecasted. For GDP, this might include components of the expenditure approach to calculating GDP (i.e., consumption, investment, government spending, and net exports).

Causality and Correlation: Economic theory can suggest causal relationships that are worth investigating. For example, increases in government expenditure might theoretically stimulate short-term GDP growth, or high unemployment might lead to lower consumer spending.

Transmission Mechanisms: The way changes in one variable affect others (e.g., how interest rates influence investment and consumption, and in turn GDP) is fundamental to economic theory and informs variable selection.

Leading Indicators: Some variables are included because they are believed to be leading indicators of economic activity, such as the yield curve for forecasting recessions.

Market Expectations: Expectations can be self-fulfilling in economics. For instance, if consumers expect inflation to rise, they may spend more now, boosting GDP in the short term.

Policy Variables: These are variables that policymakers directly control, such as open market operations that influence money supply and interest rates.

Empirical Considerations
Data Availability and Quality: The variable must have reliable and consistent historical data available for the period being studied.

Stationarity: For VAR models, the data should ideally be stationary. If a variable is integrated of order one (I(1)), its first difference is often used.

Endogeneity: In a VAR model, all variables are treated as endogenous. If theory strongly suggests that some variables are exogenous, a different modeling approach may be needed.

Multicollinearity: Highly correlated independent variables can distort the results of a regression analysis, so it's important to check for multicollinearity and potentially exclude some variables.

Structural Breaks: If the economic relationship between variables has changed over time due to a structural break (e.g., a major policy change or a financial crisis), this needs to be accounted for in the model.

Econometric Tests: Empirical tests like Granger causality tests can help determine whether a variable should be included based on whether it provides any predictive power for the variables of interest.

Practical Application in Model Selection
The practical application of these theories involves:

Literature Review: Reviewing academic and industry literature on similar models to understand which variables are commonly used and why.
Expert Consultation: Speaking with economists and industry experts to understand which variables they believe are most important.
Model Testing: Using statistical methods to test different combinations of variables to see which provide the best fit and forecasting power.
Model Validation: Validating the model using out-of-sample tests to ensure it predicts well not just in-sample, but also for data it hasn't been trained on.
In summary, selecting variables for a VAR model to forecast GDP and inflation is a complex task that should be based on a combination of economic theory and empirical evidence. Each variable should have a justified place in the model based on its expected relationship with the variables being forecasted and its historical behavior.


# Sources For Data

1. Bank of Canada - Expectations data: https://www.bankofcanada.ca/publications/canadian-survey-of-consumer-expectations/canadian-survey-of-consumer-expectations-survey-data/
2. Corporate profits have contributed disproportionately to inflation: https://www.epi.org/blog/corporate-profits-have-contributed-disproportionately-to-inflation-how-should-policymakers-respond/
3. Bank of Canada - International Portfolio Rebalancing and Fiscal Policy Spillovers:https://www.bankofcanada.ca/2023/11/staff-working-paper-2023-56/
4. Identifying News Shocks from Forecasts, September 2023, International Monetary Funds: [wpiea2023208-print-pdf.pdf](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/files/13260831/wpiea2023208-print-pdf.pdf)
5. How to Improve Inflation Forecasting in Canada - IMF Working Paper: [wpiea2019190-print-pdf.pdf](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/files/13262729/wpiea2019190-print-pdf.pdf)






