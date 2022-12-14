---
title: "README File for 'Sea Level and Water Temperature Data Analyses in Coastal North Carolina'"
author: "Nicole Eastman, Ariel Lam, and Jiyoung Park"
date: "December 14, 2022"
output: pdf_document
geometry: margin=2.54cm
---
# EastmanLamPark_ENV872_EDA_FinalProject

## Summary
We are using this repository to upload data from NOAA's Tides & Currents Datasets for sea level measurements and NOAA's National Data Buoy Center for water temperature measurements. We are looking at monthly data for water temperature and sea level at three different coastal sites: Beaufort Marine Lab, Hatteras Island, and Wrightsville Beach. Sea level and water temperature were the chosen parameters to assess because they are indicators of climate change, and we want to analyze the changes occuring on the coast of North Carolina due to climate change. The data begins on the first day of 2011 and ends on November 31, 2022. This project will use a time series analysis to identify seasonal trends and changes in sea level and water temperature over the past 12 years using a Mann Kendall test. We will then identify if there is a statistical relationship between the two parameters using a Kendall correlation test.

## Investigators
Nicole Eastman, Ariel Lam, and Jiyoung Park are Masters students at the Nicholas School of the Environment at Duke University. 
Contact information:
  Nicole: nicole.eastman@duke.edu
  Ariel: ariel.lam@duke.edu
  Jiyoung: jiyoung.park@duke.edu

## Keywords
sea level rise
water temperature
climate change
coastal change
seasonality
statistical significance

## Database Information
Data from NOAA's Tides and Currents Database was accessed on November 20, 2022. The data acquired from the website includes monthly sea level data from Beaufort Marine Lab, Hatteras Island, and Wrightsville Beach from their earliest recorded data April 27, 2010 to November 30, 2022. The water temperature data was collected every 6 minutes by NOAA and we acquired this data from NOAA's National Data Buoy Center on December 1, 2022. The water temperature data dates back to January 1, 2011. We wrangled the data to average the sea level and water temperature measurements from NOAA for each month from 2011 to 2022 in order to create dataframes with identical periods of measurements for the analyses.

## Folder structure, file formats, and naming conventions 
This repository contains a code folder containing the code developed in R studio to complete the analysis, an output folder with final plots and computed statistics from analyses, a Raw_Data folder with the raw datasets downloaded from NOAA, and a Processed_Data folder with the raw data wrangled for monthly average values (excluding N/As). All of the raw and processed data are in csv format, the code files are RMDs, and the outputs will be jpg. We use "_" to dictate a space in a folder name and include the type of data, either sea level or water temperature. We also include the station name or if the data contains measurements from all stations we label the file as combined. In the Project_Instructions folder, we compiled all written guidance and templates for our reference created by the instructors of our Environmental Data Analysis course at Duke University, Dr. John Fay and Dr. Luana Lima.

## Metadata
In the Raw_Data folder, Beaufort_Marine_Lab_2010_2022_SeaLevelRise.csv, the Hatteras_2010_2022_SeaLevelRise.csv, and WrightsvilleBeach_2010_2022_SeaLEvelRise.csv have the same columns. They begin with a column for the date the sea level measurement was collected which is classified as a Date and is in the format of Year-Month-Day. The second column marks the time of the collection as a numeric value with a unit of time in GMT, but they are all 0 because these are daily average measurements. The column noted as "Highest" reports the highest sea level recorded that day as a numeric in feet. MHHW is the mean higher high water measurement in feet, this numeric value represents the mean of the two highest sea level measurements. Similarly, MHW is recorded in feet as a numeric string and averages the mean high water values recorded at high tide. MSL is recorded as a numeric in feet and this value is the mean of recorded sea level measurements for that day. MTL is measured as feet and classified as numeric. This measurement is the mean tide level which is calculated as a datum based on the average of the MHW and MLW. MLW, also a numeric measured in feet, is the mean of all low water heights for that day. MLLW is a numeric in feet that calculates the mean of the two lowest low water heights for each day. The numeric "Lowest" column marks the lowest sea level measurements in feet measured for each day. 

The WaterTempData located in the Raw_Data folder was acquired from NOAA's National Data Buoy Center to represent several different measurements taken at each site, Beaufort, Hatteras, or Wrightsville Beach, every six minutes. Inside the folder there are three folders with the data for each site from 2010 to 2021. Each data frame is labeled by year to show the year the data was collected in 6 minute increments. We only used the first few columns, #YY which represents the year, MM which represents the month, DD which represents the day, hh which represents the hour, and mm which represents the minute the measurement was recorded. Additionally, we extracted the WTMP column which was listed as a character to acquire the water temperature measurement for that given minute of that specific data. 

We wrangled the previously described datasets and created the combine_daily_water_temp.csv. This dataframe starts with a Year integer column to represent the year the measurement was taken, then a Month integer column with the number corresponding to the month the measurement was taken, and an integer column named Day for the day of the month the measurement was acquired. The Date column is classified as a Date and represent the exact date the same was taken in Year-Month-Day format. Then, the dailywtmp column provides the average  of the water temp at the given site for that day. Finally, the Station column provides characters for the names of the specific site where the data was collected, either Beaufort, Hatteras Island, or Wrightsville Beach.

The combined_monthly_wtmp_data has a column named X to provide integers that correspond to the sequential number of the acquired measurements for that date. The Date column is in date format and presents the first date of every month to represent the month of the year that sample was taken and averaged. The monthlywtmp column is classified as numeric and provides the average monthly water temperature for a given site. Lastly, the Station column represents a character for the site where the sample was collected: Beaufort, Hatteras Island, or Wrightsville Beach.

Finally, the combine_sealevel.csv has four columns to represent the data. The Data column is in Year-Month-Day format and represents the month and year the measurements were averaged for at that time. The Date column is classified as a date. The MSL (ft) column has numeric values to represent the mean sea level for the measurements collected at a given site for a given month of a specific year. Similarly, the MTL (ft) column provides numerics for the mean tide level for a specific month. The Station presents characters for the same collection site names.

## Scripts and code
In the code folder, we began the project by using the Wrangling_Data file to process the data to be in monthly format for sea level rise and water temperature data acquired from NOAA beginning in 2011. We then created the Data_Exploration rmd file to begin graphing the data and looking at trends over the years in sea level rise and water temperature fluctuations. We used the Data_Analysis rmd file to import our processed data frames and complete time series analysis, graphical representations, and a correlation test between the two variables. Finally, we used the Eastman_Lam_Park_ENV872_Projcet.rmd file to organize the three different rmd files previously listed into one replicable code.

## Quality assurance/quality control
In order to ensure quality assurance during the creation of this project and the associated analyses, we used consistency in our techniques. For example, we chose one method for the labeled missing values found in different dataframes. We formatted our csv files the same way, using "combine" in the name to indicate there is data from all sites in the file or the site name if the data is for one specific site. We also consistently used "_" to represent a space between words in a csv file name. Additionally, we formatted our dates the same "Year-Month-Day."

Another way to ensure quality control includes the consistent use of Git. We committed our work often with descriptive messages attached to each push to the main branch. 

We created file names that provided sufficient information to any reader who may want to know what the folder contains. Also, descriptive comments prior to each segment of code helps the reader understand the objective of each code chunk. 
