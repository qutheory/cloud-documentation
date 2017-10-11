# Database beta

!!! warning
    This product is in beta. This means there can be instabilities etc. We have stepped up our backup procedures on beta program, to have more often backups.
    We never suggest you run production workloads during a beta.

As our strive to always provide the best product to our clients, we are starting to roll out a beta of a completely new Database system. The idea is to make it more flexible and give better control over your database.

## Core concept

The basic idea is to setup a database server for an application. The system will automatically make sure there is a database for each environment.

The database server is externally accessible, with the credentials provided through the API. This can be used to connect through Sequel Pro, CLI and other applications depending on your database engine.

## Supported database engines and versions

* MySQL
    * 5.7.x (Default)
    * 5.6.x
    * 5.5.x
* PostgreSQL
    * 10.0.x (Default)
    * 9.6.x
    * 9.5.x
    * 9.4.x
    * 9.3.x
* MongoDB
    * 3.4.x (Default)
    * 3.2.x
    * 3.0.x

## Commands

You can see the commands under the `database` command.

```
vapor-beta cloud database --help
```

### Setting up database server

```
vapor-beta cloud database create --app=<your-app>
```

You will be notified when it's created, and get login information.

### Scale your database server

If you want to scale your database server up/down. You can run

```
vapor-beta cloud database scale --app=<your-app> --size=hobby
```

To scale your app to hobby.

!!! warning
    Scaling your database server can involve risks, we always suggest you make a backup before using the Backup command in the toolbox.

### Reboot database server

As with all systems, it can from time to time be good to be able to restart a service. This can easily be done by running:

```
vapor-beta cloud database restart --app=<your-app>
```

### Get information about your database

To get information about your database server (databases, credentials etc.) you can easily run:

```
vapor-beta cloud database inspect --app=<your-app>
```

### CLI login

You can always use the credentials from the inspect command to connect through your favorite program. To make it easier you can also run the toolbox command to login. This requires the required packages are installed locally.

```
vapor-beta cloud database login --app=<your-app>
```

### backup

To perform a manual backup, run the following command:

```
vapor-beta cloud database backup --app=<your-app>
```

You can also get a list of all stored backups:

```
vapor-beta cloud database backup-list --app=<your-app>
```

If you want to see more information about the backup, run

```
vapor-beta cloud database backup-inspect --backup=<id>
```

(We are currently working on features to download and restore backups.)
