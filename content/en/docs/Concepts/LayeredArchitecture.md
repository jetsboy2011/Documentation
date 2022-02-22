---
title: "Layered Architecture"
linkTitle: "Layered Architecture"
weight: 20
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

RoverCore is organized as an Tiered Architecture but in many of the above architectures there is a clear separation of what each layer is responsible for. The project itself is organized into three layers with distinct responsibilities and is intended to help you begin the process of understanding how to work with multi-project web applications. As you grow in your understanding of ASP.NET you may decide to add additional layers as your project grows in scope.  You may also make stricter decisions on how to isolate the responsibilities of each layer.  For example, you may decide to avoid making any direct calls to Entity Framework code in the Infrastructure layer from the Web layer in the chance that you want to swap out EF for something else.  For now, these layers can make it easier to reuse your code, as one layer may share much of the code you might reuse in an entirely different project.

<img src="/docs/concepts/layeredarchitecture.svg" width="600"/>

The organization for RoverCore consists of three tiers (or layers):
- Presentation
- Infrastructure
- Core

As you see with the above diagram, the arrows always point inward towards the core. This is because each layer depends on an inner layer to function. The Core layer is intended to be as free of dependencies as possible as it is typical that all projects will depend on the Core layer.


### Presentation Layer

The presentation layer is closest to the end user, and contains the actual user interface they have to interact with your application.  Whether the interface is html-based, an API, or even a mobile app, there are a myriad of ways that your data can be presented to the user.  

Ideally you would not place a lot of the business logic (decisions about what happens to data when it is stored or outputted) in this layer, but as a beginner it may be easier for you to begin your journey placing these coding decisions in your controllers.  As you progress you may decide to push business logic to another layer entirely. 

Presentation Layer types
- Controllers
- Custom Filters
- Custom Middleware
- Views
- ViewModels
- Startup

### Infrastructure Layer

The Infrastructure project typically includes data access implementations. In a typical ASP.NET Core web application, these implementations include the Entity Framework (EF) DbContext, any EF Core Migration objects that have been defined, and data access implementation classes. The most common way to abstract data access implementation code is through the use of the [Repository design pattern](https://deviq.com/design-patterns/repository-pattern).

The Infrastructure layer contains supporting services for the Presentation layer. This includes services such as:

- Database
- Cache
- Logging
- Email
- Templates
- Configuration

In many of the above architectures you would typically create services that provide a way to manipulate the data entities stored in the database in the Infrastructure layer.  The business logic itself would typically be put into a fourth project (typically named Application) and these data manipulation services would be injected into any Application layer service that might need it through dependency injection.

For this project, you can decide what you want to do.  The beginning approach would be to simply add any supporting services your application needs inside the Infrastructure project.  The services you create in Infrastructure can then be used in any controller in the web project that you want.

### Core Layer

The core layer includes projects (like Domain) that have no dependencies on the other application layers.  The core holds entities, services, and interfaces. These interfaces include abstractions for operations that will be performed using Infrastructure, such as data access, file system access, network calls, etc. Sometimes services or interfaces defined at this layer will need to work with non-entity types that have no dependencies on UI or Infrastructure. These can be defined as simple Data Transfer Objects (DTOs). 

Application Core types
- Entities (business model classes that are persisted)
- Aggregates (groups of entities)
- Interfaces
- Domain Services
- Specifications
- Custom Exceptions and Guard Clauses
- Domain Events and Handlers

## References

> The preceding text contains excerpts that are creative-commons licensed from Microsoft.  The full article can be found [here](https://docs.microsoft.com/en-us/dotnet/architecture/modern-web-apps-azure/common-web-application-architectures).

## More Reading
a
[Common Web Application Architectures](https://docs.microsoft.com/en-us/dotnet/architecture/modern-web-apps-azure/common-web-application-architectures)