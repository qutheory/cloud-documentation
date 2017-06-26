# Custom configuration

## Cloud.yml

If you want to add configuration variables in your vapor config files,
you can do this by adding them to the .vcloud.yml file.

You can both add environment specifics or variables accessible in all
environments.

### Basic structure

The basic structure is:

```
config:
    <environment>:
        <KEY>: "<VALUE>"

    all:
        <KEY>: "<VALUE>"
```

`all:` will be available in all environments

### Full example

Here is a full example of how it could look:

```
config:
    production:
        VAR1: "My production variable"
        VAR2: "My production variable 2"

    staging:
        VAR1: "My staging variable"
        VAR2: "My staging variable 2"

    all:
        VAR3: "My variable in all environments"
        VAR4: "My variable in all environments 2"
```

The environment name will be the name you gave the environment when it
was created.

## CLI

Sometimes, you have secret keys you don't want in GIT. These can be added through the toolbox.

e.g.:

```
vapor cloud config modify VAR1=KEY1 VAR2=KEY2
```

If the key exists, it will be overwritten, if it doesn't, it will be created.

## System settings

Some keys are automatically added by Vapor Cloud. These can be overwritten with your own if you need to overwrite it.

```
AWS_ACCESS_KEY # Access key to AWS for S3
AWS_SECRET_KEY # Secret key to AWS for S3
AWS_S3_BUCKET # AWS Bucket for S3
PROJECT_NAME # Application name
ENVIRONMENT # Environment name
DATABASE_USER # Database user
DATABASE_PASSWORD # Database password
DATABASE_DB # Database db
DATABASE_HOSTNAME # Database hostname
REDIS_HOSTNAME # Redis server hostname if Redis is enabled
REDIS_DATABASE # Redis server database if Redis is enabled
PORT # Server port
HOST # Server host 
```

## Implementing in Vapor

If we take the full example, we need to add the `VAR` to a file in our `Config/` folder

Lets take `Config/test.json` as an example:

```JSON
{
    "var1": "$VAR1",
    "var2": "$VAR2",
    "var3": "$VAR3",
    "var4": "$VAR4"
}
```

This will allow us to do:

```
let var1 = drop.config["test", "var1"]?.string
let var2 = drop.config["test", "var2"]?.string
let var3 = drop.config["test", "var3"]?.string
let var4 = drop.config["test", "var4"]?.string
```
