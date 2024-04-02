---
layout: post
title:  "Social Data Analysis of San Fransisco Data"
date:   2024-04-02 10:10:41 +0200
categories: jekyll update
---
# Our Story of the San Francisco Data 

## Intro
We decided to see how the crimes of Drug Possession and Drunkenness go over time, and how they interact with the other focus crimes.  For the combination we choose only where the description of the DRUG/NARCOTIC was possession. This was done because it is for personal use, since if an amount is exceeded or further suspicion is there, then it becomes another crime level which is selling or distribution charges.
This is why we will explore how they change over the years, see how and when they are spatially and temporarily noted in the system and then see how they correlate and interact with other focus crimes.

The focus is to see how it changes and affects other crime types also.


## How the Crimes Change Over time, Highlight 1.
Our first figure is An Area stack plot of the Crimes.
It is done with Boheh so it is possible to see how each of Drunkenness and Narcotics contribute both together and individually.

Stack Area Plot works by having the components on top of each other and lastly the final aggregated, in this case a sum over each day of the Counts of the crimes and the final one one top.

They are similar to line figures, but the values of counts except the metric values are illustrated by two-dimensional bands rather than lines. The advantage is that we can see Multiple time-series together simply by stacking the bands.

Here we see that in time the crimes caught have become less and less and that the greatest contributor to the combination is the drug possession rather that drunkness.

We see that the crime rates for Drunk and Drug have been reducing. Althought the city os notorious for being a hub of drung and homelessness crisis. 

This bu our research has to do with its lenient policy on drug arrests. 

It seems the citizens are of many different views. Some agree with the policy of acceptance while other disagree with the relatively relaxed nature of laws.

For example, San Francisco’s drug tolerance policies are based on the idea of “harm reduction,” which is the view that those using illegal drugs should be protected, not shamed nor prosecuted for their drug use, and that their lifestyle should be accepted as a normal part of life for those choosing to use. San Francisco prosecutes very little, provides free drug paraphernalia, including hypodermic needles, rubber tourniquets to pop veins, metal cookers for heroin, and sheets of foil and straws for fentanyl and crack pipes.
This would potentially reduce disease chances and spread. 
[Journalist link](https://www.hoover.org/research/economics-how-san-franciscos-drug-policies-are-devastating-city)
- Lee E. Ohanian is a senior fellow (adjunct) at the Hoover Institution and a professor of economics and director of the Ettinger Family Program in Macroeconomic Research at the University of California, Los Angeles (UCLA).


<embed 
       type="text/html" 
       src="/images/my_stacked_counts_plot_until_2017.html"
       width="1100"
       height="600"
       >
</embed>

## How Crimes are located in Space and time

<b> The second figure is a Heat map with Time.</b>

Here, we can see where they are located at different times of the day.
We did an aggregation that is based on a double loop, the first is the day of week, the inside is the hour. Then it gets appended into a list so it can be plotted.

This is an advantage over the classical map, because we can also see, the time instead of just a static sum. This helps us explore and explain the data with more detail.

We decided to do it this way, because further aggregations would lose the geographical and time data that is with each element of the crime dataframe.

What is mostly illustrated is that the Crimes mostly happen in the central Tenderloin Area, near the Bay, Jackson Square and on the main road close to the bridge.

### Regarding the Paper of The scaling of crime concentration in cities [link](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0183110)

- By Marcos Oliveira ,Carmelo Bastos-Filho,Ronaldo Menezes

It seems that population size does not have an influence on the levels of concentration—despite the relationship between crime and total population. 

<b> Also Crime concentration manifests in the probability distribution of crime across a city which can be described by a power law. </b>

P of x is arrpoximatexy proportional to x to the power of -a,
- where the exponent α relates to the type of crime.


#### In Our case the crime we selected was a new engineered feature that has Drunkenness and Drug possession for personal use.

Keeping in mind that in the article they found that the distribution of crime in a city can be approximated by a power-law distribution with exponent α that depends on the type of crime. Though criminal activities present regularities of concentration, they found that criminal ranks have the tendency to change continuously over time—features that support the perspective of crime as a complex system and demand analyses and evolving urban policies covering the city as a whole.

Andto quote them directly  
- "**Human dynamics also play a major role in criminal activities, which are likely to drive patterns in crime activity. In fact, empirical evidence has shown that crime presents a remarkable regularity of concentration in several dimensions that relate to context (e.g., target, location, offender) and to features (e.g., spatial, temporal, type of crime). In particular, the spatial concentration of crime exists in such way that, regardless of granularity level, some areas have disproportionately more crime than others—popularly called hotspots** "


#### Local Journals and Newspapers 
As cited by Journalist Source : [Newspaper link](https://www.sfchronicle.com/projects/2023/san-francisco-drug-trade-policy/)

It seems that the concetration that we see at Tenderloin ( the central area hub near the Bridge and Bay ). Has been in a way organised by local goverment and police forces.

<b> Citing San Francisco Chronicle : </b>  
Mayor Breed and Chief Scott will also have to reckon with the city’s unofficial, decades-long practice of allowing the Tenderloin to serve as the city’s containment zone for drug markets, homelessness and other societal ills. The city has concentrated housing for the formerly homeless in the neighborhood, as well as social programs. Meanwhile, police have traditionally taken a moderate approach to law enforcement there, according to one former captain, tolerating a certain level of crime to keep it from spreading elsewhere.

Tenderloin residents — and drug users confronted with constant temptation — have borne the burden of that strategy.
- By Crime Reporter
Megan Cassidy, a crime reporter with The Chronicle, also covering cops, criminal justice issues and mayhem. Previously, Cassidy worked for the Arizona Republic covering Phoenix police, Sheriff Joe Arpaio and desert-area crime and mayhem.

<embed 
       type="text/html" 
       src="/images/heatmap_with_time.html"
       width="1100"
       height="600"
       >
</embed>

## Relationships between Crimes and Log transformation

Here we illustrate how the crimes are in relation to each other values. 

We display the correlation for the focus crimes for the original data and also the Log Transformed Data.
We do this to showcase the difference, between the magnitudes of data. Because it penalizes high and low values and some crimes as more rare than others, although they could be correlated and the high/ low value could interfere with the correlation results.

So, they are plotted side by side. This changes results and in a sense 'normalizes' data, without caring so much about absolute values of counts. 

This also is in alignment with the Paper we read in Class [link here ](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0183110)


<b> Regarding the Power Law </b>  
We based the logic of using Log - Log transformation because of the the general framework used to perform a comprehensive analysis of the allometric relationship between crime distribution and city population. 

Since the data used was from United States and United Kingdom it is a good assumption to use the Log Transformation in order to Make the Data Appear In Similar Magnitude Sizes.

Because population size does not have an influence on the levels of concentration—despite the relationship between crime and total population. 

Highlighting that :
<b> P of x is arrpoximatexy proportional to x to the power of -a,  </b>

- where the exponent α relates to the type of crime.



A general perspective is that several urban indicators have been found to scale with the population size N of the city according to a law of the form: 


<b> Y of x is approximately proportional to N to the power of b,  </b>

- where Y several urban indicatos, population size N , exponent β relates to the class of the indicator


In detail the next figure, is a Bokeh scatter plot with correlation for our Target new Variable, called Drunk & Drug, and on the y axis all the other crimes of the focus crimes set.

This helps us see, if there are correlations for high or low values of one against the others.

We will also input a table of 5 Highest and 5 Lowest Correlatiosn for the 168 Hours of the Week among all 36 crimes.

<embed 
       type="text/html" 
       src="/images/Bokeh_scatter.html"
       width="1100"
       height="800"
       >
</embed>



[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
