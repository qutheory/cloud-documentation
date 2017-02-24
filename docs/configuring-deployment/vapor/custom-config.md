# Custom configuration

If you want to add configuration variables in your vapor config files,
you can do this by adding them to the .vcloud.yml file.

You can both add environment specifics or variables accessible in all
environments.

## Basic structure

The basic structure is:

```
config:
    <environment>:
        <KEY>: "<VALUE>"

    all:
        <KEY>: "<VALUE>"
```

`all:` will be available in all environments

## Full example

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

## Implementing in Vapor

If we take the full example, we need to add the `VAR` to a file in our `Config/` folder

Lets take `Config/test.json` as an example:

```
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
