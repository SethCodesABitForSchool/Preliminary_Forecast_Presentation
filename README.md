# Preliminary_Forecast_Presentation
Revision of Forecast

- ![#f03c15](https://placehold.co/15x15/f03c15/f03c15.png) `#Text.`
- ![#c5f015](https://placehold.co/15x15/c5f015/c5f015.png) `#c5f015`
- ![#1589F0](https://placehold.co/15x15/1589F0/1589F0.png) `#1589F0`




  
# Data Collection - GDP and CPI - Exogeneous Variables 
1. For GDP:
 - Consumer spending (Seth)
 - Business investments (Seth)
 - Government expenditure (Seth)
 - Real GDP - log (Seth)
 - Net exports (Heena)
 - Corporate Pricing (Seth)
 - Labor Market participation (Heena)
 - Mortgage rate (Ayesha)
 - Unemployment (Ayesha)
 
2. For Inflation: 
- Consumer price index (Seth)
- Yield curve/ Open market operations (Ayesha)
- Interest rates (Heena)
- Money supply  (Ayesha)
- Expectations (Seth)
- Gas prices due to the geopolitical events (Heena)
- Consumer spending (Seth)

# Data wrangling - CPI Core - Codes

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

# Gas Prices dataset - 218 observations 

![#f03c15](https://placehold.co/15x15/f03c15/f03c15.png) `Not data available during 2000 - 2001`
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

# Unemployment Rate and Participation Rate - Heena 
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
> - library(openxlsx)
> - file_path <- "/Users/kumbalas-INS/Documents/participation_rate.xlsx"
> - write.xlsx(participation_rate, file_path, sheetName = "participation_rate", rowNames = FALSE)
> - cat("Data exported to:", file_path, "\n")
- __Data exported to: /Users/kumbalas-INS/Documents/participation_rate.xlsx__
 
![image](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/assets/147195203/34588c2a-7a6c-4365-a39d-a48027695b75) **Find the excel file here:** [participation_rate.xlsx](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/files/13246407/participation_rate.xlsx)

> - library(openxlsx)
> - file_path <- "/Users/kumbalas-INS/Documents/unemployment_rate.xlsx"
> - write.xlsx(unemployment_rate, file_path, sheetName = "unemployment_rate", rowNames = FALSE)
> - cat("Data exported to:", file_path, "\n")
- __Data exported to: /Users/kumbalas-INS/Documents/unemployment_rate.xlsx__

![image](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/assets/147195203/34588c2a-7a6c-4365-a39d-a48027695b75) **Find the excel file here:** [unemployment_rate.xlsx](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/files/13246416/unemployment_rate.xlsx)







