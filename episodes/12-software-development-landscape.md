---
title: "1.2 Software Development Process and the Landscape of Approaches"
teaching: 0
exercises: 0
---

::: questions
-   What are the main stages in a typical software development process?
-   What are waterfall, iterative, and V-Model approaches to software development?
-   What is Agile and how does it compare to project management?
-   How does Scrum compare and relate to project management frameworks?
:::

::: objectives
-   Highlight the main stages in a software development process
-   Demystify, compare and contrast agile approaches against project management
-   Describe how Scrum compares and relates to project management frameworks [AgilePM, PRINCE2]
-   Summarise the V-Model approach to software development
-   Order and describe the stages within a typical software development process and how these apply within waterfall and iterative approaches
:::

## The Stages of a Typical Software Development Process

### Writing Code vs Engineering Software

Traditionally in academia, software and the process of writing it is often seen as a necessary but throwaway artefact in research.
For example, there may be research questions for a given research project, code is created to answer those questions, the code is run over some data and analysed, and finally a publication is written based on those results.
These steps are often taken informally.

The terms *programming* (or even *coding*) and *software engineering* are often used interchangeably.
They are not.
Programmers or coders tend to focus on one part of software development: implementation, more than any other.
In academic research, often they are writing software for themselves, where they are their own stakeholders.
And ideally, they write software from a design that fulfills a research goal to publish research papers.

Someone who is engineering software takes a wider view:

-   The *lifecycle* of software: recognises that software development is a *process* that proceeds from understanding what is needed, to writing the software and using/releasing it, to what happens afterwards.
-   Who will (or may) be involved: software is written for *stakeholders*. This may only be the researcher initially, but there is an understanding that others may become involved later (even if that is not evident yet). A good rule of thumb is to always assume that code will be read and used by others later on, which includes yourself!
-   Software (or code) is an asset: software inherently contains value - for example, in terms of what it can do, the lessons learned throughout its development, and as an implementation of a research approach (i.e. a particular research algorithm, process, or technical approach).
-   As an asset, it could be reused: again, it may not be evident initially that the software will have use beyond its initial purpose or project, but there is an assumption that the software - or even just a part of it - could be reused in the future.

### Software Development Process

The typical stages of a software development process are:

-   **Requirements gathering:** the process of identifying and recording the exact requirements for a software project before it begins. This helps maintain a clear direction throughout development, and sets clear targets for what the software needs to do.
-   **Design:** where the requirements are translated into an overall design for the software. It covers what will be the basic software 'components' and how they will fit together, as well as the tools and technologies that will be used, which will together address the requirements identified in the first stage.
-   **Implementation:** the software is developed according to the design, implementing the solution that meets the requirements set out in the requirements gathering stage.
-   **Testing:** the software is tested with the intent to discover and rectify any defects, and also to ensure that the software meets its defined requirements, i.e. does it actually do what it should do reliably?
-   **Deployment:** where the software is deployed or in some way released, and used for its intended purpose within its intended environment.
-   **Maintenance:** where updates are made to the software to ensure it remains fit for purpose, which typically involves fixing any further discovered issues and evolving it to meet new or changing requirements.

These stages are followed implicitly or explicitly in every software project but there are many different ways to arrange them.
The order in which these stages are arranged depends on factors including the scale, use case, and criticality of the software project.
The stages may be arranged according to an established model of software development such as the Waterfall Model, V-Model, or an iterative approach such as Agile.

## Waterfall, V-Model and Iterative Models of Software Development

### Waterfall

The Waterfall Model is a software development methodology in which the typical stages of the software development process (that we outlined above) are followed step-by-step in a set, sequential order.

The Waterfall Model is effective when used for projects where the requirements are clearly defined from the outset.
It is ideal for projects with long timelines and minimal tolerance for errors, where stakeholders require high confidence in the final outcome.
For example, software for military applications may use the Waterfall Model as it is likely to be meticulously planned, analysed and tested.

However, there are some disadvantages to the Waterfall Model:

-   The model is relatively inflexible. Once a phase is completed, the model does not account for going back to make changes and therefore there is no mechanism for error correction.
-   The model assumes that project requirements are fully defined from the beginning, which is rarely the case for smaller, non-critical software projects, particularly in research.
-   The software is not seen by the client until late in the project timeline, which may increase the risk of it not meeting the client's expectations.

### V-Model

The V-Model emphasises the importance of testing and validation at each development stage, running parallel to the corresponding development activity.
This approach ensures that verification (checking work during development) and validation (checking final products against requirements) are systematically integrated throughout the process.

The two sides of the "V" represent:

-   Verification phases (requirements gathering, system design, architectural design, module design, and coding) on the left side.
-   Validation phases (unit testing, integration testing, system testing, and user acceptance testing) on the right side.

Due to the emphasis on verification and validation, the V-Model is often used for mission-critical software in fields such as medical imaging and railway signalling.

Advantages

-   Focus on quality through early and continuous testing
-   The strong link between requirements and the final product improve the traceability of software changes.

Disadvantages

-   Not flexible so struggles to deal with changing requirements

-   Time-consuming due to extensive documentation and testing.

-   No support for development activities to occur concurrently or to iterate.

### Iterative

Sometimes it doesn't make sense for software development to follow a linear process such as the Waterfall or V model for a number of reasons:

-   A group may build on the same project for years, adding more complexity
-   The research questions change
-   The design of a key algorithm needs changing, leading to a need to change the implementation
-   A mistake is found during data analysis and a bug needs to be fixed
-   And what happens when a follow-on project crops up, perhaps some time later?
-   How about other collaborators come on board an existing project?

In iterative development, a large application is built in smaller, manageable parts called iterations.
Each iteration includes planning, design, development, and testing, and produces a working version of the product.
Unlike the Waterfall and V models, where the entire product is developed at once, iterative development adds features incrementally, with each cycle enhancing the functionality of the product.

Advantages of Iterative Development:

-   Progress on the software product can initially be faster as less time is spent on the requirements and design stages before starting implementation
-   Iterative approaches allow for continuous feedback, adaptation, and improvement throughout the project's lifecycle.
-   Defects can be found and corrected early, preventing them from affecting later stages.
-   After each iteration, feedback can be gathered from users, allowing for adjustments and improvements to meet their expectations.

Disadvantages of Iterative Development:

-   Without fully determined requirements and design, software can become messy or 'hacky'
-   Since not all requirements are defined from the start, unforeseen changes may arise during the development process which require revision of the software architecture.

Iterative approaches allow for rapid software development, though often with less emphasis on strict quality control or formal assurance processes.
For this reason, they are typically used in the development of non-critical systems, where flexibility and speed are more important than absolute reliability.
Iterative methods are also widely used in prototyping, where quick development and user feedback help shape early versions of a system, and in research software, where evolving requirements and experimental objectives demand adaptability.
Agile is one well-known example of an iterative methodology.
In this course, we will focus on Agile, as it will form the foundation for the processes used in the team project.

## Agile Software Development

### Differences Agile Compared to Project Management

### Scrum

## References

-   Stages of Software Development from [Python Intermediate Development Carpentries Training](https://carpentries-incubator.github.io/python-intermediate-development/30-section3-intro.html)
-   Waterfall Method ideas from [geeksforgeeks](https://www.geeksforgeeks.org/waterfall-model/)
-   V-Model ideas from [geeksforgeeks](https://www.geeksforgeeks.org/software-engineering-sdlc-v-model/)
-   Iterative from [SABS slides](https://docs.google.com/presentation/d/1xR3CVxMSiUsbMMwoLwBeI85w9dxpIgX7-gEO7MTWUkQ/edit?slide=id.g63043845db_0_149#slide=id.g63043845db_0_149)
-   Iterative ideas from from [Eastern Peak](https://easternpeak.com/definition/iterative-development/#:~:text=Iterative%20development%20is%20a%20software,%2C%20development%2C%20and%20testing%20steps.)

::: keypoints
-   FIXME
:::
