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

![image](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/assets/147195203/34588c2a-7a6c-4365-a39d-a48027695b75) `Find the excel file here:`[cpi_core.xlsx](https://github.com/SethCodesABitForSchool/Preliminary_Forecast_Presentation/files/13245727/cpi_core.xlsx)

# Gas Prices dataset - 218 observations 

![#f03c15](https://placehold.co/15x15/f03c15/f03c15.png) `Not data available during 2000 - 2001`
> - gasp = read.csv("C:/Users/kumbalas-INS/Downloads/gas_prices.csv")
> - colnames(gasp)

 [1] "REF_DATE"      "GEO"           "DGUID"         "Type.of.fuel"  "UOM"           "UOM_ID"       
 [7] "SCALAR_FACTOR" "SCALAR_ID"     "VECTOR"        "COORDINATE"    "VALUE"         "STATUS"       
 [13] "SYMBOL"        "TERMINATED"    "DECIMALS"     


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

