---
title: "4.2 Sprint 2 Planning Meeting"
teaching: 0
exercises: 0
---

:::::::::::::::::::::::::::::::::::::: questions 

- What methods exist to help a team reach a consensus on estimates?
- What is planning (or Scrum) poker?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Apply a group planning poker technique for estimating the size of each task
- Devise a sprint backlog for sprint 2 from the updated product backlog

::::::::::::::::::::::::::::::::::::::::::::::::

## Improving Estimation through Structured Consensus

We've looked at t-shirt estimation as a quick technique for estimating task effort,
particularly early in the planning cycles.
However, for projects with more complex requirements a more structured approach that is based on team consensus can prove more effective.

Scrum (or planning) poker is a method for estimation that helps a Scrum team arrive at a consensus of effort (or complexity) for a given user story or requirement.
In Scrum estimation sessions, each team member has a deck of cards containing story point values (often based on the Fibonacci sequence).
When estimating a user story or requirement, everyone selects a card privately and reveals it at the same time, similar to players revealing cards in poker.

Usually moderated by the Product Owner or Scrum Master, it has a number of benefits:

- It helps make the activity interactive and engaging
- Encourages team discussion, as differences in estimation prompt useful conversations about the work
- The simultaneous reveal prevents people from being influenced by others’ estimates, encouraging more independent and honest assessments
- Increases shared understanding of the backlog and reduces assumptions, since the team collectively clarifies the requirements, as well as their complexity and risks
- Improves estimation accuracy, since multiple perspectives often lead to more realism in estimates

This approach typically occurs before Sprint Planning,
but also proves useful whenever team consensus on an estimate is required.

The team needs to agree on what each story point card value means,
and serves as a baseline for estimation meetings.
For the purposes of this training and the time constraints of the next sprint, let's use the following *story point matrix*,
which uses scaled down time effort estimates for each card:

| Story Points | Relative Size | Typical Effort | Characteristics / Example |
|---------------|---------------|----------------|---------------------------|
| 1/2 | Extremely Small | < 2 mins | Minor change, small bug fix, simple configuration update |
| 1 | Very Small | < 5 mins | Minor change, small bug fix, simple configuration update |
| 2 | Small | 10 mins | Small code change, minor enhancement, simple UI adjustment |
| 3 | Small–Medium | 15 mins | Straightforward feature with minimal complexity |
| 5 | Medium | 25 mins | Feature requiring multiple steps or moderate logic |
| 8 | Medium–Large | 40 mins | More complex feature with dependencies or testing required |
| 13 | Large | 65 mins | Complex functionality with multiple components |
| 20 | Very Large | > 100 mins | Major feature; often a candidate to break into smaller stories |
| 40+ | Too Large | Too big to estimate | Should be split into smaller user stories before sprint planning |

The process works as follows:

**Setup:** All team members are given an identical set of cards containing the values: 0, 1/2, 1, 2, 3, 5, 8, 13, 20, 40, and 100.
These are typically aligned with the Fibonacci sequence.
They often portray abstract "story points" as an approximation of the complexity of a given task,
although some teams use them as direct time estimates for how long that task takes to complete.

1. The Product Owner/Scrum Master briefly explains a user story or requirement from the backlog.

1. The development team asks questions to ensure everyone understands its scope and gets an accurate sense of the work that needs to be done to complete that specific item.

1. Each team member chooses an estimate privately, selecting one of their cards.

1. Everyone reveals their estimates simultaneously, to prevent anchoring or influence from others.

1. If there is consensus and everyone reveals the same estimate, that becomes the official estimate for that backlog item and is recorded.

1. If there are differing opinions about these initial estimates, the team members with the highest and lowest estimates take some time to discuss why they those that specific number.
Following this, everyone reselects their cards, and the process repeats until the team reaches a reasonable consensus.

This process continues until all backlog items have been estimated.

::: challenge

## Group Exercise: Play Scrum Poker

20 mins.

Conduct a planning poker exercise in your team.

Instead of using physical cards, use the free [Firepoker](https://firepoker.app/#/) online tool:

1. Either the Product Owner or Scrum Master role assumes the role of moderator
1. The Moderator:
   - Creates a new game by selecting `Play now`, adding in some game details and selecting `Create game`
   - Copies the browser URL from the next page into the shared document so the other team members can access it in their own browser
   - Selects the `Free-form` tab on the page, and copies in the requirement issue number and title from the backlog, and selects `Add story`
1. Everyone in the team (including the Moderator) vote by selecting their estimate from the cards.
1. Once everyone has voted, everyone's selections are automatically revealed to all
1. If there isn't total consensus, discuss the lowest and highest estimates from those that suggested them, and repeat the voting until a consensus is reached. he Moderator ensures that discussions are kept brief so the exercise finishes within the allotted time
1. The Moderator enters the consensus value into the backlog item issue on GitHub as a comment

Continue the exercise until all backlog items have been estimated.

NB: don't press `Back` on your browser, since it will terminate the poker voting session and you'll need to reopen it from the link!

:::

::: challenge

## Group Exercise: Sprint 2 Planning for Coffee Beans Analysis

20 mins.

Conduct the Sprint Planning Meeting for Sprint 2 of the Coffee Beans Analysis Project.

**Roles**

-   One person should be Scrum Master.  You are the servant leader who helps the group apply Scrum effectively, removes blockers and improves flow for the Scrum Team.
-   One person should role play as the Product Owner.  You should represent the interests of the client throughout the meeting.
-   The rest of the group should be developers.  **The Scrum Master and acting Product Owner can also be developers.**

**Questions for Sprint Planning**

Remember to answer the following questions during the Sprint Planning Meeting:

-   Why is this Sprint valuable?
-   What can be Done this Sprint?
-   How will the chosen work get Done?

The output from your Sprint Planning Meeting should be your Sprint 2 Backlog including:

-   A Sprint Goal
-   The subset of items from the Product Backlog that you will work on this Sprint
-   A plan for delivering the Increment by the end of the Sprint

:::

:::::::::::::::::::::::::::::::::::::: keypoints

- Planning Poker makes estimation sessions interactive and encourages active team participation.
- Simultaneous estimation reduces bias and helps clarify requirements, complexity, and risks.
- Collaborative discussion improves shared understanding of the backlog and leads to more realistic estimates.

::::::::::::::::::::::::::::::::::::::::::::::::