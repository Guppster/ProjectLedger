--- 
layout: post 
title: "Hacking Cancer" 
date: "2017-04-07 15:25:48 -0400" 
---

[HackingCancer](https://github.com/Guppster/HackingCancer) is an attempt to 
create a challenging web applet game in Java with the main purpose of utilizing
the power of crowd sourcing to improve cancer research.

This is a side-scroller, platform game in which the user first creates their
own map from visual representations of a Gene Micro-Array. The user is
challenged to determine the path with the most amount of orbs present which
would allow them to collect these orbs in the second stage of the game. 

This path is not a automatable process due to sheer amount of data and thus is
the bottleneck for scientists in their progression to find a cure for cancer.
Allowing users to solve these simple problems has been statistically proven to
increase analysis speed by 600% (Jonna Reynolds, Cancer Research UK).

Once the map has been created, the user is placed at the starting point on
their own map. The map is populated with many monsters that will kill the user
if they touch them to make the game challenging and competitive. Upon reaching
the finish line the user is shown their score and the score + the extracted
research data is saved online in JSON format for further analysis. 

My partner, Konrad Pfundner, and I programmed this project in under 36 hours at
HackWestern 2015 and were awarded as one of the top finalist at the event. Our
goal for this hackathon was to attempt something challenging and really improve
our programming skills. To achieve this level of difficulty we refrained from using
any external libraries or frameworks to make the game development easier and 
programmed everything using basic java graphics and processing. This decision
turned out to be very rewarding as I ended up learning a lot about drawing and 
manipulating shapes in java.

HackWestern 2015 was also my first time presenting a hackathon project on stage 
by myself. I had been awake for 36 hours and didn't have any time to prepare so it was
quite an interesting experience.  

For further analysis take a look at the [code on Github](https://github.com/Guppster/HackingCancer).
