---
title: "Metadata for 'Sea Level and Water Temperature Data Analyses in Coastal North Carolina'"
author: "Nicole Eastman, Ariel Lam, and Jiyoung Park"
date: "December 14, 2022"
output: pdf_document
geometry: margin=2.54cm
---
Data from NOAA's Tides and Currents Database was accessed on November 20, 2022. The data acquired from the website includes monthly sea level data from Beaufort Marine Lab, Hatteras Island, and Wrightsville Beach from their earliest recorded data April 27, 2010 to November 30, 2022. The water temperature data was collected every 6 minutes by NOAA and we acquired this data from NOAA's National Data Buoy Center on December 1, 2022. The water temperature data dates back to January 1, 2011. We wrangled the data to average the sea level and water temperature measurements from NOAA for each month from 2011 to 2022 in order to create dataframes with identical periods of measurements for the analyses.

In the Raw_Data folder, Beaufort_Marine_Lab_2010_2022_SeaLevelRise.csv, the Hatteras_2010_2022_SeaLevelRise.csv, and WrightsvilleBeach_2010_2022_SeaLEvelRise.csv have the same columns. They begin with a column for the date the sea level measurement was collected which is classified as a Date and is in the format of Year-Month-Day. The second column marks the time of the collection as a numeric value with a unit of time in GMT, but they are all 0 because these are daily average measurements. The column noted as "Highest" reports the highest sea level recorded that day as a numeric in feet. MHHW is the mean higher high water measurement in feet, this numeric value represents the mean of the two highest sea level measurements. Similarly, MHW is recorded in feet as a numeric string and averages the mean high water values recorded at high tide. MSL is recorded as a numeric in feet and this value is the mean of recorded sea level measurements for that day. MTL is measured as feet and classified as numeric. This measurement is the mean tide level which is calculated as a datum based on the average of the MHW and MLW. MLW, also a numeric measured in feet, is the mean of all low water heights for that day. MLLW is a numeric in feet that calculates the mean of the two lowest low water heights for each day. The numeric "Lowest" column marks the lowest sea level measurements in feet measured for each day. 

The WaterTempData located in the Raw_Data folder was acquired from NOAA's National Data Buoy Center to represent several different measurements taken at each site, Beaufort, Hatteras, or Wrightsville Beach, every six minutes. Inside the folder there are three folders with the data for each site from 2010 to 2021. Each data frame is labeled by year to show the year the data was collected in 6 minute increments. We only used the first few columns, #YY which represents the year, MM which represents the month, DD which represents the day, hh which represents the hour, and mm which represents the minute the measurement was recorded. Additionally, we extracted the WTMP(in degree Celcius) column which was listed as a character to acquire the water temperature measurement for that given minute of that specific data. 

We wrangled the previously described datasets and created the combine_daily_water_temp.csv. This dataframe starts with a Year integer column to represent the year the measurement was taken, then a Month integer column with the number corresponding to the month the measurement was taken, and an integer column named Day for the day of the month the measurement was acquired. The Date column is classified as a Date and represent the exact date the same was taken in Year-Month-Day format. Then, the dailywtmp column provides the average  of the water temp at the given site for that day. Finally, the Station column provides characters for the names of the specific site where the data was collected, either Beaufort, Hatteras Island, or Wrightsville Beach.

The combined_monthly_wtmp_data has a column named X to provide integers that correspond to the sequential number of the acquired measurements for that date. The Date column is in date format and presents the first date of every month to represent the month of the year that sample was taken and averaged. The monthlywtmp column is classified as numeric and provides the average monthly water temperature for a given site. Lastly, the Station column represents a character for the site where the sample was collected: Beaufort, Hatteras Island, or Wrightsville Beach.

Finally, the combine_sealevel.csv has four columns to represent the data. The Data column is in Year-Month-Day format and represents the month and year the measurements were averaged for at that time. The Date column is classified as a date. The MSL (ft) column has numeric values to represent the mean sea level for the measurements collected at a given site for a given month of a specific year. Similarly, the MTL (ft) column provides numerics for the mean tide level for a specific month. The Station presents characters for the same collection site names.