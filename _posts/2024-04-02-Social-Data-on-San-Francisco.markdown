---
layout: post
title:  "Social Data Analysis of San Fransisco Data"
date:   2024-04-02 10:10:41 +0200
categories: jekyll update
---
# Our Story of the San Francisco Data 

## Intro
We showcase the crimes of Drug Possession, Drunkenness and a combination of them over time, and their interaction with other crimes.  
The new Feature has Drunkness and Drug/Narc where the description of the DRUG/NARCOTIC was possession. This was for personal use, since there is an amount dependency on criminal charges.

We will explore the change over the years, where and when they are reported and finally correlation with other focus crimes.


## How the Crimes Change Over time
The figure is An Area stack plot of selected Crimes.
It is done with Boheh, so it is possible to see how each of Drunkenness and Narcotics contribute both together and individually.

Stack Area Plot works by having the components on top of each other and lastly the final aggregated, in this case a sum over each day of the Counts of the crimes and the final one one top.
The advantage is that we can see Multiple time-series together simply by stacking the bands.

It appears, that the greatest contributor to the combination is the drug possession rather that drunkenness.

T crime rates seem to be reducing. Although the city is notorious for being a hub of drug and homelessness crisis. 

After research, it seems it has to do with its lenient policy on drug arrests. 

The citizens are of many different views. Some agree with the policy of acceptance while other disagree with the relatively relaxed nature of laws.

 <b> [Hoover Institution Newspaper link](https://www.hoover.org/research/economics-how-san-franciscos-drug-policies-are-devastating-city) </b>
> San Francisco’s drug tolerance policies are based on the idea of “harm reduction,” which is the view that those using illegal drugs should be protected, not shamed nor prosecuted for their drug use, and that their lifestyle should be accepted as a normal part of life for those choosing to use. San Francisco prosecutes very little, provides free drug paraphernalia, including hypodermic needles.
> - Lee E. Ohanian is a senior fellow (adjunct) at the Hoover Institution and a professor of economics and director of the Ettinger Family Program in Macroeconomic Research at the University of California, Los Angeles (UCLA).

This would potentially reduce disease chances and spread.   

<embed 
       type="text/html" 
       src="/images/my_stacked_counts_plot_until_2017.html"
       width="1100"
       height="600"
       >
</embed>

## How Crimes are located in Space and Time

<b> Here we see a figure is a Heat map with Time.</b>

Shows, where they are located at different times of the day.
We did an aggregation that is based on a double loop, the first is the day of week, the inside is the hour. Then it gets appended into a list so it can be plotted.

This is an advantage over the classical map, because we can also see, the time instead of just a static sum. This helps us explore and explain the data with more detail.

We decided to do it this way, because further aggregations would lose the geographical and time data that is with each element of the crime dataframe.

What is mostly illustrated is that the Crimes mostly happen in the central Tenderloin Area, near the Bay, Jackson Square and on the main road close to the bridge.

### Regarding the Paper of The scaling of crime concentration in cities [link](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0183110)

- Marcos Oliveira ,Carmelo Bastos-Filho,Ronaldo Menezes

It seems that population size does not have an influence on the levels of concentration despite the relationship between crime and total population. 

<b> Also Crime concentration manifests in the probability distribution of crime across a city which can be described by a power law. </b>
[Power Law Link](https://en.wikipedia.org/wiki/Power_law)

#### In Our case the crime we selected was a new engineered feature that has Drunkenness and Drug possession for personal use.

In the article they found that the distribution of crime in a city can be approximated by a power-law distribution with exponent α that depends on the type of crime. Though criminal activities present regularities of concentration, they found that criminal ranks have the tendency to change continuously over time—features that support the perspective of crime as a complex system and demand analyses and evolving urban policies covering the city as a whole.

Quoting directly : 
- "**Human dynamics also play a major role in criminal activities, which are likely to drive patterns in crime activity. In fact, empirical evidence has shown that crime presents a remarkable regularity of concentration in several dimensions that relate to context (e.g., target, location, offender) and to features (e.g., spatial, temporal, type of crime). In particular, the spatial concentration of crime exists in such way that, regardless of granularity level, some areas have disproportionately more crime than others—popularly called hotspots** "


### Local Journals and Newspapers 
It seems that the concentration that we see at Tenderloin ( the central area hub near the Bridge and Bay ). Has been in a way organized by local government and police forces.

<b> Citing San Francisco Chronicle : [Newspaper link](https://www.sfchronicle.com/projects/2023/san-francisco-drug-trade-policy/)</b>  
> Mayor Breed and Chief Scott will also have to reckon with the city’s unofficial, decades-long practice of allowing the Tenderloin to serve as the city’s containment zone for drug markets, homelessness and other societal ills. The city has concentrated housing for the formerly homeless in the neighborhood, as well as social programs. Meanwhile, police have traditionally taken a moderate approach to law enforcement there, according to one former captain, tolerating a certain level of crime to keep it from spreading elsewhere.
Tenderloin residents — and drug users confronted with constant temptation — have borne the burden of that strategy.

> - By Crime Reporter
Megan Cassidy, with The Chronicle. Cassidy worked for the Arizona Republic covering Phoenix police, Sheriff Joe Arpaio and desert-area crime and mayhem.

<embed 
       type="text/html" 
       src="/images/heatmap_with_time.html"
       width="1100"
       height="600"
       >
</embed>

## Relationships between Crimes and Log transformation

Here we illustrate the crimes and relationships. 

We display the correlation for the focus crimes for the original data and also the Log Transformed Data.
This showcases the difference, between the magnitudes of data. It penalizes high and low values, since some crimes as more rare, although they could be correlated and the high/low value could interfere with the correlation.

They are plotted side by side. This changes the visualizations, in a sense 'normalizes' data, without caring so much about absolute count values. 

This also is in alignment with the Paper, [link here](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0183110)


<b> Regarding the Power Law </b>  
We based the logic of using Log - Log transformation because of the the general exponential framework that is mostly used by researchers to perform analysis on allometric relationships between crime distribution and city population. 

Based on journal, the data used was from United States and United Kingdom it is a good assumption to use the Log Transformation in order to Make the Data Appear In Similar Magnitude Sizes.

Directly Quote:
>Because it appears that population size does not have an influence on the levels of concentration—despite the relationship between crime and total population. 

Highlighting that :
<b> P of x is arrpoximatexy proportional to x to the power of -a,  </b>

- where the exponent α relates to the type of crime.



A general perspective is that several urban indicators have been found to scale with the population size N of the city according to a law of the form: 


<b> Y of x is approximately proportional to N to the power of b,  </b>

- where Y several urban indicatos, population size N , exponent β relates to the class of the indicator


Here, a Bokeh scatter plot with correlation for our Engineered Variable, x axis "Drunk & Drug", y axis the other crimes of the focus set.

This helps us to see, correlations for high/low values against the others.

<embed 
       type="text/html" 
       src="/images/Bokeh_scatter_2.html"
       width="1100"
       height="800"
       style="margin: 0; padding: 0;"
       >
</embed>

A table of 5 Highest and 5 Lowest Correlations for the 168 Hours of the Week among all crimes.

A question that arose after creating our new crime category, was to get some deeper understanding of how being drunk and possibly under some narcotic substance, would interact with the rest of the crime types of our data. Therefore, we decided that the Pearson corelation between our new crime category against all the other categories. Link for more information:
[Pearson Correlation Coefficient](https://en.wikipedia.org/wiki/Pearson_correlation_coefficient)



Calculations showed that there is a strong positive correlation with the ones in the table. It is worth mentioning that our focused crime is highly correlated with the warrant crime, as well as with non-criminal crimes. This would be interesting fact, as warrant crimes means that police would arrest someone if they suspected a crime. In addition, non-criminal crimes in most cases seem to be drug-related violations, as well as actions like activating a smoke sprinkler device, or being involved in a motorized accident where damages are caused to the vehicles only. Actions that would be excused if a person was under some substance.

| Rank | Category        | Score    |
|------|-----------------|----------|
| 1    | WARRANTS        | 0.977644 |
| 2    | STOLEN PROPERTY | 0.897906 |
| 3    | OTHER OFFENSES  | 0.880912 |
| 4    | NON-CRIMINAL    | 0.850609 |
| 5    | LIQUOR LAWS     | 0.833276 |

| Rank | Category                    | Score     |
|------|-----------------------------|-----------|
| 1    | ARSON                       | -0.279992 |
| 2    | DISORDERLY CONDUCT          | -0.200893 |
| 3    | DRIVING UNDER THE INFLUENCE | -0.087187 |
| 4    | TREA                        | 0.003610  |
| 5    | SEX OFFENSES, NON FORCIBLE  | 0.116725  |


[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
