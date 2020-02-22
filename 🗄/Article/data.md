---
title: Data & Models
summary: With Stacklane data models become a fundamental building block of the web – as easy to use and define as a CSS file.
order: 600
---

# How Do I Define Data in Stacklane?

With Stacklane, everything is a file – logic, views, and even data models.  To define your data models, you’ll place configuration files into a special directory within your source code.

First you’ll decide on the type of model, which describes its overall purpose (Universal, Content, User Profile, or Embedded).  Next you’ll define field names, and any relationship between with other models, such as parent/child (one-to-many).

Once you define your data models, Stacklane automatically transforms them into JavaScript types with appropriate fields and methods.  It also provisions tables and indexes for both testing and production environments.

# What Data Types Can I Use in Stacklane?

Stacklane supports a rich set of field types, speeding up time-to-market by addressing specific, repeatable business cases.

- *String* – letters, numbers, spaces, emoji’s, and other characters
- *Boolean* – true or false
- *Integer* – 64 bit whole number
- *Double* – 64 bit floating point number
- *Timestamp* – a point in time
- *Date* – a calendar date
- *Options* – one value from a predefined set of values
- *Country Code* – ISO 3166-1 alpha-3 country code
- *Map* – freeform name / value pairs or attributes
- *Geo Point* – latitude and longitude
- *Image* – public or privately accessible image
- *Hierarchy* – custom ordering, including hierarchical reordering
- *HTML* – validated rich text as HTML
- *Markdown* – validated rich as Markdown
- *Model Links* – link or reference to another model
- *Embedded* – a complex embedded model
- *Lists* – lists of multiple strings or embedded models
- *User Friendly IDs* – URL friendly unique string values or “slugs”

# How Is Data Queried?

With Stacklane you don’t need to learn another query language.  All data access is performed using JavaScript methods, ensuring that a single language stays front and center.  Queries may be created using our fluent JavaScript builder methods, and then reused across multiple endpoints and views.

Stacklane’s query builder supports the following operations:

- *Equals* – equal to a specific value
- *Less Than* – less than or equal to a value
- *Greater Than* – greater than or equal to a value
- *Custom Filters* – use JavaScript for further filtering
- *Mapping / Transform* – transform results into another format
- *Expansion* – expand time series data to fill in gaps
- *Distinct* – after transformation, return distinct values
- *Group By Parent* – query children, and group by parent

# How Can I Optimize My Queries?

Stacklane’s high performance, horizontally scaled, and redundant data storage eliminates the burden of database administration, patching, and indexing.  And our pricing model ensures that you are not penalized for fundamental performance techniques such as denormalized data and parallel requests.

There are two basic principles to keep in mind during design and development which will help get the most out your web app’s query performance, ensuring a page displays as quickly as possible for the visitor:

## Denormalized Data

Make part of the development phase consideration of potential model uses, and denormalize data where it makes sense.  This means storing data redundantly to help facilitate faster access to commonly used data.

For example, if displaying the last 5 comments every time you display a post, then it makes sense to keep the most recent 5 comments denormalized on the post itself.

Stacklane supports rich data models, including embedded models, which make denormalization easy and natural.  Similarly you might store a counter for the total number of comments on the post itself.

Stacklane’s pricing model is based on individual records stored, ensuring denormalization does _not_ lead to higher costs.

## Parallel Requests

Browsers have been parallelizing requests for CSS and images for decades.  It’s not uncommon to see a given web page loading 20+ such assets.  But it’s still all too uncommon to think of the HTML body as being broken up in this way.

Unlike data where it may make sense to redundantly store the same data in multiple locations, endpoints should be normalized and highly purpose specific.  Consider a given endpoint or HTML view as performing no more than 1-2 queries in a single request.  Then use AJAX as needed to parallelize multiple requests.

There are many techniques for this.  It could be as simple as beginning to load the AJAX fragments immediately, usually giving a visual placeholder in the UI.  Another technique is to only load more content as it’s scrolled into view.  For example, in a long list, the visitor does not need to immediately see the content below the fold.

Stacklane’s pricing model is based on individual records stored, ensuring parallel requests do _not_ lead to higher costs.

# How Does Stacklane Handle Transactions?

Transaction handling in Stacklane is automatic.  We favor short, purpose specific transactions, that usually deal with a user interaction.  Whenever an endpoint is called which creates, updates, or deletes data, the entire set of changes is performed within a single atomic transaction (ACID).  It’s not possible for some of the data changes performed at an endpoint to succeed, and some to fail – it’s all or nothing.  In short, a successful endpoint call means the transaction is committed, while a failed endpoint call means the transaction will be rolled back.

# How Do I Ensure the Integrity of My Data?

Stacklane supports the following techniques to ensure the integrity of your application data:

- *Unique Values* – ensures unique values across a table / collection
- *Field Types* – large set of field data types for specific cases
- *Validation Rules* – each field type exposes its own constraints and validation
- *Access Rules* – ensures only authorized users may access or modify data
- *Parent / Child* – strong relationships between parent and child types
- *Protected Values* – values which may only be accessed from JavaScript

# How Does Stacklane Ensure Data Security?

Security is one of Stacklane’s fundamental principles – all data managed by Stacklane is encrypted-at-rest and in transit.

Stacklane provides built-in support for various third party user identity providers.  A given web app area may be easily locked down to only be accessible to specific user roles.

Beyond this, your web app must ensure data security by specifying appropriate access controls.  Stacklane facilities this by providing role-based user access, and per-role access rules for your data models.

We also provide “protected values”, which are values which may not be inadvertently exposed in an HTML view – instead they must only be manipulated from JavaScript endpoints.

Stacklane strives to make data security both inherent, and easy to customize for your specific business cases.

[Learn more about security](/🗄/Article/security.md)
