---
title: 'Making Nice Figures (in MATLAB) - Part 1'
date: 2020-06-24
permalink: /posts/2020/06/FigureTutorial1/
tags:
  - MATLAB
  - Figure
  - Data
  - EEG
---

I was recently invited to participate in a workshop for visiting *Research Experience for Undergraduates* ([REU](https://www.nsf.gov/funding/pgm_summ.jsp?pims_id=5517)) students at the [University of Houston's REU site](http://reu.egr.uh.edu/). This is the first of a few posts outlining my presentation on making nice figures. 

In any normal summer, talented and ambitious REU students gleefuly show up at the University, ready to embark on their summer research experience. They will spend the next 12 weeks in a research lab full of graduate students and postdocs who, under normal circumstances, have yet to discover it is summer break. In some labs, a student will show up and a project is sitting there ready for them to tackle. In other labs, graduate students and postdocs sit down with the student and try to identify a project for the next few months. In all cases, its an incredibly overwhelming experience where you are not only learning about *your* research project, but you are learning about what it means just to *do research*. 

Due to the COVID-19 pandemic, the REU summer internship (still ongoing as of this post) is now limited to an online research experience. As part of the training at the [UH REU site](http://reu.egr.uh.edu/), the group of fifty or so students is expected participate in a regularly-scheduled workshop covering topics on research practices, signal processing, machine learning, and a handful of more advanced topics in signal processing (with a primary focus being on neural signals, especially EEG). When consdering what topic I was going to present, I tried to think back to some of the essential skills I would have appreciated learning earlier on in my research career. Often times, one of the most challenging things you encounter when you first embark on a research journey is not the actual project itself, but learning how to explain *what* you did and exactly *how* you did it. One of the most important facets of great scientific story telling is the illustrations, or figures, you use to convey the message in your data (or theory). I am definitely not an expert in figure design or scientific visualization. However, I do care about the interpretability and aesthetics of my figures, and I try to put a lot of effort into maximizing both. While I am still young in my career, I consider myself enough of a veteran in research to know the aches and pains that come with the bumpy (but exhilerating!) ride.

I want to point the reader to a nice paper, entitled [Ten Simple Rules for Better Figures](
https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.100383). Instead of starting from scratch, I tried to draw on a lot of other 
great resources that ouline principles in figure design. In particular, I lean heavily on the paper [Ten 
Simple Rules for Better Figures](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.100383) to guide the discussion, since they 
already did a lot of the heavy lifting. Some of the points are perhaps a little less important for the budding scientists who are still new to research 
altogether, but they are all important to keep in the back of the mind when developing a figure for presenting your work. This paper is not so much about the details of *how* to make figures in any particular environment, but some general principles that guide the process. The MATLAB tutorials in the following posts were designed to illustrate a handful of these points in detail and provide guidance on the *how* aspect of figure making. I have to admit, I am working to transition 100% of my work to python and other open-source data analysis languagues, but when I started my Ph.D., MATLAB was still the go-to for neural data analysis. 

## Summarizing  *Ten Simple Rules for Better Figures*

In [Ten Simple Rules for Better Figures](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.100383), the authors outline ten points that help guide figure design and, hopefully, result in more informative and compelling figures for explaining your work. Here are the rules:

1. Know Your Audience
2. Identify Your Message
3. Adapt the Figure to Support Medium
4. Captions Are Not Optional
5. Do Not Trust the Defaults
6. Use Color Effectively
7. Do Not Mislead the Reader
8. Avoid “Chartjunk”
9. Message Trumps Beauty
10. Get the Right Tool

I am not going to go through each point individually. Instead, I urge you to read the [paper](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.100383) and then come back if you want to follow along with the MATLAB examples. We will touch on each in some way in the examples. Before we go on, however, I do at least want to point to some useful resources related to a few of these points.

### Adapt the Figure to Support Medium
While the paper tends to talk about adapting a figure's content to the medium (and this is a good point), an often overlooked point is adapting the figure to maintain the overall readability. For example, if I export a figure to fit in an article written on standard letter paper, there is no guarantee this will scale properly if I want to put it on a scientific poster or in slides for an oral presentation. We need to make sure we consider that all fonts scale properly and that the resolution remains high enough so that the image is not pixelated when we enlarge it. One invaluable tool I have found for managing this in MATLAB is the `export_fig` function. It operates as a wrapper around the `print` function, but helps to keep your figure exactly as you have it rendered on screen. Check out the [github page](https://github.com/altmany/export_fig) for more information and to download. I'll show an example of how this is used in the following post. 

### Do Not Trust the Defaults
When I first started trying to find resources on how to "beautify" figures beyond the defaults, I discovered the post, [Making Pretty Graphs](https://blogs.mathworks.com/loren/2007/12/11/making-pretty-graphs/), on Loren Shure's blog, [Loren on the Art of MATLAB](https://blogs.mathworks.com/loren/). Through a series of adjustments to the figure, she shows how to take your figures from drab...

<p align="center">
  <img src="https://blogs.mathworks.com/images/loren/118/pubQualityGraphics_01.png">
</p>

to fab!

<p align="center">
  <img src="https://blogs.mathworks.com/images/loren/118/finalPlot2.png"> 
</p>


Now, I know everyone has their own taste when it comes to aesthetics, but there is no doubt that the figure on the left (drab) is just completely uninformative and does a poor job at conveying the message (it saddens me to say that I have seen figures in slides that look like this!). This is what happens when your code looks like this:

```matlab
load data.mat
plot(x,y);
```

The data in this example are completely made-up, but just from looking at the figure on the right (fab!), I can see that whatever was measured, there is a clear relationship between length and mass, and there is more mass variance as the length increaes. Furthermore, I can see that a third order polynomial appears to fit the data, but a fair number of observations fall outside of our 95% confidence interval. Great! Without any context of what was being observed, I can still come up with a decent explanation of what is happening in the data.

### Use Color Effectively
Let me quote the article, [Why We Use Bad Color Maps and What You Can Do About It](https://www.osti.gov/servlets/purl/1338147), written by Kenneth Moreland at Sandia National Labs in Albuquerque, NM (my beloved hometown!) to give you a little flavor of what the rest of the section on color is going to taste like!

<p align="center">
  <img src="\images\Blog_20200604_FigureMaking1\RainbowColorMap"> 
</p>


