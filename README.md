# ENGR315-Final-Project-
Project Group 19: Alex Otti, Andrew Fricke, Josh Hostetter

1. Motivation and Dataset Overview

Area of interest and motivation: All three of us have an interest in civil engineering, with two of us working in traffic and transportation. 

Dataset name and public download URL: Motor Vehicle Collisions – Crashes (NYC Open Data) https://catalog.data.gov/dataset/motor-vehicle-collisions-crashes

Dataset origin and collection: (Who collected it, how and why it was collected, date range, number of observations, and file type/size.)
This was collected by the City of New York and was a combination of all police reports filed from the city that resulted in an injury, a death, or damage over $1,000. This data set was published in 2021 and was updated on July 31, 2026. It can be downloaded as a CSV, JSON, or XML. The data set contains over 1,00,000 data points, going back to 2017. 

Relevant data: Data includes the date the crashes occurred, the time the crash occurred, the zip, latitude, longitude, what street it was on and the cross street, number of people in the accident, number of injuries, number of fatalities, the contributing factor, the collision ID,  and the vehicle types. The data set is comprehensive and allows us to answer a wide range of questions 

Selected Question 1: What 15-minute interval has the most crashes? (which produced the highest number of fatal accidents) 
Analysis method: Analyze each unique 15-minute period to determine which has the highest number of crashes.
Expected finding/inference: A data set that explains the specific period of time with the maximum number of crashes and the location it occurred in We expect the highest number of crashes to occur somewhere inside of rush hour. 

Figure 1 placeholder: Scatter plot of 15-minute intervals, with number of crashes on the x-axis, and fatalities on the y-axis, to display the most dangerous 15-minute period. 

Selected Question 2: What intersection produces the most crashes relative to average daily traffic 
Analysis method: indexing each unique intersection combination where crashes occur, and seeing which has the highest number of crashes. 
Expected finding/inference: We would expect the highest number of crashes to occur at an intersection where both roads have a high number of average daily traffic

Figure 2 placeholder: Heat map of New York, color coded to show each intersection, would provide a visual representation of each crash site

Selected Question 3: Top 5 most traveled boroughs that had the most fatal accidents involving cyclists? (deaths or injuries)
Analysis method:  Analyze each borough to determine the one with the most fatalities
Expected finding/inference: A graph comparing the name of the borough with the number of fatal car crashes. 

Figure 3 placeholder: Two data plots expressing max and min number of fatal accidents versus borough location. The data set includes all the boroughs in the city and a column that records numbers of persons injured and killed. 

Sub task 4
Question 1: “What 15-minute interval has the most crashes? Which has the highest percentage of fatal crashes?  (which produced the highest number of fatal accidents).”
What metric might be calculated from that data that could help your analysis?
Total amount of crashes per 15-minute interval, and number of crashes in that interval where fatal crashes > 0. Intervals may be collected by creating 1440 unique intervals and sorting each crash into applicable bins; each crash should fit into 15 different bins, which will allow us to find the unique 15 minute interval with the most crashes
Potential fatal crash percentage, to represent especially dangerous intervals. 
If any additional Python packages would be useful in analysis
Pandas is useful for data analysis
Numpy potentially for processing data 
What type of plot or visualization would be helpful? 
A line plot with the start of the 15-minute interval on the x-axis and the number of crashes on the y, we could have a second line below it representing fatal crashes as well. 
Question 2: “What intersection produces the most crashes relative to average daily traffic”
What metric might be calculated from that data that could help your analysis?
Total number of crashes at each intersection
Average daily traffic, accounting for the number of vehicles passing or approaching the intersection per day.
Number of crashes relative to traffic exposure
If any additional Python packages would be useful in analysis
Scipy.stats would be useful for analyzing data
Pandas 
What type of plot or visualization would be helpful? 
Geographic heat map to display crash sites across the city. 
Ranked bar chart to compare the top 10 intersections by traffic rates
Question 3: “Top 5 most traveled boroughs that had the most fatal accidents involving cyclists? (deaths or injuries)”
What metric might be calculated from that data that could help your analysis
Amount of daily traffic between streets/boroughs
Number of cyclist-involved accidents, including fatalities or injuries
Percent of cyclists involved in accidents 
If any additional Python packages would be useful in analysis
Pandas 
Scipy
Numpy
What type of plot or visualization would be helpful? 
Line graph showing cyclist deaths and injuries over a period of time in different locations 

RESULTS:
Question 1:
Using a 15-minute rolling window method. We loaded the data and used NumPy to calculate crash frequencies and perform data analysis, and used matplotlib to graph the results. We converted the crash times in minutes after midnight to perform the analysis, and for each minute we calculated a unique window, resulting in 1,440 different 15 minute aerages. as well as calculating a percentage of the crashes that were fatal. 
The results from question 1 are as follows:
MOST CRASHES
Time: 16:46 to 17:01
Total crashes: 53134
Fatal crashes: 39
Fatal crash percentage: 0.0734%

MOST FATAL CRASHES
Time: 18:37 to 18:52
Total crashes: 30661
Fatal crashes: 62
Fatal crash percentage: 0.2022%

HIGHEST FATAL CRASH PERCENTAGE
Time: 04:05 to 04:20
Total crashes: 6334
Fatal crashes: 53
Fatal crash percentage: 0.8368%

Question 2:
Using the NYC Motor Vehicle Collisions dataset, we loaded the data and used Pandas to organize and analyze the number of crashes occurring at each intersection. We identified intersections using the borough, street name, and cross street name. We then grouped matching intersections and calculated the total number of crashes at each location. The analysis identified 36,695 intersections with usable crash records. We used Matplotlib to graph the top 10 intersections with the highest number of crashes and will function once our traffic volume data is found.
The results from Question 2 are as follows:
MOST CRASHES
Intersection: Major Deegan Expressway and West Fordham Road
Borough: Bronx
Total crashes: 547

SECOND MOST CRASHES
Intersection: Flatbush Avenue Extension and Tillary Street
Borough: Brooklyn
Total crashes: 468
THIRD MOST CRASHES
Intersection: Bruckner Boulevard and Hunts Point Avenue
Borough: Bronx
Total crashes: 432

CONCLUSIONS: 
Question 1:
The results show that time of day was the contributing factor towards the number of crashes; the greatest amount of crashes occurred during a high-traffic time, during the afternoon rush hour. We can also see that the most fatal crashes occurred in the evening, which makes sense due to high amounts of traffic plus potentially people running late. The greatest percentage, however, occurred in the early morning around 4 am, potentially being related to drunk driving. 

Question 2:
Based on our analysis, the intersection of Major Deegan Expressway and West Fordham Road in the Bronx experienced the highest number of recorded crashes, with 547. The Bronx also contained three of the top 10 intersections with the most crashes, while Brooklyn contained three, Manhattan contained two, and Queens contained one. This suggests that several intersections in the Bronx and Brooklyn experience particularly high crash frequencies. We originally expected intersections with higher average daily traffic to experience more crashes. However, because the dataset did not include average daily traffic (ADT), we could not determine which intersection had the highest crash rate relative to traffic volume. Additional traffic data would be needed to fully answer our original question and determine whether the intersections with the most crashes are also the most dangerous relative to the number of vehicles traveling through them.

ACTIONS THAT NEED TO BE COMPLETED: 

Question 2:
We need to locate and download an Average Daily Traffic (ADT) dataset for NYC intersections. Once this data is obtained, we will match the traffic volumes with the intersections identified in our crash dataset and calculate crash rates relative to the number of vehicles traveling through each intersection. We will then use Matplotlib to create a graph comparing the top 10 intersections based on their traffic-normalized crash rates. Finally, we will compare these results to our original hypothesis that intersections with higher traffic volumes experience more crashes and update our conclusions based on the findings.

REFERENCES: 






