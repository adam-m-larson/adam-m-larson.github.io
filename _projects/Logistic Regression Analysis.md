---
title: Using logistic regression to analyze scene cateogization performance between central vs. peripheral visual fields
---

## Summary

I analyze data published in [Larson and Loschky (2009)](https://jov.arvojournals.org/article.aspx?articleid=2122327).  The study examines the contributions of differt parts of our visual field to categorizing an image's setting (for example, an image could depict a "City", "Park", or "home").  The python code briefly summarizes the study and its findings.  Afterwards, I use Python and the statsmodel library to analyze the data using a logistic regression.  This [link to github repository](https://github.com/adam-m-larson/Logistic-Regression-Analysis-with-Larson-and-Loschky-2009-) contains the raw data in a .csv file and the python code in an .ipynb.

### Key Ideas

This post will focus on:

1. Providing a summary of the research examining how central and peripheral vision contributes to the task of scene classification
2. Computing descriptive statistics from the data collected
3. Analyzing the data using logistic regression
4. Visualizing the data

### Research Summary

Our view of the visual world is quite extensive. It allows us a glimpse as to where we are, what objects and poeple are in front of us, how we may go about navigating the enivornment, and so on. However, with such a large view of the world, only a very small percentage of it can extract out sharp details. This area is called central vision and we place our gaze on things that require this sharp detailed vision, like object and face recognition. Outside of central vision is peripheral vision. It takes up most of our visual field. Furthermore, it only detects blurry visual details and motion. Would these visual features be enough for people to recognize the scene category of an image (e.g., "Forest" vs. "Mountain")?

This study presented participants with images that presented information in central vision or peripheral vision. Like in the figure below, the Window condition presented visual information in central vision, whereas the scotoma condition blocked central visual information except for that in the periphery.

<div class="card mb-3">
    <img class="card-img-top" src="/theme/img/ScoWin_img/Leo-with-frosting.jpeg"/>
    <div class="card-body bg-light">
        <div class="card-text">
            Example images of a Window and Scotoma image.  Window images show visual scene content in central vision.  Whereas, Scotoma images present content in peripheral vision.
        </div>
    </div>
</div>





