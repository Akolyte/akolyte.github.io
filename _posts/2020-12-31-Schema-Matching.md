---
layout: post
title: Schema Matching with FlexMatcher
tag: project
excerpt_separator: <!--more-->
---

Hojin Ryoo & Debanshu Das

DS 320

Marc Rigas

Date: December 31st, 2020

### Introduction

In this phase of the semester project our objective was to practice using data science techniques to extract and clean data, and then to integrate data using implementations of some of the techniques we learned in class. In part A of phase 2 we cleaned the data, identified missing values, and formally assessed the similarity of the data using instance-based matching. In part B we used FlexMatcher to match columns of different coronavirus datasets together. 

Link to code [here](https://colab.research.google.com/drive/1pVdyLwwS0c9t_tYFYLqR7zmgtD-FK0zn?usp=sharing).

<!--more-->

### Data Description

Our group used a multitude of datasets. We did not use the same data that we used for part 1. For part A we used fast food location datasets, one from data.world which focused on subway restaurant locations, and another from Kaggle which used a variety of fast food restaurant’s locations such as McDonalds, Wendy’s, etc. 

We used the drop_duplicates() function on both datasets once they were converted into dataframes, and after comparing the shape of both the original and the dropped duplicate dataframes, the number of records was the same, so we concluded that there were no 
duplicates.

![Duplicate 1](/imgs/schema_matcher/dup1.JPG) ![Duplicate 2](/imgs/schema_matcher/dup2.JPG)

To determine where the missing values were we used the count function to count the cells in each column that had non-missing values and compared that to the total number of records.

![NA 1](/imgs/schema_matcher/na1.JPG) ![NA 2](/imgs/schema_matcher/na2.JPG) ![Total Records](/imgs/schema_matcher/total_records.JPG)

As you can see from the number of records compared to the count of non-missing values, the dataworld dataframe, the url, phone_number, fax, email, website, facebook, twitter, instagram, pinterest, and youtube values all have missing values. Some of these attributes had all missing values, so we decided to remove them. We did not remove the column website because we thought it would be interesting to have later on for the jaccard similarity matching. We removed 12 attributes in total. 

In the kaggle dataframe on the other hand the only attribute that had missing values was websites. 

We replaced the missing values with an arbitrary value ‘X’, as we thought a random variable would be appropriate as a replacement for missing values. 

The attributes for the datasets are as follows. 

**[Data.world Restaurant Locations](https://data.world/data-hut/subway-restaurant-location-dataset) - 11 attributes, 25,533 records**

**address** - the address of the restaurant

**city** - the city the restaurant is located in

**country** - the country the restaurant is located in

**keys** - the API key used to access the information in the entity

**latitude** - the latitude location of the restaurant

**longitude** - the longitude location of the restaurant

**name** - the name of the restaurant

**postalCode** - the zipcode of the restaurant

**province** - the state the restaurant is located in

**websites** - the website url of the website related to the restaurant


**[Kaggle Fast Food](https://www.kaggle.com/datafiniti/fast-food-restaurants?select=FastFoodRestaurants.csv) - 10 attributes, 10,000 records**

**name:** represent name of the restaurant, 

**url** - used to find the information for the other attributes such as city, state, etc.

**street_address** - is the street address of the restaurant, 

**city** - is the city the restaurant is located, 

**state** -  the state the restaurant is located in, 

**zip_code** - the zip code of the restaurant, 

**country** - the country in which the restaurant is located in, 

**phone_number*** - is the phone number of the restaurant,

**fax*** - is the fax of the restaurant, email is the email of the restaurant, 

**website** - is the website of the restaurant, 

**open_hours** - is the hours the restaurant is open, 

**latitude:** is the latitude number the restaurant is located at, 

**longitude** - is the longitude number the restaurant is located at, 

**facebook*** - is the link for the facebook page of the restaurant, 

**twitter*** - is the link for the twitter page of the restaurant, 

**instagram*** - is the link for the instagram page of the restaurant, 

**pinterest*** - is the link for the pinterest page of the restaurant, 

**youtube*** - is the link for the youtube page of the restaurant.

* = Dropped Attributes

For part B we used the John Hopkins repository discussed in the assignment prompt. From the US daily covid cases reports datasets we chose the July 11th and December 2nd cases. We chose days that would have had spikes from major holidays for fun. We then used the time series data from the same prompt and ran flexmatcher on the daily covid cases datasets to train the schema matcher and then did a prediction for the times series data. Since this an instanced based match we do not need the attributes from the time series data for testing, so we dropped them.

The time series data had 3339 records, and 330 attributes. The July 11th data had 58 records and 18 attributes. The Dec 2nd data had the same number of records and attributes compared to the July 11th dataset. There were also no duplicates after dropping the duplicates using the drop_duplicates function. We show this using the number of records before the drop and after the drop. Looking below you can see that they are the same. 

![Shape 1](/imgs/schema_matcher/shape1.JPG) ![Shape 2](/imgs/schema_matcher/shape2.JPG)

Links for the different data are below. 

[US Daily Covid Cases July 11th](https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_daily_reports_us/07-11-2020.csv)

[US Daily Covid Cases Dec 2nd](https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_daily_reports_us/12-02-2020.csv)

[US Time Series Covid Cases](https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_confirmed_US.csv)

### Part A: Jaccard Similarity Measure

**Methods:**

Comparing the column names some are the same such as name, city, latitude, and longitude, totaling to 4. That leaves 7 attributes that are different for dataworld and 6 for kaggle. Some of the names are completely different from their counterparts such as state in the kaggle dataframe compared to province from the kaggle dataframe. Therefore we decided to use instance-based matching for the jaccard. 
