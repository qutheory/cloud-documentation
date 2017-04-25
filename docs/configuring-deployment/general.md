# General

## Type

If you create your .vcloud.yml file, you need to set a type. Types right
now are:

- vapor (See more under `Vapor`

- blank (See more under `Blank`)

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
