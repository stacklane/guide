---
title: Platform Architecture
summary: Stacklane’s architecture was built from the ground up for scale and security, using modern stateless best practices, and horizontal scaling to ensure resilience and scale.  The platform abstracts architecture and infrastructure from your custom application code, ensuring that over time your application can automatically take advantage of technology’s inevitable march forward.
order: 300
---

# What Are the Key Components of the Stacklane Architecture?

Stacklane’s platform is an integrated application platform-as-a-service (aPaas) for developing, building, deploying, and managing web apps.  The platform provides modern, web-scale best practices and architecture to apps large and small.  By also abstracting the infrastructure-as-a-service layer (IaaS) it shields application code from the ever-changing offerings of IaaS providers – this allows your code to focus on results and outcomes, while Stacklane focuses on how to make it happen.

Good software last for years, often outliving initial goals and original developers – Stacklane’s architecture encourages long term maintainability and inherently reduces the accumulation of technical debt and the risks of developer churn.  The various components of Stacklane’s platform architecture support the entire web application lifecycle, from initial development, iterations, dev ops, testing, production, and finally growth and maintenance.

- *Source Code* -- It all begins with code.  Stacklane knows the power of developers and code to provide the most direct and obvious path to results.  With Stacklane everything is an easily read file, organized for long term maintainability and the natural path-based based nature of URLs (REST).
- *Repositories* -- Code and files need somewhere to live to facilitate version control and collaboration.  Stacklane supports both private and public repositories hosted at GitHub and Bitbucket, ensuring that developers can keep the workflows they already know and love.
- *Development Environment* -- All Stacklane code uses easy to read standard file formats – JavaScript, HTML, YAML, etc.  This means bringing existing expertise from day one, using any favorite code editor.  For ease of testing we recommend JetBrain’s [WebStorm](https://www.jetbrains.com/webstorm/), which we’ve created a plugin for.
- *Testing Environment* -- From our [WebStorm](https://www.jetbrains.com/webstorm/) plugin you have one-click access to a fully featured build and testing environment, for fast and regular iterations.  Our testing environment has _feature parity_ with our production environment, ensuring there are zero surprises during production.
- *Production Environment* -- Deploy your web app to a domain, sub-domain, or even a sub-directory of another Stacklane web app you own.  From there your web app will automatically enter our high availability environment, taking advantage of auto-healing and global distribution.

# How Does Stacklane’s Platform Offer High Availability?

All web apps deployed on Stacklane’s platform are highly available by default – there is no other lesser mode.  We believe every app deserves high availability, from endpoints to data.

Stacklane hosts web application logic and assets in a minimum of _two_* *geographically isolated regions.  Traffic is automatically routed to regions geographically closest to the visitor or user, and even in the case of a complete failure in one region, traffic will be routed to another.

Stacklane hosts data with automatic multi-region replication, horizontal scaling, and strong consistency – even in the event of a region specific disaster, your data is safe and available.

# Where Does Stacklane Host My Application?

Stacklane hosts your web app in a minimum of _two_ geographically isolated regions on the Google Cloud or Amazon Web Service IaaS layers.  Global regions include the United States and European Union.  Certain assets and responses may be further deployed and cached by a content delivery network, with edge locations worldwide – this is completely transparent to your code.

Data your application stores and uses is hosted in the United States by default, but may optionally be hosted in the European Union for no additional cost.  In either case, data is stored using automatic multi-region replication, and horizontal scaling.

# How Does Statelessness Work in Stacklane?

Modern web-scale apps use stateless architectures for supporting greater scalability and resilience.  With stateless architecture, nothing is taken for granted on any given server.  This means that as servers inevitably fail or horizontally scale, any server is ready to pick up the requests coming from a specific user/visitor.  Every user request and transaction can be handled by any specific server.  If performance requirements call for handling additions requests, instances are automatically added to accommodate them.

With Stacklane you never need to worry about servers, containers, or instances.  We handle all of that for you, while you focus on your business, web app, and users.

# How Does Stacklane Provide Auto-Recovery & Auto-Healing?

Stacklane automatically enables auto-recovery and failover for all plans.  User load is balanced between multiple regions, directing traffic to the nearest available region.  In the rare occurrence that any given instance crashes, another runtime immediately takes over all requests for a user, while the crashed instance is replaced.  Because of Stacklane’s stateless architecture, end-users / visitors are not impacted in this scenario.
