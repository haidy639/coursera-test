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

<h3>Process</h3>
First,I tried to use all the tools that i learned during the course and my study.So, i Created a folder for the year, unzipped all the 12 files(january,february, march, april , may , jun, jul,aug,sep,oct,nov,dec) 2022.Excel was used for all the 12 files , ride_length was measured by subtracting ended_at with started_at using the right format as HH:MM:SS . Checked the day_of_week using Weekday function. I figured out it was not the right decision to use it on large data and that costs alot time and excel wasnot able to read the started_at column and ended_at column as date_time.I tried different functions to change them but it was not that effecient.
<br>
<br>
So R was used as the files were large to be used by other programs. Installed the packages Tidyverse , readr ,dplyy,ggplot2, hydroTSM ,hms,data.table,lubridate and scales. rbind was used to combine the 12 files (january,february, march, april , may , jun, jul,aug,sep,oct,nov,dec) 2022 to one file year.<br>
1.uploaded the 12 files (jan,feb.....etc) using read.csv <br>
2.rbind all the files to data frame year <br>
3.Created a new data frame to keep the a copy of my previous data year_2 <br>
4.Added columns start and end (for date_time information) , as Started_at and ended_at were considered as char. <br>
5.Added columns:<br>
- ride_length by subtracting end with start, to check the duration of the ride. <br>
- day_of_week to check the day of the week<br>
- month <br>
- hour <br>
- day <br>
- season (spring,summer..etc) <br>
- time_of_day (morning,night..etc) <br>

<h2>Prepare</h2>
1.	Removed these columns (start_station_id, end_station_id,start_lat,start_lng,end_lat,end_lng)<br> 
2.	Removed bad data where ride_length<=0 <br>
3.	Removed Remove NA with R <br>
4.	Removed duplicates using distinct<br>


<h2>Analysis </h2>
1.	checked the rnow() to get the value of total rows<br>
2.	checked the summary of the dataframe and str() the type of the columns<br>
3.	checked the calculation of mean ,median, max and min<br>
4.	compared the ride lenght of members and casuals according to day<br>
5.	compared the ride lenght of members and casuals according to hour<br>
6.	compared the ride lenght of members and casuals according to month<br>
7.	compared the ride lenght of members and casuals according to day_of_week(sunday..etc)<br>
8.	compared the ride lenght of members and casuals according to season<br>
9.	compared the ride lenght of members and casuals according to hour<br>
10.	compared the ride lenght of members and casuals according to time_of_day<br>


<h2>Visualizing by R </h2>
•	Number of rides by ridertypes ❮img src="coursera-test/membervscasual.png"❯


<br>
•	Average of rides by ridertype <br> ![3](https://user-images.githubusercontent.com/71370133/220774394-e4b59570-8b6b-4d9a-a208-9595012cf19b.png)
•	Number of rides by ridertypes per month <br>![4](https://user-images.githubusercontent.com/71370133/220773385-385a2708-db2c-4bd5-9473-c604b9e8a074.png)

•	Average of rides by ridertypes per month <br>![5](https://user-images.githubusercontent.com/71370133/220773406-5ae9173f-8abb-4e83-afaf-b692f0e43df0.png)

•	Number of rides by ridertypes per weekday<br> 
•	Average of rides by ridertypes per weekday<br>
•	Number of rides by ridertypes per season <br>
•	Average of rides by ridertypes per season<br>
<br>
<h2>Visulaizing by Tableau</h2>
<br>
<h3>Members vs Casual</h3>
<p>


Casual people tend to drive about 61% more than members.
<br>
<h3>Rideable types</h3>
<br>
![rideable_type](https://github.com/haidy639/coursera-test/blob/3766c804d10e23fce47c7b0c41d5c501146bfe39/rideable_type.png)
<br>
![rideable2](https://user-images.githubusercontent.com/71370133/220762972-e910e810-beaa-43eb-b38a-768d6887eab6.png)
<br>
people drive longer using classic bikes ; about 43% of rideable bike types.
<br>
<h3>Season</h3>
<br>
![season](https://user-images.githubusercontent.com/71370133/220763228-60a201a1-4621-4fa6-9169-af7864ffe27d.png)
<br>
Members and casuals drive more during the summer time . Especially casual people tend to drive a lot during the summer season.
<br>
<h3>Day of the weeek</h3>
![per_day_of_week](https://user-images.githubusercontent.com/71370133/220763554-15b3f443-8ee1-409b-a872-732e4995eae6.png)<right>
Ride length is higher during the weekends especially on Saturday during the summer season . Followed by Sunday during the summer season that has also a higher ride length result as well
<br>
![per_day_of_week2](https://user-images.githubusercontent.com/71370133/220763714-5db518a7-750e-43fc-b4aa-c31ee1a1cb22.png)
Casual people drive more in weekends than members
<h3>Hour</h3>
<br>
![per_hour](https://user-images.githubusercontent.com/71370133/220768977-06a5eb43-76f1-4624-aa58-6abe48ec510b.png)
<br>
Members drive more from 6 am to 8 am for work and casual people tend to drive more from 10 am till the night than members.
<br>
<h3>Day</h3>
<br>
![per_day](https://user-images.githubusercontent.com/71370133/220764271-c0b1c2d8-38ab-4a47-b1ba-7696dac2c2a3.png)
<br>
Casual people drive longer than members
<h3>Month</h3>
<br>
![per_month](https://user-images.githubusercontent.com/71370133/220764407-3855b081-80d4-4abf-886b-6b583e474e82.png)
<br>
Casual people drive longer from March to October, while members drive longer from November to February. 
</p>












