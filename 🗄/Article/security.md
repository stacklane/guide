---
title: Security
summary: Stacklane approaches security as a default requirement of any web application, from simple to complex. Security should be an inherent consideration from the first line of code written, and not require later revisiting after the early stages of development.
order: 700
---

# How Does Stacklane Help Protect My Apps?

## Key Vault

Stacklane requires that all server-to-server code, connecting to remote third party APIs, use our secure key vault. This encrypted vault is one-way — administrators may add keys to it, but from then on keys are only used in server-to-server communications.  This approach ensures that third party usernames, passwords, credentials, and tokens are not stored in source code, since they are unusable from within the source code itself.

## Content Security Policies

[Content Security Policies](https://en.wikipedia.org/wiki/Content_Security_Policy) are a security standard which helps prevent common techniques for cross-site scripting (XSS), clickjacking, and other code injection attacks. A CSP header allows a site to declare trusted sources of its content (scripts, styles, images, fonts, etc).  Stacklane makes using a Content Security Policy easy through a combination of automatic behavior and custom declarations (https://stacklane.com/docs/endpoints/mustache#csp).

## Scripting Engine

Stacklane uses a custom JavaScript engine for server-side logic. This engine is designed for speed, security, and compile-time validation. It ensures that all code runs in a secure sandbox, follows any user permissions (https://stacklane.com/docs/users/), and only connects to remote third party APIs using the internal key vault (https://stacklane.com/docs/security#keys).

# How Does Stacklane Help Protect Customers and Visitors?

## Identity Providers

For user login functionality, Stacklane requires the use of trusted third party providers. This ensures that users do not need to remember and manage yet another password, and also simplifies your application — there is no need to provide "remember my password", "change password", "change username" options, since these are instead the responsibility of the identity provider.

## User Content

Accepting content created by users is challenging enough. Stacklane ensures that all incoming data is sanitized. For uploaded images, unsafe content is automatically detected and blurred.

# How Does Stacklane Help Protect My Data?

## Access Controls

Configure user identities, tenants, roles, and app-specific access rules to allow Stacklane to automatically detect and manage access violations.

## Encryption & Redundancy

All data hosted with Stacklane is encrypted at rest and in transit.  Stacklane hosts data with automatic multi-region replication, horizontal scaling, and strong consistency – even in the event of a region specific disaster, your data is safe and available.

# How Is Application Security Defined in Stacklane?

Stacklane supports rich and accessible application-specific security based on the domain-specific data models you’ve defined.  Developers can create specific user roles which map specific access rules to your app model.  Fine-grained security restrictions can be created down to the attribute level on specific entities.

Each user identity accessing your web application can be assigned zero or more of these application specific roles.  From here the Stacklane platform will automatically ensure that roles and access rules are followed as a given user interacts with the application.

# How Does Stacklane Support Multi-Tenancy?

Stacklane offers built-in support for developing multi-tenant applications.  Multi-tenant apps in Stacklane share the same database, application logic, and user interface.

The tenant of an application is broader than a user of an application.  Specifically a single user may have access to multiple tenants.  Typically a tenant is represented as an organization, company, client, or partner, where individual user identities are assigned access to the tenant.

More generally a tenant is anything which multiple users may need to access.  Stacklane makes it easy it to associate users to objects with individual profiles that are unique to the user and tenant object.  You’ll define your tenant object model as you would any other data model in Stacklane – unique and specific to your business case.

# What Kind of Encryption Is Provided by Stacklane?

The Stacklane platform encrypts data at rest and data in transit.

# How Does Stacklane Support Multi-Factor Authentication?

With Stacklane all user authentication is provided by third party identity providers (Google, Microsoft, etc).  Most identity providers support multi-factor authentication, and you have full control over which identity providers your application uses.
