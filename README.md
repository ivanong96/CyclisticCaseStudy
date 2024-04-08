# Cyclistic Case Study

## Introduction

The Cyclistic Bike Share Case Study is a capstone project for the Google Data Analytics Professional Certificate on Coursera. In this project, I practiced the data analysis process which I learned to analyze the data.

## Scenario
As a junior data analyst working on the marketing analyst team at Cyclistic, a bike-share company in Chicago. The director of marketing believes the company’s future success depends on maximizing the number of annual memberships.  Lily Moreno, director of marketing and the team want casual riders to convert into annual members. The recommendations must be approved by Cyclistic and backed up with data insights and professional data visualizations.

## Background
Cyclistic is bike-sharing company in Chicago started in 2016. They offer a fleet of 5824 bicycles that are geotracked for public use across the city. The bikes can be unlocked from one station and returned to any other station.
Cyclistic offers 3 different pricing plans:
1.	Single-ride passes
2.	Full-day passes
3.	Annual memberships.
Customers who purchase single-ride or full-day passes are referred to as casual riders and those who purchase annual membership are Cyclistic members.

## Questions
Three questions will guide the future marketing program: 
1.	How do annual members and casual riders use Cyclistic bikes differently? 
2.	Why would casual riders buy Cyclistic annual memberships? 
3.	How can Cyclistic use digital media to influence casual riders to become members?

## Business Task:
To analayze Cyclistic’s historical bike trip data to understand the difference between the usage of casual riders and annual members. By using these insights to design a new marketing strategy to convert casual riders into annual members.

## Key Stakeholders:
1.	Lily Moreno: The director of marketing who is responsible for the development of campaigns and   
initiatives to promote the bike-share program.
2.	Cyclistic marketing analytics team: This is a team of data analysts who are responsible for collecting, analyzing and reporting data that helps guide Cyclistic marketing strategy.
3.	Cyclistic executive team: Tis is detail-oriented executive team will decide whether to approve the recommended marketing program.

## Assumptions and Limitations:
Assumptions: We are operating under the assumption that the provided data is accurate, up-to-date, and representative of the larger rider population. We also assume that the riders' behaviors are largely influenced by their status as casual riders or annual members, not by other unrecorded factors.
<br>

Limitations: While the dataset offers rich information about ride details, it lacks direct demographic data of users such as age, gender, or socioeconomic status. Therefore, our analysis and conclusions are drawn based on the ride patterns and cannot account for the influence of these demographic factors.

## 1. Prepare Phase 
The data used is made publicly available by Motivate International Inc. under this license. The dataset that are accessible through here. Due to privacy issues, the riders’ personally identifiable information has been excluded in the dataset. The data that has been chosen to use in this project is based on all 12 months of records in 2023.

## 2. Process Phase 
In this phase, data is cleaned to make sure that information is consistent throughout the 12 different files. We have 12 different tables to be combine from January 2023 to December 2023. Those 12 tables are combined into a single table using SQL. The combined table consists of 5,719,877 rows.
<br>

| **No.**|  **Variable**       |  **Description**                                        |
|--------|------------------   | --------------------------------------------------------|
| 1      | ride_id             | Unique ID (16 characters) assigned to each ride         |
| 2      | rideable_type       | Electric bike,  Classic bike, Docked bike               |
| 3      | started_at          | Date and time at the start of trip                      |
| 4      | ended_at            | Date and time at the end of trip                        |
| 5      | start_station_name  | Station name at the start of the trip                   |
| 6      | start_station_id    | The ID of the starting station                          |
| 7      | end_station_name    | Station name at the end of the trip                     |
| 8      | end_station_id      | The ID of the ending station                            |
| 9      | start_lat           | Latitude of starting station                            |
| 10     | start_lng           | Longitude of starting station                           |
| 11     | end_lat             | Latitude of ending station                              |
| 12     | end_lng             | Longitude of ending station                             |                  
| 13     | member_casual       | Type of membership (casual,member)                      |
</br>

The data type of each variable as show below:
<br>
| **No.**|  **Variable**       |  **Type**     | **Mode**    |
|--------|------------------   | --------------|------------- |
| 1      | ride_id             | STRING        | NULLABLE     |
| 2      | rideable_type       | STRING        | NULLABLE     |
| 3      | started_at          | TIMESTAMP     | NULLABLE     |
| 4      | ended_at            | TIMESTAMP     | NULLABLE     |
| 5      | start_station_name  | STRING        | NULLABLE     |
| 6      | start_station_id    | STRING        | NULLABLE     |
| 7      | end_station_name    | STRING        | NULLABLE     |
| 8      | end_station_id      | STRING        | NULLABLE     |
| 9      | start_lat           | FLOAT         | NULLABLE     |
| 10     | start_lng           | FLOAT         | NULLABLE     |
| 11     | end_lat             | FLOAT         | NULLABLE     |
| 12     | end_lng             | FLOAT         | NULLABLE     |                
| 13     | member_casual       | STRING        | NULLABLE     |
</br>

The data is then cleaned by:
<br>
•	Checking for any duplicated trips
<br>
•	Adding 3 columns which are “month”,  “ride_length_in_mins”,  “day_of_week”
<br>
•	Excluding rides that are less than a minute
<br>
•	The latitude and longitude have lots of null values but is ignored and not used for further analysis.

## 3. Analyse Phase 
The total number of rides in 2023 carried out by Cyclistic members and casual riders  is displayed as below. Cyclistic member recorded a greater bicycle activity than casual riders. The total rides for member are 3,480,623 while for causal riders is 1,975,161. Cylicstic member accounted for 63.8% of total rides while casual riders accounted for the remaning 36.2%.

![Screenshot 2024-03-20 181026](https://github.com/ivanong96/CyclisticCaseStudy/assets/81286426/7b594376-7e2d-495c-a532-aa38c5bb980b)

![Percentage](https://github.com/ivanong96/CyclisticCaseStudy/assets/81286426/f3b8efed-673b-4431-af3d-885208750c96)

The graph reveals that the majority of Cyclistics members primarily utilize the services for commuting to and from work, evidenced by the peak ride times occurring at approximately 8am and 5pm. In contrast, casual riders tend to use the service primarily for leisure with the highest number of rides occurring around 5pm. Additionally, the total rides(weekly) graph provides further evidence, indicating that members tend to have higher ride frequencies during the weekdays whereas casual riders have higher counts during the weekends.

<img src="https://github.com/ivanong96/CyclisticCaseStudy/assets/81286426/244809ca-7a97-4e70-9e8a-1e0bb48f2cf3">


![Total Rides (hourly)](https://github.com/ivanong96/CyclisticCaseStudy/assets/81286426/07a032f3-b194-403e-b87d-34e7fa44a09e)

Both Cyclistic members and casual riders demonstrate a preference for riding during the spring and summer seasons, spanning from May to September. However, ride frequency begins to decline as temperatures drop, leading people to take fewer rides.

![Total Rides (Monthly)](https://github.com/ivanong96/CyclisticCaseStudy/assets/81286426/81ba8dbe-ac8d-40a0-af65-bcf3191a4ce7)

## 4. Share Phase 
The outcomes are communicated with stakeholders. The execution stage of this project was carried out utilizing SQL on Google Cloud BigQuery for analysis and Looker Studio for data visualization. Dashboard is created with visualizations to present relevant information to the stakeholders.

![Bike Share](https://github.com/ivanong96/CyclisticCaseStudy/assets/81286426/b7476293-858e-4608-bb0a-cb550174c997)


## 5. Act Phase 
Here are few recommendations according to the analysis above. We can design a marketing strategy that target to casual riders into Cyclistic members.
<br>

1. Membership Personalisation
<br>• To accommodate the various needs of casual riders, we can do by providing variety of memberships such as annual membership, monthly membership or even weekly membership. By providing these options, it provides casual riders more flexibility to choose their membership plan that best aligns their preferences and usage patterns.
<br>

2. Membership Loyalty Programs
<br>• By implementing a system for Cyclistic members to be able to collect point according to the amount they spend each time and be able to exchange for some perks like discounts on their memberships will encourage casual to sign into members and start collecting points for each ride they take.
<br>

3.	Influencer Partnership
<br>• Partner with local influencers who are able to share their stories, joy and convenience for using the service and provide an exclusive promo code their followers to be able to try it as well as a discounted rate
<br>

4. Video content marketing
<br>• Create and share video that able to tell a story. For example a rider that could not afford a car, to avoid traffic jam or even to become healthier to commute to their destination, showing the flexibility of the service and share through social platforms like TikTok or even facebook.

