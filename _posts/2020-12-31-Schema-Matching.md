---
layout: post
title: Schema Matching with FlexMatcher
tag: project
excerpt_separator: <!--more-->
---

###Introduction###

In this phase of the semester project our objective was to practice using data science techniques to extract and clean data, and then to integrate data using implementations of some of the techniques we learned in class. In part A of phase 2 we cleaned the data, identified missing values, and formally assessed the similarity of the data using instance-based matching. In part B we used FlexMatcher to match columns of different coronavirus datasets together. 

##Data Description##

Our group used a multitude of datasets. We did not use the same data that we used for part 1. For part A we used fast food location datasets, one from data.world which focused on subway restaurant locations, and another from Kaggle which used a variety of fast food restaurant’s locations such as McDonalds, Wendy’s, etc. 

We used the drop_duplicates() function on both datasets once they were converted into dataframes, and after comparing the shape of both the original and the dropped duplicate dataframes, the number of records was the same, so we concluded that there were no 
duplicates.

![Duplicate 1](dup1.jpg) ![Duplicate 2](dup2.jpg)

<!--more-->