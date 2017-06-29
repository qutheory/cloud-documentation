# Managing your apps

The toolbox provides an easy way to manage your apps, both in terms of logging, deployment, running commands etc.

You can always see available commands and options by using `--help`

e.g.
```
vapor cloud --help

vapor cloud deploy --help
```

## Deploy your application

Deploying your application is easy through the toolbox, and it will automatically inform you in the terminal if something goes wrong.

!!! tip
    If the project doesn't exist, you will be guided through the creation process before the deployment starts.

**Options**
```
app The slug name of the application to deploy
    This will be automatically detected if your are
    in a Git controlled folder with a remote matching
    the application's hosting Git URL.
env The name of the environment to deploy to.
    This will always be required to deploy, however
    omitting the flag will result in a selection menu.
branch The name of the Git branch to deploy from.
    If not passed, the environment's default branch
    will be used
build The type of build to perform.
    Options include: incremental, update, clean
    This will always be required to deploy, however
    omitting the flag will result in a selection menu.
replicas The number of replicas to deploy.
    ex: 2
    Hourly cost is based on the replica size and number of replicas.
replicaSize The size of replicas to deploy.
    ex: small
    Hourly cost is based on the replica size and number of replicas.

```

**Examples**

```
# Deploy, will autodetect or ask for app/env
vapor cloud deploy

# Will deploy my-app to staging environment
vapor cloud deploy --app=my-app --env=staging

# Will deploy my-app to staging with my-feature branch
vapor cloud deploy --app=my-app --env=staging --branch=my-feature

# Will change replicas to 3
vapor cloud deploy --replicas=3

# Will change replica size to medium
vapor cloud deploy --replicaSize=medium
```

!!! tip
    If you want to close down the project, set the replicas to **0**. We keep the data in your database and on S3, so you can always boot it up again.

!!! info
    When starting a deployment, it will inform you about the progress in the terminal. If you cancel **CTRL+C** the deployment will keep running, but not inform you in the terminal

## Get live log output

It can be a good debug tool to get the logs directly from your replicas. To do this, there is a simple log feature build into the toolbox. This will start a `tail` of the runtime Vapor logs as they come in.

**Examples**

```
# Start a tail of logs from my-app on staging
vapor cloud logs --app=my-app --env=staging

# Start a tail, and get logs for the last 20 minutes
vapor cloud logs --app=my-app --env=staging --since=20m

# Start a tail, and get logs for the last 2 hours
vapor cloud logs --app=my-app --env=staging --since=2h

# Start a tail, and get logs for the last 2 days
vapor cloud logs --app=my-app --env=staging --since=2d
```

!!! info
    To prevent cluttered terminal, logs will as default return logs for the past **5 minutes**. Use the **--since** option to get more log history

## Run command

If you want to run a command e.g. `prepare` in your replicas, you can use the `run` command. The system will pick a replica of random to run it, if you have more than one replica.

**Examples**

```
# Run prepare on my-app on staging environment
vapor cloud run --app=my-app --env=staging prepare

# Run command with options on my-app on staging environment
vapor cloud run --app=my-app --env=staging "prepare --help"
```

!!! info
    You should not prefix your command with a path or Vapor, the system will do that, so only write the direct command e.g. **prepare**

!!! tip
    If you need to add options e.g. `--help`, you can quote the command e.g. **vapor cloud run "prepare --help"**

## Open phpMyAdmin

To get access to your database, you can open phpMyAdmin in your browser directly from the toolbox.

**Example**

```
vapor cloud database --app=my-app --env=staging
```

## Create custom domain

In the toolbox, you can attach your own domain to your application. For more information, and advice on DNS settings read the docs [here](../custom-domain/add-domain.md)

**Example**

```
vapor cloud create domain
```

## Attach free SSL/TLS certificate with VCCM

When using your own domain, you can for **free** obtain a SSL/TLS certificate. For more information about DNS settings etc. See [here](../custom-domain/certificate-manager.md)

**Example**

```
vapor cloud create tls
```

## Custom environment variables

You can create your own environment variables through the toolbox. To get more detailed documentation read [this](../configuration/vapor/custom-config.md)

**Example**

```
# Create/update config variables
vapor cloud config modify --app=my-app --env=staging VAR1=KEY1 VAR2=KEY2

# List existing variables
vapor cloud config dump --app=my-app --env=staging
```

If the key exists, it will be overwritten, if it doesn't, it will be created.
