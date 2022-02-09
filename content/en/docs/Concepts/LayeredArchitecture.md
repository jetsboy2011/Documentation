---
title: "Layered Architecture"
linkTitle: "Layered Architecture"
weight: 2
description: >
  Layered Architectures break a codebase up into areas according to responsibilities or concerns.
---

## What is a layered architecture?

As your projects become larger it becomes helpful to break the project into parts based on responsibilities or concerns.  This idea of separating pieces of your project from one another makes it ultimately easier to test your software and ensure that it is working as you would expect.  Just like you wouldn’t want to write overly lengthy methods for that very same reason, we want to avoid single projects that take on too much responsibility for the workload of the application. This separation involves splitting the codebase into multiple projects which we will refer to as *layers*.

There are a number of advantages to using layers:
- Easier to work with in teams as individuals can focus on distinct layers
- Simplifies the process of understanding a codebase as each layer is isolated from each other and classes are typically grouped together by responsibility
- Testing is easier

There are also disadvantages, but for now we will focus on the rationale behind this framework.

## Tiered Architecture

If you do enough searching you’ll quickly come across a number of ideas on how large software projects should be organized.  Some of the most common approaches to software architecture for ASP.NET projects include:

- Tiered Architecture
- Onion Architecture
- Hexagonal Architecture
- Clean Architecture
- Vertical Slice Architecture

RoverCore is organized as an Tiered Architecture and borrows ideas from Clean Architecture. The project itself is organized into three layers with distinct responsibilities. However, as you grow in your understanding of ASP.NET you may decide to add additional layers as your project grows in scope.  These layers can also at times make it easier to reuse your code, as one layer may share much of the code you might reuse in an entirely different project.

<img src="/docs/concepts/layeredarchitecture.svg" width="600"/>

The organization for RoverCore consists of three tiers (or layers):
- Presentation
- Infrastructure
- Core

As you see with the above diagram, the arrows always point inward towards the core. This is because each layer depends on an inner layer to function. The Core layer is intended to be as free of dependencies as possible as it is typical that all projects will depend on the Core layer.


### Presentation Layer

### Infrastructure Layer

### Core Layer



## More Reading

[Common Web Application Architectures](https://docs.microsoft.com/en-us/dotnet/architecture/modern-web-apps-azure/common-web-application-architectures)