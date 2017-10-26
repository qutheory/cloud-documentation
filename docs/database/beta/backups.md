# Backups

!!! warning
    Backup features are not implemented yet.

Backups are a vital part of data hosting. We basically have 2 ways of managing backups. `Continuous Backups` and `On-demand backups`. There are some core differences explained here.

## Continuous Backups

Continuous backups, are backups on the harddrive level. And are running automatically on `Standard` and `Premium` database plans. A snapshot of the harddrive containing the data will be performed **every 4 hours**. Continuous backups are only for restore within Vapor Cloud. Due to the nature of the backup, you can't copy this backup outside of Vapor Cloud.

Backups are stored on Amazon S3, distributed to multiple datacenters, to secure for major outages.

### How to restore

If you want to restore a Continuous backup, you can use:

```
vapor cloud database --token=<TOKEN> cb-list
```

To see a list of backups. If you want to restore to a previous backup, just run

```
vapor cloud database cb-restore --token=<TOKEN> --id=<backup-id>
```

This will spin up a new database server, added as a secondary, so you can test the backup before promoting it to primary.

## On-demand backup

On-demand backup uses the `dump` feature for your specified database engine to generate a file. This is a much heavier way to perform a backup, and can only be scheduled to once a day.

On-demand backups can both be performed manually, and be scheduled.

You On-demand backups can be downloaded, so it's a good way to for example get the data from your database to your local environment.

### Schedule on-demand backup

To schedule on-demand backup, you need to provide the time. The timezone is always UTC. This example will schedule a backup for my application every night at 3am UTC. It should always be in 24 hour format.

```
vapor cloud backup-schedule --token=<TOKEN> --time="02:00"
```

### Manual on-demand backup

To perform a manual backup, simply run

```
vapor cloud backup --token=<TOKEN>
```

### List manual backups

If you want a list of the backups, you can just run

```
vapor cloud backup-list --token=<TOKEN>
```

### Download a backup

To download a backup, run

```
vapor cloud backup-download --id=<backup-id>
```

This will show a link where to download the backup. The link will only be available for `60 minutes`
