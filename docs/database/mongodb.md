All our clients are allowed to get a database on our MongoDB servers, for a small fee.

This is a cheap way to store your data.

## Vapor integration

Set this up in a `mongodb.json` file in your `Config` directory with the following content

```
{
    "server": "$MONGODB_SERVER"
}
```

This will then automatically be set by our systems.

In your project using [MongoKitten](https://github.com/OpenKitten/MongoKitten) connect to the server with the following in your code:

```
let config = try Config()
let mongoConfig = config["mongodb", "server"]?.string ?? "default"
let db = try Database(mongoConfig)
```

## Create database to your environment

### Toolbox

When running the deploy command through the toolbox, you will be asked if you want a database.

Say yes, and select a server with `(MongoDB)`. After deployment the database is created.
