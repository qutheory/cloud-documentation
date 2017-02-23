# Blank

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
