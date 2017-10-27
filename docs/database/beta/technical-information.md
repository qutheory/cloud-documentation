# Technical information

The Vapor Cloud Database is running in a quite complicated setup. To be able to run so many database servers stable requires a lot of automation.

The database servers run on EC2 host instances. And the actual database servers run inside Containers, to separate them logically. This allows for a high degree of security and stability.

Database servers are publicly accessible, but is built with random generated usernames and password. It is possible to rotate username and password for the database servers.

Data for the database are kept safe in volumes, and mounted to the database server, so even if the container gets deleted, the data is saved.
