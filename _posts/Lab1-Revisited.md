---
layout: post
title: Digimon Lab Revisited
subtitle: Improving Problem 3
tags: [Lab]
comments: true
---

**Premise**

In lab 1 for the final question was to create a team of 3 digimon such that their combined memory was less than 15 and their combined attack was greater than or 
equal to 300. For the question there was an obvious and slow way, and a couple better ways. However a lot of the better ways, including the way I ended up using, do 
not work for every possible digimon dataset. So in this exploration I want to find the most efficient way to do this problem.

**Setup**

Before we start, there are a couple things we need to clarify. First, what do I mean by most efficient? I mean the program that takes the least operations. But what 
do I define as an operation? Since I am not willing to determine the actions of the base level computer, I will define a operation as a check, assignment, a run of 
a loop, or other similar processes. While this may not be entirely accurate to the processing time of the program, its a good indicator. If it ever becomes unclear why I counted operations the way I did, I will clarify it.

**Start**

The baseline for this is the first solution I shared in my lab blog post. The every permutation method. This method just checks each possible permutation of the digimon against the conditions. It looks like this:
~~~
def createTeamOptimization():
        for row in data:
            for row2 in data:
                for row3 in data:
                    if row3["Memory"] + row2["Memory"] + row["Memory"] <= 15  and row3["Atk"] + row2["Atk"] + row["Atk"] >= 300:
                        return([row["Digimon"],row2["Digimon"],row3["Digimon"]])
~~~
For this program I found the max number operations to be 3f^3+1 with f being the number of rows in the file. Note I'm counting the if statement as 2 operations 
since it is doing 2 checks. This is not great which is why it is the baseline. If the dataset is large, the number of operations can get very large very quickly.

**Optimizations**

The first optimization we can do is to delete the row after the base for loop loops through it. This turns us using all of the permutations to using all the 
combinations
