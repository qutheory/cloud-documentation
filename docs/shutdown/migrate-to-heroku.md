## Setup Heroku account

First make sure you have an Heroku account, if you don't, go to https://signup.heroku.com

## Installing CLI

Next let's install the Heroku CLI

    brew install heroku/brew/heroku

Now we can login in the CLI

    heroku login

Enter your Email and password.

## Create your application

Using the CLI we can create our application like this

Add a Profile and .swift-version, make sure you are in your project folder

    echo "web: Run --env production --hostname 0.0.0.0 --port $PORT" > Procfile
    echo "5.1.3" > .swift-version

Now let's add the files to git

    git add .
    git commit -am "Setup Heroku deployment"

Now we can create our app and deploy it

    heroku apps:create your-application-name --buildpack vapor/vapor
    git push heroku master
    
    heroku ps:scale web=1

heroku apps:create can take a --**region eu** if you want your app in EU rather than the US.

## Create a Postgres database

Create a postgres database on Heroku

    heroku addons:create heroku-postgresql:<PLAN_NAME>

To create a free plan database, use

    heroku addons:create heroku-postgresql:hobby-dev

## Migrate data from Cloud 1 to Heroku

Start by finding the credentials, these are exposed in the dashboard, navigate to your project, hosting, application and environment. In the bottom, click Database, and you can see the Hostname, username and password. Database is the same as the username.

### Dump your database

Let's start by exporting data to a file.

    pg_dump --dbname=postgresql://<USERNAME>:<PASSWORD>@<HOSTNAME>:5432/<USERNAME> > /tmp/my-db.sql

### Import the file into Heroku

Find the credentials you can get them by running this command

    heroku pg:credentials:url DATABASE

Now use the credentials in the command below

    psql -h <HOSTNAME> -U <USER> -W -d <DATABASE> -f /tmp/my-db.sql

You should now be able to use your application on Heroku.