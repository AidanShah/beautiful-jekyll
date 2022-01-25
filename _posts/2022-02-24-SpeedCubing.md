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


![Summary](https://github.com/AidanShah/beautiful-jekyll/blob/master/assets/img/describetotal.png)

We can see some cool statistics, but this doesn't actually tell us anything too interesting besides the fact that year is skewed towards later years. The mean is also around 8 seconds which is very fast. Let's look at violin plots by country to make some more sense of this data.

![Violin](https://github.com/AidanShah/beautiful-jekyll/blob/master/assets/img/violinbad.png)
Aaaaaaaah! This graph is less than useful. It doesn't tell us anything of note and takes up a massive amount of space. This image is just a screenshot and in the real graph, the key goes on and on. So instead lets limit the countries to the 6 with the most number of people on this list. This comes out to the United States, Canada, The Philippines, Australia, China, and Poland not in any particular order. Now let's take a look at those summary statistics and violin plots again.

![Summary](https://github.com/AidanShah/beautiful-jekyll/blob/master/assets/img/describeall.png)
![Violins](https://github.com/AidanShah/beautiful-jekyll/blob/master/assets/img/violinplottopcountries.png)

These summary statistics look very similar to the original dataset's with the mean being slightly lower. We can also see through the violin plots that most of the averages are clustered in the 8-9 second range, but each country has a couple 5s or low 6s. Interestingly these 6 countries make up about half of the averages of the top 1000. Next let's look at the number of cubers, in the top 1000, that each country has.

![Countplot](https://github.com/AidanShah/beautiful-jekyll/blob/master/assets/img/countrycount.png)

The US is clearly in the head with China trailing in a distinctive second. The rest of the countries in the top 6 have about the same number of averages with Poland slightly ahead. Next I will show the summary statistics for these countries. Feel free to not read them deeply as I will cover the important points after, but they will be there if you want to look at them.

![Describe](https://github.com/AidanShah/beautiful-jekyll/blob/master/assets/img/americadescribe.png)
![Describe](https://github.com/AidanShah/beautiful-jekyll/blob/master/assets/img/chinadescribe.png)
![Describe](https://github.com/AidanShah/beautiful-jekyll/blob/master/assets/img/polanddescribe.png)
![Describe](https://github.com/AidanShah/beautiful-jekyll/blob/master/assets/img/philippinesdescribe.png)
![Describe](https://github.com/AidanShah/beautiful-jekyll/blob/master/assets/img/canadadescribe.png)
![Describe](https://github.com/AidanShah/beautiful-jekyll/blob/master/assets/img/australiadescribe.png)

The mean of the times is fairly consistent with the US leading at 8.09 and The Phillipines at the back with 8.33. These aren't significantly different, but do align with the general trend of the US being the best. The most important thing to me however is the mean of the years for each country. While this isn't strictly meaningful since year isn't continuous, it can give us a general idea of when these countries competitors did their best. For most of the countries, this number is around 2019. However The Philippines is near 2018.5 and China is close to 2020. This indicates that The Philippines is becoming less of a force in speedcubing while their are many Chinese competitors that are breaking into the top 1000 more recently. At this point in the analysis it seems like the US is the clear best country for speedcubing while China is quickly getting better, Let's look at one final graph by year to confirm this trend. 

![Countplot](https://github.com/AidanShah/beautiful-jekyll/blob/master/assets/img/yearcount.png)

This plot exposes something very important. We can see that cubers have been becoming progressively faster up until 2020 where suddenly there are less averages in the top 1000. The factor that we have not been considering so far is the effect of COVID. For much of 2020 and 2021 all competitions were canceled due to COVID. However, when they came back they did not come back equally everywhere. The US has had a reduced number due to high levels of COVID while China has had many competitions. This may be the reason behind the China vs The Philippines year discrepancy. China has had many competitions while the Philippines has not had any. 

In conclusion, the US has the fastest cubers with China in second. It is possible that China's competitors are quickly becoming a more influential portion of the cubing community, but this might be caused by having many competitions while other areas do not. Finally average times are getting faster over the year with the fastest average in this dataset coming in 2021.



