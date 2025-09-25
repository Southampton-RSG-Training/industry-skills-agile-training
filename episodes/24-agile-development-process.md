---
title: "2.4 The Agile Development Process"
teaching: 0
exercises: 0
---

::: questions
-   What are the two key principles of Scrum Theory?
-   What are the five Scrum Values?
-   How do the Scrum Pillars relate to each other?
-   What are the responsibilities of each of the Scrum Team roles?
-   What are the commitments for each of the three Scrum Artifacts?
:::

::: objectives
-   Explain the Philosophy of Scrum
-   List and briefly describe the five Scrum Values
-   List and briefly describe the three Scrum Pillars
-   Describe the responsibilities of the three Scrum roles
-   Describe the primary artifacts and stages within Scrum and how they relate as a process
-   Describe the purpose of the sprint backlog and how it is used throughout a sprint
-   Define Definition of Done
:::

::: callout
*'Scrum is a lightweight framework that helps people, teams and organizations generate value through adaptive solutions for complex problems'* - The Scrum Guide
:::

# Scrum Philosophy

Scrum is an iterative and incremental approach.

Scrum is intentionally **minimalist**. It defines only what is essential to implement Scrum theory, encouraging teams to build on it and adapt it to their context.

Scrum is deliberately **incomplete**.It doesn't provide detailed instructions, but instead provides a structure to guide interactions and relationships.

Scrum can be used alongside or around existing practices, processes and frameworks. 

Just as important as the visible elements of Scrum, such as the Scrum Team Roles, Events and Artifacts, are the underlying values and philosophy of Scrum.  For Scrum to work effectively, you need to adopt a mindset and way of working that is underpinned by certain values and actions. 

These are defined in the Scrum Guide as the Principles, Values and Pillars.  

They can be depicted as a temple with the key principles of Empiricism and Lean Thinking as the foundations, the Values as the steps, and the Pillars holding up the roof of the temple.  The Scrum Events (i.e. everything that happens in the Sprint) can be thought of as part of the 'roof', and will only run effectively when the pillars, steps, and foundations are in place.

![](fig/scrum_temple.png){alt='diagram of scrum philosophy, values, pillars and artifacts stacked on top of each other in the shape of a temple'}


## Key Principles of Scrum Theory

There are two key principles of Scrum Theory:

-   **Empiricism**: Decisions are based on observation and experience, not speculation. Work is guided by evidence and continuous learning.
-   **Lean Thinking**: Focus on delivering value while eliminating waste i.e. doing only what matters most.

![](fig/scrum_philosophy.png){alt='diagram of scrum philosophy, values, pillars and artifacts stacked on top of each other in the shape of a temple with scrum philosophy highlighted as the foundations'}

:::: challenge
## Solo Exercise: Fill in the Blanks

3 mins.

We've just introduced some key concepts of Scrum philosophy.  To reinforce your learning, think about the information you've just read (or heard) and fill in the blanks to create sentences that accurately describe the philosophy of Scrum. 

1.  It is intentionally \_\_\_\_\_\_\_\_\_\_, meaning it provides only the essential structure and leaves room for adaptation.
2.  Scrum is based on \_\_\_\_\_\_\_\_\_\_, which means knowledge comes from experience and decisions are based on observation.
3.  It also draws on \_\_\_\_\_\_\_\_\_\_ thinking, which emphasizes reducing waste and maximizing value.
4.  Scrum is both \_\_\_\_\_\_\_\_\_\_ and \_\_\_\_\_\_\_\_\_\_, allowing teams to inspect and adapt regularly.

::: solution
1.  incomplete
2.  empiricism
3.  lean
4.  iterative, incremental
:::
::::


# Scrum Values

Scrum isn't only about what is done but how it is done.
Scrum has five values that encourage a healthy and productive working environment.
These guide the Scrum Team's work, actions and behaviour.

1.  Commitment - the Scrum Team commits to achieving its goals and supporting each other
2.  Focus - the primary focus of the Scrum Team is the work of the sprint to make the best possible progress toward the Sprint Goal.
3.  Openness - the Scrum Team and its stakeholders are open about the work and the challenges. This builds trust and surfaces problems early.
4.  Respect - Every team member is valued as capable and autonomous. Scrum works best in an environment of mutual respect.
5.  Courage - Scrum Team members need courage to tackle hard problems and speak truthfully.

Scrum isn't just a set of meetings and roles.
Scrum only works when the team truly adopts the values it was built to support.

::: callout
*“Scrum is the framework I built to put those values into practice. There is no methodology.”* - Jeff Sutherland (co-creator of Scrum)
:::

![](fig/scrum_values.png){alt='diagram of scrum philosophy, values, pillars and artifacts stacked on top of each other in the shape of a temple with the steps to the temple highlighted and each step showing a value'}


::: challenge
## Pair Exercise: Scrum Values in Practice

3 mins.

Discuss the following questions with your partner:

-   Which Scrum Value do you think you would find hardest to put into practice?
-   Why?
-   How could a team support each other in developing that Scrum Value?
:::

# Scrum Pillars

The effectiveness of Scrum relies on three core pillars, which are built on top of the foundations of Empiricism and Lean Thinking, and the steps of Scrum Values:

1.  **Transparency:** the process and work must be visible to those performing the work and stakeholders.
    Transparency is essential for effective inspection and adaptation.

2.  **Inspection:** the progress toward goals must be inspected to detect problems quickly.

3.  **Adaptation:** when problems are identified through inspection, the team must adapt to minimise any further deviation from the goal.


The pillars are interconnected and each one is critical to Scrum - without transparency, inspection is misleading. Without inspection, adaptation is impossible.

![](fig/scrum_pillars.png){alt='diagram of scrum philosophy, values, pillars and artifacts stacked on top of each other in the shape of a temple with the pillars highlighted'}


::: callout
## Consequences of a Lack of Transparency: From Inconvenience to Devastation

**Manipulating Burndown Charts**

An anecdote of Scrum ineffectiveness from Scrum.org describes how a team deliberately altered their burndown chart to align exactly with the ideal progress line on the chart.  The Scrum Team said that they were "manipulating the numbers so that the management does not bother them".

The empirical data was falsified, going against one of the key principles of Scrum theory.  This meant that the Scrum Team and wider organisation couldn't accurately inspect or adapt, making Sprint Planning and Review totally ineffective activities.


**Horizon IT British Post Office Scandal**

The Post Office’s Horizon accounting software, introduced in 1999, contained numerous bugs (e.g., duplicating ledger entries, phantom shortfalls) that erroneously implicated hundreds of subpostmasters in fraud.

The software company Fujitsu and the Post Office were aware of these serious issues as early as 1999–2002 but concealed them from the public, subpostmasters, and even prosecution courts. They denied errors and pressured individuals to cover unexplained deficits, while claiming system reliability in court.

This highlights the disastrous consequences that a lack of transparency can have.  
:::

::: discussion
## Group Exercise: What happens when the Pillar of Transparency Crumbles?

3 mins.

Discuss in small groups the following questions:

-   What’s an example of “transparency” you’ve seen - or failed to see - in a previous project?

-   How did it affect the outcome?
:::

:::: challenge

## Group Exercise: Inspecting and Adapting

3 mins.

During a Daily Stand-Up Meeting, inspecting the progress on the project reveals some problems:

-   A developer has created a front-end component which displays some output from an API endpoint, but the endpoint doesn't currently exist and isn't scheduled for the current Sprint.  The Developer can't continue with the rest of their work until this endpoint is in place.
-   When discussing their planned work, the group notices that two developers are working on elements that heavily depend on each other - if one isn't compatible with the other, the software won't work. 
-   One developer is scheduled to work on a large task over the next couple of days, which is critical to the rest of the group's work.  However, the developer is going on holiday the next day.

**Can you suggest a possible adaptation for each of the problems?**

::: solution

Suggested **adaptations** (others are also possible):

-   Talk to the Product Owner to determine whether the creation of this API endpoint can be moved to the current Sprint and decide which tasks could be deprioritised to enable this.
-   The two developers decide to set up co-working sessions using pair programming and whiteboard design to ensure that the components are compatible.
-   Reassign the large task to another developer and assign the developer who's going on holiday to smaller task(s) that can be finished in less than a day. 

:::

::::


# Scrum Artifacts and Commitments


The Scrum Artifacts are tangible items that provide transparency about the work being done. They are the Scrum Team's source of truth.
They make visible what's being worked on, why it matters, and how close you are to delivering value.

There are three key Artifacts in Scrum: the **Product Backlog**, **Sprint Backlog** and **Increment**. Each Artifact comes with a commitment that helps to keep the team focused and aligned

![](fig/scrum_artifacts.png){alt='diagram of scrum philosophy, values, pillars and artifacts stacked on top of each other in the shape of a temple with the roof of the temple highlighted and scrum artifacts written on it'}

## Product Backlog

The Product Backlog is an ordered list of everything the product might need including features, fixes, experiments, and improvements.
It evolves constantly based on things like feedback, market shifts, and changing stakeholder goals.

-   The Product Backlog belongs to the Product Owner, but anyone can contribute ideas.
-   Helps the team to understand what might come next in the product's development.
-   Refined continuously so that items are clear, provide value and ready when needed.

### Commitment: Product Goal

The Product Goal is the long-term vision for the product, a clear destination that the team is moving toward over time.

::: callout
## Designing a Board Game: The Solent Voyage

Imagine you have an idea to create a board game 'The Solent Voyage', about a ship that sailed from Southampton in Roman times.

The Product Goal is like your big vision:

“Create a complete, balanced, and fun strategy board game that 4 friends can play in under an hour.”

You may not know all the mechanics or artwork details yet, but you know what success looks like: something playable, sharable, and maybe even publishable.

The Product Backlog is your ever-evolving list of features and ideas:

-   Create player roles and abilities
-   Draft simple turn mechanics for the game
-   Design custom mechanics for each role's combat, trade, and movement
-   Write the a comprehensive rulebook
-   Decide win/lose conditions
-   Sketch a rough paper game board
-   Design custom artwork for the board
-   Print the game board onto high quality material
-   Create quick example cards
-   Design and print cards
-   Build a scoring system
-   Run a short 20-minute test with two players
-   Run a full test with four players
-   Gather feedback from players
-   Create custom miniatures for each character


Some items are critical (like the rules), others are stretch goals (like custom miniatures).
The backlog helps your team stay focused on building toward the big idea.
:::

## Sprint Backlog

The Sprint Backlog is the game plan for the current block of work and is created at the start of each Sprint, during the Sprint Planning Meeting.
It includes:

-   A Sprint Goal.
-   A subset of the items from the Product Backlog that will be worked on during this Sprint.
-   An actionable plan for delivering a working increment by the end of the Sprint.

The Sprint Backlog is owned and maintained by the Developers.
It is likely to evolve as the team learns more about the current work but should always stay grounded in the Sprint Goal.

### Commitment: Sprint Goal

The Sprint Goal is a single objective for the current Sprint and should be the primary focus of the Scrum Team.

::: callout
## The Start of the Solent Voyage

You’re not building the whole game at once - during the first Sprint, you’re aiming for a step towards the overall goal.

For example, your Sprint Goal might be: “Test the basic turn system with 2 players using paper placeholders.”

From this Sprint Goal you would create your Sprint Backlog, which would include all the tasks needed to achieve this goal.

If you completed all the items in the Sprint Backlog, you would still be far from achieving the Product Goal, but your Sprint Goal is a stepping stone in the right direction.
:::

:::: challenge
## Group Exercise: Sprint Backlog for the Sail Away

3 mins.

You have the Sprint Goal: “Test the basic turn system with 2 players using paper placeholders.”

Discuss in your group:

Which items would you select from the Product Backlog for this Sprint?

::: solution

Your Sprint Backlog might include:

-   Draft simple turn mechanics for the game
-   Create quick example cards
-   Sketch a rough paper game board
-   Decide win/lose conditions
-   Run a short 20-minute test with two players
-   Gather feedback from players

:::

::::

## Increment

The Increment is the result of the Scrum Team's work during the Sprint and is a working, usable part of the product that meets any quality criteria that have been agreed.

The Increment should be:

-   Integrated with the rest of the product
-   Tested 
-   Reviewed
-   Potentially releasable

The Increment includes the sum of all previous Increments and so it increases in value after every Sprint.

### Commitment: Definition of Done

The Definition of Done is a a formal description of the state that the Increment should be in to meet the quality measures required for the product.

You could think of the increment as being like a brick in a wall.
The Definition of Done would be a checklist to ensure that the brick is strong, stable, and usable in the wall.

::: callout
## The Maiden Voyage

At the end of the Sprint, your team has a working prototype.
The artwork might be rough and the game play might be unbalanced, but it can be played and evaluated.

That's your Increment: an overly simple and incomplete, but usable, version of the game that brings you closer to your Product Goal.

If the Increment meets the Definition of Done, it will become part of the growing, evolving game.

Next Sprint, you might improve the experience further, possibly by expanding the the map area for the game, balancing roles, or designing better cards.
:::

:::: challenge
## Group Exercise: Voyage Complete?

5 mins.

The Definition of Done is an important checklist of the quality standards that each Increment must meet.

Discuss and write down a possible Definition of Done for the Solent Voyage project?

::: solution

The Definition of Done in this case might be:

-   The rules are clear enough to play without additional explanation.
-   The components labelled and functional.
-   The test players complete a game.
-   Any bugs or confusing moments were documented.

:::

::::


# Scrum Team

The Scrum Team has a simple structure, with no sub-teams and no hierarchies, just one self-managing unit working toward a common goal.

A Scrum Team includes:

-   Developers (usually 3-9 people)
-   One Product Owner
-   One Scrum Master

::: callout
## Why no hierarchy?

Because Agile processes do best when teams make decisions and adapt quickly, without waiting for permission from higher-ups.
:::

## Developers

In a software development project, most developers will probably be software engineers, but developers could also be designers, testers, data analysts or any other role doing work to turn ideas into a working product.

-   They are **committed to quality**, and collectively responsible for delivering Done work.
-   They decide **how** to accomplish the Sprint Goal.
-   They collaborate, inspect, and adapt.

You could think of developers as the engine of the team.

![By Clerk, Dugald, Sir, 1854-1932. Library of Congress Catalog, Public Domain](fig/engine.jpg){alt='daigram of an old machine'}

## Product Owner

The Product Owner is responsible for maximising the value delivered by the Scrum Team.
The Product Owner is one single person, but they may represent a group of clients or other stakeholders.

-   Owns and manages the Product Backlog by ordering and refining it to ensure clarity for the rest of the Team
-   Represents the user perspective and works according to the business goals for the product.
-   Decides what gets built next but not how it gets built

You could think of the Product Owner as the compass, ensuring that the Scrum Team is always pointing toward the highest-value outcome.

![Image by freepik](fig/compass.jpg){alt='compass and map'}

## Scrum Master

The Scrum Master ensures that the Scrum framework is understood and carried out correctly.

-   A servant leader, not a manager or a taskmaster.

-   Helps the team to remove blockers, improve flow, and reflect on what has gone well and what could be improved.

-   Supports the Scrum Team in applying Scrum effectively.

You could think of the Scrum Master as a coach, empowering the Scrum Team to work as effectively as possible.

![Image by Creazilla, Creazilla Open License](fig/coach.png){alt='football coach'}

::: callout
## Roles Aren't Always Fixed

In practice, Scrum Team roles are often flexible. Each person doesn't necessarily only take one role. 

For instance:

-   The Scrum Master role might rotate between several developers.

-   One person could even take on all three roles for a solo project. 

Scrum defines the roles but teams can adapt them to fit their context.

:::

::: challenge
## Group Exercise: Getting in the Mindset of a Scrum Team Member

5 mins.

Pick one of the Scrum Team roles and discuss within your group:

-   What challenges might you face in the role?
-   What skills or mindset would you need to succeed in the role?

:::


## References

-   [Scrum Guide](https://scrumguides.org/scrum-guide.html)
-   [British Post Office Scandal Wikipedia](https://en.wikipedia.org/wiki/British_Post_Office_scandal)
-   [5 Reasons Leading to Scrum Team Ineffectiveness](https://www.scrum.org/resources/blog/5-reasons-leading-scrum-team-ineffectiveness)

::: keypoints
-   Scrum is an iterative, incremental, minimalist, and deliberately incomplete framework emphasizing empiricism and lean thinking.  
-   Scrum is built upon five core values: commitment, focus, openness, respect, and courage.  
-   Scrum relies on the three interconnected pillars of transparency, inspection, adaptation.  
-   A Scrum Team consists of Developers, a Product Owner, and a Scrum Master.  
-   Scrum makes use of three main artifacts which are the Product Backlog, Sprint Backlog, and Increment.
-   The Sprint Backlog includes a sprint goal, a subset of items from the Product Backlog selected for the current sprint, and an actionable plan for completing them. 
-   The Increment is the usable output from a sprint that must meet the Definition of Done, which is a checklist of quality standards for the Increment.  
-   Scrum roles and structures are defined but adaptable and teams should adjust them to fit their context.

:::
