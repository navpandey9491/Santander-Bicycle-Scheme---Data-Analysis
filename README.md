# Santander-Bicycle-Scheme-London - Data Analysis
Santander Cycles is a public bicycle hire scheme in London. This scheme was launched by Borris Johnson, the then Mayor of London. 
This scheme was sponsored by Santander bank UK to promote bicycle 

## Problem Statement
Goal is to predict the total number of bike hired at each station considering various given parameters.

## Dataset
We have three dataset in three separate csv files such as bike_journey, bike_station and London_census. One of the biggest challenge about this data set was to combining together to make a single dataset to perform analysis.

## Pre-processing
We need to import ad read the data to understand and manipulate it. We will use R-programming language to read and manipulate the data to get the useful insights.
Several steps needs to be done here Such as inspecting the data for any missing value using missmap library, Checking whether data contains null values or outliers.
The Amelia package is useful to see whether our data contains missing values.

### Combining the three datasets together

First we need to check how many duplicate values are present in the dataset. To the duplicate values in the dataset and see how many unique values are present in bike _journey dataset we have taken the field #### Start_Station_ID. Similary checked the number of unique values in #### bike_station dataset using field station_ID

The code above shows that in the bike journey data, the Station_ID field contains 779 uniquevalues and bike journey data contains 773 unique values. 
The two dataset has 771 unique values which is good overlap.

# Hypothesis
This step is called hypothesis creation, this is a very important step before performing a data analysis operation. Because it will give and idea about what can be the possibilities/reason due to which more bikes are hired at particular station compared to other station.

Hypothesis 1. Bike demand will be higher where ratio of number of employees are higher near that station

Hypothesis 2. Bike demand will be higher in a bike station which is close proximity of the green space such as parks and ground.

Hypothesis 3. Higher the number of bike rented in sation where ratio of number of people not born in UK are more.

Hypothesis 4. Bike rented in a bike station will be higher during weekdays

Hypothesis 5. Bike rented in a bike station will be higher during the peak hour

All the above hypotheses are falsifiable by using our data. In fact, the below metrics can help us to prove/disprove them

# Metrics
To tackle hypothesis 1 we will use NoEmployee data from London_census to calculate ratio of employee using this formula –> RatioEmployee = (NoEmployee / (PopDen * AreaSqKm))

To tackle hypothesis 2 we will use GrenSpace from LondonCensus data where we will consider the greenspace in square kilo meter.

To tackle hypothesis 3 we will use BornUK and NotBornUK from London census data to calculate ratio as RatioBornUK = (BornUK / (BornUK + NotBornUK))

To tackle hypothesis 4 we will use Start_date from bike_station data

To prove hypothesis H5 we will use Start_hour from Bike_journey data.

Removing unnecessary columns from london census dataset and used row wise manipulationand transforming the data as per our hypothesis.

# Data Processing

We need to transform the data as per the above hypothesis and unnecessary columns are eimited from the dataset.

Now the next step is to merge the dataset together, we have used geosphere package. We were given lat and log of stations and we are given centroid of the ward in London with its area in sq KM. We calulated the distance from the station to the centroid using distgeo() function and if the distance of station is less than the radius of the ward we implicitly attached the station id to that ward. The distGeo function calculating the distance between the 2 pairs of coordinates. Since the vectors of the coordinates are of the same length we are using this technique.

We will now standarised the data after combining the all three dataset into a single dataset.

## Splitting the data into train and test

Now for implementing the algorithm we have used train and test method, we can also use k-fold validation method.

# Algorithm application

Applying linear regression on the given dataset for training the algorithm using linear regression

# Finding

After we run our regression task, we will have in output its predictions. From this output, we need to investigate wheather hypothesis are true or false.

Hypothesis 1 : Bike demand will be higher where ratio of number of employees are higher near that station, true hypothesis because people who are employed might hiring the bikes to go to office.

Hypothesis 2 : Bike demand will be higher in a bike station which is close proximity of the green space such as parks and ground, true hypothesis because the more green the area more will people hire bike for cycling.

Hypothesis 3 : Higher the number of bike rented in station where ratio of number of people not born in UK are more bikes, true Hypothesis  because there would be chance of many tourist hiring the bike.

Hypothesis 4 :Bike demand is higher during weekdays as compared to weekend - False

Hypothesis - since number of people using bike for office commute would be less as comapred to people hiring bike on weekday to ride.

Hypothesis 5 : Bike demand is higher during the peak time, true hypothesis because during morning and evening time around 8-10 AM due to office hours bike demand would be more.

# Limitation
Looking at the dataset we can see that data is only availabe for the month of august and september and not the whole year which is not sufficient for better prediction.

The demand of bike may change due to various other factors such as season, weather condition which is not given in the dataset which might result into incorrect prediction.

The distance of bike station from train station or tube station is not given which might also be a factor for consideration during prediction.




