---
title: Using logistic regression to analyze scene cateogization performance between central vs. peripheral visual fields
---

## Summary

I analyze data published in [Larson and Loschky (2009)](https://jov.arvojournals.org/article.aspx?articleid=2122327).  The study examines the contributions of differt parts of our visual field to categorizing an image's setting (for example, an image could depict a "City", "Park", or "home").  The python code briefly summarizes the study and its findings.  Afterwards, I use Python and the statsmodel library to analyze the data using a logistic regression.  This [link to github repository](https://github.com/adam-m-larson/Logistic-Regression-Analysis-with-Larson-and-Loschky-2009-) contains the raw data in a .csv file and the python code in an .ipynb.

### Key Ideas

This post will focus on four parts:

1. Providing a summary of the research examining how central and peripheral vision contributes to the task of scene classification
2. Computing descriptive statistics from the data collected
3. Analyzing the data using logistic regression
4. Visualizing the data

### Part 1

Our view of the visual world is quite extensive. It allows us a glimpse as to where we are, what objects and poeple are in front of us, how we may go about navigating the enivornment, and so on. However, with such a large view of the world, only a very small percentage of it can extract out sharp details. This area is called central vision and we place our gaze on things that require this sharp detailed vision, like object and face recognition. Outside of central vision is peripheral vision. It takes up most of our visual field. Furthermore, it only detects blurry visual details and motion. Would these visual features be enough for people to recognize the scene category of an image (e.g., "Forest" vs. "Mountain")?

This study presented participants with images that presented information in central vision or peripheral vision. Like in the figure below, the Window condition presented visual information in central vision, whereas the scotoma condition blocked central visual information except for that in the periphery.

<div class="card mb-3">
    <img class="card-img-top" src="/theme/img/ScoWin_img/m_jov-9-10-6-fig002.jpeg"/>
    <div class="card-body bg-light">
        <div class="card-text">
            Example images of a Window and Scotoma image.  Window images show visual scene content in central vision.  Whereas, Scotoma images present content in peripheral vision.
        </div>
    </div>
</div>

### Methods

Participants could view windows and scotomas of different sizes, like in the figure below.  The top row shows various windows sizes from a one degree window (which consists of foveal vision, the best region of our visual field for detecting details.  To understand its size, it is the width of your index finger at arms length).  Next, a five degree window encompases all of your central vision (e.g., the width of your fist at arms length).  At 10.8 degrees, the window takes up 50% of the image and at 13.6 there is more viewable area than is being blocked.  The bottom row shows the scotomas of the same size.  a one degree scotoma blocks all of foveal vision (where we are best at extracting details), the five degree scotoma blocks all of central vision leaving just peripheral vision.  At 10.8 degrees there is an equal amount of viewable area in the periphery as there is visual area being blocked centrally.  Finally at 13.6 degrees, more veiwable area is blocked in the image than is being viewed. 

<div class="card mb-3">
    <img class="card-img-top" src="/theme/img/ScoWin_img/m_jov-9-10-6-fig003.jpeg"/>
    <div class="card-body bg-light">
        <div class="card-text">
            This shows the four different radii used in the window vs scotoma images.
        </div>
    </div>
</div>

Participants viewed many trials in our experiment.  Below is an example of one of those trails.  First, participants fixated a cross in the center of the computer screen and when ready, pressed any button to start the trial.  An image would be presented (either window or scotoma) for 106 ms, followed by a gray screen for 750 ms (three quarters of a second), and then a post cue word.  When presented with the post cue, participants responded if the word matched the scene category.  Half the time the word did match the scene category.  

<div class="card mb-3">
    <img class="card-img-top" src="/theme/img/ScoWin_img/m_jov-9-10-6-fig004.jpeg"/>
    <div class="card-body bg-light">
        <div class="card-text">
            This trial schematic shows what participants saw on each trial.
        </div>
    </div>
</div>

### Results

The results are shown in the line graph below.  The x-axis varies the size of the window/scotoma and the y-axis shows the proportion of correct responses.  The blue line shows the performance for the window condition, while the red line shows the scotoma performance.  Overall, removing the foveal visual field (one degree scotoma) and all of central vision (five degree scotoma) has no effect on scene categorization performance relative to a control condition where participants viewed the entire unaltered image.  Additionally, those scotoma conditions performance were much better than the window conditions.  However, the effect reverses with window sizes of 10.8 degrees or larger.  Specifically, at those radius sizes, the  window condition outperforms the scotoma condition. 

<div class="card mb-3">
    <img class="card-img-top" src="/theme/img/ScoWin_img/m_jov-9-10-6-fig005.jpeg"/>
    <div class="card-body bg-light">
        <div class="card-text">
            This shows accuracy (in terms of a percentage correct) for the Window and Scotoma conditions. 
        </div>
    </div>
</div>

### Conclusion

This shows central vision is not necessary for the task of scene categorization.  Furthermore, the visual periphery can extract the necessary information needed to categorize the environment.  It is possible that after recognizing our current location, that we use that information to guide our attention to critical objects, people, and routes to interact with within that environment.

## Part 2
