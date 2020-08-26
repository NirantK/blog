+++
title = "Case Study: Building a Data Science Team at a Startup"
description = ""
date = 2020-08-30T00:09:00+05:30
tags = ["career", "verloop", "machine learning", "tech"]
toc = true
# draft = true
show_reading_time = true
+++

Hello, if we are meeting for the first time, a short version of my story so far: After doing research engineering for almost 4 years across startups and Samsung Research, I joined as an early machine learning engineer at [Verloop.io](https://verloop.io) - a B2B startup that makes customer support automation SaaS. We're directly responsible for most Data Science needs within the business.

While there is plenty of good advice on [making ML work](https://www.shreya-shankar.com/making-ml-work/) and [making a career as a Data Scientist](https://medium.com/@rchang/advice-for-new-and-junior-data-scientists-2ab02396cf5b), I want to do a retrospective on what I've learnt in building a team which is far more competent than I am.

# Who is this for? 
I hope this answers the following question: 

* "What would it be like to be a Data Science Manager?"
* "How can I build a Machine Learning team from scratch?" 
    * This is typically founders e.g. CEO/CTO looking to build out a Machine Learning function 

This is divided into the following sections:

1. [Org Design](#organisation-design)
2. [Hiring](#hiring)
3. [Stakeholders](#stakeholders)
4. [Beliefs](#beliefs)

---

*_I'm hiring for a ML SDE 2 and a Data Science Manager/ML Lead Position*_

*_If this is something which interests you, are you are interested in working with us, please directly book a calendly slot with me here: https://calendly.com/nirant-k-verloop/intro-call-with-verloop-tech_*.

---
# Organisation Design 

> Organization Design is determined by these 3 broad categories:
>
> 1. Software Engineer vs Research: To what extent is the Machine Learning team responsible for building or integrating with software? How important are Software Engineering skills on the team?
>
> 2. Data Ownership: How much control does the Machine Learning team have over data collection, warehousing, labeling, and pipelining?
>
> 3. Model Ownership: Is the Machine Learning team responsible for deploying models into production? Who maintains the deployed models?

> -- Josh Tobin at [Full Stack Deep Learning](https://course.fullstackdeeplearning.com/course-content/ml-teams/team-structure)

From what I observed, most ML teams are harder to build+maintain than your engineering, this is because of few differentiating factors:

* Higher Skill Transfer from one role to another, which makes talent liquid and expensive
* Lack of ownership/support from Decision Makers

These were the two key pitfalls which I wanted to solve for when designing the ML team and how it sits in the larger org. The most well known ways in which companies organise Machine Learning Teams are these:

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

This was by far the most popular org design in startups or small business which themselves had a services arm or revenue attached to it. 

The basic flow is that business or product teams bring specific problems to a data science lead, who then scopes out a plan, defines a succsess criteria and hands it off to a Data Scientist within the team. 

There are so many understated but commonly known limitations of this, which ultimately hurt the gross margins of a SaaS business. This was dropped fairly early as a candidate for that specific reason.

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

Hiring for Machine Learning Engineering is hard. 

Despite what the media might tell you about the glut of data science talent. There are too many people who can model churn well or do the Titanic dataset right with Logistic Regression, not enough people who can come up with a simple TF-IDF model in a language they've not ever worked with e.g. not English. 

In Summer of 2019, I did over 120 introductory calls between February and August. Averaging, 6 calls every week from April to June. This converted to 1 summer intern, and 3 full time people. 

## One Role to Rule Them All

For >1 year, we have hired for exactly ONE role: Machine Learning Engineer. 

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

This input biasing seems to work amusingly well because it enables developers to always keep learning from each other. 

For instance, one of the things which I have asked from each team is a load test of their service - this led one developer to simply build an internal wrapper around the popular `locustio` which works with our service design out of the box. 

It frankly makes my job a lot easier if developers do amazing work without me pushing them to do it - specially by observing each other. I can honestly sit back and simply steer their curiosity, instead of investing my attention into solving the "motivation" problem.

## Process

Our hiring process consists of two primary rounds: a programming challenge and ML challenge. 

The programming challenge is a take home exercise which is focussed on low level design and straightforward API design. We typically give 2-3 days to the candidate for this. 

For the ML Challenge, we share a dataset for a take home challenge and then discuss the same with the candidate. This round has no right answer. It is deliberately open ended. 

It gives us a lot of signals on a wide variety of things we care about, for instance:

- how the candidate formulates the problem,
- measures the model performance,
- thinks about model selection and important of loss functions,
- prior/acquired experience with real world datasets,
- literature review/comfort with close to research work,
- ability to write clean, readable code,
- whether they include failed experiments, indicates their confidence with sharing honest results

To me, what has suprised most is the number of otherwise skilled people who use "this is what I saw on Medium" as a valid explanation for selecting a particular approach. This lack of agency (autonomy?) is a red flag.

## Onboarding

I am almost devilish when it comes to designing the best possible onboarding experience that I can. In the case of 1 intern, where I let it go off my radar - I think we didn't do our best as a team. The onboarding at Verloop ML consists of two specific pieces:

### 1. Before Joining Verloop
We share 6-8 week learning calendar focussed mostly on Deep Learning and Natural Language Processing. 

Each week is expected to take 8-10 hours of your time (but interns have told me that it takes closer to 30 hours) - and then I get on with them on a 1-1 call and discuss what they did well and what they missed. I share context from research or our own systems when relevant. One core byproduct of this onboarding calendar is that the candidate should get _very_ comfortable writing tons of experimental code of varying quality. 

This onboarding calendar is custom designed to each candidate, depending on their strengths which I should ideally understand during the interview process. 

### 2. After Joining Verloop

The onboarding process for each engineer is customizer to their weaknesses. For instance, an engineer coming from a stronger systems background will be first given a project which is mostly data cleaning and benchmarking ML models. So that they can get a deeper, more intimate understanding of how experiment design and evaluation works. 

Similarly, freshers out of college, who typically come from weaker engineering backgrounds (but stronger DL skills) - will spend the first few months paying off tech debt, learning to read legacy code or building new CRUD services. 

This is obviously in addition to the one heuristic which I've tried to follow: Ensure that every engineer gets one release into production within 4 weeks of joining Verloop.

# Stakeholders

## Managing Up

A common refrain from most senior ML people I spoke to is that: **Leadership does not understand AI/Data Science**

To me, this has always been an opportunity than a handicap. The most inspirational to me in this sense is the work of the likes of DJ Patil. He is the guy who coined the term, "Data Scientist" and was the Chief Data Scientist of the United States of America under Obama administration. 

I somehow think that an analytical & numerical leadership can be worked with, independent of their own training within the domain. For instance, I don't think Barack Obama can tell a random forest from a convolutional neural network.

Communication and convincing non-experts outside your domain is always hard, painstaking and tedious. I should clarify to say that I don't think this is an easy challenge and, hopefully, our peers in Design will hopefully agree. I think that it's worth the effort.

It'd be extremely stupid to assume that any of this would have been possible without the high degree of support and autonomy from the CEO, Gaurav himself. 

As much as I'd like to say/think that I earned that unfailing trust, Lord knows that I have made some messes which he had to clean up.

## Managing People 

This has been more tedious and detailed oriented than I'd expected. Early on, I'd decided that I'd not repeated any of the mistakes that my previous managers had made. Unfortunately, that bar was quite low. 

After >1 year, I've realized the way which works for me is to listen to what people want and then give them that. Hiring smart people and then getting out of their way seems to work really well in our specific team. 

I should point out books that have shaped how I think about Engineering/ML managment as well: 

- The Manager's Path by Camille Fournier
- Effective Engineer by Edmond Lau

On Managing Myself:

- Managing Oneself by Peter Drucker
- Standout 2.0 by Marcus Buckingham

Books which are highly recommended, but didn't help me enough:

- The Elegant Puzzle by William Larson
- Randical Candor by Kim Scott

Books which will probably have high impact, but in the future:

- HBR's 10 Must Reads: On Communication
- Effective Executive, by Peter Drucker
- Nonviolent Communication, by Rosenberg

Any book recommendation from me is incomplete with a mention to The Hard Things About Hard Things by Ben Horowitz

## Peer Management

While I'd expected this to be easy, this turned out to be quite emotionally hard. Since I transitioned out of backend engineering roles pretty early in my career - there are entire topics and concepts which I am not great at. This is made worse by the fact that I'm familiar with them, but not comfortable. 

So if 2 developers are discussing something, I can very well follow their conversation - but I don't have anything to contribute. 

This is quite frustrating. The sheer, persistent feeling of incompetency. Luckily, I don't have too much of a self respect/ego to care about this. I've always gravitated towards the best what I can do -- and what others cannot do well. At Verloop, that is Machine Learning/Data Science Management right now.

That said, within Verloop - ML has been the first adopter of almost all new dev tooling: 
- alerting and monitoring systems
- inhouse logging library to improve our microservice observability
- porting from previous Proto serving solution to twirpy

This is atleast partially because I didn't want the devs in my team to suffer. 

# Beliefs

## Don't be Clever

Machine Learning is a game where [87% models never go to production](https://venturebeat.com/2019/07/19/why-do-87-of-data-science-projects-never-make-it-into-production/) - almost every model we have picked, has gone to production.

I've worked in B2B SaaS companies for almost 4 years. Hence, I've some opinions on what doesn't work. I don't have strong opinions on what works though.

I encourage my teammates to come up with new ideas and propose everything from the annotation process to the alerting and monitoring configuration. The only place where I really intervene is if the rigour is absent, or they're solving for an imaginary problem.

So far, this mindset of simply trying to avoid mistakes, instead of trying to be clever has worked well. I suspect as long as ML deployment is a failure-prone business, this mindset will serve me well. If something like GPT3/GPT4 lowers the risk considerably well, I will have to adopt a different mindset altogether.

This has not always worked. We've made some stupid (in hindsight) bets which didn't work for a multitude of reasons, including our own overconfidence in our technical skill and market reasons. 

## Premortems

[Pre-mortems](https://hunterwalk.com/2012/04/23/the-premortem-preventing-failure-before-you-fail/) is a habit/tool which is still somewhat better known in Product Management than Data Science. In fact, it's better understood in Military Strategy than Data Science: 

He who knows his enemy ... - Sun Tzu

I typically list down the top 3 causes which will kill a project - and then actively monitor them till the project is so stable that I can pay attention to something else. 

## Do Less 

I am a low key fan of [Auren Hoffman](https://twitter.com/@auren)'s advice that great things come from focus and not from building optionality. In the design and selection of tasks which our team has picked, this has been my guiding idea. 

Almost every Data Science team can be considered to be built to serve two "purposes": Analytics and Product

Analytics teams contribute in two ways: 
1. Inform decision makers
2. Measure and monitor internal metrics

At Verloop, the Analytics function is purely owned by Product Management. We assist but don't own any outcomes.

We build a reasonable number of ETL and Data Exploration tools for our own use (e.g. a Metabase installation) - which we make available to every Verloop employee, but we don't own the outcomes.

This also has a direct bearing on our team size, scope and skill set: We don't need to hire anyone to handle your common churn, forecasting or similar insights problems. Everyone is a competent, contributing NLP Engineer.

## Make Bold Bets

TK Flesh this out

# In Hindsight

In the last 18 months, our team has grown from 1 engineer (me) to 6 engineers. When I joined, ML was a blocker for the wider org with both latency and performance challenges, which were quickly compounded because of legacy code. We were behind the curve where Machine Learning was seen as a cost center. 

Today, almost 18 months later, we're almost definitely ahead of the curve in terms of shipping. In the best case scenario, we can also become a profit center in as early as 6-12 months.

A large part of the impact comes from our excellent customer support team, product and engineering. Machine learning is a mere amplifier of what they already do well.

This has been one of the most fulfilling and hard things I have done. If you are considering a career in Data Science, I hope this helps you see beauty and effort beyond our love for data and ever increasing technical intricacies.

Natkhat,

Nirant

---
[ATL] Advanced Technologies Lab (CTO's Office), Samsung Research Institute, Bengaluru.