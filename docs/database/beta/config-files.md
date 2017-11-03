# Config files

When using the database system, the system will automatically setup the connection url as environment variable for your project.

We use the connection url, to make less manual configuration for the project.

Use the database engine below to see how to setup your project. To set it up, you need the database TOKEN, this is **DB_#ENGINE#_#NAME#** .. e.g. **DB_MYSQL_MAIN** to replace **$TOKEN** in the below examples with your token, this is written when you create your databaes server, you can also see it by running:

```
vapor cloud db list
```
or
```
vapor cloud config dump
```

## MySQL

Setup **Config/mysql.json** with the following content:

```
{
    "url": "$TOKEN"
}
```

## PostgreSQL

Setup **Config/postgresql.json** with the following content:

```
{
    "url": "$TOKEN"
}
```

## MongoDB

Setup **Config/mongodb.json** with the following content:

```
{
    "url": "$TOKEN"
}
```
