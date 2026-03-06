---
title: "4.1 Prepare Code for Release"
teaching: 0
exercises: 0
---

:::::::::::::::::::::::::::::::::::::: questions 

- What preparation should be considered prior to releasing software?
- How should I document my code?
- What tools help teams write and generate documentation?
- Why is licensing software important?
- How do I apply a software licence to code?
- What is the typical process to create a release on GitHub?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Describe the different levels of software reusability
- Construct a README file which contains all necessary elements
- Describe the main types of software documentation
- Implement basic project documentation using a documentation generator such as mkdocs
- Explain why adding licensing information to a repository is important
- Outline your rights and obligations under common types of license (e.g. the GPL, MIT, BSD, Apache 2 and Creative Commons licenses)
- Apply an appropriate license to a code repository that is shared on Github
- Understand how to create a release on GitHub

::::::::::::::::::::::::::::::::::::::::::::::::

In previous episodes we have looked at skills, practices, and tools to help us
design and develop software in a collaborative environment.
In this lesson we will be looking at
two critical pieces of the development puzzle that builds on what we have learnt so far -
reuse and sharing our software with others.

## What do we Mean by Reusability?

FIXME: consider just removing in favour of the next section

In industrial software development software reuse is a deliberate strategy for improving productivity,
quality, and delivery speed, by building on existing assets instead of developing everything from scratch.
Reuse can occur at multiple levels,
from individual code snippets and libraries to entire frameworks and system architectures.

:::::::::::::::::::::::::::::::::::::::  challenge

## Class Exercise: Why Reuse?

5 mins.

What are the benefits of reusable software?

:::::::::::::::  solution

- Increases productivity by using pre-built components, instead of "reinventing the wheel"
- Reduces development and maintenance costs, since despite a higher cost of incorporating reusability, this is paid off over time by minimising total effort required across projects that inherit that code
- Improves software quality and reliability, since reusing proven, tested components reduces introduction of new bugs
- Improves consistency across projects, by standardising development practices
- Faster onboarding and knowledge transfer, where common components and architectural patterns reduces subsequent ramping-up time across projects
- Increases scalability performance, since reusable components are often designed to be modular as opposed to monolithic, reducing effort required to scale applications

:::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::::

### What do we Want from Reuse?

Firstly, whilst we want to ensure our software is reusable by others, as well as ourselves,
we should be clear what we mean by 'reusable'.
There are a number of definitions out there,
but a helpful one written by [Benureau and Rougler in 2017](https://dx.doi.org/10.3389/fninf.2017.00069)
offers the following levels by which software can be characterised:

1. **Re-runnable** - the code is simply executable
  and can be run again (but there are no guarantees beyond that)
2. **Repeatable** - the software will produce the same result or behaviour more than once
3. **Reproducible** - results or behaviour generated from the same version of the software
  can be generated consistently given the same inputs
4. **Reusable** - easy to use, understand, maintain, and modify for others, as well as incorporate (as a whole or in part) into other development ventures

Later levels imply the earlier ones.

As developers we should always aim for reusable software.
It is crucial that we can write software that can be *understood*
and ideally *modified* by others within our team and elsewhere.
Where 'others', of course, can include a future version of ourselves.

### Levels of Software Reuse

Here are some example levels of software development reuse in industry:

1. **Code-level Reuse** - functions and small-scoped utility libraries, classes and objects
1. **Component-level Reuse** - larger self-contained software modules, packages, API, or microservices that provide specific functionality and have well-defined interfaces
1. **Design and Architectural-Level Reuse** - reuse of design patterns, frameworks, and architectural styles, or set of platform components conforming to an architecture
1. **System-level Reuse** - entire system or application used with other similar systems or components to create a new, larger system
1. **Document and Knowledge Reuse** - beyond code and design, the reuse of technical documentation, manuals (or their structural design or technical underpinning), and test plans or test scripts from similar projects

FIXME: add class thinking exercise

## The Need for Documentation

A cornerstone of software reusability is documentation.
Software development in industry typically adopts a longer-term, sustainable view of software that is produced.
Unlike small personal projects, industrial software is usually developed by teams over long periods of time,
often with developers joining and leaving the project.

Documentation thus ensures that knowledge about a given system is preserved and accessible,
and the extent to which that system is reusable is closely tied to its supporting documentation.
In many cases, beyond trivial software outputs, reusability is critically dependent on documentation since it's the main enabler for developers to find, understand, trust, and modify software components.

Good documentation:

- **Reduces development time** - when requirements, interfaces and behaviour are clearly documented
- **Reduces maintenance costs** - since clear documentation helps developers understand it to maintain, debug and extend the system without requiring the original authors
- **Improves quality and reliability** - because documentation of testing procedures, requirements, and design decisions helps ensure system continues to behave as expected
- **Increases knowledge transfer** - explaining how the system works in terms of its architecture, design decisions, and codebase
- **Improved compliance governance** - with some industries requiring documentation for regulatory or auditing purposes
- **Improved user support** - with user guides and manuals supporting the correct use of software by customers

Documentation therefore acts as a collective memory for the software being developed,
and you may notice the stroing overlap with the benefits of reusability,
and is therefore intrinsically tied to it.
It is difficult to have truly reusable software without documentation.
As a developer you will very likely find yourself involved in both sides of this reuse,
either as a producer, generating software to be reused,
or as a consumer, reusing software developed by others.

A golden rule of software development is to *always assume that someone else may need to both understand and run the software you have written*, which includes a future version of yourself.

### Types of Documentation

Software documentation can be grouped into several broad categories, each serving a different audience.

:::::::::::::::::::::::::::::::::::::::  challenge

## Class Exercise: Types of Documentation

2 mins.

What different types of software documentation have you generated or used from other software?

::::::::::::::::::::::::::::::::::::::::::::::::::

At a lower level, there is also **code commenting**,
a very useful form of documentation for understanding our code is code commenting,
and is most effective when used to explain complex interfaces or behaviour,
or the reasoning behind why something is coded a certain way.
But code comments only go so far.

Broadly speaking, supporting documentation tends to fall into:

- **Product documentation**, describing the the software as a whole, including it's purpose and aims, and key functionality
- **Requirements documentation**, such as a Software Requirements Specification (SRS) or user stories
- **Technical documentation**, such as architectural diagrams, technical specifications that support development, testing, and deployment, technical how-to guides, and documentation of APIs and database schemas
- **User documentation**, which describes how to use the functionality of the software for users
- **Process & project documentation**, which covers *how* the software is developed, e.g. the development workflow (for example, Git branching strategy), issue tracking and backlog documentation, continuous integration procedures, test plans, and release notes

:::::::::::::::::::::::::::::::::::::::::  callout

## Scrum and Documentation

From an agile Scrum perspective, documentation should be **minimalist** and **purposeful**.
Documentation should only be created and maintained that continues to add value,
and should be living documents that evolve with the product.
Essentially, create documentation when it is needed, as opposed to creating it initially all at once,
and documentation tasks (creation or amendment) should be included in the definition of done and completed within that given sprint cycle.
This helps avoid technical debt accruing over time, which applies equally to documentation as it does to the software itself.

::::::::::::::::::::::::::::::::::::::::::::::::::

## Code Commenting

FIXME: add something on docstrings

## Writing a Project README

A repository README file is the first piece of documentation that people should read to acquaint themselves with the software.
It concisely explains what the software is about and what it is for,
and covers the steps necessary to obtain and install the software
and use it to accomplish basic tasks.

In short, it provides enough information across the documentation areas we looked at earlier for people to get started.
Think of it not as a comprehensive reference of all functionality,
but more a short tutorial with links to further information -
hence it should contain brief explanations and be focused on instructional steps.

Repository README files are typically written in Markdown format.
a lightweight markup language which is basically a text file with
some additional basic syntax to provide ways of formatting them.
A big advantage of them is that they can be read as plain-text files
or as source files for rendering them with formatting structures,
and are very quick to write.
GitHub provides a very useful [guide to writing Markdown][https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax] for its repositories.

Our repository already has a `README.md` file with a number of example headings:

```markdown
# coffee-analysis

## Description

## Pre-requisites

## Installation

## Usage

## Running Tests

## Maintainers

## Licence

## Authors

## Acknowledgements
```

FIXME: add The Software Sustainability Institute’s [guide on naming projects and products](https://www.software.ac.uk/guide/choosing-project-and-product-names) may provide some helpful pointers.

## Adding Supporting Technical Documentation

## Licensing

FIXME: licensing w.r.t. types of licences, reusing external software, compatibility, and industrial practices

## Creating a Release

FIXME: create a release on GitHub

:::::::::::::::::::::::::::::::::::::: keypoints

- FIXME

::::::::::::::::::::::::::::::::::::::::::::::::