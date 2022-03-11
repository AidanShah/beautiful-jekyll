---
layout: post
title: Is Power Creep in Competitive Pokemon Real?
subtitle: Lab 4
thumbnail-img: /assets/img/Screen%20Shot%202022-03-10%20at%207.36.12%20PM.png
gh-repo: AidanShah/beautiful-jekyll/
tags: [Lab]
comments: true
---

**Introduction**

In this post we will be discussing whether power creep exists in competitive Pokemon. To do this we will be analyzing usage datasets from the 7 years of the official format VGC. In this format both players bring 6 pokemon to the matchup and after seeing their opponents pokemon choose 4 of the 6 to bring to the actual game. Players also cannot repeat pokemon on their team of 6. Usage is defined, in competitive Pokemon, as the number of times a pokemon is on a team of 6 in a battle divided by the total number of teams in battles. 


**What is Power Creep**

Power creep is the idea that each Pokemon generation that comes out introduces more and more powerful pokemon so pokemon that are older end up being significantly worse. This view is held widely throughout the Pokemon community though its specifics vary. Some say that all the pokemon in the newer generations are stronger, while others say that there are always a couple pokemon that are stronger than the rest in the new generations. Regardless, let's try and see for ourselves if pokemon power creep is real.

**Data**

Let's look at our data. In our dataset we have all pokemon that were used on the Pokemon Showdown battle simulator in February 2022. I chose the most recent month because people have found which pokemon are good so the usage rates are a more accurate representation of how good the pokemon are. The reason I am using usage rates rather than the pokemon's statistics is because abilities, typing, and moves contribute to the power of a pokemon. The dataset includes the pokemon's name, generation, image, usage percentage, and raw number of uses. Let's first look at usage graphed against rank to see the shape of our data.

visualization is not available


From this graph, we notice something interesting. First, the pokemon are not distributed normally rather there are a couple pokemon that are used extensively while the rest are used very sparsely. If usage does happen to be correlated with generation, it would seem like the first theory of specific pokemon being more powerful than the pokemon in older generations would be true. If you haven't already I recommend mousing over each data point to see a picture, the name, and the generation of pokemon. Next let's look at the distribution of the generations.

![gendist](https://github.com/AidanShah/beautiful-jekyll/blob/master/assets/img/pokehist.png?raw=true)

The general number of pokemon is the same for half of the generations, but there is a dip in generations 2,3,4, and 6. This means that are usage numbers hopefully will be more affected by the quality of pokemon rather than the quantity.

**Analysis**

Now let's get to the interesting things. First let's graph the usage percentage against rank again, but this time only use the top 50 pokemon and separate the generations by color. By clicking on the legend on the side, the different generations will be highlighted.

visualization is not available

The results of this are interesting. There does not seem to be a consistent trend, but each generation is different. Generation 1 has a lot of mid ranked pokemon, 3 has 2 highly used and 2 mid ranged, 5 is spread evenly, and 6 is barely even there. Generation 8 is definitely dominating, having many of the top 10 and some mid ranged. This result seems to suggest that power creep doesn't exist for any generation but generation 8. This next graph showing the number of times a pokemon from each generation shows a similar result.

![hist](https://github.com/AidanShah/beautiful-jekyll/blob/master/assets/img/gen8restricted.png?raw=true)

While there is a general upwards trend, the data is too eratic to say that power creep exists for any generation but generation 8. So just to make sure, I checked 6 of the last 9 years (the 3 years I didn't include had rulesets that limited the number of non new generation pokemon so they were excluded).

![gif](https://media.giphy.com/media/YASHIhsC4SM7VHW13b/giphy.gif)

With this new visualization, the effects of power creep seem to exist. This year's data looks like an outlier compared to clear data that shows the existance of power creep. 

**Conclusion**

Power creep is definitely real. In each generation its pokemon were the strongest. However there have always been pokemon that are good from older generations. This is especially seen this year where besides generation 8 having the most usage by far, the overall usage per generation seems to be random. 

**Reflection**

This project was an incredibly fun experience. Over the course of the lab I spent a lot of time working on getting the data I wanted and presenting it in the way I wanted. I ended up cleaning 6 datasets which did require a significant amount of manual revision to remove errors. However because I planned very ambitiously, I was not able to spend the time I wanted writing this post or making the visualizations that I wanted to. I think I had a bigger plan than I could feasibly accomplish in 1 week. However I enjoyed it very much, and understand what I can do for the final project. There are many places in this project that I want to expand on, and while I don't plan to continue this for my final project, I want to go to those places with the time that I have. Overall I am 8/10 satsified with my work. I happy with what I was able to do, but I wish I could have done a lot more.

Image sources: https://www.youtube.com/watch?v=QVnVFjf5jyE&t=639s&ab_channel=foofootoo
