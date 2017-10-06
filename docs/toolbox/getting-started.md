# Getting Started with the Toolbox

The Vapor Cloud commands are provided in Vapor's [Toolbox](http://docs.vapor.codes/2.0/getting-started/toolbox/) CLI.
You likely already have this installed, but if not, head over to Vapor's [Getting Started](http://docs.vapor.codes/2.0/getting-started/toolbox/) docs to install it.

## Cloud Commands

All Vapor Cloud commands are available under the `cloud` command group.

```sh
vapor cloud
```

You can view help using `vapor cloud --help`.

## Login

The first step to getting started using Vapor Cloud commands is to login. 

```sh
vapor cloud login
```

If you don't have an account, you can signup.

```sh
vapor cloud signup
```

## Deploy

Once you've logged in, you can create your first deployment.
If you don't already have a project you want to deploy, you can create a new one.

```sh
vapor new HelloWorld --branch=beta
cd HelloWorld
```

Make sure you are in the root directory of your project (where the `Package.swift`) file is, and run
the following command.

```sh
vapor cloud deploy
```

The toolbox will automatically detect your Vapor project and guide you through your first deployment.

!!! tip
	You can use the toolbox even while not inside of a Vapor project directory. You will instead be presented with
	menus to choose which application, environment, etc you would like to deploy.

After you have followed the prompts, and your deployment has finished, you can visit your project online!
