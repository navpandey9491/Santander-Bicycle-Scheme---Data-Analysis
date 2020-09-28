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

All the above hypotheses are falsifiable by using our data. In fact, the following metrics can help us to prove/disprove them
