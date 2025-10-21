---
title: Recoding a variable with Pandas's replace function
tags:
  - Python
  - Recoding variables
  - Pandas
---

When analyzing data from a survey, it is common that some questions have to be recoded.  Commonly, this means reverse coding, but the specific recoding procedure depends on the author's recommendation who developed the scale.  Let me give an example.  Say you are injured, were taken to the hospital, and the staff in the  emergency room asks you to rate your pain on a 10-point scale.  One represents the absense of pain.  Conversely, a ten indicates the worst pain you have ever felt.  In this case, your response represents the magnitude of pain experienced and we wouldn't reverse code your answer.

However, what if I asked Vincent, my 4.5 year old son, "Does your tummy feel okay?"  This question is still asking about pain, but it is framed in terms of "okay-ness" instead of pain.  In other words, I could plot your experience on a continuum, where one side is pain and the other is "okay-ness".  if I still REALLY care about how much pain he fells in his tummy, I could recode his "okay-ness" reponse into a pain response.  

<div class="card mb-3">
    <img class="card-img-top" src="/theme/img/Vindent-at-Kia.jpg"/>
    <div class="card-body bg-light">
        <div class="card-text">
            Vicent wanted me to include this picture of him and a Kia.  It's his favorite.  And has nothing to do with recoding a variable.  
        </div>
    </div>
</div>


<!--more-->

To revese code "okay-ness" into my pain scale, I would simply reverse the order of my scale.  So, a Okay score of 10 would become a pain score of 1.  A okay score of 9 becomes a pain score of 2, an 8 is now a 3, and so forth.

There a couple of options to choose from that are from different libraries.  In this post, I'll focus on Pandas's replace function.  

### Python

And here's an additional reference for the [Pandas's replace function](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.replace.html):

{% highlight python %}
import pandas as pd

df = pd.DataFrame({'Pain Score': [10, 8, 7, 2], 'Okay Score': [1, 3, 4, 9]})
{% endhighlight %}

On the first line, I've import the Pandas library, and then I created a variable called `df`.  This contains a matrix of scores.  The first column is called `Pain Score' and each patient has given a pain rating on a 10 point scale.  The second column is called `Okay score', where I reverse coded the pain score into this column by hand.  

**Note:  Reverse coding by hand is a terrible idea.  Don't do it.  It takes way too much time and is error prone.  I say this because I have seen many undergrads to just that.  Don't!  There are better ways.  

In the codeblock below, I'll show how to create a new variable in the data frame.  The use replace to reverse code the Pain Score into a new variable called, `Reverse_coded_pain_score`.

{% highlight python%}

df["Reverse_coded_pain_score"] = df['Pain Score'].replace(np.arange(1,11), np.arange(10,0, -1))

{% endhighlight %}

Before the equal size, I've told Python to create a new column called `Reverse_coded_pain_score` and place it in the `df` Data Frame.  After the equal sign, I'm identifying the column with the origianl score `df['Pain Score']`.  I used dot notation to apply the replace function to that data `.replace`.  And in the paratheses I create two lists.  The first is an ordered list starting from 1 and going to 10.  This list represents my original 10 point Pain scale.  The second is an ordered list starting from 10 and going to 1.  This represents the reverse coded list.  So when Python sees a value of 6 in the pain score, it can map that value to the reverse coded list.  

Recoding with pandas's replace function is fast.  And if you make a mistake, you can go back, look at your code, and correct it.  This saves you lots of time so you can spend it doing more important things, like this...

<div class="card mb-3">
    <img class="card-img-top" src="/theme/img/Leo-sleeping.jpg"/>
    <div class="card-body bg-light">
        <div class="card-text">
            Leonardo napping after a hard morning of playing.  
        </div>
    </div>
</div>





