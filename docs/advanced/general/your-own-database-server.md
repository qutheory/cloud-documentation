# Your own database server

Vapor Cloud provides a cheap way to get started using databases, giving you a database cheap for your project on our shared servers.

But for various reasons, you might want your own database server. We provide this option, but still managed and maintained by the Vapor Cloud team.

## Why have your own database server

Some good reasons to get your own database server.

- You can have as many projects on it, without being charged extra
- Full use of the hardware (No shared servers)
- Possible external administrator access

## Get a database server

Contact us at:

`support@vapor.cloud`

**Subject:** Request MySQL server **[Organisation name]**

With the following information:

- Size (See https://vapor.cloud for sizes possible)
- External access yes/no
- [If external access] Whitelist ips (Ips you need access to externally `0.0.0.0` for everywhere)
- Start date (When should it be setup)

!!! Warning
    If you choose access `0.0.0.0` this will add possible vulnerability to the server

## Databse server elsewhere

If you want to host your data outside of Vapor Cloud, you can easily to that.

Just overwrite the database variables in the configuration with your own.
