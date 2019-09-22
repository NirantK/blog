+++
title =  "ML Model Monitoring"
date = 2019-09-21T23:29:18+05:30
tags = ["python", "machine learning", "production ml"]
featured_image = "images/ink.png"
description = "How to keep your identity small?"
toc = true
show_reading_time = true
+++

# ML Model Monitoring

Mayank asked on [Twitter](https://twitter.com/MayankSatnalika/status/1175446811860824064): 

> Some ideas/ papers/ tools on  monitoring models in production. A use case would be say a classification task over large inputs and I visualise how are the predicted values or even confidence scores very over time? 

## Quick Hacks

### pandas-profiling

If you are logging confidence scores, the quickest hack is to load them into a dataframe and visusalize with pandas-profiling: https://github.com/pandas-profiling/pandas-profiling/

### Rolling means

Similarly quick is to calculate rolling aggregates (e.g. mean, variance) of your confidence scores and add them to your set of monitoring and alerting product metrics. 

A slightly better version of this would be to do it on cohort level. Actually, doing all of the following analyis on cohort level makes sense:

### Confidence Scores and Thresholds

One of the most common mistakes is to use static threshold(s) on a confidence score(s). 

If you hear someone saying that they do not use thresholds for a classification problem. Stop and think. They are using a threshold, usually 0.5 from within the ML library that you are using. 

This is sub-optimal. The better option would be to use a holdout validation set and determine the threshold from that. 

### Tagging Data 

It is obvious that you will tag the predictions for which the model is least confident -- so that the model can learn. 

What you should also do is this: 

- Find out samples which have high confidence and tag them first, this is a form of negative sample mining

- In case of multi-class: Figure out samples which have low confidence, but the highest prediction is correct -- add these back to your new training+validation set first

- Tag samples which are too close to the threshold (or close to the hyperplane separating the classes) - this will help you understand your model and dataset's (vaguely) _margin of separation_ better

## Training-Serving

Let me share a secret with you Mayank: You can discover some of the most frequent issues with your model-in-production issues just by investigating **training-serving skews** or differences. 

The differences can be on 3 levels:
Data, Features, Predictions

The better hack would be to consider a rolling mean of 

## Data Differences 
Data differences can be of several types, the most frequest are these:
Schema change - someone dropped a column!, 
Class Distribution Change - When did this 10% training class have 20% predictions, or 
Data Input Drift - users have started typing instead of copy-pasting!

### Schema skew (copied from Google's ML Guide)
Training and serving input data do not conform to the same schema. 	The format or distribution of the serving data changes while your model continues to train on old data. 	

**Solution?** Use the same schema to validate training and serving data. Ensure you separately check for statistics not checked by your schema, such as the fraction of missing values 

### Class Distribution check with Great Expectations
Training and serving input data do not conform to the same class frequency distribution. After confirming that this has indeed happened for valid reasons, update the model by training with updated frequency distribution of each class.

For monitoring these first two, check out: https://github.com/great-expectations/great_expectations

For understanding data drift, you need to visualize data itself. This is too data-domain specific (e.g. text, audio, image). And more often than not, it is just as better to visualize features or vectors.

## Feature Viz for Monitoring 

Almost all models for high dimensional data (images or text), indirectly or directly *vectorize* data. I am using features and vectorized embedding as loosely synonymous here.

Let's take text as an example:

### Class Level with umap
With umap https://github.com/lmcinnes/umap, you can get plots like these for pretty much any vector space on the class level:

![umap-tweet-plots](https://raw.githubusercontent.com/NirantK/blog/master/content/images/umap-tweets-plot.png "UMAP Tweet Plots")

Plot similar plots for both training and test, and see if they have visually similar distributions. 

## Prediction Viz for Monitoring

Here you can get lazy, but I'd still recommend that you build data-domain specific _explainers_

### Sample Level with LIME

Consider this for text:

![lime-viz](https://raw.githubusercontent.com/NirantK/blog/master/content/images/lime-viz.png "Lime Visualization for Explaining Model Predictions")

Check out other black box ML explainers: https://lilianweng.github.io/lil-log/2017/08/01/how-to-explain-the-prediction-of-a-machine-learning-model.html by the amazing @lilianweng

### Class Level

You can aggregate your predictions across multiple sameples on a class level:

![agg-lime-viz](https://raw.githubusercontent.com/NirantK/blog/master/content/images/agg-lime-viz.png "Aggregated Lime Visualization for Explaining Model Predictions on Class Level")

# Citations and Resources

[1] Machine Learning Testing in Production: https://developers.google.com/machine-learning/testing-debugging/pipeline/production

[2] Recommended by DJ Patil as "Spot On, Excellent": http://www.unofficialgoogledatascience.com/2016/10/practical-advice-for-analysis-of-large.html

[3] Practical NLP by Ameisen: https://bit.ly/nlp-insight. The images for umap, LIME, and aggregated LIME are all from nlp-insight

[4] Machine Learning:The High-Interest Credit Card of Technical Debt: https://storage.googleapis.com/pub-tools-public-publication-data/pdf/43146.pdf