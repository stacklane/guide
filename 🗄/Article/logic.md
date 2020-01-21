---
title: Application Logic
summary: Stacklane fully embraces JavaScript as the language of the web.  This means that whether adding server-side logic, or client-side logic, developers are working with a uniform language syntax from end-to-end.
order: 500
---

# How Can I Add Logic to My Web App?

For server-side logic, we provide a custom validating and JavaScript runtime – it’s the syntax you already know, but more predictable, and less breakable.

For client-side logic, you can bring your own library, or better yet stick closely the native functionality of the web browser.

Stacklane fully embraces JavaScript as the language of the web.  This means that whether adding server-side logic, or client-side logic, developers are working with a uniform language syntax from end-to-end.

# How Do I Build Server-Side Logic?

As with everything in Stacklane, adding logic to your web app is just another file.  All logic is written in our highly tuned and secured server-side JavaScript runtime.

Unlike traditional JavaScript, Stacklane compiles and validates server-side JavaScript.  For apps growing in complexity, or iterated on by multiple developers, this means that invalid method calls, missing properties, and bad syntax are all caught well before any release.  In fact, Stacklane won’t even execute JavaScript that it can’t validate.

There are two main types of logic in Stacklane:

- *Endpoints* – Logic that is designed to produce a concrete response to the client.  The response will be either JSON, a redirect, or an error.
- *Suppliers* – Logic that produces values used by endpoints, other suppliers, or HTML views.  This enables decoupling requirements, breaking logic into smaller pieces, and reusing code.

What about the HTML view finally rendered to the browser?  Stacklane’s HTML generation is “logic-less”, via the template language called Mustache.  This ensures a stricter separation between where logic does and does not appear.

# How Do I Build Client-Side Logic?

Bring your own client-side libraries, or better yet use native browser functionality.  Stacklane does not require using any special client-side library we provide.  This means on the client-side your web apps are as simple or complex as needs dictate.

We’re opinionated though, and in general we recommend ditching many crutches that have been built up over the years.  JQuery is a good example – it was originally used as a way to combat the discrepancies in various browsers – unifying their behavior under a single syntax.  As concise as JQuery is, those days are thankfully long gone.  Browsers now enjoy constant updates and great compatibility.

In short, whenever possible, we recommend usually sticking closely to native universal runtime of the browser itself, rather than reaching for a crutch.  This will not only create the fastest user experience with no waiting on a library, but it will ensure your code isn’t tied too closely to the inevitable churn of an external API, or next shiny library.

For more complex user interfaces, libraries can have their place to ease user interactions and UI changes.  When reaching for a third party library, look for those that generally respect the web, and act more like mediators to native browser functionality, rather than trying to completely replace it as many do.

# How Can I Reuse Logic?

With Stacklane it’s natural to break up logic into small, purpose specific files.  For example, each JavaScript endpoint serves a highly specific and short-lived interaction.  Across many endpoints there are two major areas of logic reuse:

- *Models* – Stacklane makes the business’s data model a fundamental building block of any web app – as easy to define and use as a CSS file.  A rich variety of model fields are available, as well as the relationships between each domain model.  Once defined, Stacklane automatically decorates your models with properties and methods.  The model is then made available to all other logic, as well as being stored and queryable.
- *Suppliers* – Suppliers help to define values that are commonly used across many endpoints, or to simply add additional organization to your web app.  For example, a specific query on a model may be defined in JavaScript logic, and then returned from a supplier as “MyCommonlyUsedQuery”.  Supplier values may also be used from HTML views.

