
---
title: "Project Structure"
linkTitle: "Project Structure"
weight: 10
date: 2017-01-05
description: >
  The default boilerplate structure is organized into several projects.
---

<div class="row">
<div class="col">
<img src="/docs/fundamentals/structure.png">
</div>
</div>

## Domain
The domain project is a core dependency that all of your other projects will likely depend on. For the time being, you will use this project to store any Entity Framework entities you intend on using.  You can also store Data Transfer Objects (DTOs) and any other abstractions (typically interfaces) that might be useful across your solution.

## Infrastructure

Each folder has roughly the following structure:
```
+- Feature Name
  +- Extensions
  +- Models (any data models needed by the feature)
  +- Seeding (holds any ISeeder classes in case this feature needs data to be seeded)
  +- Services
  Startup.cs (holds all the startup services and application configuration logic just for this feature)
```

The most common services you will need (email, Hangfire, seeder, templates, etc) are in the Common folder.  The remaining folders (Authentication, Identity, Persistence, etc) are all largely organized exactly the same as any folder in Common.

The end goal is to try to keep as much of the code and supporting code that makes up one of these feature services in a single location. 

### Startup

The Startup.cs should look familiar.  Here is an example for Identity:

```csharp
public static class Startup
{
	/// <summary>
	///     Add custom identity user, roles, etc.
	/// </summary>
	public static void ConfigureServices(IServiceCollection services, IConfiguration configuration)
	{
		services.AddIdentity<ApplicationUser, ApplicationRole>()
			.AddEntityFrameworkStores<ApplicationDbContext>()
			.AddClaimsPrincipalFactory<ApplicationClaimsPrincipalFactory>()
			.AddDefaultTokenProviders();
	}

	public static void Configure(IApplicationBuilder app, IConfiguration configuration)
	{
	}
}
```


## Presentation

