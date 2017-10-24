# Features

There are a lot of features to easily manage your database server.

## Restart server

If you ever need to restart your database server, you can easily run the restart command:

```
vapor-beta cloud database restart --token=<ENGINE>_URL
```

## Shutdown server

If you don't need the database server in some time, but still want the data, and would be able to spin it up fast, you can shut it down.

```
vapor-beta cloud database shutdown --token=<ENGINE>_URL
```

## Delete server

If you don't need your database server again, you can delete the server. After 24 hours the data will be wiped, and can't be reconstructed, make sure to take a local backup before.

```
vapor-beta cloud database delete --token=<ENGINE>_URL
```
