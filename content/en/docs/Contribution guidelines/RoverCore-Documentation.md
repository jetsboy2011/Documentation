---
title: "RoverCore Documentation"
linkTitle: "RoverCore Documentation"
weight: 2
description: >
  How to contribute to the documentation
---

## Writing Etiquette
When writing and contributing to the RoverCoreDocs GitHub repository, there are a few rules you should follow.
1. Writing should be in English.
2. Writing should be free of major grammatical errors.
3. All references should be linked properly.
4. Try to refrain from lengthy sentences and using contractions.
5. Titles and linkTitles for pages should be the same, with the exception of abbreviations or acronyms.
   1. An example is [ModelViewController](/docs/concepts/mvc). The linkTitle is "Model View Controller", but the title is "MVC - Model View Controller".
6. File names should be short and be able to distinguish one page from another.

## Frequently Asked Questions
Here is where you can find more information on tips and tricks to write for the documentation.

### How do I link a reference to something?
Good question! It is pretty easy. If for example you write the following:

> Sometimes, visiting Microsoft's documentation for ASP.NET is a useful place to learn.

You will have to replace "Microsoft's documentation" with: 

    \[Microsoft's documentation]\(https://asp.net)

Then, it will look like this:
> Sometimes, visiting [Microsoft's documentation](https://asp.net) for ASP.NET is a useful place to learn.


### How do I link to another part of the site?
To link to another part of the site, do the same as before, but use

    \[Contribution Guidelines]\(docs/contribution-guidelines)

instead of hard-coding the URL. This allows the domain to change without all of the references within the site being changed.


