---
title: "1.3 User Stories and Capturing Project Requirements"
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
 
- Describe the key features of writing user stories
- Highlight the characteristics and differences between functional and non-functional requirements
- Describe the purpose and composition of the product backlog
- Describe what makes a good product requirement
- Describe the purpose of a product backlog and what it contains
- Create an initial product backlog from a given scenario

::::::::::::::::::::::::::::::::::::::::::::::::

In this section, we'll introduce two established key concepts for capturing the needs of a project,

- *User stories*, which capture what is needed from solely the perspective of the client
- *Requirements*, which state what needs to be built (or what needs to change) by the development team 

So whilst they both capture what the software will do,
each reflects one side of the client/developer perspective.


## User Stories: Understanding what is Needed from the User Perspective

Capturing "requirements" is pivotal to understanding what needs to be built,
but whilst they state what is technically required,
they lack the end-user context of what they are and why they are important.
User stories aim to capture this perspective, being short and simple descriptions of new features or functionality from the perspective of the end user themselves.
Therefore, user stories help:

- The project remains *user-centered* and *focused on real needs*,
rather than jumping prematurely to solution or technical requirements
- To clarify the the *value* behind a feature,
and anchor development in *user outcomes*, not just functionality
- Prevent requirements ballooning, if not guided by real user goals
- Prioritise what matters to users

They typically follow the following template,
to ensure user stories are clear and concise:

> As a *[type of user]*, I want *[an action]* so that *[benefit]*.

Breaking each of these three aspects down:

- "As a *[type of user]*": who are we building this for? There may be more than one type of user, but in any case we need to think about this from the user's perspective.
- "I want *[an action]*": this describes the intent of this type of user, not the features of the system. What do they want to achieve?
- "so that *[benefit]*": what is the benefit they are trying to realise? How will it help them directly, solve a problem for them?

Some examples of user stories include:

- E-commerce site: as a shopper, I want to add items to my cart so that I can purchase multiple products at once
- Mobile application: as a user, I want to receive push notifications for important updates so that I stay informed when I'm not using the app


FIXME: mention acceptance criteria for functional and non-functional requirements

:::::::::::::::::::::::::::::::::::::::  challenge

## Solo Exercise: User Stories

Consider this scenario:

*"A small town cheese-making business has received many enquiries about being able to make online purchases delivered to their homes or place of business,
and so now want to also sell their many types of cheeses using an online store.
Online customers are looking to be able to search the store, select cheeses to purchase,
and when ready, add payment and shipping details and confirm the order.
There is some evidence that some online customers are environmentally and ecologically conscious,
so are interested in the environmental impacts of products.
In order to schedule their supply chains efficiently, business customers are keen to have updates on shipping.
From the perspective of the business owner, they want to able to manage available stock inventory on the online store."

Identify at least two types of user - also known as *personas* - that would use the store.
From the above scenario, create at least four user stories using this format:

> As a *[type of user]*, I want *[an action]* so that *[benefit]*.

Hint: focus on the user needs, not what may be implementated.

:::::::::::::::  solution

Here are some example user stories:

Business owner:
- As a business owner, I want to add new stock to the sit,e so that customers can purchase it.
- As a business owner, I want to remove old stock from the site, so that customers cannot purchase expired stock.

Personal customer:
- As a customer, I want to search available cheeses by name, so I can find the ones I want easily.
- As a customer, I want to add cheeses to a basket, so I can continue to shop and purchase them all later.

Eco-conscious customer:
- As an eco-conscious customer, I want to view the environmental impact details of products, so I can make environmentally-informed purchasing choices.

Business customer:
- As a business customer, I want to have real-time updates of orders that have been shipped, so I can organise my supply chains efficiently.

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::


## What Exactly is a Requirement, and Why are they Important?

In general, a requirement is a *capability or condition that must be met for software to solve a problem or address a need*.
They form the foundation of our project and drive what will be developed,
so if we do not properly explore and understand what is required, the software will not be suitable for it's intended purpose.

Whilst user stories focus purely on the user perspective,
requirements concentrate on what technically needs to change.
For this reason, it's common to develop user stories first (to understand the user),
then from those stories,
derive requirements (to understand what needs to be built).
Therefore, they typically address technical aspects of software functionality and features,
and are more numerous than the collection of user stories,
with each user story often being addressed by more than one requirement.

There is repeated evidence that most errors aren't actually introduced during the software development stage,
but during requirements analysis and design.
For example, [one analysis](https://doi.org/10.1109/ISRE.1993.324825) of the software errors uncovered during integration and testing and the Voyager (1977) and Galileo (1989) probes discovered that 79% of these errors were due to a poor understanding of requirements.

However, it is unlikely that we will be able to determine all of the requirements correctly and completely upfront.
In practice, very often requirements may need be flexible to some extent and may change as the project evolves, so we need to ensure we are able to accommodate any agreed changes.

## Requirements are More than just Features

When considering software requirements, it is very tempting to just think about the features users need. 
However, many design choices in a software project depend on the users themselves and the environment in which the software is expected to run (as well as *how* the software should run),
and these aspects should be considered as part of the software’s *non-functional* requirements.

To explore the importance of this aspect, let's consider two software types, mobile applications and embedded software.
They may appear similar, but examining the environments in which they are developed and operate uncovers many differences that need to be accounted for in order for the software to be fit for purpose.

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

## Solo Exercise: Types of Software

Think about some software you are familiar with
(could be software you have written yourself or by someone else)
and how the environment it is used in has affected its design or development.
Here are some examples of questions you can use to get started:

- What environment does the software run in?
- How do people interact with it?
- What features of the software have been affected by these factors?

:::::::::::::::  solution

## Some Examples

Desktop Application
- Has a graphical interface for use with mouse and keyboard
- May need to work on multiple, very different operating systems
- May be intended for users to modify / compile themselves
- Should work on a wide range of hardware configurations
- Documentation probably either in a manual or in the software itself

Command-line Application - Linux Tool
- User interface is text based, probably via command-line arguments
- Intended to be modified / compiled by users - though most will choose not to
- Documentation has standard formats - also accessible from the command line
- Should be usable as part of a pipeline

Command-line Application - High Performance Computing
- Similar to a UNIX Tool
- Usually supports running across multiple networked machines simultaneously
- Usually operated via a scheduler - interface should be scriptable
- May need to run on a wide range of hardware
  (e.g. different CPU architectures)
- May need to process large amounts of data
- Often entirely or partially written in a lower-level language for performance
  (e.g. C, C++, Fortran)

Web Application
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
- Reproducibility: how do we ensure others are able to reproduce results generated using the software?
- Portability: to what extent should the software be able to run on different systems with minimal changes?
- Maintainability: how easily can the software be modified, enhanced, or restructured?
- Reliability: to what extent should the software we able to operate without errors and unexpected failures?
- Availability: to what extent should the software remain accessible and operational when needed?


## The Coffee Beans Analysis Project

For the remainder of the course, 
we'll be making use of a hypothetical scenario for many exercises,
where a fictional coffee company is looking for a small software company to do some software development and analysis for them on an existing dataset.

Details for this scenario are found in the [Project Brief](files/ProjectBrief.pdf).

:::::::::::::::::::::::::::::::::::::::  challenge

## Group Exercise: Create a Product Repository

For this course each group will create it's own GitHub software repository,
based on another repository that contains the original client code that will be adapted.

First, select one member of the group to create the repository,
who needs to:

1. Go to https://github.com/softwaresaved/coffee-analysis on GitHub.
1. Select the `Use this template` button on the right, and then `Create a new repository`.
1. On the following page, enter a suitable owner (such as yourself) and the repository name (such as `coffee-analysis`), and ensure the repository is public. Ordinarily in such circumstances, development would very likely be private, but for the purposes of training, select a public repository.
1. Select 'Create repository'

A new repository will be created, with the contents of the original repository included.

Secondly, each member of the group needs to be invited to collaborate on the repository,
to ensure they have access.
The individual who created the repository thus needs to:

1. Select `Settings` on the new repository page, then select `Collaborators` (you may need to provide additional authentication for this step).
1. On the `Collaborators and teams` page, under `Manage people`, select `Add people`.
1. In the pop-up box, you should be able to search for each group member's GitHub account by username, and select `Add to repository` to send an invite.
1. Each new member will need to accept the invite, which is sent out by email.
1. Ensure each member has the `Maintain` permission on the repository,
which will allow them to push commits to the repository,
and perform other non-destructive repository actions.

::::::::::::::::::::::::::::::::::::::::::::::::::



## Capturing Requirements in a Product Backlog

A *product backlog* is a prioritised list of functionality that a product should contain;
essentially, a list of work for the development team.
It represents everything that might be needed in the product and is the single source of truth for all work.
They include requirement-related aspects such as features, bugs, improvements, and non-functional requirements,
but also any other supporting tasks such as any needed research (also known as *spikes*),
and other implementation-related tasks (like cleaning up/refactoring code).

A product backlog is owned by the *product owner* (the client),
and is dynamic, in that it evolves as the needs of the product evolves.
Regular backlog refinement sessions throughout a project ensure items are updated, estimated,
re-prioritised if necessary, and ready for upcoming sprints.



:::::::::::::::::::::::::::::::::::::::: callout

## What Makes a Good Requirement?

::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::::::::::::::::::::::::::  challenge

## Create a Product Backlog

:::::::::::::::  solution


:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::




:::::::::::::::::::::::::::::::::::::: keypoints
 
- FIXME
 
::::::::::::::::::::::::::::::::::::::::::::::::
