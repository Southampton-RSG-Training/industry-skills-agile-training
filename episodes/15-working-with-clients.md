---
title: "1.5 Working with Clients"
teaching: 0
exercises: 0
---
 
:::::::::::::::::::::::::::::::::::::: questions
 
- FIXME
 
::::::::::::::::::::::::::::::::::::::::::::::::
 
::::::::::::::::::::::::::::::::::::: objectives
 
-   Collaborate with clients to refine and prioritise product backlog items.
-   Develop a focused, outcome-driven agenda for a client meeting.
-   Conduct a productive and professional client kickoff meeting.
-   Apply communication and negotiation techniques in a technical context.
::::::::::::::::::::::::::::::::::::::::::::::::

 
# Communicating with Clients

One of the most important skills for a software engineer working in industry is the ability to communicate effectively with clients. 

Clear communication builds trust, prevents expensive misunderstandings, and ensures that the business goals and technical implementation are aligned

 
## Speaking the Same Language

Often you may need to translate technical concepts into non-technical language to ensure a shared understanding with the client.

-   Use analogies or briefly explain any terminology that you may need to use.  For example, rather than saying you're refactoring the code you might say 'We need to tidy up the code so that it's easier to change in future'.
-   Expand acronyms, even those which may seem obvious to you. 
-   Translate changes to the technical implementation to benefits for the client.  For example, rather than just saying you are 'upgrading the framework', you might say you are 'upgrading the framework to reduce future bugs and support newer features'.
-   Explain how technical decisions you need to make will impact the clients' goals, which might include things like revenue, usability, time to market, compliance etc.
-   Use diagrams to support shared understanding with non-technical clients

## Setting Realistic Expectations

-   **Under-promise, Over-deliver**: Clients would rather be pleased that something is delivered early or with more features than expected than be disappointed when something is delivered late.  So, it's better to underestimate what you will be able to deliver in a particular time.
-   Always build in contingency time and assume that some things will go wrong.  Think about the aspects of the development that could take longer than you initially anticipate.
-   Avoid committing on the spot, you can always say you will check with your team and get back to the client later.
-  Don't be afraid to be honest about limitations and communicate these clearly, even when it's not what the client wants to hear.  For example, “We can deliver this in two weeks, but without automated testing. If you want it tested properly, we’ll need an extra week.”

:::callout
## Techniques for Expectation Setting

### Timeboxing

Timeboxing is where you allocate a fixed amount of time to an issue and stop when that time is up, regardless of whether the issue has been resolved. Timeboxing can be useful when the work is exploratory or uncertain because it: 

-   makes transparent to the client how much time is being allocated to learning or discovery, which may not be clear from observable progress on the product.
-   helps avoid analysis paralysis (getting stuck on one issue indefinitely)
-  controls the risk when the outcome is uncertain

For example: *“Since we’re not yet sure how complex this integration is, we’ll allocate 2 days to investigate. We’ll regroup after that to decide the next steps based on what we learn.”*

### Tracking Velocity

In this context, velocity describes the amount of work that a team delivers in a set period. 

You would track how many tasks your team has completed in previous Sprints and use this as a baseline for how many tasks of a similar size can be completed in the current sprint.  This gives you an evidence-based approach to expectation setting.

Tracking velocity can help you to set realistic timelines based on what your team has actually delivered in the past.  It can also help you to build trust with the client through transparency and predictability

:::

## Handling Trade-offs with Professionalism

You may need to help clients make informed decisions about scope, time and cost.

-   Explain the project management triangle: You can have two out of three of fast, cheap and good.
-   Stay focused on solutions.  Instead of saying 'that's not possible' consider options, for example, “We can do X by Friday, or Y by next week - what’s more important?” 
-   Discuss the impact of adding a feature on increasing risk or delaying the development of another feature.
-   Try to stay neutral and fact-based, avoid any emotional language or blame.

## Minimum Viable Product

The Minimum Viable Product (MVP) is an early, basic version of a product that meets the minimum necessary requirements for use.  An MVP is often created to validate product assumptions and identify areas for improvement with minimal investment.  

The MVP is often a core artifact in an iterative development process.  When the most basic version of the product exists, it can be evaluated and improved in subsequent iterations.

You can use MoSCoW to help you and the client decide on the features necessary for the MVP.  It will probably include some or all of the must haves but few or none of the could/should haves.

![By Teemu - Own work, CC BY-SA 4.0, https://commons.wikimedia.org/w/index.php?curid=65494330](fig/minimum_viable_product.png){alt='diagram of a car mvp'}

## Reaching Clarity

Clarifying anything that is unclear to anyone involved is really important to avoid incorrect assumptions and ensure a shared understanding of what the team is trying to achieve.

Methods of improving clarity:

 - Give concrete examples for abstract requests. For example, ask follow-up questions like “When you say ‘fast’, do you mean under 1 second?”
 -  Confirm you understand by summarising what the client has requested.  For example, "So just to confirm, you’d like the dashboard to show data from the last 7 days by default?”
 -   Use written follow-ups in the form of email recaps and/or meeting notes.
 -  Don't pretend to understand. You could say something like “I’m not sure I follow, please can you give me an example?”


::: challenge
## Group Challenge: There's No Such Thing as a Silly Question

Think about what is unclear to you in the project brief and formulate a list of questions for the client.
:::

# Designing a Kickoff Meeting

## Objectives of a Kickoff Meeting

The three key objectives of a kickoff meeting are:

-   **Agree prioritised requirements**: Work with the client to review and prioritise the product backlog. While the final decision rests with the client, prioritisation should be a two-way conversation. Developers should feel confident advocating for items they believe are critical, especially technical tasks that may not appear important to non-technical stakeholders but are essential for enabling future features or maintaining system stability.
-   **Set expectations**: Establish a shared understanding of what will be delivered, when, and to what standard. This includes clarifying timelines, defining the scope of work for early iterations (such as the MVP), and agreeing on communication channels and response times. Setting clear expectations upfront helps reduce misunderstandings and prevents scope creep later in the project.
-   **Resolve ambiguity**: Clarify any unclear or vague requirements before development begins. This may involve asking the client to define specific terms, provide examples, or explain business rules in detail. The goal is to remove guesswork and ensure that both the development team and the client share the same understanding of what is being built and why.

## Anatomy of an Agenda

Every good meeting should have an agenda which maps out the key points that the meeting should cover.  A well-structured agenda helps to keep the meeting focused, efficient and productive.  An agenda for a kickoff meeting would usually include the following elements:

### Introductions & context

-   Introduce all participants of the meeting, including their roles and responsibilities.
-   Briefly explain why this project is happening.
-   Allow the client to describe the problem from their perspective.
-   Establish an open and collaborative atmosphere.

### Clarification of Brief and Identification of Gaps

Use your list of questions for the client in this section of the meeting

-   Review the brief provided by the client.
-   Confirm working definitions of any technical language i.e. make sure that any technical language means the same thing to the client and the whole team.
-   Highlight areas where the brief is vague, conflicting, or incomplete.
-   Ask follow-up questions to understand goals, constraints and assumptions.
-   Identify dependencies, risks, or areas where the team needs more detail.
-   Record all unanswered questions and agree who will follow up with answers.

### Prioritisation and MVP Discussion

-   Introduce the concept of a minimum visable product if necessary.
-   Use techniques such as MoSCoW to prioritise backlog items.
-   Help the client decide which features are essential for launch and which can wait.

### Expectations and Timelines

-   Discuss delivery phases or sprints and milestone dates (In this case you have two sprints, each about 3 hours in length, and the delivery is on day 5).
-   Clarify any constraints such as resource limitations.
-   Mention how changes to scope will be handled (e.g., change requests or backlog re-prioritisation).

Note: Be conservative in time estimates to allow for unforeseen delays.

### Summary of decisions

-   Recap all major decisions (e.g., MVP scope, timelines).
-   Review any open questions and note who will investigate and provide answers, and by when.
-   Clarify how and when a summary of this meeting will be shared (e.g., post-meeting email, shared document).
-   End the meeting by inviting final questions or concerns and confirming that the client is happy and confident about the plan.

::: challenge
## Group Challenge: Agenda Assembly

Create an agenda for a 30 minute kickoff meeting with the client for the Coffee Beans Analysis project.  

The agenda should take the form of either a bullet list or a table.

Use the structure above to develop your agenda ensuring it:
-   is logically structured.
-   each section has a rough timing assigned to it.
-   includes key questions or talking points under each section.
-   is appropriate for use with a non-technical client.
:::

## Meeting Notes

-   Capture decisions
-   Capture ambiguity
-   Actions

## Chairing the Meeting

-   the supplier i.e. the software developers should lead the meeting (When an electrician comes to your house they will ask the questions to get the information they need.  The customer shouldn't be expected to lead the interaction.)
-   make sure you get the information you need
-   the customer is unlikely to ask/answer the right questions
-   choose one person to take the lead

::: challenge
Client meeting
:::

::: challenge
Refine the backlog
:::

## References
-   [IEEE Software Engineering Body of Knowledge (SWEBOK), "Software Engineering Professional Practice"](https://swebokwiki.org)
-   [Minimum viable product wikipedia](https://en.wikipedia.org/wiki/Minimum_viable_product)

:::::::::::::::::::::::::::::::::::::: keypoints
 
- FIXME
 
::::::::::::::::::::::::::::::::::::::::::::::::
