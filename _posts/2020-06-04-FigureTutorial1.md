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

Due to the COVID-19 pandemic, the REU summer internship (still ongoing) is now limited to an online research experience. As part of the training at the [UH REU site](http://reu.egr.uh.edu/), the group of fifty or so students is expected participate in a regularly-scheduled workshop covering topics on research practices, signal processing, machine learning, and a handful of more advanced topics in signal processing (with a primary focus being on neural signals, especially EEG). When consdering what topic I was going to present, I tried to think back to some of the essential skills I would have appreciated learning earlier on in my research career. Often times, one of the most challenging things you encounter when you first embark on a research journey is not the actual project itself, but learning how to explain *what* you did and exactly *how* you did it. One of the most important facets of great scientific story telling is the illustrations, or figures, you use to convey the message in your data (or theory). In this first post, I want to summarize some of the main ideas I presented to the group. Instead of starting from scratch, I draw on a lot of other great resources that ouline principles in figure design. In particular, I lean heavily on the paper [Ten Simple Rules for Better Figures](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.100383) to guide the discussion, since they already did a lot of the heavy lifting. 

## Ten Simple Rules for Better Figures

In [Ten Simple Rules for Better Figures](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.100383), the authors outline ten points that help guide figure design and, hopefully, result in more informative and compelling figures for explaining your work. Some of the points are perhaps a little less important for the budding scientists who are still new to research altogether, so I will spend a little more time on the ones I think are relevant to them. While I am still young in my career, I consider myself enough of a veteran in research to know the aches and pains that come with the bumpy (but exhilerating!) ride. 
