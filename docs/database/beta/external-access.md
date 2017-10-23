# External access

Vapor Cloud databases are build to be supported by Vapor Cloud applications. So you can't create a database server without an application. You can though either connect to the database from another hosting provider, or from your local computer.

## Connect from your local computer

To connect from your local computer, you can get the connect information with:

```
vapor-beta cloud database inspect
```

This will show information for all environments.

If you want to connect through the CLI (mysql, psql or mongo) you can just run:

```
vapor-beta cloud database login
```

this is a shortcut to run the login command on your local computer.
