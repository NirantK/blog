+++
title = "Verloop ML Interview Prep Guide"
description = "What we share with our ML candidates"
date = 2020-09-01T00:09:00+05:30
tags = ["career", "verloop", "tech"]
toc = true
show_reading_time = true
+++

# Preparation Guide

I've been a Machine Learning Engineer at [Verloop.io](https://verloop.io) for almost 1.5 years, primarily working on NLP problems and now more in an Engineering Manager-ish role.

This is the guide which we send to our candidates after they submit the Programming Challenge. We don't always do that, given that some of the candidates already have this skill set. 

I have also expanded on the overall piece to give the recommendation some context.

This is most useful to:
* Early career folks - typically less than 2 years of NLP experience
* Folks coming from Computer Vision/Tabular Data/Classical ML background

# What’s a Machine Learning Engineer?

Machine Learning Engineers at Verloop develop technologies that influence how users interact, engage and feel about chat and customer service. As a/an MLE, you will specialize in supervised/unsupervised learning and apply techniques to various problems, mostly dealing with high volume natural language processing applications.

At Verloop, the same team of engineers owns the entire stack from research to production. This means that the following roles HAVE NOT EXISTED at Verloop:

1. Data Scientist: 
    - Does: Data Analytics, Exploration, Model A/B Testing and Data Modeling
    - Tools: Everything from Data Viz to Excel, Pandas, spaCy and Scikit-Learn

2. Data Engineer: 
    - Does: Builds ata pipelines, storage, data version control, monitoring
    - Tools: Kafka, Airflow etc.

3. ML Researcher: 
    - Does: Trains forward looking, NOT production ready models. Focussed on experimentation
    - Tools: huggingface/transformers, spaCy, flair (by Zolando Research)

All of the above is done by MLE at Verloop. Every engineer is expected to build a strong suite in one or more of the above roles, while maintaining a "high" minimum at the others. MLE often contribute to adjacent/overlapping challenges such as DevOps for Machine Learning aka ML Ops. These are often problems in model serving, automated deployment and the like. 

Part of the following role got absorbed into what I've been doing as a Machine Learning Manager because we did not have a full time Product Manager in the company for more than 6 months:

1. ML Product Manager: 
    - Does: Work with ML team, data owners to prioritize, execute and spec out projects
    - Tools: Jupyter for PoC, JIRA, Slack, Google Docs for Comms

# Recommended Study

These are supposed to be indicative/descriptive of the technical skill we desire. These are not prescriptive i.e. you do not have to do the course to clear our interviews. 

We just have seen everyone with equivalent skill as these courses to do well in our interview process.

## Deep Learning
* Basics for Beginners: [FastAI Part 1 & 2](https://course.fast.ai)

**Deep Learning for NLP**

* NLP with Deep Learning: [cs224n by Stanford](https://web.stanford.edu/class/cs224n/)
    * For a SDE 2 role, having Deep Learning skills equivalent to this course is necessary but not sufficient
* [NLP: Code First Introduction](https://www.fast.ai/2019/07/08/fastai-nlp/) by FastAI’s Dr. Rachel Thomas

## Natural Language Processing
* [NLP Basics](https://github.com/NirantK/nlp-python-deep-learning/) - Open Source Code Notebooks on Github or [NLP by spaCy](https://course.spacy.io)
* Yandex Data School’s [NLP Course](https://github.com/yandexdataschool/nlp_course)

# General Interview Tips
**Think Out Loud** - We want to understand how you think, so explain your thought process and decision making throughout the interview. 

Remember we’re not evaluating your technical ability alone, but also how you solve problems.

**Clarify** - Many questions will be deliberately open-ended to provide insight into what parts and information you value within the technological puzzle.

We’re looking to see how you engage with the problem and your primary method for solving it. 

Be sure to talk through your thought process and feel free to ask specific questions if you need clarification.

# Machine Learning Interview Technical Prep

* At least one interview will be focused on your expertise within Machine Learning. General knowledge of the field and its main concepts should be demonstrated throughout the interview, such as supervised learning, unsupervised learning, overfitting, boosting, and regularization.

* Experience with common learning paradigms such as decision trees, k-means, LSTMs and understanding of how to apply those techniques to various problems is important.

# How to Prepare?

* Get extremely comfortable with writing code to do Machine Learning (and by extension, Deep Learning). This means knowing what to google, what libraries to use and so on is very valuable.

* Be mentally prepared to talk about your approaches and results. This is effectively a defence of your work. Help us understand why you made certain decisions, choices, and what went in your head. 

# Things to Think About

* This round is case-study driven. We value initiative and experimentation speed+quality over success. This means that even if you try an approach, which does not work for some reason - show us the work that you did: We’d love to learn what you tried.

* Ask yourself why would they have selected this problem for the challenge? What are some basics in this domain I should know about?

* What is the highest level of accuracy that others have achieved with this dataset or similar problems/datasets?

* What types of visualizations will help me grasp the nature of the problem/data?

* Which modelling techniques are good at capturing the types of relationships I see in this data?

* What are some of the weaknesses of the model and how can the model be improved with additional work?

* How do I measure performance? Does it help to have confidence values against the prediction?

* What is latency and compute needs for this model?

This document is inspired by similar documents by Google Inc. We borrow from the same when relevant. In case there are unintentional copyright violations, please inform at my email.

<iframe src="https://niranting.substack.com/embed" style="border:1px solid #EEE; background:white;" frameborder="0" scrolling="no"></iframe>
