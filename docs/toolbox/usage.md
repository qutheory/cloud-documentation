# Usage

You can always use `vcloud --help` to see the help screen.

For each command, you can also see help by typing `vcloud COMMAND --help`

## Create application

To see help for create application type `vcloud apps:create --help`

### Simple create

1. Go to a folder connected to GIT
2. Type `vcloud apps:create`
3. VCloud will automatically detect your GIT project, and ask if you want to create it.

### Manual install

`vcloud apps:create -r my-app -n "My cool app" -g git@my.git:url/app.git`

### Understand naming

`repoName` when we use the word repoName, this is the name you want in your URL e.g.: my-repo-name.vapor.cloud

`name` a more user friendly name, e.g. My awesome app

`gitUrl` this is the GIT ssh url, e.g. git@github.com:my-user/my-app.git