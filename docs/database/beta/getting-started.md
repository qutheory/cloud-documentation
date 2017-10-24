# Getting started

## Beta access

As we are still in beta, we are slowly opening access, so ensure we can provide the best quality possible.

To get into the database beta program, send us an Email to:

`support@vapor.cloud`

**Subject:** Database beta

With the following information:

- Email added in Vapor Cloud
- What database engines you want to use
- Number of database servers you will be starting

## Create your database

To create your new database, you can simply run.

```
vapor-beta cloud database create
```

This will create a full database server, and a database for each environment.

When you create your database server, we will automatically setup a configuration variable on each of your environments called: `<ENGINE>_URL` this will contain the connect URL to your database.

In your project config file, you can simply read it with `$<ENGINE>_URL`.

Most database commands will require this name to be sent, for example:

```
vapor-beta cloud database inspect --token=<ENGINE>_URL
```

If you don't add `--token` it will default to the primary database server.

### Multiple databases with same engine

Let's say you want to have 2 database servers both PostgreSQL.

The name you sent, will be added to the secondary database, so if i give it the name `test`

The secondary will have the token `MYSQL_test_URL`

You can always promote the secondary database to primary by running

```
vapor-beta cloud database promote MYSQL_test_URL
```

This will promote our secondary and demote our primary.
