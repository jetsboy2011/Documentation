---
categories: ["Getting Started", "Setup"]
tags: ["setup","installation","docs"] 
title: "Getting Started"
linkTitle: "Getting Started"
weight: 3
description: >
  Here's what you need to know to get up and running quickly with your own project.
---

## Prerequisites
- [Visual Studio 2022](https://visualstudio.microsoft.com/vs/) with ASP.NET and web development workload
- [Latest .NET 6 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/6.0)
-   Install the latest [.NET & EF CLI Tools](https://docs.microsoft.com/en-us/ef/core/cli/dotnet) by using this command :

    ```.NET Core CLI
    dotnet tool install --global dotnet-ef
    ```
- Git Client 
  - [GitHub Desktop](https://desktop.github.com/)
  - [Axosoft's GitKraken](https://www.gitkraken.com/)
  - [Tower](https://www.git-tower.com/)

## Installation

Get the newest RoverCore template on [nuget.org](https://www.nuget.org/packages/RoverCore.Template/).

```
dotnet new --install RoverCore.Template
```

## Setup

To create a new project create a directory and open a command line console (cmd).  Change the directory to your working folder with the following command (assuming your working folder is c:\users\\**_username_**\\documents\\)

```
cd c:\users\username\documents\
```

Then to create your project, type in the following command to generate a brand new solution with a name of your choosing.  For this example I am using the name **RoverDemo**.

```
dotnet new rovercore -o RoverDemo
```

Give it a few moments. A new folder called RoverDemo will be created for you at `c:\users\username\documents\roverdemo\`

## Try it out!

The RoverDemo folder that was created will have all of the files and folders you will need to run your own starter project.

Here's what you need to get your project running:
- Open the Solution in Visual Studio 2022
- Initialize the SQL Server Express LocalDB
  - In Visual Studio, go to `View > Other Windows > Package Manager Console`
  - Set the default project in the Package Manager Console to the Infrastructure project
  - In the console that appears at the bottom, type the command `Update-Database` and wait for the migration to finish.
- Run the project
  - Press `Control + F5` to run the project without the debugger, or `F5` to run the project with the debugger attached.
- Seed Data
  - When running the project for the first time, the database will be seeded with an admin user.
  - You can log in to this account with the username `admin` and the password `Password123!`. It is _highly_ recommended that you change this password after logging in for the first time.


