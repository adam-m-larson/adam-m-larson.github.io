---
title: Recoding a variable based on a condition
tags:
  - Python
  - Recoding variables
  - Numpy
  - Recoding by condition
---

After collecting data, you may decide to use a single variable to create groups.  For example, let's say you conducted a long-term memory study and you want to see if your experimental effect is consistent between who have a good memory vs. a poor memory.  This requires you examine the data and set conditions that must be met for someone to have "good" memory vs. "poor" memory.  One option would be to divide your sample into thirds.  The good memory group would consist of the participants who scored in the highest third, while theo poor memory group would be the participants who scored in the lowest third.  In this case, you're taking a data-driven approach to set a threshold that groups people into low or high memory groups.     

<!--more-->

Alternatively, perhaps there is an established benchmark that designations membership in a group.  For example, you may have to be a certain age to earn your drivers license.  Or a drive has to have a certain blood alcohol level to be considered an impaired driver.  In these cases, you are still setting a condition, a threshold, that indicates group membership.

For these instances, [numpy's select](https://numpy.org/doc/stable/reference/generated/numpy.select.html) function will help you recode data to establish groups.

First, I'll create a dataframe with three columns containing Age, Sex, and Blood Alcohol Level.  There will be three rows where each row represents data collected from one person.  All data is ficticious.  

{% highlight python %}
import pandas as pd
import numpy as np

df = pd.DataFrame({'Age' : [18, 24, 47], 'Sex' : ['M', 'F', 'M'], 'BAC' : [0.1, 0.0, 0.08]})
{% endhighlight %}

The first two lines of Python code import the necessary libraries and assign each an alias.  The last line creates a DataFrame called `df`.  Within the pd.DataFrame paratheses, I define each column and the data values in each column.

Next, I'll create a list that defines the conditions specifying if a drive is impaired.  I'll create a second list that defines the grouping variable as either "Impaired" or "Not Impaired".

{% highlight python %}
cond = [df["BAC"] >= 0.08, df["BAC"] < 0.08]
group = ["Impaired", "Not Impaired"]

df["Assigned Group"] = np.select(cond, group)
{% endhighlight %}

After creating the conditions list and the grouping list, I specify a new column, called `Asssigned Group`, that will be added to the `df` DataFrame.  I call the numpy function select and pass in my two lists `cond` and `group`. 