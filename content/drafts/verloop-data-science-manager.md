+++
title = "Reflections on Building a Machine Learning Team at a Startup"
description = ""
date = 2020-09-01T00:09:00+05:30
tags = ["career", "verloop", "tech"]
toc = true
show_reading_time = true
+++

Hello, if we are meeting for the first time, a short version of my story so far: After doing machine learning engineering for almost 4 years across startups and BigCo, I joined as an early machine learning engineer at [Verloop.io](https://verloop.io) - a startup that provides customer support automation software. 

While there is plenty of good advice on [making ML work](https://www.shreya-shankar.com/making-ml-work/) and [making a career as a Data Scientist](https://medium.com/@rchang/advice-for-new-and-junior-data-scientists-2ab02396cf5b), I want to do a retrospective on what I've learnt in building a team which is far more competent than I am.

# Who is this for? 
I hope this answers the following question: 

* "What would it be like to be a Data Science Manager?"
* "How can I build a Machine Learning team from scratch?" 
    * This is typically founders e.g. CEO/CTO looking to build out a Machine Learning function 

# Problems we did not solve for

## Building an Analytics Function

Almost every Data Science team can be considered to be built to serve two "purposes": Analytics and Product

Analytics teams help in two ways: 
1. Inform decision makers
2. Measure and monitor internal metrics

At Verloop, the Analytics function is purely owned by Product Management. We assist but don't own any outcomes.

We build a reasonable number of ETL and Data Exploration tools for our own use (e.g. a Metabase installation) - which we make available to every Verloop employee, but we don't own the outcomes. 

## Building a state of the art Model Deployment Toolchain


# One Role to Rule Them All

For almost 1 year, we have hired for exactly ONE role: Machine Learning Engineer. 

As explained in our [MLE Prep Guide](./verloop-ml-prep-guide/), we collapsed several roles into one. This means we don't hire a specialized Data Scientist, Researcher and then separate Product and Data Engineers to productionize the models. 

At Verloop, the same engineer takes the entire system live from research to production, and occassionally several months into maintenance and growth as well.

This allows us to keep the hiring process straightforward, highly repeatable, while still maintaining enough faith in the process.

## T Shaped Skill Maps

The hiring process as we defined set a high bar on only 3 skills: 
1. Low Level API Design for Web Services
2. Programming Mindset and Quality
3. Natural Language Processing/Machine Learning Skills

I biased the top of the funnel of the interview process to hire a team of compliments around my weaknesses, but that individual's strengths. 

Of each of the first 3 full time hires, each person was atleast 2x better than me on that skill. This was important as each person would have a multiplier effect on the productivity of other developer's on the team. 

To give you a sense of these:
1. Person A has clear, proven strengths in High Level System Design and Databases
2. Person B has clear, proven strengths in DevOps and Cloud Deployments
3. Person C has clear, proven strengths in "hacking" with Deep Learning, optimizing for speed

# Team Structure

# Hiring

# Mindset

## Unforced Errors & Premortems

Machine Learning is a game where [87% models never go to production](https://venturebeat.com/2019/07/19/why-do-87-of-data-science-projects-never-make-it-into-production/) - almost every model we have picked, has gone to production.

I've worked in B2B SaaS companies for almost 4 years out of my 5 years in the game. Hence, I've some strong opinions on what doesn't work. I don't have strong opinions on what works though.

# Random Notes

When I was working on this problem, I came across very few people who had done this in my context: someone who is young, and hiring for a cash-starved company which barely had a functioning web page. My problems are distinct from not just Google, but also Swiggy, GoJek and Freshworks. I looked for more actionable advice then, but even Harvard Business Review had advice which was [pretty generic shit](https://hbr.org/2018/10/managing-a-data-science-team)

It'd be extremely stupid to assume that any of this would have been possible without the high degree of support and autonomy from the CEO, Gaurav himself. As much as I'd like to say/think that I earned that unfailing trust, Lord knows that I have made some messes which he had to clean up.

In the 18 months since, our team has grown from 1 engineer (me) to 6 engineers. When I joined, ML was a blocker for the wider org with both latency and performance challenges, which were quickly compounded because of legacy code. We were behind the curve where Machine Learning was seen as a cost center. 

Today, almost 18 months later, we're almost definitely ahead of the curve in terms of shipping. In the best case scenario, we can also become a profit center in as early as 6-12 months.

A large part of the impact comes from our excellent customer support team, product and engineering. Machine learning is an amplifier of what they already do well.

Machine learning performance is also, hopefully a way for us to differentiate against our less-good `.ai` counterparts.