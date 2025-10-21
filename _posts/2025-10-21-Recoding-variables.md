---
title: Options for recoding a variable
tags:
  - Python
  - Recoding variables
  - Numpy
  - Pandas
---

When analyzing data from a survey, it is common that some questions have to be recoded.  Commonly, this means reverse coding, but the specific recoding procedure depends on the author's recommendation who developed the scale.  Let me give an example.  Say you are injured, were taken to the hospital, and the staff in the  emergency room asks you to rate your pain on a 10-point scale.  One represents the absense of pain.  Conversely, a ten indicates the worst pain you have ever felt.  In this case, your response represents the magnitude of pain experienced and we wouldn't reverse code your answer.

However, what if I asked Vincent, my 4.5 year old son, "Does your tummy feel okay?"  This question is still asking about pain, but it is framed in terms of "okay-ness" instead of pain.  In other words, I could plot your experience on a continuum, where one side is pain and the other is "okay-ness".  if I still REALLY care about how much pain he fells in his tummy, I could recode his "okay-ness" reponse into a pain response.  

<div class="card mb-3">
    <img class="card-img-top" src="/theme/img/Leo-with-frosting.jpg"/>
    <div class="card-body bg-light">
        <div class="card-text">
            Leonardo eating frosting on a cupcake, but not the cupcake itself.
        </div>
    </div>
</div>


<!--more-->

To revese code "okay-ness" into my pain scale, I would simply reverse the order of my scale.  So, a Okay score of 10 would become a pain score of 1.  A okay score of 9 becomes a pain score of 2, an 8 is now a 3, and so forth.

There a couple of options to choose from that are from different libraries.  In this post, I'll focus on Pandas's replace function.  

### Python

And here's some Python from [this tutorial](https://www.tutorialspoint.com/python/python_classes_objects.htm):

{% highlight python %}
import pandas as pd

df = pd.DataFrame({'Pain Score': [10, 8, 7, 2], 'Okay Score': [1, 3, 4, 9]})
{% endhighlight %}

On the first line, I've import the Pandas library, and then I created a variable called `df`.  This contains a matrix of scores.  The first column is called `Pain Score' and each patient has given a pain rating on a 10 point scale.  The second column is called `Okay score', where I reverse coded the pain score into this column by hand.  

**Note:  Reverse coding by hand is a terrible idea.  Don't do it.  It takes way too much time and is error prone.  I say this because I have seen many undergrads to just that.  Don't!  There are better ways.  


## Supported Languages

The highlighting is done with Rouge and at time of writing [their website] says they support 132 languages. I'm not 100% sure if all those are available in the version bundled within Jekyll. If you have successfully installed this theme, then you can run `rougify list` from the Terminal and you should get a list of supported languages. Or check out [this wiki page](https://github.com/jneen/rouge/wiki/List-of-supported-languages-and-lexers).



