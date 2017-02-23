# VCloud file

To customize the deployment process, it's possible to setup a
.vcloud.yml in your project.

This file need to be in your project root.

## Vapor

For Vapor, you can specify:
- Swift version
- Unit tests

When adding a .vcloud.yml file to your vapor project, always add:
```
type: "vapor"
```

### Swift version

To specify a swift version, add it like this:

```
swift_version: 3.0.2
```

`default is: 3.0.2`

Currently supported versions:
- 3.0.2

- 3.1.0

### Unit tests

You can choose to run unit tests during deployments. Set it up like
this:

```
unit_test: true
```

## NPM / Blank

If you just want a HTML project, you can use the blank type. This also
supports NPM Build

```
type: "blank"
webroot: "/dist"
```

This will create a simple webserver running

- Apache 2.x

And load a file from `/dist`

### NPM Build

If you want to build your project, you can setup

```
npm_build:
    staging: "build:aot:staging"
    production: "build:aot:prod"
```

This will run:
`npm install`

On staging env: `npm run build:aot:staging`

On production env: `npm run build:aot:prod`
