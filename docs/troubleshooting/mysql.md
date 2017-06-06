# Troubleshooting MySQL

## Can't connect to MySQL

If your application can't connect to MySQL, is often caused by one of to reasons.

### 1 MySQL DB is not created

Make sure you have created a MySQL database for the application on the environment.

1: Go to https://dashboard.vapor.cloud and find your application.

2: Choose Hosting service

3: Select the environment e.g. `production`

4: Add the bottom of the page, click `Add database` and create MySQL DB

5: Redeploy your project

### 2 MySQL is not setup in the project

1: Add MySQL package to your `Package.swift` file:
```
.Package(url: "https://github.com/vapor/mysql-provider.git", majorVersion: 1)
```
2: Make sure you have a `mysql.json` file in your application

3: with the following content:
```
{       
    "host": "$DATABASE_HOSTNAME",
    "user": "$DATABASE_USER",
    "password": "$DATABASE_PASSWORD",
    "database": "$DATABASE_DB",
    "encoding": "utf8mb4"
}
```

## Root/External access to MySQL

When using our `clients` databases, it's not possible to get external/administrator access to the database.

But it is possible to get your own MySQL server, with external/administrator access.

For now to get this, please contact us at:

`support@vapor.cloud`

**Subject:** Request MySQL server **[Application slug]**

With the following information:

- Size (See https://vapor.cloud for sizes possible)
- Whitelist ips (Ips you need access to externally `0.0.0.0` for everywhere)
- Start date (When should it be setup)

!!! Warning
    If you choose access `0.0.0.0` this will add possible vulnerability to the server
