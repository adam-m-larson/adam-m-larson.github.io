---
title: Computing trial-by-trial Accuracy
tags:
  - Python
  - Computing Accuracy 
  - Recoding variables
  - Numpy
---

Computing accuracy from an experiment is not too different from recoding a variable.  Instead of recoding a single column in your data frame, you'll compare two columns to computer an accuracy score.  For example, Let's say you did a recognition memory study. You participants stimuli to learn and then you gave them a chance to recall them.  During the recall phase, you'll randomly present stimuli that was seen with stimuli that was not seen.  For this exampel, this data is placed in a column named `Presented Stimuli`.  A value of 1 means the stimuli was presented in the learning phase, and a zero means the stimuli was not seen.  For each presentation, you'd collect a response from particiapnts in a column named `Participant Response`.  For example, stimuli that they think they saw in the learning phase could be coded as a 1 and new stimuli as a 0.  

<!--more-->

| Trial Number | Presented Stimuli | Participant Response |
| ------------ | ----------------- | -------------------- |
| 1 | 1 | 0 |
| 2 | 1 | 1 |
| 3 | 0 | 0 |
| 4 | 0 | 0 |
| 5 | 1 | 1 |

Computing accuracy will reply on [Numpy's where function](https://numpy.org/doc/2.3/reference/generated/numpy.where.html)

First, I'll import the libraries and the data in a variable called `df`.
{% highlight python %}
import numpy as np
import pandas as pd

df = pd.DataFrame({"Trial Number" : [1, 2, 3, 4, 5], "Presented Stimuli" : [1, 1, 0, 0, 1], "Participant Response" : [0, 1, 0, 0, 1]})
{% endhighlight %}

Now, I'll create a new column in the data frame, and use np.where to describing a condition that results in a correct response (coded as a 1) vs an incorrect response (coded as a 0).

{% highlight python %}

df["Correct Response"] = np.where(df["Presented Stimuli"] == df["Participant Response"], 1, 0)

{% endhighlight %}

This statment compares the `Presented Stimuli` column to the `Participant Response` column.  If the values match, the the `Correct Response` column gets a value of 1.  And if they don't match, then it gets a zero value.
