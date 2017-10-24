# Backups

Backups are a vital part of data hosting. We basically have 2 ways of managing backups. `Continuous Backups` and `On-demand backups`. There are some core differences explained here.

## Continuous Backups

Continuous backups, are backups on the harddrive level. And are running automatically on `Standard` and `Premium` database plans. A snapshot of the harddrive containing the data will be performed **every 4 hours**. Continuous backups are only for restore within Vapor Cloud. Due to the nature of the backup, you can't copy this backup outside of Vapor Cloud.

Backups are stored on Amazon S3, distributed to multiple datacenters, to secure for major outages.

### How to restore

If you want to restore a Continuous backup, you can use:

```
vapor-beta cloud database --token=<ENGINE>_URL cb-list
```

To see a list of backups. If you want to restore to a previous backup, just run

```
vapor-beta cloud database cb-restore --token=<ENGINE>_URL --id=<backup-id>
```

This will spin up a new database server, added as a secondary, so you can test the backup before promoting it to primary.

## On-demand backup

On-demand backup uses the `dump` feature for your specified database engine to generate a file. This is a much heavier way to perform a backup, and can only be scheduled to once a day.

On-demand backups can both be performed manually, and be scheduled.

You On-demand backups can be downloaded, so it's a good way to for example get the data from your database to your local environment.

### Schedule on-demand backup

To schedule on-demand backup, you need to provide the time. The timezone is always UTC. This example will schedule a backup for my application every night at 3am UTC. It should always be in 24 hour format.

```
vapor-beta cloud backup-schedule --token=<ENGINE>_URL --time="02:00"
```

### Manual on-demand backup

To perform a manual backup, simply run

```
vapor-beta cloud backup --token=<ENGINE>_URL
```

### List manual backups

If you want a list of the backups, you can just run

```
vapor-beta cloud backup-list --token=<ENGINE>_URL
```

### Download a backup

To download a backup, run

```
vapor-beta cloud backup-download --token=<ENGINE>_URL
```

This will show a link where to download the backup. The link will only be available for `60 minutes`
