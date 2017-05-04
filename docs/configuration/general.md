# General

Adding custom configurations to your project like cronjobs is made easy with `cloud.yml`.

!!! tip
	The `cloud.yml` file is optional and not required for deployment.

## Setting up a cloud.yml

Add a file in your project root called: `cloud.yml`. Make sure to commit it to git.

Vapor Cloud will automatically detect the file and apply the settings on the next deploy.

## Type

If you create your `cloud.yml` file, you need to set a type. Types right
now are:

- [vapor](vapor/basic.md)
- [blank](blank.md)

## Force HTTPS

If you want your project to force users on https setup:
```
force_tls: true
```

!!! warning
    this will make a 301 (permanent) redirect from http to https. So make sure your client can follow redirects before using this.

## Cronjobs

To setup cronjobs, add the following to .vcloud.yml:

```
cronjobs:     
   <environment>:         
        <name>:             
             time: "<time>"
             command: "<command>"
```

So if i e.g. want to run `vapor run prepare` every 5 minutes in production, i am going to add:

```
cronjobs:     
   production:         
        prepare:             
             time: "*/5 * * * *"
             command: "prepare"
```
