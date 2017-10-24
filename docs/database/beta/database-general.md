# Database general

## Beta information

!!! warning
    This product is in beta. This means there can be instabilities etc. We have stepped up our backup procedures on beta program, to have more often backups.
    We never suggest you run production workloads during a beta.

!!! info
    Currently, when ever change occur to the configuration, you need to redeploy your application (The toolbox will tell you this). We are working on a system to make this happen automatic without redeploy.

As our strive to always provide the best product to our clients, we are starting to roll out a beta of a completely new Database system. The idea is to make it more flexible and give better control over your database.

## Core concept

The basic idea is to setup a database server for an application. The system will automatically make sure there is a database for each environment.

The database server is externally accessible, with the credentials provided through the API. This can be used to connect through Sequel Pro, CLI and other applications depending on your database engine.

### Supported engines

* MySQL
* PostgreSQL
* MongoDB
