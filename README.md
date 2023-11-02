# Preliminary_Forecast_Presentation
Revision of Forecast


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
