# Your own database server

Vapor Cloud provides a cheap way to get started using databases, giving you a database cheap for your project on our shared servers.

But for various reasons, you might want your own database server. We provide this option, but still managed and maintained by the Vapor Cloud team.

## Why have your own database server

Some good reasons to get your own database server.

- You can have as many projects on it as you want, without being charged extra
- Full use of the hardware (No shared servers)
- Option to have external administrator access

## External access

As default our servers is closed from Internet access. This improves security. But in some use cases, it can be helpful to be able to get access, for example MySQL CLI access, access through application Sequel Pro etc.

It can also be you have an application in another server setup you want to connect to the database.

If you choose to have a database server with external access, you would still have all the automation from Vapor Cloud, setting up databases, auto connect your applications etc.
But you also get both administrator account, and accounts for each application, making it easy to connect to the DB server

!!! tip
    To improve security, we advice the DB server only is accessible from trusted IP addresses, for example from your office or home. You can give a list of IPs when requesting the DB server. These can always be changed without any sort of downtime.

## Get a database server

Contact us at:

`support@vapor.cloud`

**Subject:** Request MySQL server **[Organisation name]**

With the following information:

- Size (See https://vapor.cloud for sizes possible)
- Server type (MySQL, PostgreSQL, Aurora or MariaDB)
- External access yes/no
- [If external access] Whitelist ips (IPs you need access to externally `0.0.0.0` for everywhere)
- Start date (When should it be setup)

!!! Warning
    If you choose access `0.0.0.0` this will add possible vulnerability to the server

!!! tip
    External access and size can always be changed, but would result in downtime on your database server. If you request changes to this, you will be advised on this. We will try to the best of our ability to make changes at a time you think would fit best (Off peak hours).

## Database server elsewhere

If you want to host your data outside of Vapor Cloud, you can easily to that.

Just overwrite the database variables in the configuration with your own.
