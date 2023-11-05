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

![image](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/assets/147195203/34588c2a-7a6c-4365-a39d-a48027695b75) **Find the excel file here:**[mrate.xlsx](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/files/13260692/mrate.xlsx)



# Sources For Data

1. Bank of Canada - Expectations data: https://www.bankofcanada.ca/publications/canadian-survey-of-consumer-expectations/canadian-survey-of-consumer-expectations-survey-data/
2. Corporate profits have contributed disproportionately to inflation: https://www.epi.org/blog/corporate-profits-have-contributed-disproportionately-to-inflation-how-should-policymakers-respond/
3. Bank of Canada - International Portfolio Rebalancing and Fiscal Policy Spillovers:https://www.bankofcanada.ca/2023/11/staff-working-paper-2023-56/




