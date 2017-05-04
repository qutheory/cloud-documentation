# Core principles

## Projects and applications

In Vapor Cloud we talk about `Projects` and `Applications`. This is intended to give you are short overview
what the differences is.

A project is a collection of one or more applications, and don't have a lot more functionality than you are able to group your applications.

For example:

- My cool project (Project)
    - my-cool-backend (Application - Vapor APP)
    - my-cool-ios-app (Application - iOS APP)
    - my-cool-android-app (Application - Android APP)

In the above example, we have our project, and below that 3 apps (Vapor API, iOS app and Android app)

Applications consists of:

- `repoName`: This will be the URL e.g. `repo-name.vapor.cloud`, and will usually be your git repository name
- `User friendly name`: This is just a name, to make it easier to find.
- `gitUrl`: A URL for your git repository in SSH format e.g. `git@github.com:my-name/my-repo.git`

!!! note
    If your GIT repository is private, read more about setup [here](../server-setup/general/using-private-git.md)

## Environments

When you use the `Hosting` service you can setup different environments for your application. This is an easy way to push code to be tested before moved to production.

You can call your environment what you want.

For example:
I have `my-cool-backend` hosted on `my-cool-backend.vapor.cloud`

If i create an environment called `staging` the URL will be:

`my-cool-backend-staging.vapor.cloud`

All environments are mostly separated from each other. They have their own databases, and run inside their own containers.

The only thing shared is S3 bucket, we advice people to separate this by adding folders based on the environment, but it is possible to share uploaded files between environments.

!!! note
    All applications are automatically created with a `Production` environment. This is accessible on the root domain e.g. `my-cool-backend.vapor.cloud`
