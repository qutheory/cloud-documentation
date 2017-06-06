# Troubleshooting

Sometimes problems can occur in your application. Here is some pages with the often reported problems.

## Get log details

It can often help to look at the application logs. To do this, the toolbox allows you to tail the log files live.

Use:

```
vapor cloud logs
```

This will only show logs for the last `5 minutes`, to avoid clutter in the terminal. To get a larger timeframe, use the `--since` option.

```
# For 20 minutes
vapor cloud logs --since=20m

# For 2 hours
vapor cloud logs --since=2h
```

## Get support

You can always contact our support team at:

`support@vapor.cloud`

Make sure to inform us of the `Application slug` and `Environment` to get faster support
