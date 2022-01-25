---
layout: post
title: Speedcubing Averages Analysis
subtitle: Top 1000 Averages
tags: [Lab]
comments: true
---

##Speed Cubing Averages Analysis##

For the third lab I wanted to analyze a dataset related to speedcubing. First what is speedcubing? Speedcubing is a competitive "sport" where poeple try to solve a Rubik's Cube as fast as possible. In these competitions you do 5 sovles. Your average, what determines the rankings of the competition, is calculated by dropping the best and worst solve and averaging the middle solves. Your best average is commonly seen as the most important measure of your skill level. 

The dataset we will be looking at today is of the top 1000 fastest speed cubers and their best averages. This also came with the competition and country of the average. Going into this dataset I want to find relationships between country, year, and times so not having the date of the averages was an obstacle. However thankfully each competition has the year it was hosted. So I wrote some code to convert the competition into a year column. The original dataset was completely clean, but the process of converting the competition names to years introduced some weird results which I promptly removed.

Now that we have the dataset completely clean, lets look at the summary statistics for the dataset as a whole. 


![Summary](https://s3-media3.fl.yelpcdn.com/bphoto/cQ1Yoa75m2yUFFbY2xwuqw/348s.jpg){: .mx-auto.d-block :}

