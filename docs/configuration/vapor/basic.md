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

## Adding cURL HTTP/2 Support

Currently cURL with HTTP/2 is in beta support, so it's optional to add. This will be default at a later point.

To add this, add the following to your .yml file:

```
type: "vapor"
swift_version: "3.1.0"
docker_template: "vapor-3.1.0-http2"
```

## Unit tests

You can choose to run unit tests during deployments. Set it up like
this:

```
unit_test: true
```
