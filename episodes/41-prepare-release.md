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
- Describe the main types of software documentation (tutorials, how to guides, reference and explanation)
- Implement basic project documentation using a documentation generator such as mkdocs
- Explain why adding licensing information to a repository is important
- Outline your rights and obligations under common types of license (e.g. the GPL, MIT, BSD, Apache 2 and Creative Commons licenses)
- Apply an appropriate license to a code repository that is shared on Github
- Understand how to create a release on GitHub

::::::::::::::::::::::::::::::::::::::::::::::::

## Introduction

In previous episodes we have looked at skills, practices, and tools to help us
design and develop software in a collaborative environment.
In this lesson we will be looking at
two critical pieces of the development puzzle that builds on what we have learnt so far -
reuse and sharing our software with others.

## What do we Mean by Reusability?

FIXME: consider just removing in favour of the next section

In industrial software development software reuse is a deliberate strategy for improving productivity,
quality, and delivery speed by building on existing assets instead of developing everything from scratch.
Reuse can occur at multiple levels,
from individual code snippets and libraries to entire frameworks and system architectures.

### What do we Want from Reuse?

Firstly, whilst we want to ensure our software is reusable by others, as well as ourselves,
we should be clear what we mean by 'reusable'.
There are a number of definitions out there,
but a helpful one written by [Benureau and Rougler in 2017](https://dx.doi.org/10.3389/fninf.2017.00069)
offers the following levels by which software can be characterised:

1. *Re-runnable* - the code is simply executable
  and can be run again (but there are no guarantees beyond that)
2. *Repeatable* - the software will produce the same result or behaviour more than once
3. *Reproducible* - results or behaviour generated from the same version of the software
  can be generated consistently given the same inputs
4. *Reusable* - easy to use, understand, maintain, and modify for others, as well as incorporate (as a whole or in part) into other development ventures

Later levels imply the earlier ones.

As developers who write software, we should always aim for reusability.
It is crucial that we can write software that can be *understood*
and ideally *modified* by others within our team.
Where 'others', of course, can include a future version of ourselves.

### Levels of Software Reuse

Here are some example levels of software development reuse in industry:

1. *Code-level Reuse* - functions and small-scoped utility libraries, classes and objects
1. *Component-level Reuse* - larger self-contained software modules, packages, API, or microservices that provide specific functionality and have well-defined interfaces
1. *Design and Architectural-Level Reuse* - reuse of design patterns, frameworks, and architectural styles, or set of platform components conforming to an architecture
1. *System-level Reuse* - entire system or application used with other similar systems or components to create a new, larger system
1. *Document and Knowledge Reuse* - beyond code and design, the reuse of technical documentation, manuals (or their structural design or technical underpinning), and test plans or test scripts from similar projects



:::::::::::::::::::::::::::::::::::::: keypoints

- FIXME

::::::::::::::::::::::::::::::::::::::::::::::::