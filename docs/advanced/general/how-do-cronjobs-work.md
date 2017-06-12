# How do Cronjobs work

Cronjobs is a way to run a job at a specified time. This can be every 5 minutes,
every hour or every monday at 9:00

Cronjobs is a good way to offload large tasks, so it dosn't slow down your website.

## How cronjobs work in Vapor Cloud

You can easily setup your cronjob through either the `Toolbox` or `Dashboard`.
The time syntax is just as normal on Linux and Mac

When your cronjob is starting, we will spin up a new replica and run the job
inside that. After the job is finished, we will terminate the replica again.

This way you only pay for the time while the job is running. This replica
won't receive any web requests, so it won't slow down your requests.

!!! note
    Be aware that when the job is starting, it might take 5-30 seconds for the job to start, because we need to spin up the replica.

## Cronjob syntax

### Command

!!! note
    Never prefix your job with `vapor` or `App` etc. We will do this for you.

So if i want to run `prepare` in a cronjob, simply set command to:
```
prepare
```

### Time

The basic cronjob syntax is:

```
* * * * * command to be executed
- - - - -
| | | | |
| | | | ----- Day of week (0 - 7) (Sunday=0 or 7)
| | | ------- Month (1 - 12)
| | --------- Day of month (1 - 31)
| ----------- Hour (0 - 23)
------------- Minute (0 - 59)
```

So if we want to run a cronjob every 5 minutes, we can do:
```
*/5 * * * *
```
