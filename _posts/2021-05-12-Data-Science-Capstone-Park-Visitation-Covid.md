---
layout: default
title: Data Science Capstone - Park Visitation Covid Dashboard
description: By Thomas Zhao, Charles Alba, Hojin Ryoo, Evan Menendez, Jinhan Li, Xutao Li, Xueshi Bai, Benjamin Crooks, Jin Hee Lee
tag: project
excerpt_separator: <!--more-->
---

![dashboard](/imgs/capstone_covid_dashboard/dashboard.JPG)

### Date: May 11th, 2021

### Class: DS 440 (Capstone)

### Instructor: Prasenjit Mitra (Penn State University, College of Information Sciences and Technology)

## Project Summary

### Overview

Parks are dedicated public spaces that provide valuable benefits to public health and well-being. Park managers and tourism researchers have much to gain by understanding the patterns behind visitations to parks. Better decisions about which parks to allocate resources to can be made, so being able to track park visitation has major policy implications. Visitation data is available from companies like Safegraph; the challenge then is to make the raw visitation data accessible, visual, and otherwise useful for non-technical users.

### Objectives

Our client’s requirements and thus our team objectives were two-fold, though more emphasis was placed on the first point:

1. Create a dashboard that allows the user to easily select a park and see its visitation data with visuals and charts.

2. Analyze and draw insights from visitation data.

### Approach

– Met weekly with our client Dr. Pan to get his feedback on our project and adjust direction if needed

– Conducted exploratory data analysis with initial sample data to familiarize ourselves

– Built a prototype dashboard to test visualizing park data using Python

– Worked out tentative user + design specifications for an actual website with our client

– Downloaded full visitation dataset from Safegraph

– Began development of the dashboard frontend using ReactJS

– Implemented the interactive map with multiple layers using Mapbox

– Implemented interactive charts using the amCharts Javascript library

– Tested PostgresQL as a backend, ultimately switched to MongoDB due to convenience

– Wrote an API to retrieve visitation data from MongoDB using ExpressJS

– Demoed our product to social scientists from the National Park Service and got their feedback

– Created map functionality to visualize visitor-origins for a park

– Deployed the dashboard application via Heroku

– Developed an ANCOVA model to analyze the impact COVID19 has had on vistations to National Parks, alongside the determinants of racial demographic, distance, urban classification and median income of the visitors census origin.

### Outcomes

1. Tourism researchers, park managers, and others interested in tracking park visitations now have a fully functional dashboard to do so (live now at park-visitation.herokuapp.com !)
2. COVID19 has significantly impacted visitations to national parks, with racial demographics and distance from visitor census origin showing significance towards park visitations amidst COVID19.

[Application Link](https://park-visitation.herokuapp.com/){:target="_blank"}

[PSU Capstone Project Website](https://sites.psu.edu/lfshowcasesp21/2021/04/29/park-visitation-dashboard/){:target="_blank"}

---

<!--more-->