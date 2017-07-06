All our clients are allowed to get a database on our PostgreSQL servers, for a small fee.

This is a cheap way to store your data.

## Vapor integration

Set this up in a `postgresql.json` file in your `Config` directory with the following content

```
{       
    "hostname": "$DATABASE_HOSTNAME",
    "user": "$DATABASE_USER",
    "password": "$DATABASE_PASSWORD",
    "database": "$DATABASE_DB"
}
```

## Create database to your environment

### Toolbox

When running the deploy command through the toolbox, you will be asked if you want a database.

Say yes, and select a server with `(PostgreSQL)`. After deployment the database is created.
