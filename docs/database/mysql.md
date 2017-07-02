All our clients are allowed to get a database on our MySQL servers, for a small fee.

This is a cheap way to store your data.

## Vapor integration

Set this up in a `mysql.json` file in your `Config` directory with the following content

```
{       
    "host": "$DATABASE_HOSTNAME",
    "user": "$DATABASE_USER",
    "password": "$DATABASE_PASSWORD",
    "database": "$DATABASE_DB",
    "encoding": "utf8mb4"
}
```

## Create database to your environment

### Toolbox

When running the deploy command through the toolbox, you will be asked if you want a database.

Say yes, and select a server with `(MySQL)`. After deployment the database is created.
