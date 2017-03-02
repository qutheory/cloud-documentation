# Application API

Microservice for managing applications, environments, and domains.

## Overview

The Application API is manages all things related to applications and their environments. You can create new applications and environments or update existing ones. Some updates to environments, such as updating the number of replicas, will trigger deployments on the [Deploy API](/api/deploy-api/) automatically.

### Application

An application consists of a repository name and a Git url. This repository name will be used to interact with your application at `<repoName>.vapor.cloud`. 

!!! note
    Applications belong to a project. The authenticated user must have the appropriate project permissions to create, view, and update applications.

### Environment

Each application can have several environments. The environment holds information such as the database credentials and configuration variables that your Vapor project will need when it runs.

The environment's name, e.g. `staging`, is used to interact with your application at `<environmentName>.<repoName>.vapor.cloud`. 

!!! note
    The default environment `production` can be omitted when visiting your application.

Each environment can have an unlimited number of replicas running. To scale your application in any environment, update the replicas count.

## Usage

Instructions and examples for using the various RESTful endpoints.

### Create Application

To create an application, supply the names, Git information, and associated project identifier.

```http
POST api.vapor.cloud/application/applications
```

```json
{
  "project": {
    "id": "E24261DE-532A-4E09-85DD-3F46C59E936B"
  },
  "repoName": "pig-latin-translator",
  "name": "Pig Latin Translator",
  "gitUrl": "https://github.com/user/pig-latin-translator.git"
}
```

The API will respond with the created application.

```http
200 OK
```

```json
{
  "id": "6DD860E7-1FCB-44C3-8C2D-7EF183D62982",
  "project": {
    "id": "E24261DE-532A-4E09-85DD-3F46C59E936B"
  },
  "repoName": "pig-latin-translator",
  "name": "Pig Latin Translator",
  "gitUrl": "https://github.com/user/pig-latin-translator.git"
}
```

### Create Environment

To create an environment, supply the name and the default Git branch to use.

!!! note
    Include the Application's repo name in the URL.

```http
POST api.cloud.cloud/application/applications/<repoName>/environments
```

```json
{
  "name": "staging",
  "defaultBranch": "develop"
}
```
