# Quick Start

This tutorial will walk you through deploying your first Vapor app to Vapor Cloud.

## TL;DR

Run `vapor cloud deploy` inside your Vapor project (in the same folder as `Package.swift`) and follow the instructions.

![Vapor Toolbox Deploy](https://user-images.githubusercontent.com/1342803/31300850-14d7d8b0-aac4-11e7-8e42-84d406ffb76b.png)

## Step-by-step Guide

If you haven't already, sign up for a Vapor Cloud account at [https://dashboard.vapor.cloud/signup](https://dashboard.vapor.cloud/signup).

## Install Vapor

If you don't already have Vapor installed on your computer, follow the guide at [https://docs.vapor.codes/2.0/getting-started/install-on-macos/](https://docs.vapor.codes/2.0/getting-started/install-on-macos/). Or for Ubuntu: [https://docs.vapor.codes/2.0/getting-started/install-on-ubuntu/](https://docs.vapor.codes/2.0/getting-started/install-on-ubuntu/).

## Install Toolbox

Vapor Cloud applications are deployed through the [Vapor Toolbox](https://github.com/vapor/toolbox).

```sh
brew install vapor
```

You can also install through APT.

```sh
sudo apt-get install vapor
```

!!! note
	If you have not already configured Vapor's Homebrew or APT sources on your computer, visit [https://docs.vapor.codes/2.0/getting-started/toolbox/](https://docs.vapor.codes/2.0/getting-started/toolbox/).

Verify that the toolbox is correctly installed by calling the help command.

```sh
vapor cloud --help
```

<img width="682" alt="screen shot 2017-07-05 at 6 17 39 pm" src="https://user-images.githubusercontent.com/1342803/27888580-cd8b44c2-61b4-11e7-93eb-97abe4202895.png">


## Create an Organization

If you didn't already create an organization during the signup process, create one now.

You can do this through the toolbox `vapor cloud create org` or through the dashboard.

![screen shot 2017-07-05 at 6 35 05 pm](https://user-images.githubusercontent.com/1342803/27887817-b56b3e8c-61b0-11e7-8196-8e67398f772c.png)

## Create a Project

You can do this through the toolbox `vapor cloud create proj` or through the dashboard.

![screen shot 2017-07-05 at 6 39 24 pm](https://user-images.githubusercontent.com/1342803/27887943-522b9c58-61b1-11e7-856c-4bdbc68016e5.png)


Projects help organize related applications. 
You can invite individual users to your projects and assign read, write, or admin permissions. 
You can even create teams of users and add those to your projects.

You cannot assign different permissions to each application, only to a project. 
So feel free to create as many projects as you want for your permissioning needs.

## First Deployment

Now that we have created an Organization and Project, we can begin our first deployment.

To deploy your app, your code needs to be available through Git. The easiest way to do this is through GitHub.

The toolbox will automatically walk you through this process and the other required steps to deploy your first app.

Let's get started.

```sh
vapor cloud deploy
```

### Create Git Remote

The easiest way to host code for your deployed project is as a public repo on GitHub.
If you would like to use this method, respond `yes` to the first prompt. GitHub will be opened automatically.

Once you have created your new repository (or using an existing) copy the **SSH** (not HTTP) url into the next prompt.

### Create Application

After the Git remote has been added, you can create your first application. 
Each application can have multiple services, such as hosting, databases, caches, and more. 

Not every Vapor Cloud application needs to have hosting. For instance, you could create a Vapor Cloud application that
just consists of a MySQL database for your own use. 

However, in this tutorial, we will be creating an application with hosting.

Respond yes to the prompt to create an application. Give it a name, and a slug.

#### Slug

Application slugs will be used to access your app on Vapor Cloud. If you use the slug `foo`, then your application would
be accessible at `https://foo.vapor.cloud`. 

If you create environments besides `production`, like `dev`, then you can access those separate environments using a `-` suffix. For example, `https://foo-dev.vapor.cloud`. 

### Add Hosting

As we mentioned in the previous section, we will be adding the hosting service to our application to host our Vapor app.
Respond `yes` to the prompt to create hosting, and select the Git URL that we just added previously.

### Create Environment

The hosting service can have unlimited environments. This is useful for creating environments like testing, staging, devlopment, and more. 

For now, we will create our main `production` environment. This environment is special because it is not followed by a suffix in the `*.vapor.cloud` domain. 

To create this special environment, ensure the environment name is exactly `production`. 

#### Git Branch

After you have named your environment, choose the branch it will deploy from. This is usually the `master` branch for `production`.

#### Replica Size

You can host your project for free with the `Free` size replicas. This size has a monthly request limit, but is free forever. Select the `Free` size for this environment.

### Add Database (Optional)

Next you will be asked if you'd like to add a database. If your application will need a database, you can do this now.
Otherwise, ignore the prompt. You can always add a database later using `vapor cloud create db`.

If you do add a database, the environment variables to accesso the database will be exposed to your Vapor application's config.

See https://docs.vapor.cloud/database/mysql/ for more information about accessing these variables.

### Replica Count

For high availability and throughput, Vapor Cloud allows you to deploy your application to multiple replicas. However,
for Free size replicas you are limited to `0` or `1` replicas. If you set the replica count to `0` your application will be taken offline. If you set it to `1` it will be online.

Set the replica count to `1` so that our application will be online when we deploy.

### Build Type

The Swift Package Manger 3.1 allows a few different ways to build your application. 

#### Incremental

Vapor Cloud simply runs `swift build` on your application. Dependencies are not updated. This is the fastest method for subsequent deploys.

#### Update

Vapor Cloud runs `swift package update` before running `swift build`. This option is slightly slower than incremental, but required if you have modified your `Package.swift` file.

#### Clean

Vapor Cloud deletes all build metadata (such as the `.build` folder) then runs `swift build` on your application. This option takes a considerably longer amount of time than update or incremental, but can sometimes fix strange build issues.

!!! note
	These build types will be simplified in SPM 4.0 and this question will likely go away.

### Deploy!

Verify that the information is correct and deploy your application! 
Once your app is deployed, you will get a URL to visit in your browser.

![screen shot 2017-07-05 at 6 55 43 pm](https://user-images.githubusercontent.com/1342803/27888360-91a5c88e-61b3-11e7-99c4-b48b21bbd0f4.png)

Congratulations on deploying your first app through Vapor Cloud.

Please let us know if you have any ideas or feature requests through [https://ideas.vapor.cloud](https://ideas.vapor.cloud). 

Also free free to chat with one of us through the chat feature (blue bubble in lower right corner) in [https://dashboard.vapor.cloud](https://dashboard.vapor.cloud).

