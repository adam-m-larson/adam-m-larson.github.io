---
layout: defaults/page
permalink: index.html
narrow: true
title: Welcome to my Webpage!
---

I am an associate professor of Psychology at the University of Findlay.  I am passionate about researching topics in visual cognition and using data to drive insight.  I've created this site to demonstrate programming and data analytical skills through posts and projects.  Posts are geared towards new learners of Python (its libraries), SQL, and Tableau/Power BI.  Posts contain short descriptions of a single function that may help transform, select, or analyze data.  On the other hand, projects are longer and demonstrate the thought process behind generating insight from data.  

I hope this webpage helps you on your learning journey so you may not struggle as much as I did (In other words: Learn from your mistakes).  And, this may help provide insight to the usefulness of data analytic tools available to learn from the abundance of data all around us.      


<hr />

### Recent Posts

{% for post in site.posts limit:3 %}
{% include components/post-card.html %}
{% endfor %}


