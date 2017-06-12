# About our server setup

## Setup in general

Our setup is build on Amazon Web Services (AWS). Our core is using Docker to seperate applications. Our system will automatically rollout containers on Node servers with free capacity, we will never assign more containers to a Node server than there is capacity to handle.

Our loadbalancers are configured with NGinx, and is terminating TLS, this way we only have the Vapor application running inside the container, this way we can limit the memory usage in each Vapor container to a minimal.

## What is a replica

You can see a replica as a Docker container. If you only spawn one, you will have one
container on one of our Node servers.

If you spin up two or more, our Replica Scheduler will try to the best of it's
ability to place them on different Node servers.

!!! note
    We always suggest two or more replicas for production workloads. If you only have one, and the Node server it's located on goes down, there might be 30-120 seconds downtime.

## Database and Cache

When you start a database or cache server from the dashboard or toolbox,
you will be provisioned your own AWS RDS or AWS ElastiCache server.
And this will never be shared with any other clients.

### Supported databases

* AWS Aurora (Compatible with MySQL 5.6)
* MySQL 5.6 and up
* PostgreSQL 9.5 and up
* MariaDB 10.0 and up

!!! note
    Patch version is always the latest. When a new Patch is issued, we will make sure to update your server automatically.

### Supported Cache

* Redis
