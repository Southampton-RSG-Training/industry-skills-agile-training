---
title: "1.3 Capturing project requirements"
teaching: 0
exercises: 0
---
 
:::::::::::::::::::::::::::::::::::::: questions
 
- What types of requirements should be captured for a project?
- What is a non-functional requirement?
- How do I describe and ensure how desired features will provide value to the end user?
- How should I capture and manage requirements for change?

::::::::::::::::::::::::::::::::::::::::::::::::
 
::::::::::::::::::::::::::::::::::::: objectives
 
- Highlight the characteristics and differences between functional and non-functional requirements
- Describe the key features of, types of, and approaches to writing user stories
- Describe the purpose and composition of the product backlog
- Describe what makes a good product requirement
- Create an initial product backlog with approximate effort estimates

::::::::::::::::::::::::::::::::::::::::::::::::

FIXME: keep this episode focused on requirements, intro to project brief, coming up with questions for client, capture from client? Move product backlog creation to next episode?
FIXME: or:
FIXME: lesson 1: user stories, intro to project brief, coming up with questions for client, meeting with client to capture user stories
FIXME: lesson 2: project requirements derived from user stories, SteveP video on importance of reqs (and user stories), adding to github, estimation, prioritisation

FIXME: reorder user stories with requirements, summary with process of us, reqs, prod. backlog

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
the other *non-functional* considerations describe facets of how the software must be developed and how it must operate (often as constraints),
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

FIXME: consider reordering reqs and user stories (so narratively, user stories flow into derived requirements)

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



:::::::::::::::::::::::::::::::::::::: keypoints
 
- FIXME
 
::::::::::::::::::::::::::::::::::::::::::::::::
