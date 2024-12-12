---
output:
  html_document: default
  pdf_document: default
---

# ZhangWuZhu_ENV872_EDA_FinalProject

## Summary

The 2021 Texas winter storm was a severe and unprecedented cold weather event that caused widespread power outages and significant damage across the state due to a combination of extreme temperatures (as low as -2°F/-19°C ) and infrastructure failures. 

Our team wishes to study the trend of occurrence of extreme low temperature events in Texas, and how does these events correlate with the local energy demand and electricity price. Using historical data, we hope to predict the grid demand for future extreme cold days for preparedness, increasing local resilience and energy security in winter.

The main research questions we are trying to answer are:
 1. How did local energy load and electricity price changed in 2016-2023?

 2. How does the frequency of extreme cold days correlates with energy load and electricity price in Texas?
 
 3. If following the past trend, how much energy will be demanded for preparing extreme cold days in 2024 and 2025?


## Investigators

Judy Hua Zhu
hua.zhu@duke.edu

Rosie Wu
rosie.wu@duke.edu

Zhaoxin Zhang
zhaoxin.zhang@duke.edu 

Master of Environmental Management
Duke Nicholas School of Environment


## Keywords

Extreme temperature, cold climate, electricity load, electricity price


## Database Information

 Data used for this analysis is from different sources. 
 
 Historical records of temperature were found in the archive API https://archive-api.open-meteo.com/v1/era5. Given the information on Texas's latitude and longitude and the start and end dates from January 2016 to December 2023, the API archive could provide data on daily temperature in Texas from 2016 to 2023. The API gave the maximum and minimum temperatures in Texas from 2016 to 2023 in degrees Celsius. 

Data from outside sources: 

 In the Raw folder under the Data folder, there are two sub-folders: EnergyLoad_ercot and EnergyPrice. EnergyLoad_ercot: The Electric Reliability Council of Texas (ERCOT) gave hourly energy load data in Texas, from year 2016 to 2023, in MW. EnergyPrice: The U.S. Energy Information Administration (EIA) contained monthly average electricity price data in cent/kwh from 2001 to 2024. The data for daily electricity prices was unavailable.
 
 All of the data from the three sources used in this analysis had a date column, which could ensure the time series analysis's viability. The data had continuous data on daily temperature, hourly load, and monthly price, which would be used for both time series and linear model analysis. All of the outside data listed above was accessed and retrieved in November 2024.
 
 The Raw data were all wrangled in the Data_Wrangling rmd file and the exported csv files are stored in the Processed folder under the Data folder. 
 

## Folder structure, file formats, and naming conventions 

 We have 3 general folders: Data, Data Wrangling & Analysis, Report
- Data folder: this folder contains csv data in 2 categories. Processed data: extracted and wrangled. Raw: data extracted directly from online searching or scrapping
- Data Wrangling & Analysis folder: this folder contains rmd files for data wrangling (which output were exported to Processed Data folder) and analysis process (Time Series, Linear Modeling, Visualizations)
- Report folder: Our final project report rmd file and html output is located in this folder.


## Metadata

Raw Data:

  1. File: EnergyLoad_ercot
  Shows the hourly energy load in MW from 2016 to 2023

  1.1. native_Load_2016.xlsx
    i. Columns: "Hour_End","COAST","EAST","FAR_WEST","NORTH","NORTH_C","SOUTHERN","SOUTH_C","WEST","ERCOT"
    ii. Column Meaning: "Each hour through a day", "Load in Coast weather zone", "Load in East weather zone", "Load in Far West weather zone", "Load in North weather zone", "Load in North Central weather zone", "Load in Southern weather zone", "Load in South Central weather zone", "Load in West weather zone", "Total ERCOT reported Load"

  1.2. native_Load_2017.xlsx
    i. Columns: "Hour Ending","COAST","EAST","FAR_WEST","NORTH","NORTH_C","SOUTHERN","SOUTH_C","WEST","ERCOT"
    ii. Column Meaning: "Each hour through a day", "Load in Coast weather zone", "Load in East weather zone", "Load in Far West weather zone", "Load in North weather zone", "Load in North Central weather zone", "Load in Southern weather zone", "Load in South Central weather zone", "Load in West weather zone", "Total ERCOT reported Load"
  
  1.3. native_Load_2018.xlsx
    i. Columns: "HourEnding","COAST","EAST","FAR_WEST","NORTH","NORTH_C","SOUTHERN","SOUTH_C","WEST","ERCOT"
    ii. Column Meaning: "Each hour through a day", "Load in Coast weather zone", "Load in East weather zone", "Load in Far West weather zone", "Load in North weather zone", "Load in North Central weather zone", "Load in Southern weather zone", "Load in South Central weather zone", "Load in West weather zone", "Total ERCOT reported Load"

  1.4. native_Load_2019.xlsx
    i. Columns: "HourEnding","COAST","EAST","FAR_WEST","NORTH","NORTH_C","SOUTHERN","SOUTH_C","WEST","ERCOT"
    ii. Column Meaning: "Each hour through a day", "Load in Coast weather zone", "Load in East weather zone", "Load in Far West weather zone", "Load in North weather zone", "Load in North Central weather zone", "Load in Southern weather zone", "Load in South Central weather zone", "Load in West weather zone", "Total ERCOT reported Load"

  1.5. native_Load_2020.xlsx
    i. Columns: "HourEnding","COAST","EAST","FAR_WEST","NORTH","NORTH_C","SOUTHERN","SOUTH_C","WEST","ERCOT"
    ii. Column Meaning: "Each hour through a day", "Load in Coast weather zone", "Load in East weather zone", "Load in Far West weather zone", "Load in North weather zone", "Load in North Central weather zone", "Load in Southern weather zone", "Load in South Central weather zone", "Load in West weather zone", "Total ERCOT reported Load"
 
  1.6. native_Load_2021.xlsx
    i. Columns: "Hour Ending","COAST","EAST","FAR_WEST","NORTH","NORTH_C","SOUTHERN","SOUTH_C","WEST","ERCOT"
    ii. Column Meaning: "Each hour through a day", "Load in Coast weather zone", "Load in East weather zone", "Load in Far West weather zone", "Load in North weather zone", "Load in North Central weather zone", "Load in Southern weather zone", "Load in South Central weather zone", "Load in West weather zone", "Total ERCOT reported Load"
 
  1.7. native_Load_2022.xlsx
    i. Columns: "Hour Ending","COAST","EAST","FAR_WEST","NORTH","NORTH_C","SOUTHERN","SOUTH_C","WEST","ERCOT"
    ii. Column Meaning: "Each hour through a day", "Load in Coast weather zone", "Load in East weather zone", "Load in Far West weather zone", "Load in North weather zone", "Load in North Central weather zone", "Load in Southern weather zone", "Load in South Central weather zone", "Load in West weather zone", "Total ERCOT reported Load"
 
  1.8. native_Load_2023.xlsx
    i. Columns: "Hour Ending","COAST","EAST","FAR_WEST","NORTH","NORTH_C","SOUTHERN","SOUTH_C","WEST","ERCOT"
    ii. Column Meaning: "Each hour through a day", "Load in Coast weather zone", "Load in East weather zone", "Load in Far West weather zone", "Load in North weather zone", "Load in North Central weather zone", "Load in Southern weather zone", "Load in South Central weather zone", "Load in West weather zone", "Total ERCOT recorded Load"
 
2. File: EnergyPrice
  Includes monthly energy price from November 2001 to August 2024.

  SeriesExport-11-20-2024-10-13-55.csv
    i. Columns: "Series Key","ELEC.PRICE.TX-ALL.M","Series Key","ELEC.PRICE.TX-RES.M","Series Key","ELEC.PRICE.TX-COM.M","Series Key","ELEC.PRICE.TX-IND.M"
    ii. Column Meaning:"Including Units:cents per kilowatt-hour, Frequency: Monthly, Start Date, End Date, Source:EIA", "All sectors average monthly electricity price in Texas", "Including Units:cents per kilowatt-hour, Frequency: Monthly, Start Date, End Date, Source:EIA", "Residential average monthly electricity price in Texas", "Including Units:cents per kilowatt-hour, Frequency: Monthly, Start Date, End Date, Source:EIA","Commercial average monthly electricity price in Texas", "Including Units:cents per kilowatt-hour, Frequency: Monthly, Start Date, End Date, Source:EIA", "Industrial average monthly electricity price in Texas"
 
 Processed Data:
 
  1. ElectricityPrice_Monthly.csv
    i. Columns: "Date","Price(cent/KWh)"
    ii. Column Meaning: "Date", "Electricity Price in the month in cent/kWh"
  2. EnergyLoad_Daily.csv
    i. Columns: "Date","ERCOT(MW)"
    ii: Columns Meaning: "Date", "Total ERCOT recorded Load (MW) on the day in Texas"
  3. Monthly_Load.csv
    i. Columns: "month","MW"
    ii. Column Meaning: "Month", "Total ERCOT recorded Load (MW) in the month in Texas"
  4. Temperature_MaxMin_Daily.csv
    i. Columns: "Date","Temperature_Max","Temperature_Min"
    ii. Column meaning: "Date", "Daily Maximum Temperature in °C", "Dailt Minimum Temperature in °C"
    
 
## Scripts and code

1. DataWrangling.Rmd: code for wrangling of Texas daily and monthly load data, Texas all sectors monthly electricity price data, Texas daily temperature data. 

2. DataVisual.Rmd: code for visualizations of temperature change (the number of extremely cold days) through 2016-2023, monthly energy load in MW in Texas through 2016-2023, and monthly average electricity price in Texas through 2016-2023. The code also includes plots of correlation between energy load and electricity price, correlation between minimum temperature and energy load, and correlation between minimum eemperature and electricity price.

3. LinearModelAnalysis.Rmd: code for LM analysis on impacts of frequency of extremely cold days on energy load, impacts of frequency of extremely cold days on electricity price, and impact of energy load on electricity price. The code aims to check if the parameters have impact on others. 

4. TimeSeriesAnalysis.Rmd: code for seasonal Mann Kendall tests on electricity price, energy load, and minimal temperature over 2016-2023. Code for Detrended Mann Kendall test on electricity price over 2016-2023. Code for forecasting energy load based on historical data from 2016 to 2023.


