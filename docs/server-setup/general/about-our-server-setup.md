# About our server setup

## Setup in general

![vaporcloud-server](https://cloud.githubusercontent.com/assets/2535140/24201453/5b6a9f56-0f10-11e7-9053-436fae365bc3.png)

Our server setup is build on the container technology Docker, and build on AWS.

A request gets in through our DNS, to our loadbalancers, here we have `Ingress controllers` inside containers, to direct the requests to the application.

On our Node servers, the applications is started inside containers. Our `Replica scheduler` makes sure to start the `Replicas` on servers that is most suited to handle the requests.

## What is a replica

You can see a replica as a Docker container. If you only spawn one, you will have one
container on one of our Node servers.

If you spin up two or more, our Replica Scheduler will try to the best of it's
ability to place them on different Node servers.

`NB:` We always suggest two or more replicas for production workloads.
If you only have one, and the Node server it's located on goes down, there might
be 30-120 seconds downtime.

## Database and Cache

When you start a database or cache server from the dashboard or toolbox,
you will be provisioned your own AWS RDS or AWS ElastiCache server.
And this will never be shared with any other clients.

### Supported databases

* AWS Aurora (Compatible with MySQL 5.6)
* MySQL 5.6 and up
* PostgreSQL 9.5 and up
* MariaDB 10.0 and up

`NB:` Patch version is always the latest. When a new Patch is issued, we will
make sure to update your server automatically.

### Supported Cache

* Redis
