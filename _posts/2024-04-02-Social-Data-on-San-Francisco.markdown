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

<embed 
       type="text/html" 
       src="/images/heatmap_with_time.html"
       width="1100"
       height="600"
       >
</embed>

The third figure is a Bokeh scatter plot with correlation for our Target new Variable, called Drunk & Drug, and on the y axis all the other crimes of the focus crimes set.

This helps us see, if there are correlations for high or low values of one against the others.

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
