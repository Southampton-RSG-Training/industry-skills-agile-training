---
title: "1.2 Software Development Process and the Landscape of Approaches"
teaching: 0
exercises: 0
---

:::::::::::::::::::::::: questions

- What are the main stages in a typical software development process?
- What are waterfall, iterative, and V-Model approaches to software development? 
- What is Agile and how does it compare to project management? 
- How does Scrum compare and relate to project management frameworks?

::::::::::::::::::::::::

:::::::::::::::::::::::: objectives

- Highlight the main stages in a software development process
- Demystify, compare and contrast agile approaches against project management
- Describe how Scrum compares and relates to project management frameworks [AgilePM, PRINCE2]
- Summarise the V-Model approach to software development
- Order and describe the stages within a typical software development process and how these apply within waterfall and iterative approaches

::::::::::::::::::::::::

## The Stages of a Typical Software Development Process

### Writing Code vs Engineering Software

Traditionally in academia, software - and the process of writing it -
is often seen as a necessary but throwaway artefact in research.
For example, there may be research questions for a given research project,
code is created to answer those questions,
the code is run over some data and analysed,
and finally a publication is written based on those results.
These steps are often taken informally.

The terms *programming* (or even *coding*) and *software engineering* are often used interchangeably.
They are not.
Programmers or coders tend to focus on one part of software development:
implementation, more than any other.
In academic research, often they are writing software for themselves,
where they are their own stakeholders.
And ideally, they write software from a design,
that fulfils a research goal to publish research papers.

Someone who is engineering software takes a wider view:

- The *lifecycle* of software: recognises that software development is a *process*
  that proceeds from understanding what is needed,
  to writing the software and using/releasing it,
  to what happens afterwards.
- Who will (or may) be involved: software is written for *stakeholders*.
  This may only be the researcher initially,
  but there is an understanding that others may become involved later
  (even if that is not evident yet).
  A good rule of thumb is to always assume that
  code will be read and used by others later on, which includes yourself!
- Software (or code) is an asset: software inherently contains value -
  for example, in terms of what it can do,
  the lessons learned throughout its development,
  and as an implementation of a research approach
  (i.e. a particular research algorithm, process, or technical approach).
- As an asset, it could be reused:
  again, it may not be evident initially that the software will have use
  beyond its initial purpose or project,
  but there is an assumption that the software - or even just a part of it -
  could be reused in the future.

### Software Development Process

The typical stages of a software development process can be categorised as follows:

- **Requirements gathering:**
  the process of identifying and recording the exact requirements for a software project
  before it begins.
  This helps maintain a clear direction throughout development,
  and sets clear targets for what the software needs to do.
- **Design:** where the requirements are translated into an overall design for the software.
  It covers what will be the basic software 'components' and how they will fit together,
  as well as the tools and technologies that will be used,
  which will together address the requirements identified in the first stage.
- **Implementation:** the software is developed according to the design,
  implementing the solution that meets the requirements
  set out in the requirements gathering stage.
- **Testing:** the software is tested with the intent to discover and rectify any defects,
  and also to ensure that the software meets its defined requirements,
  i.e. does it actually do what it should do reliably?
- **Deployment:** where the software is deployed or in some way released,
  and used for its intended purpose within its intended environment.
- **Maintenance:** where updates are made to the software to ensure it remains fit for purpose,
  which typically involves fixing any further discovered issues
  and evolving it to meet new or changing requirements.


Whether projects or people that develop software are aware of them or not,
these stages are followed implicitly or explicitly in every software project.
What is required for a project (during requirements gathering) is always considered, for example,
even if it is not explored sufficiently or well understood.

Following a **process** of development offers some major benefits:

- **Stage gating:** a quality *gate* at the end of each stage,
  where stakeholders review the stage's outcomes to decide
  if that stage has completed successfully before proceeding to the next one
  (and even if the next stage is not warranted at all -
  for example, it may be discovered during requirements of design
  that development of the software is not practical or even required).
- **Predictability:** each stage is given attention in a logical sequence;
  the next stage should not begin until prior stages have completed.
  Returning to a prior stage is possible and may be needed, but may prove expensive,
  particularly if an implementation has already been attempted.
  However, at least this is an explicit and planned action.
- **Transparency:** essentially, each stage generates output(s) into subsequent stages,
  which presents opportunities for them to be published
  as part of an open development process.
- **Time saving:** a well-known result from
  [empirical software engineering studies](https://web.archive.org/web/20160731150816/http://superwebdeveloper.com/2009/11/25/the-incredible-rate-of-diminishing-returns-of-fixing-software-bugs/)
  is that fixing software mistakes is exponentially more expensive in later software development
  stages.
  For example, if a mistake takes 1 hour to fix in the requirements stage,
  it may take 5 times that during design,
  and perhaps as much as 20 times that to fix if discovered during testing.

## Waterfall, Iterative, and V-Model Approaches to Software Development

### Waterfall

The Waterfall Model is a traditional software development methodology in which
the  typical stages of the software development process (that we outlined above) 
are followed step-by-step in a set, sequential order.  

The Waterfall Model can be effective when used for projects where the requirements
are clearly defined from the outset. It is ideal for projects with long timelines 
and minimal tolerance for errors, where stakeholders require high confidence in 
the final outcome.

However, there are some disadvantages to the Waterfall Model:

- The model is relatively inflexible.  Once a phase is completed, the model does
  not account for going back to make changes and therefore there is no mechanism
  for error correction.
- The model assumes that project requirements are fully defined from the beginning,
  which is rarely the case for real-world projects.
- The software is not seen by the client until late in the project timeline, 
  which increases the risk of it not meeting the client's expectations.


### V-Model

The V-Model is an extension of the traditional Software Development Life Cycle 
model, structured in the shape of a "V." It emphasises the importance of testing
and validation at each development stage, running parallel to the corresponding
development activity. This approach ensures that verification (checking work 
during development) and validation (checking final products against requirements)
are systematically integrated throughout the process.

The two sides of the "V" represent:

- Verification phases (requirements gathering, system design, architectural 
  design, module design, and coding) on the left side.
- Validation phases (unit testing, integration testing, system testing, and user
  acceptance testing) on the right side.

Verification Phases

- Business Requirement Analysis: Involves gathering and understanding customer 
  needs, with acceptance test planning beginning early.
- System Design: Outlines the overall architecture and structure based on the 
  requirements.
- Architectural Design: Focuses on high-level design, identifying how modules 
  interact internally and externally.
- Module Design (Low-Level Design): Specifies detailed designs for individual 
  modules, enabling early unit test preparation.
- Coding: Developers write code according to design standards, ensuring 
  performance and maintainability through code reviews.

Validation Phases

- Unit Testing: Verifies each module’s functionality individually, based on test
  plans from the module design phase.
- Integration Testing: Ensures that modules work together correctly, guided by 
  architectural design documentation.
- System Testing: Tests the entire system for functional and non-functional 
  requirements.
- User Acceptance Testing: Conducted in an environment resembling real-world 
  usage to confirm the software meets user needs.
  
Advantages

- Simple to understand and apply
- Focus on quality through early and continuous testing
- Strong links between requirements and final product improve traceability of software 
  changes.
- Clear structure makes it easier to track progress and communicate progress 
  with stakeholders.
  
Disadvantages

- Not flexible so struggles to deal with changing requirements.
- Time-consuming due to extensive documentation and testing.
- No support for development activities to occur concurrently or to iterate.

### Iterative

In practice, software development is rarely linear.  There are a number of 
reasons for this:

- You often find that a group has been building on the same project for years, 
  adding more complexity
- The research questions change
- The design of a key algorithm needs changing, leading to a need to change the 
  implementation
- A mistake is found during data analysis and a bug needs to be fixed 
- And what happens when a follow-on project crops up, perhaps some time later?
- How about other collaborators come on board an existing project?
- Someone wants to reproduce your results by running your software themselves?


Modern software engineering often favours iterative approaches, which allow for 
continuous feedback, adaptation, and improvement throughout the project's lifecycle.

Iterative Development is a software development approach where a large 
application is built in smaller, manageable parts called iterations. Each 
iteration includes planning, design, development, and testing, and produces a 
working version of the product. Unlike the Waterfall model, where the entire 
product is developed at once, iterative development adds features incrementally,
with each cycle enhancing the functionality of the product.

Advantages of Iterative Development:

- Early Defect Identification: Defects can be found and corrected early, 
  preventing them from affecting later stages.
- Continuous User Feedback: After each iteration, feedback can be gathered from 
  users, allowing for adjustments and improvements to meet their expectations.
- Reduced Documentation: Unlike Waterfall, which requires extensive 
  documentation, iterative development focuses more on design and functionality.

Disadvantages of Iterative Development:

- Rigid Phases: While the overall process is flexible, each iteration phase must
  be followed carefully.
- Unpredictable Changes: Since not all requirements are defined from the start, 
  unforeseen changes may arise during the development process.
  
Examples of iterative development approaches include Agile, Scrum, Kanban, and 
Extreme Programming. Agile, for instance, promotes working in short cycles 
called "sprints," where teams regularly reassess project goals and adapt to 
changes. Scrum provides a structured framework for iterative work, with defined 
roles, ceremonies, and deliverables. Kanban emphasizes visualising work, 
limiting work in progress, and continuously improving flow, making it ideal 
for projects with shifting priorities. Extreme Programming encourages 
frequent releases and rigorous testing to improve software quality and 
responsiveness to changing requirements.

Let's look more closely at Agile and Scrum because you will use these methods
for your project throughout this course. 

## Agile Software Development

### Differences Agile Compared to Project Management

### Scrum


## References

- Stages of Software Development from [Python Intermediate Development Carpentries Training](https://carpentries-incubator.github.io/python-intermediate-development/30-section3-intro.html)
- Waterfall Method ideas from [geeksforgeeks](https://www.geeksforgeeks.org/waterfall-model/)
- V-Model ideas from [geeksforgeeks](https://www.geeksforgeeks.org/software-engineering-sdlc-v-model/)
- Iterative from [SABS slides](https://docs.google.com/presentation/d/1xR3CVxMSiUsbMMwoLwBeI85w9dxpIgX7-gEO7MTWUkQ/edit?slide=id.g63043845db_0_149#slide=id.g63043845db_0_149)
- Iterative ideas from from [Eastern Peak](https://easternpeak.com/definition/iterative-development/#:~:text=Iterative%20development%20is%20a%20software,%2C%20development%2C%20and%20testing%20steps.)

:::::::::::::::::::::::: keypoints

- FIXME

::::::::::::::::::::::::


