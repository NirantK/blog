+++
title = "Reflections on Building a Machine Learning Team at a Startup"
description = ""
date = 2020-08-30T00:09:00+05:30
tags = ["career", "verloop", "machine learning", "tech"]
toc = true
draft = true
show_reading_time = true
+++

Hello, if we are meeting for the first time, a short version of my story so far: After doing research engineering for almost 4 years across startups and Samsung Research, I joined as an early machine learning engineer at [Verloop.io](https://verloop.io) - a B2B startup that makes customer support automation SaaS. We're directly responsible for most Data Science needs within the business.

While there is plenty of good advice on [making ML work](https://www.shreya-shankar.com/making-ml-work/) and [making a career as a Data Scientist](https://medium.com/@rchang/advice-for-new-and-junior-data-scientists-2ab02396cf5b), I want to do a retrospective on what I've learnt in building a team which is far more competent than I am.

# Who is this for? 
I hope this answers the following question: 

* "What would it be like to be a Data Science Manager?"
* "How can I build a Machine Learning team from scratch?" 
    * This is typically founders e.g. CEO/CTO looking to build out a Machine Learning function 

---

*_I'm hiring for multiple ML Roles, including a Lead Position*_

*_If this is something which interests you, are you are interested in working with us, please directly book a calendly slot with me here: _*.

---
# One Role to Rule Them All

For almost 1 year, we have hired for exactly ONE role: Machine Learning Engineer. 

As explained in our [MLE Prep Guide](./verloop-ml-prep-guide/), we collapsed several roles into one. This means we don't hire a specialized Data Scientist, Researcher and then separate Product and Data Engineers to productionize the models. 

At Verloop, the same engineer takes the entire system live from research to production, and occassionally several months into maintenance and growth as well.

This allows us to keep the hiring process straightforward, highly repeatable, while still maintaining enough faith in the process.

## T Shaped Skill Maps

Our hiring process evaluates all candidates on primarily 3 skills:

1. Low Level API Design for Web Services
2. Programming Mindset and Quality
3. Natural Language Processing/Machine Learning Skills (see [Prep Guide](./verloop-ml-prep-guide) if you're curious)

I biased the top of the funnel of the interview process to hire a team of compliments around my weaknesses.Each compliment should bring in a skill which is my weakness, but that individual's strength. 

Of each of the first 3 full time hires, each person was atleast 2x better than me on that skill. This is important as each person has a multiplier effect on the productivity/quality of other developers on the team. 

To give you a sense of these:

1. Person A has clear, proven strengths in High Level System Design and Databases
2. Person B has clear, proven strengths in DevOps and Cloud Deployments
3. Person C has clear, proven strengths in "hacking" with Deep Learning, optimizing for speed

# Team Structure

> Organization Design is determined by these 3 broad categories:
>
> 1. Software Engineer vs Research: To what extent is the Machine Learning team responsible for building or integrating with software? How important are Software Engineering skills on the team?
>
> 2. Data Ownership: How much control does the Machine Learning team have over data collection, warehousing, labeling, and pipelining?
>
> 3. Model Ownership: Is the Machine Learning team responsible for deploying models into production? Who maintains the deployed models?

> -- Josh Tobin at [Full Stack Deep Learning](https://course.fullstackdeeplearning.com/course-content/ml-teams/team-structure)

The most well known ways in which companies organise Machine Learning Teams are these:

## 1. Research & Development Labs

Of these, a R&D Lab is ideal for most well capitalized businesses because it enables them to attract talent, which can in turn work on long term business/tech challenges. Uber AI Labs, Google AI Research, DeepMind, and FAIR are some examples from the top of my head which have executed this well. 

I have personally spent some time working in such an org design. [ATL] 

The limitation with this org design is that R&D teams don't own inputs (data) and outputs (model performance in production).  This makes this org design all but useless for a pre/near Product Market Fit startup.

## 2. Embedded within Business & Product Teams

I asked different people on how they organize Data Science teams/function within their companies in India. I tried to talk to folks who had worked on the 10-30 employee count stage to get a better estimate of challenges which occur there but disappear later in the life cycle of the organization, but didn't really come across too many of them.

By far the most popular org design in Indian startups, a Data Scientist is embedded into an engineering team along with an analyst which is then assigned to a business or product team. From the top of my head, this is how some of the best Data Science teams like AirBnb, Flipkart, and Facebook organize their ML teams. 

I strongly considered this org design, but ultimately opted against this because it would not play to my strengths at all. Specifically, I expected these challenges:

1. Hard to maintain uniform data standards and practices across the org
2. Management Complexity, in terms of the ever increasing breadth of problems across different features

## 3. Data Science Consultant

This was by far the most popular org design in startups or small business which themselves had a services arm or revenue attached to it. The basic flow is that business or product teams bring specific problems to a data science lead, who then scopes out a plan, defines a succsess criteria and hands it off to a Data Scientist within the team. 

There are so many understated but commonly known limitations of this, which ultimately hurt the gross margins of a SaaS business. This was dropped fairly early as a candidate in my homework.


## 4. [Near Future] Productized Data Science Team

When I studied more modern teams, especially in B2B SaaS or eCommerce from outside, I _felt_ they made a small but important change in this model: Instead of a matrix where the Data Scientist was ultimately responsible to their own unit and nothing else, they had a central Data Science function to which all Data Scientists reported. 

Some teams created a new, "Chief Data Scientist" or "VP, Machine Learning" designations to reflect this increased autonomy and status within the org. Notice, that this is quite similar to how some Design teams are organized.

While I had not worked under this org design, I had interned at a place which was small (10-50 employees) and I could understand the limitations of this org design when I was told the same. 

The most common warning was the amount of context which any lead/manager Data Science had to keep beyond a certain project count within the company. I expect that **Verloop ML Team will evolve into this** over the next 12-24 months. I'm estimating this on the basis of the problem complexity and the head count needed  engineering and data science teams both  

## 5. [Today] Machine Learning Pillar

This is the **org design at Verloop ML today**.

From the top of my head, I don't know of any large businesses which have executed this well except for TikTok and Baidu. The defining characteristic of this org design is that the ML Lead reports directly to the CEO.

The CEO directly brings the business context and drives quick wins. The ML Lead needs to negotiate continuously on organisational goals, constantly query for added context, and makes long term bets.

Part of the ML Product Manager role also got absorbed into what I've been doing as a Machine Learning Manager because we did not have a full time Product Manager in the company for more than 6 months:
- Does: Work with ML team, data owners to prioritize, execute and spec out projects
- Tools: Jupyter for PoC, JIRA, Slack, Google Docs for Comms

The only real advantage of this org design is that it makes attracting talent easier by giving them quite high autonomy. The team also owns model performance and deployment. The deployment ownership is made possible by a ML Sytem Design decision as well: The strong adherence to multi-tenant models instead of client specific models.

There are so many reasons that this org design is a bad design that it'd take us an entire night to spell it out. Since the team can influence everything (to varying degrees) from engineering to front end changes - the blast radius of what this team can screw up or drastically improve is quite large. 

# Hiring

# Mindset

## Unforced Errors

Machine Learning is a game where [87% models never go to production](https://venturebeat.com/2019/07/19/why-do-87-of-data-science-projects-never-make-it-into-production/) - almost every model we have picked, has gone to production.

## Premortems

[Pre-mortems](https://hunterwalk.com/2012/04/23/the-premortem-preventing-failure-before-you-fail/) is a habit/tool which is still somewhat better known in Product Management than Data Science. In fact, it's better understood in Military Strategy than Data Science. 

He who knows his enemy ... - Sun Tzu

I've worked in B2B SaaS companies for almost 4 years out of my 5 years in the game. Hence, I've some strong opinions on what doesn't work. I don't have strong opinions on what works though.

## Managing Up

### Leadership

A common refrain from most senior ML people I spoke to is that: **Leadership does not understand AI/Data Science**

To me, this has always been an opportunity than a handicap. The most inspirational to me in this sense is the work of the likes of DJ Patil. He is the guy who coined the term, "Data Scientist" and was the Chief Data Scientist of the United States of America under Obama administration. 

I somehow think that an analytical & numerical leadership can be worked with, independent of their own training within the domain. For instance, I don't think Barack Obama can tell a random forest from a convolutional neural network.

Communication and convincing non-experts outside your domain is always hard, painstaking and tedious. I should clarify to say that I don't think this is an easy challenge and, hopefully, our peers in Design will hopefully agree. I think that it's worth the effort.

It'd be extremely stupid to assume that any of this would have been possible without the high degree of support and autonomy from the CEO, Gaurav himself. 

As much as I'd like to say/think that I earned that unfailing trust, Lord knows that I have made some messes which he had to clean up.

## Managing Down

## Peer Management:w


# Random Notes



<!-- # Simplifying Decisions

I am a low key fan of [Auren Hoffman](https://twitter.com/@auren)'s advice that great things come from focus and not from building optionality. In the design and selection of tasks which our team has picked, this has been my guiding idea. 

## Building an Analytics Function

Almost every Data Science team can be considered to be built to serve two "purposes": Analytics and Product

Analytics teams contribute in two ways: 
1. Inform decision makers
2. Measure and monitor internal metrics

At Verloop, the Analytics function is purely owned by Product Management. We assist but don't own any outcomes.

We build a reasonable number of ETL and Data Exploration tools for our own use (e.g. a Metabase installation) - which we make available to every Verloop employee, but we don't own the outcomes.

This also has a direct bearing on our team size, scope and skill set: We don't need to hire anyone to handle your common churn, forecasting or similar insights problems. Everyone is a competent, contributing NLP Engineer.

## Building a state of the art Model Deployment Toolchain
 -->


When I was working on this problem, I came across very few people who had done this in my context: someone who is young, and hiring for a cash-starved company which barely had a functioning web page. My problems are distinct from not just Google, but also Swiggy, GoJek and Freshworks. I looked for more actionable advice then, but even Harvard Business Review had advice which was [pretty generic shit](https://hbr.org/2018/10/managing-a-data-science-team)

[Models for Integrating Data Science Teams](https://medium.com/@djpardis/models-for-integrating-data-science-teams-within-organizations-7c5afa032ebd) by DJ Pardis was exceptionally helpful in designing the team more consciously. More important, it gave me a vocabulary, a structure on which to hang my observations and notes.


In the 18 months since, our team has grown from 1 engineer (me) to 6 engineers. When I joined, ML was a blocker for the wider org with both latency and performance challenges, which were quickly compounded because of legacy code. We were behind the curve where Machine Learning was seen as a cost center. 

Today, almost 18 months later, we're almost definitely ahead of the curve in terms of shipping. In the best case scenario, we can also become a profit center in as early as 6-12 months.

A large part of the impact comes from our excellent customer support team, product and engineering. Machine learning is an amplifier of what they already do well.

Machine learning performance is also, hopefully a way for us to differentiate against our less-good `.ai` counterparts.

[ATL] Advanced Technologies Lab (CTO's Office), Samsung Research Institute, Bengaluru.