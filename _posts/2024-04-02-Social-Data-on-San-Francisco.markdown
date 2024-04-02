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

What is mostly illustrated is that the Crimes mostly happen in the central Area, near the Bay, Jackson Square and on the main road close to the bridge.

As we also read from in Class on [link](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0183110).
It seems that population size does not have an influence on the levels of concentration—despite the relationship between crime and total population. 

<b> Also Crime concentration manifests in the probability distribution of crime across a city which can be described by a power law. </b>

P of x is arrpoximatexy proportional to x to the power of -a, ${thus}$ :  

<b> $$ p(x) \propto x^{-a} $$ </b> 
where the exponent α relates to the type of crime.
In Our case the crime we selected was a new engineered feature that has Drunkenness and Drug possession for personal use.

**They found that the distribution of crime in a city can be approximated by a power-law distribution with exponent α that depends on the type of crime. Though criminal activities present regularities of concentration, we found that criminal ranks have the tendency to change continuously over time—features that support the perspective of crime as a complex system and demand analyses and evolving urban policies covering the city as a whole.**

Accordingly to quote them directly  
- "**Human dynamics also play a major role in criminal activities, which are likely to drive patterns in crime activity. In fact, empirical evidence has shown that crime presents a remarkable regularity of concentration in several dimensions that relate to context (e.g., target, location, offender) and to features (e.g., spatial, temporal, type of crime). In particular, the spatial concentration of crime exists in such way that, regardless of granularity level, some areas have disproportionately more crime than others—popularly called hotspots** "

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

This also is in alignment with the Paper we read in Class [link](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0183110)


<b> Regarding the Power Law </b>  
We based the logic of using Log - Log transformation because of the the general framework used to perform a comprehensive analysis of the allometric relationship between crime distribution and city population. 

Since the data used was from United States and United Kingdom it is a good assumption to use the Log Transformation in order to Make the Data Appear In Similar Magnitude Sizes.

Because population size does not have an influence on the levels of concentration—despite the relationship between crime and total population. 

Highlighting that :
<b> P of x is arrpoximatexy proportional to x to the power of -a, ${thus}$ :  </b>

$$ p(x) \propto x^{-a} $$
where the exponent α relates to the type of crime.


A general perspective is that several urban indicators have been found to scale with the population size N of the city according to a law of the form: 
$$ Y \propto N^{b} $$ 
{Y several urban indicatos, population size N , exponent β relates to the class of the indicator}


In detail the next figure, is a Bokeh scatter plot with correlation for our Target new Variable, called Drunk & Drug, and on the y axis all the other crimes of the focus crimes set.

This helps us see, if there are correlations for high or low values of one against the others.

We will also input a table of 5 Highest and 5 Lowest Correlatiosn for the 168 Hours of the Week among all 36 crimes.

<embed 
       type="text/html" 
       src="/images/Bokeh_scatter.html"
       width="1100"
       height="400"
       >
</embed>


Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
