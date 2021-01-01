---
layout: post
title: Schema Matching with FlexMatcher
tag: project
excerpt_separator: <!--more-->
---

Hojin Ryoo & Debanshu Das

Date: December 31st, 2020

### Introduction

In this phase of the semester project our objective was to practice using data science techniques to extract and clean data, and then to integrate data using implementations of some of the techniques we learned in class. In part A of phase 2 we cleaned the data, identified missing values, and formally assessed the similarity of the data using instance-based matching. In part B we used FlexMatcher to match columns of different coronavirus datasets together. 

<!--more-->

### Data Description

Our group used a multitude of datasets. We did not use the same data that we used for part 1. For part A we used fast food location datasets, one from data.world which focused on subway restaurant locations, and another from Kaggle which used a variety of fast food restaurant’s locations such as McDonalds, Wendy’s, etc. 

We used the drop_duplicates() function on both datasets once they were converted into dataframes, and after comparing the shape of both the original and the dropped duplicate dataframes, the number of records was the same, so we concluded that there were no 
duplicates.

![Duplicate 1](/imgs/schema_matcher/dup1.JPG) ![Duplicate 2](/imgs/schema_matcher/dup2.JPG)

To determine where the missing values were we used the count function to count the cells in each column that had non-missing values and compared that to the total number of records.

![NA 1](/imgs/schema_matcher/na1.JPG) ![NA 2](/imgs/schema_matcher/na2.JPG) ![Total Records](/imgs/schema_matcher/total_records.JPG)

<!--more-->