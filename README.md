# Cyclistic Bike-Sharing Data Analysis Case Study

### About Cyclistic

In 2016, Cyclistic launched a successful bike-share offering. Since then, the program has grown to a fleet of 5,824 bicycles that are geotracked and locked into a network of 692 stations across Chicago. The bikes can be unlocked from one station and returned to any other station in the system anytime. 

Until now, Cyclistic’s marketing strategy relied on building general awareness and appealing to broad consumer segments. One approach that helped make these things possible was the flexibility of its pricing plans: single-ride passes, full-day passes, and annual memberships. Customers who purchase single-ride or full-day passes are referred to as casual riders. Customers who purchase annual memberships are Cyclistic members.

#### Stakeholders

1. Lily Moreno: The Director of Marketing and manager of this project. Moreno is responsible for the development and oversight of marketing initiatives which promote Cyclistic’s bike-sharing program.
    
2. Cyclistic marketing analytics team: The marketing analytics team is tasked with collecting, cleaning, analyzing and gaining insights from data obtained and presenting findings to help guide Cyclistic’s marketing strategies.
    
3. Cyclistic executive team: A team of executives which will ultimately approve/deny the implementation of the marketing plan.

#### Scenario

In this scenario, I am a Junior Data Analyst working for the Chicago-based bike-sharing company Cyclistic as part of the marketing analyst team. The marketing team was tasked by Director of Marketing Lily Moreno with gaining insights on consumer data to aid in the development of a marketing strategy with the goal of converting casual riders to annual members. As part of the **Ask** phase, the marketing analytics team posed 3 questions which we believe will ultimately guide effective marketing strategies and successfully convert casual riders into annual members:

1. How do annual members and casual riders use Cyclistic bikes differently?
2. Why would casual riders buy Cyclistic annual memberships?
3. How can Cyclistic use digital media to influence casual riders to become members?

#### Business Task

As part of the team marketing analyst team, I was tasked with answering the first question: How do annual members and casual riders use Cyclistic bikes differently?

### Data Preparation

For this project, I was given access to and requested to utilize 12 months of Cyclistic’s historical bike-sharing data in order to analyze the data, identify trends and gain insights to fulfill the business task. The data is provided and made available by Motivate International Inc. under an open license. The data can be accessed and downloaded [here](https://divvy-tripdata.s3.amazonaws.com/index.html). 

The data being accessed **ROCCC**s; it is **Reliable**, **Original**, **Comprehensive**, **Current** and **Cited**. The data is collected and stored internally by Cyclistic (a ficticious company) and is updated monthly up to present day. All PII (Personally Identifiable Information) has been removed by the company to avert any concerns regarding data-privacy. 

The following dataset being assessed was obtained by Cyclistic over the past 12 months from May 2022 to Apr 2023. The data is organized in .csv files which contain 12 distinct tables with a total of 13 columns per table. The amount of data being assessed is large, with the combined dataframe totaling 4,533,921 rows.  

### Data Processing

##### Tools

Due to the dataset I worked with being particularly large, I opted to process the data using Python as Python is a fast and reliable program to use for data cleaning, transformation and analysis. Python is open-sourced and is supported by developers who create libraries such as MatPlotLib, Numpy, Pandas and SeaBorn which I used throughout the analysis to process the data. I also used Tableau to create some of the data visualizations. These tools will give an accurate and concise representation of the most pertinent insights regarding our current business task.

### Data Cleaning

After reading in all of the .csv files and combining them into one dataframe (all_data_v1), I began the data cleaning process. Upon doing a quick check of the data, I found that the started_at and ended_at columns were listed as an object rather than data/time format, so I changed these two columns to the more appropriate date/time format. Next, I checked for any null values within the dataframe and was able to return a large number of them in 6 of the 13 columns:

- start_station_name - 832,009 null values
- start_station_id - 832,141 null values
- end_station_name - 889,661 null values
- end_station_id - 889,802 null values
- end_lat - 5973 null values
- end_lng - 5973 null values

Although these numbers may seem drastic at first glance, null values amounted to roughly 17% of the total data being assessed. As collecting and inputting data on those existing null values wouldn’t be an appropriate solution at this time and would not impact the analysis process, I ultimately made the decision to remove the null values from the data frame. I created a new version of the dataframe (all_data_v2) with the dropped null values and ran another line of code to verify that no more null values existed within the dataframe. No duplicate values existed within the dataframe, so I moved on with transforming the data.

### Data Transformation

Upon completing a check of the data using the .info() function, I found that the “started_at” and “ended _at” columns were listed as an object rather than data/time format. I transformed these two columns to the more appropriate date/time format and added a “ride_length” column to the dataframe using pandas timedelta() function to convert the ride length times from seconds to minutes. I then used the len() function to check if there were any ride lengths less than 0; the check returned 78 values less than 0 and those rows of data were removed. To further clarify the trip data, I added month (trip_month), week (trip_week), and day (trip_day) columns to the dataframe.

### Insights

Through analyzing the above data, I was able to gain a few insights about how Cyclistic members and casual riders used the bike-sharing program. 
- Members are more likely to keep Cyclistic bikes for longer periods 

- Members make longer commutes and are more likelyuse the bikes year round, possibly as a primary source of transportation. 

- Cyclistic casual users are more likely to use the bikes for leisure

- There is an increase in weekend ridership among both

- The most popular bike-sharing station for casual users is the Streeter Dr & Grand Ave station. The station is located in a highly attractive and scenic area for both Chicago residents and tourists alike. 

- A number of the more popular start stations amongst casual users were centered in areas adjacent to the Chicago Harbour along Highway 41.

### Conclusion and Recommendations

The ultimate goal of this project is to gain influence amongst casual users of Cyclistic's bike-sharing program to convert them into annual members. Based on the above data and insights gained from it, targeted advertising in those areas and stations where casual users are more likely to frequent should help influence the decisions of casual users. Also, running advertisments during weekends, especially during warmer months should also influence those casual users who prefer to use bikes for leisurely rides and activites.
