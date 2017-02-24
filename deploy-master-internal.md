# Deploy master documentation

## Base URL
```
https://deploy-master-internal.vaporcloud.io
```

## Deploy
To deploy a project, use the endpoint:
```
POST /api/deploy
```

### JSON Structure
```
{
    "id": INT (Deploy ID - Not used atm.)
    "repoName": STRING (Git repository name)
    "environmentName": STRING (The environment wanted)
    "replicas": INT (Amount of pods to be started)
    "version": INT (This needs to be unique for each project, if the same version is pushed again, it won't update the code)
    "type": STRING (code-incremental,code-clean,scale,domain)
    "gitUrl": STRING (e.g.: git@git.nodescloud.com:josc/vapor-test4.git)
    "gitBranch": STRING (Not used atm. Always deploys master)
    "databaseUsername": STRING (Database username from environments table)
    "databasePassword": STRING (Database password from environments table)
    "domains": STRING (See domains documentation)
}
```
All fields are required

#### Example
```
{
    "id": 1,
    "project": "vapor-test4",
    "environment": "staging",
    "replicas": 2,
    "version": 1,
    "type": "image",
    "gitUrl": "git@git.newodescloud.com:josc/vapor-test4.git",
    "gitBranch": "master",
    "domains": ""
}
```

#### Domains
The domains need to be a string, and needs a domain and a path.
If i want my project to have the following domain:
```
http://myproject.dk
```

The domains need to be:
```
"domains": "myproject.dk,/"
```

With another path e.g.:

```
http://myproject.dk/foo
```

```
"domains": "myproject.dk,/foo"
```

For multiple domains seperate with ;;
e.g.:
```
http://myproject.dk
http://myotherproject.dk/foo
```

```
"domains": "myproject.dk,/;;myotherproject.dk,/foo"
```
