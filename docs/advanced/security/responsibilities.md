# Responsibilities

When looking at security, the responsibilities are split between

- You as a developer
- Vapor Cloud as a provider
- Our provider AWS

We will here outline shortly what this means to you as a developer, and will go further into details on the next pages.

## You as a developer

As a developer you are responsible to ensure the security in your app on the application layer.

Some examples:

- Sanitize data before doing database operations
- Enforce good password policy
- Prevent XSS (Cross-site scripting)

## Vapor Cloud as a provider

We are responsible to ensure the security on the servers including load balancers, webservers, database servers etc.

We will also handle all monitoring on the server side, but won't monitor each individual app. If uptime is critical, we suggest you setup monitoring on your own application. https://statuscake.com is an example of a free stable monitoring system to monitor URLs

## AWS

Everything on Vapor Cloud is hosted on AWS (Amazon Web Services). AWS have a good reputation when it comes to security, and they handle the more low-level physical security. You can read more about AWS securit here: https://aws.amazon.com/security/
