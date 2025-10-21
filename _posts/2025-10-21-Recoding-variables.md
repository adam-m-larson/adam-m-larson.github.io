---
title: Options for recoding a variable
tags:
  - Python
  - Recoding variables
  - Numpy
  - Pandas
---

When analyzing data from a survey, it is common that some questions have to be recoded.  Commonly, this means reverse coding, but the specific recoding procedure depends on the author's recommendation who developed the scale.  Let me give an example.  Say you are injured, were taken to the hospital, and the staff in the  emergency room asks you to rate your pain on a 10-point scale.  One represents the absense of pain.  Conversely, a ten indicates the worst pain you have ever felt.  In this case, your response represents the magnitude of pain experienced and we wouldn't reverse code your answer.

|---| No pain | --- | --- | --- | Moderate pain | --- | --- | --- | --- | Intense Pain |
|---| ------- | --- | --- | --- | ------------- | --- | --- | --- | --- | ------------ |
| E.R. pain scale | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |  

However, what if I asked Vincent, my 4.5 year old son, "Does your tummy feel okay?"  This question is still asking about pain, but it is framed in terms of "okay-ness" instead of pain.  In other words, I could plot your experience on a continuum, where one side is pain and the other is "okay-ness".  if I still REALLY care about how much pain he fells in his tummy, I could recode his "okay-ness" reponse into a pain response.  

<!--more-->

Inline code is done using backticks to create `something like this`, which is handy for talking about a specific `variable` or a `shortExpression++`.

Code blocks are wrapped in the `highlight` liquid tag together with a keyword to define the language, like this:

{% highlight liquid %}
{% raw %}
{% highlight javascript %}
    ...JS here...
{% endhighlight %}
{% endraw %}
{% endhighlight %}
 
## Examples

### JavaScript

Here's some JavaScript I borrowed from [this StackOverflow post](https://stackoverflow.com/questions/17776940/javascript-module-pattern-with-example):

{% highlight javascript %}
var modularpattern = (function() {
    // your module code goes here
    var sum = 0 ;

    return {
        add:function() {
            sum = sum + 1;
            return sum;
        },
        reset:function() {
            return sum = 0;    
        }  
    }   
}());
alert(modularpattern.add());    // alerts: 1
alert(modularpattern.add());    // alerts: 2
alert(modularpattern.reset());  // alerts: 0
{% endhighlight %}

### Python

And here's some Python from [this tutorial](https://www.tutorialspoint.com/python/python_classes_objects.htm):

{% highlight python %}
class Employee:
   'Common base class for all employees'
   empCount = 0

   def __init__(self, name, salary):
      self.name = name
      self.salary = salary
      Employee.empCount += 1
   
   def displayCount(self):
     print "Total Employee %d" % Employee.empCount

   def displayEmployee(self):
      print "Name : ", self.name,  ", Salary: ", self.salary
{% endhighlight %}

## Supported Languages

The highlighting is done with Rouge and at time of writing [their website] says they support 132 languages. I'm not 100% sure if all those are available in the version bundled within Jekyll. If you have successfully installed this theme, then you can run `rougify list` from the Terminal and you should get a list of supported languages. Or check out [this wiki page](https://github.com/jneen/rouge/wiki/List-of-supported-languages-and-lexers).

