# Troubleshooting Redis

## Can't connect to Redis

If your application can't connect to Redis, is often caused by one of to reasons.

### 1 Redis DB is not created

Make sure you have created a Redis database for the application on the environment.

1: Go to https://dashboard.vapor.cloud and find your application.

2: Choose Hosting service

3: Select the environment e.g. `production`

4: Add the bottom of the page, click `Add cache` and create Redis DB

5: Redeploy your project

### 2 Redis is not setup in the project

1: Add Redis package to your `Package.swift` file:
```
.Package(url: "https://github.com/vapor/redis-provider.git", majorVersion: 1)
```
2: Make sure you have a `redis.json` file in your application

3: with the following content:
```
{
    "address": "$REDIS_HOSTNAME",
    "port": "6379",
    "database": "$REDIS_DATABASE"
}
```
