---
title: "1.3 Stakeholder management and project requirements"
teaching: 0
exercises: 0
---
 
:::::::::::::::::::::::::::::::::::::: questions
 
- What types of requirements should be captured for a project?
- What is a non-functional requirement?
- How do I describe and ensure how desired features will provide value to the end user?
- How should I capture, manage, and prioritise requirements for change?
- What methods help to clarify requirements with stakeholders?

::::::::::::::::::::::::::::::::::::::::::::::::
 
::::::::::::::::::::::::::::::::::::: objectives
 
- Highlight the characteristics and differences between functional and non-functional requirements
- Describe the key features of, types of, and approaches to writing user stories
- Describe the purpose and composition of the product backlog
- Describe what makes a good product requirement
- Describe the key principles and approaches to estimation [t-shirt estimation]
- Create an initial product backlog with approximate effort estimates
- Create questions for clarification needed from the client
- Apply requirements management techniques to elicit clear project requirements from stakeholders
- Apply MoSCoW with a client to prioritise items in a product backlog

::::::::::::::::::::::::::::::::::::::::::::::::

## What is a Requirement, and Why are they Important?

In general, a requirement is a *capability or condition that must be met for software to solve a problem or address a need*. They form the foundation of our project and drive what will be developed, so if we do not properly explore and understand what is required, the software will not be suitable for it's intended purpose.

FIXME: add in SWC slide references to importance of reqs and stats for failure, with examples (e.g. galileo probe)

However, it is unlikely that we will be able to determine all of the requirements correctly and completely upfront. Especially when working in a research context, requirements are flexible and may change as the project evolves, so we need to ensure we are able to accommodate any agreed changes.

## Requirements are More than just Features

When considering software requirements, it is very tempting to just think about the features users need. However, many design choices in a software project depend on the users themselves and the environment in which the software is expected to run (as well as *how* the software should run), and these aspects should be considered as part of the software’s *non-functional* requirements.

To explore the importance of this aspect, let's consider two software types, mobile applications and embedded software. They may appear similar, but examining the environments in which they are developed and operate uncovers many differences that need to be accounted for in order for the software to be fit for purpose.

| Concern   | Mobile Apps | Embedded Software
|-----------|-------------|------------------
| Platform | Work on range of mobile hardware and iOS/Android operating systems | Exact specification of hardware is known - often not necessary to support multiple devices; typically low power
| Development Language | Typically written in one of the higher-level platform preferred languages (e.g. Java, Kotlin, Swift) | Typically lower-level language (e.g. C) for better control of resources
| Compilation | Users will not (usually) modify / compile the software | Users will not (usually) modify / compile the software
| Installation | Usually distributed via a controlled app store | Usually distributed pre-installed on a physical device
| Interface | Must have graphical interface suitable for a touch display | May have no user interface, or interface may be physical buttons
| Documentation | Probably in the software itself or on a Web page | Documentation probably in a technical manual with a separate user manual
| Uptime | May not run continuously due to restarts | May need to run continuously for the lifetime of the device

Therefore, whilst a single piece of software may provide the same *functionality* on a mobile app or embedded device (for example, a photo frame application),
the other *non-functional* considerations affect many facets of how the software must be developed and how it must operate,
and we must account for them in our requirements.

:::::::::::::::::::::::::::::::::::::::  challenge

## Exercise: Types of Software

Think about some software you are familiar with
(could be software you have written yourself or by someone else)
and how the environment it is used in have affected its design or development.
Here are some examples of questions you can use to get started:

- What environment does the software run in?
- Why do people use it?
- How do people interact with it?
- What features of the software have been affected by these factors?
- If the software needed to be used in a different environment,
  what difficulties might there be?

:::::::::::::::  solution

## Some More Examples

- Desktop Application
  - Has a graphical interface for use with mouse and keyboard
  - May need to work on multiple, very different operating systems
  - May be intended for users to modify / compile themselves
  - Should work on a wide range of hardware configurations
  - Documentation probably either in a manual or in the software itself
- Command-line Application - UNIX Tool
  - User interface is text based, probably via command-line arguments
  - Intended to be modified / compiled by users - though most will choose not to
  - Documentation has standard formats - also accessible from the command line
  - Should be usable as part of a pipeline
- Command-line Application - High Performance Computing
  - Similar to a UNIX Tool
  - Usually supports running across multiple networked machines simultaneously
  - Usually operated via a scheduler - interface should be scriptable
  - May need to run on a wide range of hardware
    (e.g. different CPU architectures)
  - May need to process large amounts of data
  - Often entirely or partially written in a lower-level language for performance
    (e.g. C, C++, Fortran)
- Web Application
  - Usually has components which run on server and components which run on the user's device
  - Graphical interface should usually support both Desktop and Mobile devices
  - Client-side component should run on a range of browsers and operating systems
  - Documentation probably part of the software itself
  - Client-side component typically written in JavaScript

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

There are many categories of non-functional requirements,
but some popular examples include:

- Security: how do we ensure a user is authenticated and authorised to conduct a particular action?
- Performance: what performance goals will the software be required to satisfy?
- Usability: how will the user interact with the software?
- Portability: to what extent should the software be able to run on different systems with minimal changes?
- Reliability: to what extent should the software we able to operate without failures and remain available for use when needed?

FIXME: consider levels of requirements? e.g. business/solution/technical? Maybe include this within user stories section?


## User Stories: Understanding Requirements from the User Perspective

Capturing requirements is pivotal to understanding what needs to be built,
but whilst they state what is required, they lack the end-user context of what they are and why they are important.
User stories aim to capture this perspective, being short and simple descriptions of new features or functionality from the perspective of the end user themselves.

They typically follow the following template,
to ensure user stories are clear and concise:

> As a *[type of user]*, I want *[an action]* so that *[benefit]*.

Some examples of user stories include:

- E-commerce site: as a shopper, I want to add items to my cart so that I can purchase multiple products at once
- Mobile application: as a user, I want to receive push notifications for important updates so that I stay informed when I'm not using the app

FIXME: acceptance criteria for functional and non-functional requirements

:::::::::::::::::::::::::::::::::::::::  challenge

## User Stories

FIXME: add brief exercise

:::::::::::::::  solution


:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::


## Capturing Requirements in a Product Backlog



:::::::::::::::::::::::::::::::::::::::: callout

## What Makes a Good Requirement?

::::::::::::::::::::::::::::::::::::::::::::::::


## Estimation: the Foundation for Prioritisation

Once we have an initial set of requirements captured,
but before we assign and begin the work,
we need to understand their importance in relation to each other:
essentially we need to prioritise them.

But before we can prioritise our requirements,
there are some things we need to find out.

Firstly, we need to know:

- *The period of time we have to resolve these requirements* -
  e.g. before the next software release, pivotal demonstration,
  or other deadlines requiring their completion.
  This is known as a **timebox**.
  This might be a week or two, but for agile, this should not be longer than a month.
  Longer deadlines with more complex requirements may be split into a number of timeboxes.
- *How much overall effort we have available* -
  i.e. who will be involved and how much of their time we will have during this period.

We also need estimates for how long each requirement will take to resolve,
since we cannot meaningfully prioritise requirements without
knowing what the effort tradeoffs will be.
Even if we know how important each requirement is,
how would we even know if completing the project is possible?
Or if we do not know how long it will take
to deliver those requirements we deem to be critical to the success of a project,
how can we know if we can include other less important ones?

It is often not the reality in practice,
but estimation should ideally be done by the people likely to do the actual work:
the developers themselves.
It shouldn't be done by project managers or those otherwise not involved in development,
simply because they are not best placed to estimate,
and those doing the work are the ones who are effectively committing to these figures.
As well as lacking the inherent technical skills required to estimate,
having senior non-development roles dictating estimates is that they are at risk of non-development biases such as idealised project timelines and goals which may not be achievable.

FIXME: add 5-min estimation exercise

:::::::::::::::::::::::::::::::::::::::::  callout

## Why is it so Difficult to Estimate?

Estimation is a very valuable skill to learn, and one that is often difficult.
Lack of experience in estimation can play a part,
but a number of psychological causes can also contribute.
One of these is [Dunning-Kruger](https://en.wikipedia.org/wiki/Dunning%E2%80%93Kruger_effect),
a type of cognitive bias in which people tend to overestimate their abilities,
whilst in opposition to this is [imposter syndrome](https://en.wikipedia.org/wiki/Impostor_syndrome),
where due to a lack of confidence people underestimate their abilities.
The key message here is to be honest about what you can do,
and find out as much information that is reasonably appropriate before arriving at an estimate.

More experience in estimation will also help to reduce these effects.
So keep estimating!

::::::::::::::::::::::::::::::::::::::::::::::::::

An effective way of helping to make your estimates more accurate is to do it as a team.
Other members can ask prudent questions that may not have been considered,
and bring in other sanity checks and their own development experience.
Just talking things through can help uncover other complexities and pitfalls,
and raise crucial questions to clarify ambiguities.

## Prioritising our Backlog

FIXME: when to prioritise? essentially at a number of levels within the project

Now we have our estimates we can decide
how important each requirement is to the success of the project.
This should be decided by the project stakeholders;
those - or their representatives -
who have a stake in the success of the project
and are either directly affected or affected by the project,
e.g. Principle Investigators,
researchers,
Research Software Engineers,
collaborators, etc.

To prioritise these requirements we can use a method called **MoSCoW**,
a way to reach a common understanding with stakeholders
on the importance of successfully delivering each requirement for a timebox.
MoSCoW is an acronym that stands for
**Must have**,
**Should have**,
**Could have**,
and **Won't have**.
Each requirement is discussed by the stakeholder group and falls into one of these categories:

- *Must Have* (MH) -
  these requirements are critical to the current timebox for it to succeed.
  Even the inability to deliver just one of these would
  cause the project to be considered a failure.
- *Should Have* (SH) -
  these are important requirements but not *necessary* for delivery in the timebox.
  They may be as *important* as Must Haves,
  but there may be other ways to achieve them
  or perhaps they can be held back for a future development timebox.
- *Could Have* (CH) -
  these are desirable but not necessary,
  and each of these will be included in this timebox if it can be achieved.
- *Won't Have* (WH) -
  these are agreed to be out of scope,
  perhaps because they are the least important or not critical for this phase of development.

In typical use, the ratio to aim for of requirements to the MH/SH/CH categories is
60%/20%/20% for a particular timebox.
Importantly, the division is by the requirement *estimates*,
not by number of requirements,
so 60% means 60% of the overall estimated effort for requirements are Must Haves.

Why is this important?
Because it gives you a unique degree of control of your project for each time period.
It awards you 40% of flexibility with allocating your effort
depending on what's critical and how things progress.
This effectively forces a tradeoff between the effort available and critical objectives,
maintaining a significant safety margin.
The idea is that as a project progresses,
even if it becomes clear that you are only able to
deliver the Must Haves for a particular time period,
you have still delivered it *successfully*.

FIXME: 10 min exercise of prioritising some small list of requirements on a noddy project using moscow (close to a 60/20/20 split). Have some obvious bikeshedding-level reqs

:::::::::::::::::::::::::::::::::::::: keypoints
 
- FIXME
 
::::::::::::::::::::::::::::::::::::::::::::::::
