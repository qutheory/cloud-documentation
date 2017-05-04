# Vapor

For Vapor, you can specify:

- Swift version

- Unit tests

When adding a .vcloud.yml file to your vapor project, always add:

```
type: "vapor"
```

## Swift version

To specify a swift version, add it like this:

```
swift_version: 3.0.2
```

`default is: 3.1.0`

Currently supported versions:

- 3.0.2

- 3.1.0

## Unit tests

You can choose to run unit tests during deployments. Set it up like
this:

```
unit_test: true
```
