# Coursera-Capstone 
This article is written to cover the data analyis solution for the capstone given by Google Data analytics professional certificate. The case study will cover the phases of data analysis :

•	Ask
•	Prepare
•	Process
•	Analyze
•	Share
•	Act


The capstone is over Cyclistic that is located in Chicago and it is a bike share company.The bikes are used by casual people and people with membership so the main idea is to convince the casual people to ask for a membership by checking how casual people and membership people bike differently. Casual people are people who use a single ride trip or a full day trip and members use cyclistic member.
Ask Three questions will guide the future marketing program: 
1. How do annual members and casual riders use Cyclistic bikes differently? 
2. Why would casual riders buy Cyclistic annual memberships? 
3. How can Cyclistic use digital media to influence casual riders to become members?

I was assigned to answer the first question: How do annual members and casual riders use Cyclistic bikes differently?
The report has to cover the following deliverables: 
1.	A clear statement of the business task 
The aim of this analysis is to find out how casual people and members bike differently and how can casual people be convinced to convert to members.
2.	A description of all data sources used 
The data can be found on this link https://divvy-tripdata.s3.amazonaws.com/index.html.
The data has been made available by Motivate International Inc. under this license https://ride.divvybikes.com/data-license-agreement.)
3.	Documentation of any cleaning or manipulation of data
4.	A summary of your analysis 
5.	Supporting visualizations and key findings 
6.	Your top three recommendations based on your analysis

Process
First,I tried to use all the tools that i learned during the course and my study.So, i Created a folder for the year, unzipped all the 12 files(january,february, march, april , may , jun, jul,aug,sep,oct,nov,dec) 2022.Excel was used for all the 12 files , ride_length was measured by subtracting ended_at with started_at using the right format as HH:MM:SS . Checked the day_of_week using Weekday function. I figured out it was not the right decision to use it on large data and that costs alot time and excel wasnot able to read the started_at column and ended_at column as date_time.I tried different functions to change them but it was not that effecient.


So R was used as the files were large to be used by other programs. Installed the packages Tidyverse , readr ,dplyy,ggplot2, hydroTSM ,hms,data.table,lubridate and scales. rbind was used to combine the 12 files (january,february, march, april , may , jun, jul,aug,sep,oct,nov,dec) 2022 to one file year.
1.uploaded the 12 files (jan,feb.....etc) using read.csv 
2.rbind all the files to data frame year 
3.Created a new data frame to keep the a copy of my previous data year_2 
4.Added columns start and end (for date_time information) , as Started_at and ended_at were considered as char. 
5.Added columns:
- ride_length by subtracting end with start, to check the duration of the ride. 
- day_of_week to check the day of the week
- month 
- hour 
- day 
- season (spring,summer..etc) 
- time_of_day (morning,night..etc) 

Cleaning up before the Analysis
1.	Removed these columns (start_station_id, end_station_id,start_lat,start_lng,end_lat,end_lng) 
2.	Removed bad data where ride_length<=0 
3.	Removed Remove NA with R 
4.	Removed duplicates using distinct


Analysis 
1.	checked the rnow() to get the value of total rows
2.	checked the summary of the dataframe and str() the type of the columns
3.	checked the calculation of mean ,median, max and min
4.	compared the ride lenght of members and casuals according to day
5.	compared the ride lenght of members and casuals according to hour
6.	compared the ride lenght of members and casuals according to month
7.	compared the ride lenght of members and casuals according to day_of_week(sunday..etc)
8.	compared the ride lenght of members and casuals according to season
9.	compared the ride lenght of members and casuals according to hour
10.	compared the ride lenght of members and casuals according to time_of_day


Visualizing by R 
•	Number of rides by ridertypes 
•	Average of rides by ridertype 
•	Number of rides by ridertypes per month 
•	Average of rides by ridertypes per month 
•	Number of rides by ridertypes per weekday 
•	Average of rides by ridertypes per weekday
•	Number of rides by ridertypes per season 
•	Average of rides by ridertypes per season














