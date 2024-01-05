---
layout: defaults/page
permalink: index.html
narrow: true
title: Welcome to my Webpage!
---

I am an associate professor of Psychology at the University of Findlay.  I am passionate about researching topics in visual cognition, coding, and learning.  I hope to share my those topics with others.    

My research focuses on event perception.  Events correspond with actions that have a defined start time and end time.  For example, events can include: driving to work, making breakfast, and watching a movie.  Each example consists of an activity that most people would agree has a beginning and ending.  Events have been shown to affect our attention, memory, and comprehesion.  Some of my research has studied how we first build events.  

People track many things associated with an event.  Some of these include the characters, their goals, and the time/place of the event.  Since people consistently track these, then the characteristic recognzied first may also be used to build an event.  I presented participants with briefly presented images and asked them to identify either the action or the setting.  [The data indicated that the setting was recognized before the setting, suggesting this may be the first characteristic used to perceive an event.](https://jov.arvojournals.org/article.aspx?articleid=2141724&resultClick=1)  

If so, then recognizing the setting may also facilitate the identificatoin of other event characteristics, like the action. To test this prediction, I manipulated images so that they contained an action in a setting.  For example, an image could include cooking in a kitchen.  One set of participants viewed these images and I asked them to identify the action. Their performance was compared to another group of participants who saw the same exact images and engaged in the same task, except their images were photoshopped so that they could only view the action.  The kitchen background was replaced with the color grey.  The results showed that only viewing the action was better than seeing the action and setting, but this was only true with extremely limited viewing.  When participants viewed the images for longer times (roughly one third of a second), actions were better recognized in a setting than without.  This suggest that people extract event characteristics from images, but it takes some time to integrate these features together in a model of the event.  

<hr />

### Recent Posts

{% for post in site.posts limit:3 %}
{% include components/post-card.html %}
{% endfor %}


